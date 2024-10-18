# Yjs CRDT 算法

**Yjs CRDT Algorithm**

=== "中文"

    *无冲突复制数据类型*（CRDT）用于协作编辑，是*操作变换*（OT）的替代方法。两者的简单区分在于，OT 尝试转换索引位置以确保收敛（所有客户端最终拥有相同内容），而 CRDT 则使用通常不涉及索引转换的数学模型，例如链表。OT 目前是文本共享编辑的事实标准。支持无中央真实来源（中央服务器）的共享编辑的 OT 方法在实际操作中需要过多的记录管理，因而不太可行。CRDT 更适合分布式系统，提供了额外的保证，确保文档可以与远程客户端同步，并且不需要中央真实来源。
    
    Yjs 实现了该算法的修改版，详细信息可参考 [这篇论文](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types)。这篇 [文章](https://blog.kevinjahns.de/are-crdts-suitable-for-shared-editing/) 解释了 CRDT 模型的简单优化，并提供了有关 Yjs 性能特征的更多见解。关于具体实现的更多信息，请参见 [INTERNALS.md](./INTERNALS.md) 和 [Yjs 代码库的此指南](https://youtu.be/0l5XgnQ6rB4)。
    
    适合共享文本编辑的 CRDT 存在只能不断增长的缺陷。虽然存在不增长的 CRDT，但它们不具备对共享文本编辑有利的特性（如意图保留）。Yjs 实现了许多对原始算法的改进，减轻了文档仅增长的缺陷。我们无法在确保结构唯一顺序的同时回收已删除的结构（墓碑）。但我们可以 1. 将前面的结构合并为单个结构，以减少元信息的数量，2. 如果内容被删除，则可以从结构中删除内容，3. 如果我们不再关心结构的顺序，则可以回收墓碑（例如，如果父级被删除）。
    
    **示例：**
    
    1. 如果用户按顺序插入元素，则结构将合并为一个单一结构。例如 `text.insert(0, 'a'), text.insert(1, 'b');` 首先表示为两个结构 (`[{id: {client, clock: 0}, content: 'a'}, {id: {client, clock: 1}, content: 'b'}]`)，然后合并为一个结构：`[{id: {client, clock: 0}, content: 'ab'}]`。
    2. 当包含内容的结构（例如 `ItemString`）被删除时，该结构将被替换为不再包含内容的 `ItemDeleted`。
    3. 当类型被删除时，所有子元素都会转换为 `GC` 结构。`GC` 结构仅表示结构的存在及其被删除。`GC` 结构可以与其他 `GC` 结构合并，只要它们的 id 相邻。
    
    特别是在处理结构化内容时（例如在 ProseMirror 上进行共享编辑），这些改进在 [基准测试](https://github.com/dmonad/crdt-benchmarks) 随机文档编辑时表现出良好的结果。在实践中，它们显示出更好的效果，因为用户通常按顺序编辑文本，从而生成可以轻松合并的结构。基准测试表明，即使在用户从右到左编辑文本的最坏情况下，Yjs 对于大型文档也能保持良好的性能。

=== "英文"

    *Conflict-free replicated data types* (CRDT) for collaborative editing are an
    alternative approach to *operational transformation* (OT). A very simple
    differentiation between the two approaches is that OT attempts to transform
    index positions to ensure convergence (all clients end up with the same
    content), while CRDTs use mathematical models that usually do not involve index
    transformations, like linked lists. OT is currently the de-facto standard for
    shared editing on text. OT approaches that support shared editing without a
    central source of truth (a central server) require too much bookkeeping to be
    viable in practice. CRDTs are better suited for distributed systems, provide
    additional guarantees that the document can be synced with remote clients, and
    do not require a central source of truth.
    
    Yjs implements a modified version of the algorithm described in [this
    paper](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types).
    This [article](https://blog.kevinjahns.de/are-crdts-suitable-for-shared-editing/)
    explains a simple optimization on the CRDT model and
    gives more insight about the performance characteristics in Yjs.
    More information about the specific implementation is available in
    [INTERNALS.md](./INTERNALS.md) and in
    [this walkthrough of the Yjs codebase](https://youtu.be/0l5XgnQ6rB4).
    
    CRDTs that are suitable for shared text editing suffer from the fact that they
    only grow in size. There are CRDTs that do not grow in size, but they do not
    have the characteristics that are benificial for shared text editing (like
    intention preservation). Yjs implements many improvements to the original
    algorithm that diminish the trade-off that the document only grows in size. We
    can't garbage collect deleted structs (tombstones) while ensuring a unique
    order of the structs. But we can 1. merge preceeding structs into a single
    struct to reduce the amount of meta information, 2. we can delete content from
    the struct if it is deleted, and 3. we can garbage collect tombstones if we
    don't care about the order of the structs anymore (e.g. if the parent was
    deleted).
    
    **Examples:**
    
    1. If a user inserts elements in sequence, the struct will be merged into a
       single struct. E.g. `text.insert(0, 'a'), text.insert(1, 'b');` is
       first represented as two structs (`[{id: {client, clock: 0}, content: 'a'},
       {id: {client, clock: 1}, content: 'b'}`) and then merged into a single
       struct: `[{id: {client, clock: 0}, content: 'ab'}]`.
    2. When a struct that contains content (e.g. `ItemString`) is deleted, the
       struct will be replaced with an `ItemDeleted` that does not contain content
       anymore.
    3. When a type is deleted, all child elements are transformed to `GC` structs. A
       `GC` struct only denotes the existence of a struct and that it is deleted.
       `GC` structs can always be merged with other `GC` structs if the id's are
       adjacent.
    
    Especially when working on structured content (e.g. shared editing on
    ProseMirror), these improvements yield very good results when
    [benchmarking](https://github.com/dmonad/crdt-benchmarks) random document edits.
    In practice they show even better results, because users usually edit text in
    sequence, resulting in structs that can easily be merged. The benchmarks show
    that even in the worst case scenario that a user edits text from right to left,
    Yjs achieves good performance even for huge documents.

## 状态向量

=== "中文"
    
    Yjs 能够在同步两个客户端时仅交换差异。我们使用 Lamport 时间戳来标识结构，并跟踪客户端创建它们的顺序。每个结构都有一个 `struct.id = { client: number, clock: number}`，唯一标识一个结构。我们定义每个客户端的下一个预期 `clock` 为 *状态向量*。该数据结构类似于 [版本向量](https://en.wikipedia.org/wiki/Version_vector) 数据结构。但我们使用状态向量仅用于描述本地文档的状态，以便计算远程客户端缺失的结构。我们不使用它来跟踪因果关系。

=== "英文"

    Yjs has the ability to exchange only the differences when syncing two clients.
    We use lamport timestamps to identify structs and to track in which order a
    client created them. Each struct has an `struct.id = { client: number, clock:
    number}` that uniquely identifies a struct. We define the next expected `clock`
    by each client as the *state vector*. This data structure is similar to the
    [version vectors](https://en.wikipedia.org/wiki/Version_vector) data structure.
    But we use state vectors only to describe the state of the local document, so we
    can compute the missing struct of the remote client. We do not use it to track
    causality.
