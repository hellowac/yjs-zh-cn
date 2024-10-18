# 概述

**Overview**

=== "中文"

    此存储库包含一组可观察更改并可并发操作的共享类型。网络功能和双向绑定实现于单独的模块中。

=== "英文"

    This repository contains a collection of shared types that can be observed for
    changes and manipulated concurrently. Network functionality and two-way-bindings
    are implemented in separate modules.

## 绑定

**Bindings**

=== "中文"

    | 名称                                                                                                                                                                                                                   | 光标  | 绑定                                                                                                    | 演示                                                                  |
    | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
    | [ProseMirror](https://prosemirror.net/) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |   ✔   | [y-prosemirror](https://github.com/yjs/y-prosemirror)                                                   | [演示](https://demos.yjs.dev/prosemirror/prosemirror.html)            |
    | [Quill](https://quilljs.com/)                                                                                                                                                                                          |   ✔   | [y-quill](https://github.com/yjs/y-quill)                                                               | [演示](https://demos.yjs.dev/quill/quill.html)                        |
    | [CodeMirror](https://codemirror.net/)                                                                                                                                                                                  |   ✔   | [y-codemirror](https://github.com/yjs/y-codemirror)                                                     | [演示](https://demos.yjs.dev/codemirror/codemirror.html)              |
    | [Monaco](https://microsoft.github.io/monaco-editor/)                                                                                                                                                                   |   ✔   | [y-monaco](https://github.com/yjs/y-monaco)                                                             | [演示](https://demos.yjs.dev/monaco/monaco.html)                      |
    | [Slate](https://github.com/ianstormtaylor/slate)                                                                                                                                                                       |   ✔   | [slate-yjs](https://github.com/bitphinix/slate-yjs)                                                     | [演示](https://bitphinix.github.io/slate-yjs-example)                 |
    | [BlockSuite](https://github.com/toeverything/blocksuite)                                                                                                                                                               |   ✔   | (native)                                                                                                | [演示](https://blocksuite-toeverything.vercel.app/?init)              |
    | [Lexical](https://lexical.dev/)                                                                                                                                                                                        |   ✔   | (native)                                                                                                | [演示](https://lexical.dev/docs/collaboration/react#see-it-in-action) |
    | [valtio](https://github.com/pmndrs/valtio)                                                                                                                                                                             |       | [valtio-yjs](https://github.com/dai-shi/valtio-yjs)                                                     | [演示](https://codesandbox.io/s/valtio-yjs-demo-ox3iy)                |
    | [immer](https://github.com/immerjs/immer)                                                                                                                                                                              |       | [immer-yjs](https://github.com/sep2/immer-yjs)                                                          | [演示](https://codesandbox.io/s/immer-yjs-demo-6e0znb)                |
    | React                                                                                                                                                                                                                  |       | [react-yjs](https://github.com/nikgraf/react-yjs)                                                       | [演示](https://react-yjs-example.vercel.app/)                         |
    | React / Vue / Svelte / MobX                                                                                                                                                                                            |       | [SyncedStore](https://syncedstore.org)                                                                  | [演示](https://syncedstore.org/docs/react)                            |
    | [mobx-keystone](https://mobx-keystone.js.org/)                                                                                                                                                                         |       | [mobx-keystone-yjs](https://github.com/xaviergonz/mobx-keystone/tree/master/packages/mobx-keystone-yjs) | [演示](https://mobx-keystone.js.org/examples/yjs-binding)             |

=== "英文"

    | Name                                                                                                                                                                                                                   | Cursors | Binding                                                                                                 | Demo                                                                  |
    | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-----: | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
    | [ProseMirror](https://prosemirror.net/) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |    ✔    | [y-prosemirror](https://github.com/yjs/y-prosemirror)                                                   | [demo](https://demos.yjs.dev/prosemirror/prosemirror.html)            |
    | [Quill](https://quilljs.com/)                                                                                                                                                                                          |    ✔    | [y-quill](https://github.com/yjs/y-quill)                                                               | [demo](https://demos.yjs.dev/quill/quill.html)                        |
    | [CodeMirror](https://codemirror.net/)                                                                                                                                                                                  |    ✔    | [y-codemirror](https://github.com/yjs/y-codemirror)                                                     | [demo](https://demos.yjs.dev/codemirror/codemirror.html)              |
    | [Monaco](https://microsoft.github.io/monaco-editor/)                                                                                                                                                                   |    ✔    | [y-monaco](https://github.com/yjs/y-monaco)                                                             | [demo](https://demos.yjs.dev/monaco/monaco.html)                      |
    | [Slate](https://github.com/ianstormtaylor/slate)                                                                                                                                                                       |    ✔    | [slate-yjs](https://github.com/bitphinix/slate-yjs)                                                     | [demo](https://bitphinix.github.io/slate-yjs-example)                 |
    | [BlockSuite](https://github.com/toeverything/blocksuite)                                                                                                                                                               |    ✔    | (native)                                                                                                | [demo](https://blocksuite-toeverything.vercel.app/?init)              |
    | [Lexical](https://lexical.dev/)                                                                                                                                                                                        |    ✔    | (native)                                                                                                | [demo](https://lexical.dev/docs/collaboration/react#see-it-in-action) |
    | [valtio](https://github.com/pmndrs/valtio)                                                                                                                                                                             |         | [valtio-yjs](https://github.com/dai-shi/valtio-yjs)                                                     | [demo](https://codesandbox.io/s/valtio-yjs-demo-ox3iy)                |
    | [immer](https://github.com/immerjs/immer)                                                                                                                                                                              |         | [immer-yjs](https://github.com/sep2/immer-yjs)                                                          | [demo](https://codesandbox.io/s/immer-yjs-demo-6e0znb)                |
    | React                                                                                                                                                                                                                  |         | [react-yjs](https://github.com/nikgraf/react-yjs)                                                       | [demo](https://react-yjs-example.vercel.app/)                         |
    | React / Vue / Svelte / MobX                                                                                                                                                                                            |         | [SyncedStore](https://syncedstore.org)                                                                  | [demo](https://syncedstore.org/docs/react)                            |
    | [mobx-keystone](https://mobx-keystone.js.org/)                                                                                                                                                                         |         | [mobx-keystone-yjs](https://github.com/xaviergonz/mobx-keystone/tree/master/packages/mobx-keystone-yjs) | [demo](https://mobx-keystone.js.org/examples/yjs-binding)             |

## 提供者

**Providers**

=== "中文"

    设置客户端之间的通信、管理意识信息以及为离线使用存储共享数据相当麻烦。**提供者**为您管理所有这些，是您协作应用的完美起点。
    
    > 这个提供者列表并不完整。请提交 PR 将您的提供者添加到此列表中！

=== "英文"

    Setting up the communication between clients, managing awareness information,
    and storing shared data for offline usage is quite a hassle. **Providers**
    manage all that for you and are the perfect starting point for your
    collaborative app.
    
    > This list of providers is incomplete. Please open PRs to add your providers to
    > this list!

## 连接提供者

**Connection Providers**

=== "中文"

    <dl>
      <dt><a href="https://github.com/yjs/y-websocket">y-websocket</a></dt>
      <dd>
    一个包含简单 WebSocket 后端和连接该后端的 WebSocket 客户端的模块。 <a href="https://github.com/yjs/y-redis/"><b>y-redis</b></a>、<b>y-sweet</b>、<b>ypy-websocket</b> 和 <a href="https://tiptap.dev/docs/hocuspocus/introduction"><b>Hocuspocus</b></a>（见下文）是 y-websocket 的替代后端。
      </dd>
      <dt><a href="https://github.com/yjs/y-webrtc">y-webrtc</a></dt>
      <dd>
    通过 WebRTC 在对等方之间传播文档更新。对等方通过信令服务器交换信令数据。公共可用的信令服务器可以使用。通过提供共享密钥，可以加密信令服务器上的通信，从而保持连接信息和共享文档的私密性。
      </dd>
      <dt><a href="https://github.com/liveblocks/liveblocks">@liveblocks/yjs</a></dt>
      <dd>
    <a href="https://liveblocks.io/document/yjs">Liveblocks Yjs</a> 提供完全托管的 WebSocket 基础设施和持久化数据存储，用于 Yjs 文档。无需配置或维护。它还具有 Yjs webhook 事件、用于读取和更新 Yjs 文档的 REST API，以及浏览器 DevTools 扩展。
      </dd>
      <dt><a href="https://github.com/drifting-in-space/y-sweet">y-sweet</a></dt>
      <dd>
    一个独立的 yjs 服务器，具有 S3 或文件系统的持久性。他们还提供<a href="https://y-sweet.cloud">云服务</a>。
      </dd>
      <dt><a href="https://github.com/ueberdosis/hocuspocus">Hocuspocus</a></dt>
      <dd>
    一个独立的可扩展 yjs 服务器，具有 sqlite 持久性、webhooks、身份验证等功能。
      </dd>
      <dt><a href="https://docs.partykit.io/reference/y-partykit-api/">PartyKit</a></dt>
      <dd>
    用于构建多人应用的云服务。
      </dd>
      <dt><a href="https://github.com/marcopolo/y-libp2p">y-libp2p</a></dt>
      <dd>
    使用 <a href="https://libp2p.io/">libp2p</a> 通过 <a href="https://github.com/libp2p/specs/tree/master/pubsub/gossipsub">GossipSub</a> 传播更新。还包括一个对等同步机制，以便追赶错过的更新。
      </dd>
      <dt><a href="https://github.com/yjs/y-dat">y-dat</a></dt>
      <dd>
    [进行中] 使用 <a href="https://github.com/kappa-db/multifeed">multifeed</a> 高效地写入文档更新到 dat 网络。每个客户端都有一个仅附加的 CRDT 本地更新日志（hypercore）。Multifeed 管理和同步 hypercores，而 y-dat 监听更改并将其应用于 Yjs 文档。
      </dd>
      <dt><a href="https://github.com/yousefED/matrix-crdt">Matrix-CRDT</a></dt>
      <dd>
    通过使用 <a href="https://github.com/yousefED/matrix-crdt">MatrixProvider</a>，将 <a href="https://www.matrix.org">Matrix</a> 作为 Yjs 的现成后端。使用 Matrix 作为 Yjs 更新的传输和存储，这样您可以专注于构建客户端应用程序，而 Matrix 可以提供强大的功能，如身份验证、授权、联邦、托管（自托管或 SaaS）甚至端到端加密（E2EE）。
      </dd>
      <dt><a href="https://github.com/y-crdt/yrb-actioncable">yrb-actioncable</a></dt>
      <dd>
    Yjs 客户端的 ActionCable 伴侣。还有一个适合的 <a href="https://github.com/y-crdt/yrb-redis">redis 扩展</a>。
      </dd>
      <dt><a href="https://github.com/y-crdt/ypy-websocket">ypy-websocket</a></dt>
      <dd>
    使用 Python 编写的 WebSocket 后端。
      </dd>
      <dt><a href="https://tinybase.org/">Tinybase</a></dt>
      <dd>
    用于本地优先应用的反应式数据存储。他们支持多个 CRDT 和不同的网络技术。
      </dd>
      <dt><a href="https://codeberg.org/webxdc/y-webxdc">y-webxdc</a></dt>
      <dd>
    用于在 <a href="https://webxdc.org">webxdc 聊天应用</a> 中共享数据的提供者。
      </dd>
      <dt><a href="https://www.secsync.com/">secsync</a></dt>
      <dd>
    一种通过中央服务转发端到端加密 CRDT 的架构。
      </dd>
    </dl>

=== "英文"

    <dl>
      <dt><a href="https://github.com/yjs/y-websocket">y-websocket</a></dt>
      <dd>
    A module that contains a simple websocket backend and a websocket client that
    connects to that backend. <a href="https://github.com/yjs/y-redis/"><b>y-redis</b></a>,
    <b>y-sweet</b>, <b>ypy-websocket</b> and <a href="https://tiptap.dev/docs/hocuspocus/introduction">
    <b>Hocuspocus</b></a> (see below) are alternative
    backends to y-websocket.
      </dd>
      <dt><a href="https://github.com/yjs/y-webrtc">y-webrtc</a></dt>
      <dd>
    Propagates document updates peer-to-peer using WebRTC. The peers exchange
    signaling data over signaling servers. Publically available signaling servers
    are available. Communication over the signaling servers can be encrypted by
    providing a shared secret, keeping the connection information and the shared
    document private.
      </dd>
      <dt><a href="https://github.com/liveblocks/liveblocks">@liveblocks/yjs</a></dt>
      <dd>
    <a href="https://liveblocks.io/document/yjs">Liveblocks Yjs</a> provides a fully
    hosted WebSocket infrastructure and persisted data store for Yjs
    documents. No configuration or maintenance is required. It also features
    Yjs webhook events, REST API to read and update Yjs documents, and a
    browser DevTools extension.
      </dd>
      <dt><a href="https://github.com/drifting-in-space/y-sweet">y-sweet</a></dt>
      <dd>
    A standalone yjs server with persistence to S3 or filesystem. They offer a
    <a href="https://y-sweet.cloud">cloud service</a> as well.
      </dd>
      <dt><a href="https://github.com/ueberdosis/hocuspocus">Hocuspocus</a></dt>
      <dd>
    A standalone extensible yjs server with sqlite persistence, webhooks, auth and more.
      </dd>
      <dt><a href="https://docs.partykit.io/reference/y-partykit-api/">PartyKit</a></dt>
      <dd>
    Cloud service for building multiplayer apps.
      </dd>
      <dt><a href="https://github.com/marcopolo/y-libp2p">y-libp2p</a></dt>
      <dd>
    Uses <a href="https://libp2p.io/">libp2p</a> to propagate updates via
    <a href="https://github.com/libp2p/specs/tree/master/pubsub/gossipsub">GossipSub</a>.
    Also includes a peer-sync mechanism to catch up on missed updates.
      </dd>
      <dt><a href="https://github.com/yjs/y-dat">y-dat</a></dt>
      <dd>
    [WIP] Write document updates efficiently to the dat network using
    <a href="https://github.com/kappa-db/multifeed">multifeed</a>. Each client has
    an append-only log of CRDT local updates (hypercore). Multifeed manages and sync
    hypercores and y-dat listens to changes and applies them to the Yjs document.
    </dd>
      <dt><a href="https://github.com/yousefED/matrix-crdt">Matrix-CRDT</a></dt>
      <dd>
    Use <a href="https://www.matrix.org">Matrix</a> as an off-the-shelf backend for
    Yjs by using the <a href="https://github.com/yousefED/matrix-crdt">MatrixProvider</a>.
    Use Matrix as transport and storage of Yjs updates, so you can focus building
    your client app and Matrix can provide powerful features like Authentication,
    Authorization, Federation, hosting (self-hosting or SaaS) and even End-to-End
    Encryption (E2EE).
      </dd>
      <dt><a href="https://github.com/y-crdt/yrb-actioncable">yrb-actioncable</a></dt>
      <dd>
    An ActionCable companion for Yjs clients. There is a fitting
    <a href="https://github.com/y-crdt/yrb-redis">redis extension</a> as well.
      </dd>
      <dt><a href="https://github.com/y-crdt/ypy-websocket">ypy-websocket</a></dt>
      <dd>
    Websocket backend, written in Python.
      </dd>
      <dt><a href="https://tinybase.org/">Tinybase</a></dt>
      <dd>
    The reactive data store for local-first apps. They support multiple CRDTs and
        different network technologies.
      </dd>
      <dt><a href="https://codeberg.org/webxdc/y-webxdc">y-webxdc</a></dt>
      <dd>
    Provider for sharing data in <a href="https://webxdc.org">webxdc chat apps</a>.
      </dd>
      <dt><a href="https://www.secsync.com/">secsync</a></dt>
      <dd>
    An architecture to relay end-to-end encrypted CRDTs over a central service.
      </dd>
    
    </dl>

### 持久性提供者

**Persistence Providers**

=== "中文"

    <dl>
      <dt><a href="https://github.com/yjs/y-indexeddb">y-indexeddb</a></dt>
      <dd>
    高效地将文档更新持久化到浏览器的 indexeddb 数据库。文档立即可用，只有差异需要通过网络提供者同步。
      </dd>
      <dt><a href="https://github.com/MaxNoetzold/y-mongodb-provider">y-mongodb-provider</a></dt>
      <dd>
    为使用 MongoDB 的服务器添加持久存储。可以与 y-websocket 提供者一起使用。
      </dd>
      <dt><a href="https://github.com/toeverything/AFFiNE/tree/master/packages/y-indexeddb">@toeverything/y-indexeddb</a></dt>
      <dd>
    类似于 y-indexeddb，但支持子文档，并且完全支持 TypeScript。
      </dd>
      <dt><a href="https://github.com/podraven/y-fire">y-fire</a></dt>
      <dd>
    基于 Firestore 的 Yjs 数据库和连接提供者。
      </dd>
      <dt><a href="https://github.com/malte-j/y-op-sqlite">y-op-sqlite</a></dt>
      <dd>
    使用 <a href="https://github.com/OP-Engineering/op-sqlite">op-sqlite</a>，在 React Native 应用中持久化 YJS 更新，这是 React Native 的最快 SQLite 库。
      </dd>
      <dt><a href="https://github.com/MaxNoetzold/y-postgresql">y-postgresql</a></dt>
      <dd>
    为使用 PostgreSQL 的 Web 服务器提供持久存储，且与 y-websocket 兼容。
      </dd>
    </dl>

=== "英文"
    
    <dl>
      <dt><a href="https://github.com/yjs/y-indexeddb">y-indexeddb</a></dt>
      <dd>
    Efficiently persists document updates to the browsers indexeddb database.
    The document is immediately available and only diffs need to be synced through the
    network provider.
      </dd>
      <dt><a href="https://github.com/MaxNoetzold/y-mongodb-provider">y-mongodb-provider</a></dt>
      <dd>
    Adds persistent storage to a server with MongoDB. Can be used with the
    y-websocket provider.
      </dd>
      <dt><a href="https://github.com/toeverything/AFFiNE/tree/master/packages/y-indexeddb">
    @toeverything/y-indexeddb</a></dt>
      <dd>
    Like y-indexeddb, but with sub-documents support and fully TypeScript.
      </dd>
      <dt><a href="https://github.com/podraven/y-fire">y-fire</a></dt>
      <dd>
    A database and connection provider for Yjs based on Firestore.
      </dd>
      <dt><a href="https://github.com/malte-j/y-op-sqlite">y-op-sqlite</a></dt>
      <dd>
      Persist YJS updates in your React Native app using
       <a href="https://github.com/OP-Engineering/op-sqlite">op-sqlite</a>
      , the fastest SQLite library for React Native.  
      </dd>
      <dt><a href="https://github.com/MaxNoetzold/y-postgresql">y-postgresql</a></dt>
      <dd>
      Provides persistent storage for a web server using PostgreSQL and
      is easily compatible with y-websocket.  
      </dd>
    </dl>

## 工具

**Tooling**

=== "中文"

    * [y-sweet 调试器](https://docs.jamsocket.com/y-sweet/advanced/debugger)
    * [liveblocks 开发工具](https://liveblocks.io/devtools)
    * [Yjs 检查器](https://inspector.yjs.dev)

=== "英文"

    * [y-sweet debugger](https://docs.jamsocket.com/y-sweet/advanced/debugger)
    * [liveblocks devtools](https://liveblocks.io/devtools)
    * [Yjs inspector](https://inspector.yjs.dev)

## 端口

**Ports**

=== "中文"

    有多个 Yjs 兼容的其他编程语言的移植版本。
    
    * [y-octo](https://github.com/toeverything/y-octo) - 由 [AFFiNE](https://affine.pro) 提供的 Rust 实现
    * [y-crdt](https://github.com/y-crdt/y-crdt) - Rust 实现，具有多个语言绑定
      * [yrs](https://github.com/y-crdt/y-crdt/tree/main/yrs) - Rust 接口
      * [ypy](https://github.com/y-crdt/ypy) - Python 绑定
      * [yrb](https://github.com/y-crdt/yrb) - Ruby 绑定
      * [yswift](https://github.com/y-crdt/yswift) - Swift 绑定
      * [yffi](https://github.com/y-crdt/y-crdt/tree/main/yffi) - C-FFI
      * [ywasm](https://github.com/y-crdt/y-crdt/tree/main/ywasm) - WASM 绑定
    * [ycs](https://github.com/yjs/ycs) - .Net 兼容的 C# 实现。

=== "英文"

    There are several Yjs-compatible ports to other programming languages.
    
    * [y-octo](https://github.com/toeverything/y-octo) - Rust implementation by
    [AFFiNE](https://affine.pro)
    * [y-crdt](https://github.com/y-crdt/y-crdt) - Rust implementation with multiple
    language bindings to other languages
      * [yrs](https://github.com/y-crdt/y-crdt/tree/main/yrs) - Rust interface
      * [ypy](https://github.com/y-crdt/ypy) - Python binding
      * [yrb](https://github.com/y-crdt/yrb) - Ruby binding
      * [yswift](https://github.com/y-crdt/yswift) - Swift binding
      * [yffi](https://github.com/y-crdt/y-crdt/tree/main/yffi) - C-FFI
      * [ywasm](https://github.com/y-crdt/y-crdt/tree/main/ywasm) - WASM binding
    * [ycs](https://github.com/yjs/ycs) - .Net compatible C# implementation.

