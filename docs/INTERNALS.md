# Yjs 内部

**Yjs Internals**

=== "中文"

    本文大致解释了 Yjs 的内部工作原理。可以查看 Yjs 代码库的完整演示录制： <https://youtu.be/0l5XgnQ6rB4>
    
    Yjs CRDT 算法在 2016 年的 [YATA 论文](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types) 中有详细描述。要了解其工作原理，从论文开始是个不错的选择。Yjs 实现了一些小的改进，论文中没有描述。其中最显著的是，项目具有 `originRight` 和 `origin` 属性，这在多个并发插入发生在同一个字符之后时提高了性能。
    
    Yjs 的核心是一个列表 CRDT。一切都被压缩成一个列表，以便重用 CRDT 解析算法：
    
    - 数组很简单——它们是任意项目的列表。
    - 文本是字符的列表，可选地由格式标记和嵌入物进行标注，以支持富文本。多个字符可以包裹在一个单一的链接列表 `Item` 中（这也被称为 CRDT 的复合表示）。有关更多信息，请参见 [这篇博客文章](https://blog.kevinjahns.de/are-crdts-suitable-for-shared-editing/)。
    - 映射是条目的列表。每个键的最后插入条目会被使用，而所有其他重复条目则标记为已删除。
    
    每个客户端在首次插入时会被分配一个唯一的 *clientID* 属性。这是一个随机的 53 位整数（53 位因为它适合 JavaScript 的安全整数范围 \[JavaScript 使用 IEEE 754 浮点数\]）。

=== "英文"

    This document roughly explains how Yjs works internally. There is a complete
    walkthrough of the Yjs codebase available as a recording:
    https://youtu.be/0l5XgnQ6rB4
    
    The Yjs CRDT algorithm is described in the [YATA
    paper](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types)
    from 2016. For an algorithmic view of how it works, the paper is a reasonable
    place to start. There are a handful of small improvements implemented in Yjs
    which aren't described in the paper. The most notable is that items have an
    `originRight` as well as an `origin` property, which improves performance when
    many concurrent inserts happen after the same character.
    
    At its heart, Yjs is a list CRDT. Everything is squeezed into a list in order to
    reuse the CRDT resolution algorithm:
    
    - Arrays are easy - they're lists of arbitrary items.
    - Text is a list of characters, optionally punctuated by formatting markers and
      embeds for rich text support. Several characters can be wrapped in a single
    linked list `Item` (this is also known as the compound representation of
    CRDTs). More information about this in [this blog
    article](https://blog.kevinjahns.de/are-crdts-suitable-for-shared-editing/).
    - Maps are lists of entries. The last inserted entry for each key is used, and
      all other duplicates for each key are flagged as deleted.
    
    Each client is assigned a unique *clientID* property on first insert. This is a
    random 53-bit integer (53 bits because that fits in the javascript safe integer
    range \[JavaScript uses IEEE 754 floats\]).

## 列表项

**List items**

=== "中文"

    Yjs 列表中的每个项由两个对象组成：
    
    - 一个 `Item` (*src/structs/Item.js*)。用于将该项与其他相邻项关联。
    - 一个在 `AbstractType` 层次结构中的对象（*src/types/AbstractType.js* 的子类，例如 `YText`）。此对象存储 Yjs 文档中的实际内容。
    
    项和类型对象对具有一一映射关系。项的 `content` 字段引用 AbstractType 对象，而 AbstractType 对象的 `_item` 字段引用该项。
    
    插入到 Yjs 文档中的每个项目都会被赋予一个唯一 ID，由 *ID(clientID, clock)* 对（也称为 [Lamport 时间戳](https://en.wikipedia.org/wiki/Lamport_timestamp)）组成。时钟从 0 开始计数，随着客户端插入的第一个字符或项目而增加。这与 automerge 的操作 ID 相似，但请注意，时钟仅在插入时递增。删除操作以非常不同的方式处理（见下文）。
    
    如果一串字符被插入到文档中（例如 `"abc"`），时钟将为每个字符递增（例如这里递增 3 次）。但 Yjs 只会将一个单一的 `Item` 添加到列表中。这对核心 CRDT 算法没有影响，但这种优化显著减少了正常文本编辑过程中创建的 JavaScript 对象数量。此优化仅适用于字符共享同一 clientID、按顺序插入且所有字符要么已被删除，要么均未删除。如果运行被中断（例如运行中的一个字符被删除），该项将被拆分。
    
    当创建一个项时，它会存储对前一个和后一个项的 ID 的引用。这些引用分别存储在项的 `origin` 和 `originRight` 字段中。当对等体在文档的同一位置同时插入时，这些引用会被使用。尽管在实践中这种情况相当罕见，Yjs 需要确保列表项在所有对等体上始终按相同顺序解析。实际逻辑相对简单——只有几十行代码，位于 `Item#integrate()` 方法中。YATA 论文对此算法有更多详细信息。

=== "英文"

    Each item in a Yjs list is made up of two objects:
    
    - An `Item` (*src/structs/Item.js*). This is used to relate the item to other
      adjacent items.
    - An object in the `AbstractType` hierarchy (subclasses of
      *src/types/AbstractType.js* - eg `YText`). This stores the actual content in
    the Yjs document.
    
    The item and type object pair have a 1-1 mapping. The item's `content` field
    references the AbstractType object and the AbstractType object's `_item` field
    references the item.
    
    Everything inserted in a Yjs document is given a unique ID, formed from a
    *ID(clientID, clock)* pair (also known as a [Lamport
    Timestamp](https://en.wikipedia.org/wiki/Lamport_timestamp)). The clock counts
    up from 0 with the first inserted character or item a client makes. This is
    similar to automerge's operation IDs, but note that the clock is only
    incremented by inserts. Deletes are handled in a very different way (see
    below).
    
    If a run of characters is inserted into a document (eg `"abc"`), the clock will
    be incremented for each character (eg 3 times here). But Yjs will only add a
    single `Item` into the list. This has no effect on the core CRDT algorithm, but
    the optimization dramatically decreases the number of javascript objects
    created during normal text editing. This optimization only applies if the
    characters share the same clientID, they're inserted in order, and all
    characters have either been deleted or all characters are not deleted. The item
    will be split if the run is interrupted for any reason (eg a character in the
    middle of the run is deleted).
    
    When an item is created, it stores a reference to the IDs of the preceeding and
    succeeding item. These are stored in the item's `origin` and `originRight`
    fields, respectively. These are used when peers concurrently insert at the same
    location in a document. Though quite rare in practice, Yjs needs to make sure
    the list items always resolve to the same order on all peers. The actual logic
    is relatively simple - its only a couple dozen lines of code and it lives in
    the `Item#integrate()` method. The YATA paper has much more detail on this
    algorithm.

### 项存储

**Item Storage**

=== "中文"

    项本身存储在两个数据结构和一个缓存中：
    
    - 项以*文档顺序*存储在双向链表树中。每个项都有 `left` 和 `right` 属性，链接到文档中的兄弟项。项还有一个 `parent` 属性，引用其在文档树中的父项（根节点为 null）。(如果有的话，您可以通过 `item.content` 访问项的子项)。
    - 所有项在结构存储 (*src/utils/StructStore.js*) 中以*插入顺序*引用。它引用按时间顺序插入的每个客户端的项列表。这用于在树中查找具有给定 ID 的项（使用二分查找）。它还用于在同步期间有效收集对等体缺失的操作（下文将详细说明）。
    
    当发生本地插入时，Yjs 需要将文档中的插入位置（例如位置 1000）映射到一个 ID。仅使用链表，这将需要 O(n) 的线性扫描，速度较慢。但在编辑文档时，大多数插入要么在与上一个插入相同的位置，要么在附近。为了提高性能，Yjs 在文档中存储最近查找的 80 个插入位置的缓存。在查找位置时会咨询和更新该缓存，以改善平均情况的性能。缓存的更新使用一个仍在变化的启发式方法（目前，当新位置显著偏离缓存中的现有标记时进行更新）。在内部，这被称为跳跃列表/快速搜索标记。

=== "英文"

    The items themselves are stored in two data structures and a cache:
    
    - The items are stored in a tree of doubly-linked lists in *document order*.
      Each item has `left` and `right` properties linking to its siblings in the
    document. Items also have a `parent` property to reference their parent in the
    document tree (null at the root). (And you can access an item's children, if
    any, through `item.content`).
    - All items are referenced in *insertion order* inside the struct store
      (*src/utils/StructStore.js*). This references the list of items inserted by
    for each client, in chronological order. This is used to find an item in the
    tree with a given ID (using a binary search). It is also used to efficiently
    gather the operations a peer is missing during sync (more on this below).
    
    When a local insert happens, Yjs needs to map the insert position in the
    document (eg position 1000) to an ID. With just the linked list, this would
    require a slow O(n) linear scan of the list. But when editing a document, most
    inserts are either at the same position as the last insert, or nearby. To
    improve performance, Yjs stores a cache of the 80 most recently looked up
    insert positions in the document. This is consulted and updated when a position
    is looked up to improve performance in the average case. The cache is updated
    using a heuristic that is still changing (currently, it is updated when a new
    position significantly diverges from existing markers in the cache). Internally
    this is referred to as the skip list / fast search marker.

### 删除

**Deletions**

=== "中文"

    在 Yjs 中，删除操作的处理方式与插入操作截然不同。插入被实现为基于顺序操作的 CRDT，而删除则被视为一种更简单的基于状态的 CRDT。
    
    当任何对等体在历史的任何时刻删除一项时，该项在 Yjs 中被标记为已删除。（内部 Yjs 使用 `info` 位字段。）Yjs 不记录关于删除的元数据：
    
    - 不保留关于*何时*删除项的信息，也不记录哪个用户删除了它。
    - 结构存储中不包含删除记录。
    - clientID 的时钟不被递增。
    
    如果在 Yjs 中启用垃圾回收，当对象被删除时，其内容将被丢弃。如果被删除的对象包含子项（例如在对象中删除字段），其内容将被替换为 `GC` 对象 (*src/structs/GC.js*)。这是一种非常轻量级的结构——它仅存储被移除内容的长度。
    
    Yjs 具有一些特殊逻辑来共享文档中哪些内容已被删除：
    
    - 当发生删除时，除了标记该项外，被删除的 ID 会在事务内本地列出。（有关事务的更多信息，请参见下文。）当事务在本地提交后，被删除项的集合会附加到事务的更新消息中。
    - 快照（Yjs 历史中的一个标记时间点）通过一组 (clientID, clock) 对以及所有已删除项 ID 的集合来指定。被删除的集合是 O(n)，但因为删除通常发生在连续操作中，这个数据集在实际中通常很小。（来自 B4 基准文档的真实编辑轨迹包含 182k 次插入和 77k 个已删除字符。快照中的删除集合大小仅为 4.5Kb。）

=== "英文"

    Deletions in Yjs are treated very differently from insertions. Insertions are
    implemented as a sequential operation based CRDT, but deletions are treated as
    a simpler state based CRDT.
    
    When an item has been deleted by any peer, at any point in history, it is
    flagged as deleted on the item. (Internally Yjs uses the `info` bitfield.) Yjs
    does not record metadata about a deletion:
    
    - No data is kept on *when* an item was deleted, or which user deleted it.
    - The struct store does not contain deletion records
    - The clientID's clock is not incremented
    
    If garbage collection is enabled in Yjs, when an object is deleted its content
    is discarded. If a deleted object contains children (eg a field is deleted in
    an object), the content is replaced with a `GC` object (*src/structs/GC.js*).
    This is a very lightweight structure - it only stores the length of the removed
    content.
    
    Yjs has some special logic to share which content in a document has been
    deleted:
    
    - When a delete happens, as well as marking the item, the deleted IDs are
      listed locally within the transaction. (See below for more information about
    transactions.) When a transaction has been committed locally, the set of
    deleted items is appended to a transaction's update message.
    - A snapshot (a marked point in time in the Yjs history) is specified using
      both the set of (clientID, clock) pairs *and* the set of all deleted item
    IDs. The deleted set is O(n), but because deletions usually happen in runs,
    this data set is usually tiny in practice. (The real world editing trace from
    the B4 benchmark document contains 182k inserts and 77k deleted characters. The
    deleted set size in a snapshot is only 4.5Kb).

## 事务

**Transactions**

=== "中文"
    
    在 Yjs 中，所有更新都发生在一个*事务*中。（在 *src/utils/Transaction.js* 中定义。）
    
    该事务收集一组对 Yjs 文档的更新，以原子方式应用于远程对等体。一旦事务在本地提交，它会生成一个压缩的*更新消息*，该消息会广播给已同步的远程对等体，以通知他们本地的变化。更新消息包含：
    
    - 新插入项的集合
    - 在事务中删除的项的集合

=== "英文"

    All updates in Yjs happen within a *transaction*. (Defined in
    *src/utils/Transaction.js*.)
    
    The transaction collects a set of updates to the Yjs document to be applied on
    remote peers atomically. Once a transaction has been committed locally, it
    generates a compressed *update message* which is broadcast to synchronized
    remote peers to notify them of the local change. The update message contains:
    
    - The set of newly inserted items
    - The set of items deleted within the transaction.

## 网络协议

**Network protocol**

=== "中文"

    网络协议实际上并不是 Yjs 的一部分。有几个相关概念可以用来创建自定义网络协议：
    
    * `update`：Yjs 文档可以编码为一个*更新*对象，该对象可以解析以重建文档。此外，文档上的每个更改都会触发增量文档更新，允许客户端相互同步。更新对象是一个 Uint8Array，有效地编码 `Item` 对象和删除集合。
    * `state vector`：状态向量定义了每个用户的已知状态（一个元组集合 `(client, clock)`）。该对象也有效地编码为 Uint8Array。
    
    客户端可以通过发送其状态向量（通常称为*同步步骤 1*）向远程客户端请求缺失的文档更新。远程对等体可以使用各自客户端的 `clocks` 计算缺失的 `Item` 对象，并计算出一个最小的更新消息，以反映所有缺失的更新（同步步骤 2）。
    
    同步过程的实现位于 [y-protocols](https://github.com/yjs/y-protocols) 中。

=== "英文"

    The network protocol is not really a part of Yjs. There are a few relevant
    concepts that can be used to create a custom network protocol:
    
    * `update`: The Yjs document can be encoded to an *update* object that can be
      parsed to reconstruct the document. Also every change on the document fires
    an incremental document update that allows clients to sync with each other.
    The update object is a Uint8Array that efficiently encodes `Item` objects and
    the delete set.
    * `state vector`: A state vector defines the known state of each user (a set of
      tuples `(client, clock)`). This object is also efficiently encoded as a
    Uint8Array.
    
    The client can ask a remote client for missing document updates by sending
    their state vector (often referred to as *sync step 1*). The remote peer can
    compute the missing `Item` objects using the `clocks` of the respective clients
    and compute a minimal update message that reflects all missing updates (sync
    step 2).
    
    An implementation of the syncing process is in
    [y-protocols](https://github.com/yjs/y-protocols).

## 快照

**Snapshots**

=== "中文"
    
    快照可以用来恢复旧的文档状态。它是一个 `state vector` + `delete set`。客户端可以通过遍历序列 CRDT，忽略所有 `id.clock > stateVector[id.client].clock` 的 Items 来恢复旧的文档状态。客户端将使用删除集合来判断一个项目是否被删除，而不是使用 `item.deleted`。
    
    虽然使用快照恢复旧的文档状态是可能的，但并不推荐这样做。相反，旧状态应该通过遍历最新状态并使用状态向量中的附加信息来计算。

=== "英文"

    A snapshot can be used to restore an old document state. It is a `state vector`
    \+ `delete set`. A client can restore an old document state by iterating through
    the sequence CRDT and ignoring all Items that have an `id.clock >
    stateVector[id.client].clock`. Instead of using `item.deleted` the client will
    use the delete set to find out if an item was deleted or not.
    
    It is not recommended to restore an old document state using snapshots,
    although that would certainly be possible. Instead, the old state should be
    computed by iterating through the newest state and using the additional
    information from the state vector.
