
# ![Yjs](https://yjs.dev/images/logo/yjs-120x120.png)

[English](./README.EN.md)

> 一个具有强大共享数据抽象的 CRDT 框架

Yjs 是一个 [CRDT 实现](#yjs-crdt-algorithm)，它将其内部
数据结构暴露为 *共享类型*。共享类型是常见的数据类型，如 `Map`
或 `Array`，具有超能力：更改会自动分发给其他
对等方，并在没有合并冲突的情况下合并。

Yjs 是 **网络无关的**（p2p！），支持许多现有的 **富文本
编辑器**、**离线编辑**、**版本快照**、**撤销/重做** 和
**共享光标**。它可以支持无限数量的用户，并且非常适合处理大型文档。

* 演示: [https://github.com/yjs/yjs-demos](https://github.com/yjs/yjs-demos)
* 讨论: [https://discuss.yjs.dev](https://discuss.yjs.dev)
* 聊天: [Gitter](https://gitter.im/Yjs/community) | [Discord](https://discord.gg/T3nqMT6qbM)
* 基准测试 Yjs vs. Automerge:
  [https://github.com/dmonad/crdt-benchmarks](https://github.com/dmonad/crdt-benchmarks)
* 播客 [**“Yjs 深入探讨实时协作编辑解决方案”：**](https://www.tag1consulting.com/blog/deep-dive-real-time-collaborative-editing-solutions-tagteamtalk-001-0)
* 播客 [**“在 Gutenberg 中使用 YJS 框架进行 Google Docs 样式编辑”：**](https://publishpress.com/blog/yjs/)

:construction_worker_woman: 如果您正在寻找专业支持，请
考虑通过 [GitHub Sponsors](https://github.com/sponsors/dmonad) 支持该项目，签订“支持合同”。我会更快处理您的问题，
我们可以在定期视频会议中讨论问题和疑问。
否则，您可以在我们的社区 [讨论论坛](https://discuss.yjs.dev) 找到帮助。

## 赞助

请在财务上为项目贡献——特别是如果您的公司依赖
Yjs。[![成为赞助商](https://img.shields.io/static/v1?label=Become%20a%20Sponsor&message=%E2%9D%A4&logo=GitHub&style=flat&color=d42f2d)](https://github.com/sponsors/dmonad)

## 专业支持

* [与维护者的支持合同](https://github.com/sponsors/dmonad) -
通过对开源 Yjs 项目进行财务贡献，您可以直接从作者那里获得
专业支持。这包括每周视频通话的机会，以讨论您的具体挑战。
* [Synergy Codes](https://synergycodes.com/yjs-services/) - 专注于
为视觉应用开发实时协作编辑解决方案，Synergy Codes 专注于
互动图表、复杂图形、图表和各种数据可视化类型。他们的专业知识使开发人员能够构建
引人入胜和互动的视觉体验，利用 Yjs 的强大功能。请查看
他们在 [视觉协作展示](https://yjs-diagram.synergy.codes/) 中的工作。

## 谁在使用 Yjs

* [AFFiNE](https://affine.pro/) 本地优先、隐私优先的开源知识库。 :star2:
* [Huly](https://huly.io/) - 开源的一体化项目管理平台 :star2:
* [Cargo](https://cargo.site/) 设计师和艺术家的网站构建工具 :star2:
* [Gitbook](https://gitbook.com) 技术团队的知识管理 :star2:
* [Evernote](https://evernote.com) 笔记应用 :star2:
* [Lessonspace](https://thelessonspace.com) 企业级虚拟教室和在线培训平台 :star2:
* [Ellipsus](ellipsus.com) - 讲故事等的协作写作应用。支持版本控制、变更归属和“责任归属”。为整个出版过程（包括销售）提供解决方案 :star:
* [Dynaboard](https://dynaboard.com/) 协作构建 Web 应用。 :star:
* [Relm](https://www.relm.us/) 一个协作游戏世界，用于团队合作和社区。 :star:
* [Room.sh](https://room.sh/) 一款会议应用，集成协作绘图、编辑和编码工具。 :star:
* [Nimbus Note](https://nimbusweb.me/note.php) 由 Nimbus Web 设计的笔记应用。 :star:
* [Pluxbox RadioManager](https://getradiomanager.com/) 一款基于 Web 的应用，用于协作组织广播。 :star:
* [modyfi](https://www.modyfi.com) - Modyfi 是为多学科设计师构建的设计平台。设计、生成、动画等——无需在应用之间切换。 :star:
* [Sana](https://sanalabs.com/) 具有 Yjs 支持的协作文本编辑的学习平台。
* [Serenity Notes](https://www.serenity.re/en/notes) 端到端加密的协作笔记应用。
* [PRSM](https://prsm.uk/) 协作思维导图和系统可视化。 *[(来源)](https://github.com/micrology/prsm)*
* [Alldone](https://alldone.app/) 下一代项目管理和协作平台。
* [Living Spec](https://livingspec.com/) 产品团队协作的现代方式。
* [Slidebeamer](https://slidebeamer.com/) 演示应用。
* [BlockSurvey](https://blocksurvey.io) 端到端加密的表单/调查工具。
* [Skiff](https://skiff.org/) 私人去中心化工作空间。
* [JupyterLab](https://jupyter.org/) 协作计算笔记本。
* [JupyterCad](https://jupytercad.readthedocs.io/en/latest/) JupyterLab 的扩展，支持 3D FreeCAD 模型的协作编辑。
* [Hyperquery](https://hyperquery.ai/) 用于共享分析、文档、电子表格和仪表板的协作数据工作空间。
* [Nosgestesclimat](https://nosgestesclimat.fr/groupe) 法国碳足迹计算器具有基于 Yjs 的小组 P2P 模式。
* [oorja.io](https://oorja.io) 可扩展协作应用的在线会议空间，端到端加密。
* [LegendKeeper](https://legendkeeper.com) 协作的活动策划和世界构建应用，适用于桌面 RPG。
* [IllumiDesk](https://illumidesk.com/) 使用 AI 构建课程和内容。
* [btw](https://www.btw.so) 开源 Medium 替代品。
* [AWS SageMaker](https://aws.amazon.com/sagemaker/) 构建机器学习模型的工具。
* [linear](https://linear.app) 精简问题、项目和产品路线图。
* [btw](https://www.btw.so) - 个人网站构建器。
* [AWS SageMaker](https://aws.amazon.com/sagemaker/) - 机器学习服务。
* [Arkiter](https://www.arkiter.com/) - 实时面试软件。
* [Appflowy](https://www.appflowy.io/) - 他们使用 Yrs。
* [Multi.app](https://multi.app) - 多人应用共享：在共享应用中指点、绘制和编辑，就像它们在您的计算机上一样。它们正在使用 Yrs。
* [AppMaster](https://appmaster.io) 无代码平台，用于创建可生产的应用程序并生成源代码。
* [Synthesia](https://www.synthesia.io) - 协作视频编辑器。
* [thinkdeli](https://thinkdeli.com) - 一款由 AI 驱动的快速简单笔记应用。
* [ourboard](https://github.com/raimohanska/ourboard) - 一款协作白板应用。
* [Ellie.ai](https://ellie.ai) - 数据产品设计与协作。
* [GoPeer](https://gopeer.org/) - 协作辅导。
* [screen.garden](https://screen.garden) - PKM 应用的协作后端。
* [NextCloud](https://nextcloud.com/) - 内容协作平台。
* [keystatic](https://github.com/Thinkmill/keystatic) - 基于 git 的 CMS。
* [QDAcity](https://qdacity.com) - 协作定性数据分析平台。
* [Kanbert](https://kanbert.com) - 项目管理软件。
* [Eclipse Theia](https://github.com/eclipse-theia/theia) - 一款在浏览器中运行的云端和桌面 IDE。
* [ScienHub](https://scienhub.com) - 浏览器中的协作 LaTeX 编辑器。

## 目录

* [概述](#overview)
  * [绑定](#bindings)
  * [提供者](#providers)
  * [工具](#tooling)
  * [端口](#ports)
* [快速入门](#getting-started)
* [API](#api)
  * [共享类型](#shared-types)
  * [Y.Doc](#ydoc)
  * [文档更新](#document-updates)
  * [相对位置](#relative-positions)
  * [Y.UndoManager](#yundomanager)
* [Yjs CRDT 算法](#yjs-crdt-algorithm)
* [许可证和作者](#license-and-author)

## 概述

此存储库包含一组可观察更改并可并发操作的共享类型。网络功能和双向绑定实现于单独的模块中。

### 绑定

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

### 提供者(Providers)

设置客户端之间的通信、管理意识信息以及为离线使用存储共享数据相当麻烦。**提供者**为您管理所有这些，是您协作应用的完美起点。

> 这个提供者列表并不完整。请提交 PR 将您的提供者添加到此列表中！

#### 连接提供者

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

#### 持久性提供者

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

### 工具

* [y-sweet 调试器](https://docs.jamsocket.com/y-sweet/advanced/debugger)
* [liveblocks 开发工具](https://liveblocks.io/devtools)
* [Yjs 检查器](https://inspector.yjs.dev)

### 端口

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

## 入门

使用您喜欢的包管理器安装 Yjs 和提供者：

```sh
npm i yjs y-websocket
```

启动 y-websocket 服务器：

```sh
PORT=1234 node ./node_modules/y-websocket/bin/server.cjs
```

### 示例：观察类型

```js
import * as Y from 'yjs';

const doc = new Y.Doc();
const yarray = doc.getArray('my-array')
yarray.observe(event => {
  console.log('yarray 被修改了')
})
// 每当本地或远程客户端修改 yarray 时，观察者都会被调用
yarray.insert(0, ['val']) // => "yarray 被修改了"
```

### 示例：嵌套类型

请记住，共享类型只是普通的数据类型。唯一的限制是共享类型在共享文档中必须只存在一次。

```js
const ymap = doc.getMap('map')
const foodArray = new Y.Array()
foodArray.insert(0, ['apple', 'banana'])
ymap.set('food', foodArray)
ymap.get('food') === foodArray // => true
ymap.set('fruit', foodArray) // => 错误！foodArray 已经被定义
```

现在你了解了如何在共享文档上定义类型。接下来你可以跳转到 [演示仓库](https://github.com/yjs/yjs-demos) 或继续阅读 API 文档。

### 示例：使用和组合提供者

任何 Yjs 提供者都可以相互组合。因此你可以通过不同的网络技术同步数据。

在大多数情况下，你希望将网络提供者（如 y-websocket 或 y-webrtc）与持久化提供者（浏览器中的 y-indexeddb）结合使用。持久化允许你更快地加载文档，并在离线时持久化创建的数据。

为了演示，我们将两个不同的网络提供者与一个持久化提供者结合使用。

```js
import * as Y from 'yjs'
import { WebrtcProvider } from 'y-webrtc'
import { WebsocketProvider } from 'y-websocket'
import { IndexeddbPersistence } from 'y-indexeddb'

const ydoc = new Y.Doc()

// 这允许你立即获取（缓存的）文档数据
const indexeddbProvider = new IndexeddbPersistence('count-demo', ydoc)
indexeddbProvider.whenSynced.then(() => {
  console.log('从索引数据库加载的数据')
})

// 使用 y-webrtc 提供者同步客户端。
const webrtcProvider = new WebrtcProvider('count-demo', ydoc)

// 使用 y-websocket 提供者同步客户端
const websocketProvider = new WebsocketProvider(
  'wss://demos.yjs.dev', 'count-demo', ydoc
)

// 生成和计算总和的数字数组
const yarray = ydoc.getArray('count')

// 观察总和的变化
yarray.observe(event => {
  // 当数据变化时打印更新
  console.log('新总和: ' + yarray.toArray().reduce((a,b) => a + b))
})

// 将 1 加到总和中
yarray.push([1]) // => "新总和: 1"
```

## API

```js
import * as Y from 'yjs'
```

### 共享类型

<details>
  <summary><b>Y.Array</b></summary>
  <br>
  <p>
一种可共享的类数组类型，支持在任何位置高效地插入/删除元素。内部使用链表的数组，在必要时进行拆分。
  </p>
  <pre>const yarray = new Y.Array()</pre>
  <dl>
    <b><code>
Y.Array.from(Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;):
Y.Array
    </code></b>
    <dd>基于现有内容创建 Y.Array 的替代工厂函数。</dd>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;)</code></b>
    <dd>
在 <var>index</var> 插入内容。注意，内容是元素的数组。
即 <code>array.insert(0, [1])</code> 会在位置 0 插入 1。
    </dd>
    <b><code>push(Array&lt;Object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;)</code></b>
    <dd></dd>
    <b><code>unshift(Array&lt;Object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;)</code></b>
    <dd></dd>
    <b><code>delete(index:number, length:number)</code></b>
    <dd></dd>
    <b><code>get(index:number)</code></b>
    <dd></dd>
    <b><code>slice(start:number, end:number):Array&lt;Object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;</code></b>
    <dd>检索内容的范围</dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b>
      <code>
forEach(function(value:object|boolean|Array|string|number|null|Uint8Array|Y.Type,
 index:number, array: Y.Array))
      </code>
    </b>
    <dd></dd>
    <b><code>map(function(T, number, YArray):M):Array&lt;M&gt;</code></b>
    <dd></dd>
    <b><code>clone(): Y.Array</code></b>
    <dd>
将所有值克隆到一个新的 Y.Array 实例中。返回的类型可以包含到 Yjs 文档中。
    </dd>
    <b><code>toArray():Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;</code></b>
    <dd>将此 YArray 的内容复制到一个新数组中。</dd>
    <b><code>toJSON():Array&lt;Object|boolean|Array|string|number|null&gt;</code></b>
    <dd>
将此 YArray 的内容复制到一个新数组中。它使用其 <code>toJSON</code> 方法将所有子类型转换为 JSON。
    </dd>
    <b><code>[Symbol.Iterator]</code></b>
    <dd>
      返回一个 YArray 迭代器，包含数组中每个索引的值。
      <pre>for (let value of yarray) { .. }</pre>
    </dd>
    <b><code>observe(function(YArrayEvent, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。
    </dd>
    <b><code>unobserve(function(YArrayEvent, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observe</code> 事件监听器。
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型或其任何子项时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。事件监听器接收由自身或任何子项创建的所有事件。
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observeDeep</code> 事件监听器。
    </dd>
  </dl>
</details>
<details>
  <summary><b>Y.Map</b></summary>
  <br>
  <p>
    一种可共享的 Map 类型。
  </p>
  <pre><code>const ymap = new Y.Map()</code></pre>
  <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>size: number</code></b>
    <dd>键/值对的总数。</dd>
    <b><code>get(key:string):object|boolean|string|number|null|Uint8Array|Y.Type</code></b>
    <dd></dd>
    <b><code>set(key:string, value:object|boolean|string|number|null|Uint8Array|Y.Type)</code></b>
    <dd></dd>
    <b><code>delete(key:string)</code></b>
    <dd></dd>
    <b><code>has(key:string):boolean</code></b>
    <dd></dd>
    <b><code>clear()</code></b>
    <dd>从此 YMap 中移除所有元素。</dd>
    <b><code>clone():Y.Map</code></b>
    <dd>将此类型克隆为一个新的 Yjs 类型。</dd>
    <b><code>toJSON():Object&lt;string, Object|boolean|Array|string|number|null|Uint8Array&gt;</code></b>
    <dd>
将此 YMap 的 <code>[key,value]</code> 对复制到一个新对象。它使用其 <code>toJSON</code> 方法将所有子类型转换为 JSON。
    </dd>
    <b><code>forEach(function(value:object|boolean|Array|string|number|null|Uint8Array|Y.Type,
 key:string, map: Y.Map))</code></b>
    <dd>
      对每个键值对执行提供的函数一次。
    </dd>
    <b><code>[Symbol.Iterator]</code></b>
    <dd>
      返回一个 <code>[key, value]</code> 对的迭代器。
      <pre>for (let [key, value] of ymap) { .. }</pre>
    </dd>
    <b><code>entries()</code></b>
    <dd>
      返回一个 <code>[key, value]</code> 对的迭代器。
    </dd>
    <b><code>values()</code></b>
    <dd>
      返回所有值的迭代器。
    </dd>
    <b><code>keys()</code></b>
    <dd>
      返回所有键的迭代器。
    </dd>
    <b><code>observe(function(YMapEvent, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。
    </dd>
    <b><code>unobserve(function(YMapEvent, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observe</code> 事件监听器。
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型或其任何子项时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。事件监听器接收由自身或任何子项创建的所有事件。
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observeDeep</code> 事件监听器。
    </dd>
  </dl>
</details>

<details>
  <summary><b>Y.Text</b></summary>
  <br>
  <p>
一种可共享的类型，专为文本的共享编辑而优化。它允许为文本中的范围分配属性。这使得实现丰富文本绑定成为可能。
  </p>
  <p>
该类型还可以转换为
<a href="https://quilljs.com/docs/delta">delta 格式</a>。类似地，YTextEvents 计算变化为增量。
  </p>
  <pre>const ytext = new Y.Text()</pre>
  <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:string, [formattingAttributes:Object&lt;string,string&gt;])</code></b>
    <dd>
      在 <var>index</var> 插入字符串并为其分配格式属性。
      <pre>ytext.insert(0, 'bold text', { bold: true })</pre>
    </dd>
    <b><code>delete(index:number, length:number)</code></b>
    <dd></dd>
    <b><code>format(index:number, length:number, formattingAttributes:Object&lt;string,string&gt;)</code></b>
    <dd>为文本中的范围分配格式属性</dd>
    <b><code>applyDelta(delta: Delta, opts:Object&lt;string,any&gt;)</code></b>
    <dd>
        参见 <a href="https://quilljs.com/docs/delta/">Quill Delta</a>
        可以设置选项以防止移除结尾的新行，默认值为 true。
        <pre>ytext.applyDelta(delta, { sanitize: false })</pre>
    </dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b><code>toString():string</code></b>
    <dd>将此类型（不带格式选项）转换为字符串。</dd>
    <b><code>toJSON():string</code></b>
    <dd>参见 <code>toString</code></dd>
    <b><code>toDelta():Delta</code></b>
    <dd>
将此类型转换为 <a href="https://quilljs.com/docs/delta/">Quill Delta</a>
    </dd>
    <b><code>observe(function(YTextEvent, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。
    </dd>
    <b><code>unobserve(function(YTextEvent, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observe</code> 事件监听器。
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型或其任何子项时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。事件监听器接收由自身或任何子项创建的所有事件。
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observeDeep</code> 事件监听器。
    </dd>
  </dl>
</details>

<details>
  <summary><b>Y.XmlFragment</b></summary>
  <br>
  <p>
    一个包含 Y.XmlElements 数组的容器。
  </p>
  <pre><code>const yxml = new Y.XmlFragment()</code></pre>
  <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>firstChild:Y.XmlElement|Y.XmlText|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:Array&lt;Y.XmlElement|Y.XmlText&gt;)</code></b>
    <dd></dd>
    <b><code>delete(index:number, length:number)</code></b>
    <dd></dd>
    <b><code>get(index:number)</code></b>
    <dd></dd>
    <b><code>slice(start:number, end:number):Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>检索内容范围</dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b><code>clone():Y.XmlFragment</code></b>
    <dd>将此类型克隆为一个新的 Yjs 类型。</dd>
    <b><code>toArray():Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>将子项复制到一个新的数组中。</dd>
    <b><code>toDOM():DocumentFragment</code></b>
    <dd>将此类型及所有子项转换为新的 DOM 元素。</dd>
    <b><code>toString():string</code></b>
    <dd>获取所有后代的 XML 序列化。</dd>
    <b><code>toJSON():string</code></b>
    <dd>参见 <code>toString</code>。</dd>
    <b><code>createTreeWalker(filter: function(AbstractType&lt;any&gt;):boolean):Iterable</code></b>
    <dd>创建一个可迭代对象，以遍历子项。</dd>
    <b><code>observe(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。
    </dd>
    <b><code>unobserve(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observe</code> 事件监听器。
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型或其任何子项时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。事件监听器接收由自身或任何子项创建的所有事件。
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observeDeep</code> 事件监听器。
    </dd>
  </dl>
</details>

<details>
  <summary><b>Y.XmlElement</b></summary>
  <br>
  <p>
一个可共享的类型，表示一个 XML 元素。它具有 <code>nodeName</code>、属性和子项列表，但并不努力验证其内容或确保符合 XML 标准。
  </p>
  <pre><code>const yxml = new Y.XmlElement()</code></pre>
  <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>firstChild:Y.XmlElement|Y.XmlText|null</code></b>
    <dd></dd>
    <b><code>nextSibling:Y.XmlElement|Y.XmlText|null</code></b>
    <dd></dd>
    <b><code>prevSibling:Y.XmlElement|Y.XmlText|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:Array&lt;Y.XmlElement|Y.XmlText&gt;)</code></b>
    <dd></dd>
    <b><code>delete(index:number, length:number)</code></b>
    <dd></dd>
    <b><code>get(index:number)</code></b>
    <dd></dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b><code>setAttribute(attributeName:string, attributeValue:string)</code></b>
    <dd></dd>
    <b><code>removeAttribute(attributeName:string)</code></b>
    <dd></dd>
    <b><code>getAttribute(attributeName:string):string</code></b>
    <dd></dd>
    <b><code>getAttributes():Object&lt;string,string&gt;</code></b>
    <dd></dd>
    <b><code>get(i:number):Y.XmlElement|Y.XmlText</code></b>
    <dd>检索第 i 个元素。</dd>
    <b><code>slice(start:number, end:number):Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>检索内容范围</dd>
    <b><code>clone():Y.XmlElement</code></b>
    <dd>将此类型克隆为一个新的 Yjs 类型。</dd>
    <b><code>toArray():Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>将子项复制到一个新的数组中。</dd>
    <b><code>toDOM():Element</code></b>
    <dd>将此类型及所有子项转换为一个新的 DOM 元素。</dd>
    <b><code>toString():string</code></b>
    <dd>获取所有后代的 XML 序列化。</dd>
    <b><code>toJSON():string</code></b>
    <dd>参见 <code>toString</code>。</dd>
    <b><code>observe(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。
    </dd>
    <b><code>unobserve(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observe</code> 事件监听器。
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
为此类型添加一个事件监听器，每次修改此类型或其任何子项时都会同步调用。若在事件监听器中修改了此类型，当前事件监听器返回后会再次调用该事件监听器。事件监听器接收由自身或任何子项创建的所有事件。
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
      从此类型移除 <code>observeDeep</code> 事件监听器。
    </dd>
  </dl>
</details>

### Y.Doc

```js
const doc = new Y.Doc()
```

<dl>
  <b><code>clientID</code></b>
  <dd>一个唯一的 ID，用于标识此客户端。（只读）</dd>
  <b><code>gc</code></b>
  <dd>
是否在此文档实例上启用垃圾回收。设置 `doc.gc = false` 以禁用垃圾回收并能够恢复旧内容。有关 Yjs 中垃圾回收的更多信息，请参见 https://github.com/yjs/yjs#yjs-crdt-algorithm。
  </dd>
  <b><code>transact(function(Transaction):void [, origin:any])</code></b>
  <dd>
每次对共享文档的更改都发生在一个事务中。观察者调用和 <code>update</code> 事件在每个事务后被调用。您应该将更改<i>打包</i>到一个单独的事务中，以减少事件调用的数量。即 <code>doc.transact(() => { yarray.insert(..); ymap.set(..) })</code> 触发一个单一的更改事件。<br>您可以指定一个可选的 <code>origin</code> 参数，该参数存储在 <code>transaction.origin</code> 和 <code>on('update', (update, origin) => ..)</code> 中。
  </dd>
  <b><code>toJSON():any</code></b>
  <dd>
已弃用：建议直接在共享类型上调用 toJSON。将整个文档转换为 js 对象，递归遍历每个 yjs 类型。不会记录未定义的类型（使用 <code>ydoc.getType(..)</code>）。
  </dd>
  <b><code>get(string, Y.[TypeClass]):[Type]</code></b>
  <dd>定义一个共享类型。</dd>
  <b><code>getArray(string):Y.Array</code></b>
  <dd>定义一个共享的 Y.Array 类型。相当于 <code>y.get(string, Y.Array)</code>。</dd>
  <b><code>getMap(string):Y.Map</code></b>
  <dd>定义一个共享的 Y.Map 类型。相当于 <code>y.get(string, Y.Map)</code>。</dd>
  <b><code>getText(string):Y.Text</code></b>
  <dd>定义一个共享的 Y.Text 类型。相当于 <code>y.get(string, Y.Text)</code>。</dd>
  <b><code>getXmlElement(string, string):Y.XmlElement</code></b>
  <dd>定义一个共享的 Y.XmlElement 类型。相当于 <code>y.get(string, Y.XmlElement)</code>。</dd>
  <b><code>getXmlFragment(string):Y.XmlFragment</code></b>
  <dd>定义一个共享的 Y.XmlFragment 类型。相当于 <code>y.get(string, Y.XmlFragment)</code>。</dd>
  <b><code>on(string, function)</code></b>
  <dd>在共享类型上注册一个事件监听器</dd>
  <b><code>off(string, function)</code></b>
  <dd>从共享类型中注销一个事件监听器</dd>
</dl>

#### Y.Doc 事件

<dl>
  <b><code>on('update', function(updateMessage:Uint8Array, origin:any, Y.Doc):void)</code></b>
  <dd>
监听文档更新。文档更新必须传递给所有其他对等方。您可以以任何顺序和多次应用文档更新。使用 `updateV2` 接收 V2 事件。
  </dd>
  <b><code>on('beforeTransaction', function(Y.Transaction, Y.Doc):void)</code></b>
  <dd>在每个事务之前发出。</dd>
  <b><code>on('afterTransaction', function(Y.Transaction, Y.Doc):void)</code></b>
  <dd>在每个事务之后发出。</dd>
  <b><code>on('beforeAllTransactions', function(Y.Doc):void)</code></b>
  <dd>
事务可以嵌套（例如，当一个事务中的事件调用另一个事务时）。在第一个事务之前发出。
  </dd>
  <b><code>on('afterAllTransactions', function(Y.Doc, Array&lt;Y.Transaction&gt;):void)</code></b>
  <dd>在最后一个事务清理后发出。</dd>
</dl>

### 文档更新

对共享文档的更改被编码为 *文档更新*。文档更新是 *交换律* 和 *幂等* 的。这意味着它们可以以任何顺序和多次应用。

#### 示例：监听更新事件并在远程客户端上应用

```js
const doc1 = new Y.Doc()
const doc2 = new Y.Doc()

doc1.on('update', update => {
  Y.applyUpdate(doc2, update)
})

doc2.on('update', update => {
  Y.applyUpdate(doc1, update)
})

// 所有更改也应用于另一个文档
doc1.getArray('myarray').insert(0, ['Hello doc2, you got this?'])
doc2.getArray('myarray').get(0) // => 'Hello doc2, you got this?'
```

Yjs 内部维护一个 [状态向量](#state-vector)，表示每个客户端期望的下一个时钟。在不同的解释中，它保存由每个客户端创建的结构数量。当两个客户端同步时，您可以选择交换完整的文档结构或仅发送状态向量以计算差异。

#### 示例：通过交换完整文档结构同步两个客户端

```js
const state1 = Y.encodeStateAsUpdate(ydoc1)
const state2 = Y.encodeStateAsUpdate(ydoc2)
Y.applyUpdate(ydoc1, state2)
Y.applyUpdate(ydoc2, state1)
```

#### 示例：通过计算差异同步两个客户端

此示例演示如何通过仅使用远程客户端的状态向量计算差异，以最小的数据交换量同步两个客户端。使用状态向量同步客户端需要额外的往返，但可以节省大量带宽。

```js
const stateVector1 = Y.encodeStateVector(ydoc1)
const stateVector2 = Y.encodeStateVector(ydoc2)
const diff1 = Y.encodeStateAsUpdate(ydoc1, stateVector2)
const diff2 = Y.encodeStateAsUpdate(ydoc2, stateVector1)
Y.applyUpdate(ydoc1, diff2)
Y.applyUpdate(ydoc2, diff1)
```

#### 示例：在不加载 Y.Doc 的情况下同步客户端

可以在不将 Yjs 文档加载到内存中的情况下同步客户端并计算增量更新。Yjs 提供一个 API 以直接在二进制文档更新上计算差异。

```js
// 将当前状态编码为二进制缓冲区
let currentState1 = Y.encodeStateAsUpdate(ydoc1)
let currentState2 = Y.encodeStateAsUpdate(ydoc2)
// 现在我们可以继续使用状态向量同步客户端，而不使用 Y.Doc
ydoc1.destroy()
ydoc2.destroy()

const stateVector1 = Y.encodeStateVectorFromUpdate(currentState1)
const stateVector2 = Y.encodeStateVectorFromUpdate(currentState2)
const diff1 = Y.diffUpdate(currentState1, stateVector2)
const diff2 = Y.diffUpdate(currentState2, stateVector1)

// 同步客户端
currentState1 = Y.mergeUpdates([currentState1, diff2])
currentState2 = Y.mergeUpdates([currentState2, diff1])
```

#### 混淆更新

如果您的用户遇到奇怪的错误（例如，富文本编辑器抛出错误消息），您不必请求用户的完整文档。相反，他们可以在发送给您之前混淆文档（即，用无意义的生成内容替换内容）。请注意，某人可能仍会通过查看文档的一般结构来推断内容的类型。但这比请求原始文档要好得多。

混淆更新包含合并所需的所有与 CRDT 相关的数据。因此，合并混淆更新是安全的。

```javascript
const ydoc = new Y.Doc()
// 进行一些更改..
ydoc.getText().insert(0, 'hello world')
const update = Y.encodeStateAsUpdate(ydoc)
// 以下更新包含混乱的数据
const obfuscatedUpdate = Y.obfuscateUpdate(update)
const ydoc2 = new Y.Doc()
Y.applyUpdate(ydoc2, obfuscatedUpdate)
ydoc2.getText().toString() // => "00000000000"
```

#### 使用 V2 更新格式

Yjs 实现了两种更新格式。默认情况下，您使用的是 V1 更新格式。您可以选择使用 V2 更新格式，该格式提供了更好的压缩效果。并非所有提供者都使用它。不过，如果您正在构建自己的提供者，您已经可以使用它。所有以下函数都有后缀 "V2"。例如 `Y.applyUpdate` ⇒ `Y.applyUpdateV2`。此外，在监听更新时，您需要特别监听 V2 事件，例如 `yDoc.on('updateV2', …)`。我们还支持两种格式之间的转换函数：`Y.convertUpdateFormatV1ToV2` 和 `Y.convertUpdateFormatV2ToV1`。

#### 更新 API

<dl>
  <b><code>Y.applyUpdate(Y.Doc, update:Uint8Array, [transactionOrigin:any])</code></b>
  <dd>
在共享文档上应用文档更新。您可以选择指定 <code>transactionOrigin</code>，该值将存储在 <code>transaction.origin</code> 和 <code>ydoc.on('update', (update, origin) => ..)</code> 中。
  </dd>
  <b><code>Y.encodeStateAsUpdate(Y.Doc, [encodedTargetStateVector:Uint8Array]):Uint8Array</code></b>
  <dd>
将文档状态编码为可以应用于远程文档的单个更新消息。可以选择指定目标状态向量，仅将差异写入更新消息。
  </dd>
  <b><code>Y.encodeStateVector(Y.Doc):Uint8Array</code></b>
  <dd>计算状态向量并将其编码为 Uint8Array。</dd>
  <b><code>Y.mergeUpdates(Array&lt;Uint8Array&gt;)</code></b>
  <dd>
将多个文档更新合并为单个文档更新，同时删除重复信息。合并后的文档更新始终比单独的更新更小，因为采用了压缩编码。
  </dd>
  <b><code>Y.encodeStateVectorFromUpdate(Uint8Array): Uint8Array</code></b>
  <dd>
从文档更新计算状态向量并将其编码为 Uint8Array。
  </dd>
  <b><code>Y.diffUpdate(update: Uint8Array, stateVector: Uint8Array): Uint8Array</code></b>
  <dd>
将缺失的差异编码为另一个更新消息。此函数类似于 <code>Y.encodeStateAsUpdate(ydoc, stateVector)</code>，但适用于更新。
  </dd>
  <b><code>convertUpdateFormatV1ToV2</code></b>
  <dd>
将 V1 更新格式转换为 V2 更新格式。
  </dd>
  <b><code>convertUpdateFormatV2ToV1</code></b>
  <dd>
将 V2 更新格式转换为 V1 更新格式。
  </dd>
</dl>

### 相对位置

在处理协作文档时，我们经常需要处理位置。位置可以表示光标位置、选择范围，甚至将评论分配给一段文本。正常的索引位置（以整数表示）不方便使用，因为一旦远程更改操作文档，索引范围就会失效。相对位置为您提供了一个强大的 API 来表达位置。

相对位置固定于共享文档中的一个元素，并且不受远程更改的影响。即给定文档 `"a|c"`，相对位置附加到 `c`。当远程用户通过在光标之前插入一个字符来修改文档时，光标将保持附加在字符 `c` 上。`insert(1, 'x')("a|c") = "ax|c"`。当相对位置设置在文档末尾时，它将保持附加在文档的末尾。

#### 示例：转换为相对位置并返回

```js
const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
const pos = Y.createAbsolutePositionFromRelativePosition(relPos, doc)
pos.type === ytext // => true
pos.index === 2 // => true
```

#### 示例：将相对位置发送给远程客户端（json）

```js
const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
const encodedRelPos = JSON.stringify(relPos)
// 将 encodedRelPos 发送给远程客户端..
const parsedRelPos = JSON.parse(encodedRelPos)
const pos = Y.createAbsolutePositionFromRelativePosition(parsedRelPos, remoteDoc)
pos.type === remoteytext // => true
pos.index === 2 // => true
```

#### 示例：将相对位置发送给远程客户端（Uint8Array）

```js
const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
const encodedRelPos = Y.encodeRelativePosition(relPos)
// 将 encodedRelPos 发送给远程客户端..
const parsedRelPos = Y.decodeRelativePosition(encodedRelPos)
const pos = Y.createAbsolutePositionFromRelativePosition(parsedRelPos, remoteDoc)
pos.type === remoteytext // => true
pos.index === 2 // => true
```

<dl>
  <b><code>
Y.createRelativePositionFromTypeIndex(type:Uint8Array|Y.Type, index: number
[, assoc=0])
  </code></b>
  <dd>
创建一个相对位置，固定于任何序列类型共享的第 i 个元素（如果 <code>assoc >= 0</code>）。默认情况下，该位置与指定索引位置之后的字符关联。如果 <code>assoc < 0</code>，则相对位置与指定索引位置之前的字符关联。
  </dd>
  <b><code>
Y.createAbsolutePositionFromRelativePosition(RelativePosition, Y.Doc):
{ type: Y.AbstractType, index: number, assoc: number } | null
  </code></b>
  <dd>
从相对位置创建绝对位置。如果相对位置无法引用，或者类型已被删除，则结果为 null。
  </dd>
  <b><code>
Y.encodeRelativePosition(RelativePosition):Uint8Array
  </code></b>
  <dd>
将相对位置编码为 Uint8Array。二进制数据是文档更新的首选编码格式。如果您更喜欢 JSON 编码，可以简单地使用 JSON.stringify / JSON.parse 相对位置。
  </dd>
  <b><code>Y.decodeRelativePosition(Uint8Array):RelativePosition</code></b>
  <dd>将二进制编码的相对位置解码为 RelativePosition 对象。</dd>
</dl>

### Y.UndoManager

Yjs 附带一个用于选择性撤销/重做 Yjs 类型更改的撤销/重做管理器。这些更改可以选择性地限制在事务来源上。

```js
const ytext = doc.getText('text')
const undoManager = new Y.UndoManager(ytext)

ytext.insert(0, 'abc')
undoManager.undo()
ytext.toString() // => ''
undoManager.redo()
ytext.toString() // => 'abc'
```

<dl>
  <b><code>constructor(scope:Y.AbstractType|Array&lt;Y.AbstractType&gt;
  [, {captureTimeout:number,trackedOrigins:Set&lt;any&gt;,deleteFilter:function(item):boolean}])</code></b>
  <dd>接受单个类型作为范围或类型数组。</dd>
  <b><code>undo()</code></b>
  <dd></dd>
  <b><code>redo()</code></b>
  <dd></dd>
  <b><code>stopCapturing()</code></b>
  <dd></dd>
  <b>
    <code>
on('stack-item-added', { stackItem: { meta: Map&lt;any,any&gt; }, type: 'undo'
| 'redo' })
    </code>
  </b>
  <dd>
注册一个事件，当一个 <code>StackItem</code> 被添加到撤销或重做栈时被调用。
  </dd>
  <b>
    <code>
on('stack-item-updated', { stackItem: { meta: Map&lt;any,any&gt; }, type: 'undo'
| 'redo' })
    </code>
  </b>
  <dd>
注册一个事件，当现有的 <code>StackItem</code> 被更新时被调用。这在“捕获间隔”内发生两个更改时发生。
  </dd>
  <b>
    <code>
on('stack-item-popped', { stackItem: { meta: Map&lt;any,any&gt; }, type: 'undo'
| 'redo' })
    </code>
  </b>
  <dd>
注册一个事件，当一个 <code>StackItem</code> 从撤销或重做栈中弹出时被调用。
  </dd>
  <b>
    <code>
on('stack-cleared', { undoStackCleared: boolean, redoStackCleared: boolean })
    </code>
  </b>
  <dd>
注册一个事件，当撤销和/或重做栈被清除时被调用。
  </dd>
</dl>

#### 示例：停止捕获

UndoManager 会合并在小于 `options.captureTimeout` 的时间间隔内创建的撤销栈项。调用 `um.stopCapturing()` 以便下一个栈项不会被合并。

```js
// 未停止捕获
ytext.insert(0, 'a')
ytext.insert(1, 'b')
undoManager.undo()
ytext.toString() // => '' (注意 'ab' 被删除)
// 停止捕获
ytext.insert(0, 'a')
undoManager.stopCapturing()
ytext.insert(0, 'b')
undoManager.undo()
ytext.toString() // => 'a' (注意只有 'b' 被删除)
```

#### 示例：指定跟踪来源

共享文档上的每个更改都有一个来源。如果未指定来源，则默认为 `null`。通过指定 `trackedOrigins`，您可以选择性地指定哪些更改应该被 `UndoManager` 跟踪。UndoManager 实例始终会被添加到 `trackedOrigins` 中。

```js
class CustomBinding {}

const ytext = doc.getText('text')
const undoManager = new Y.UndoManager(ytext, {
  trackedOrigins: new Set([42, CustomBinding])
})

ytext.insert(0, 'abc')
undoManager.undo()
ytext.toString() // => 'abc' (未跟踪，因为来源为 `null`，并且不属于
                 //           `trackedTransactionOrigins`)
ytext.delete(0, 3) // 撤销更改

doc.transact(() => {
  ytext.insert(0, 'abc')
}, 42)
undoManager.undo()
ytext.toString() // => '' (被跟踪，因为来源是 `trackedTransactionorigins` 的一个实例)

doc.transact(() => {
  ytext.insert(0, 'abc')
}, 41)
undoManager.undo()
ytext.toString() // => 'abc' (未被跟踪，因为 41 不是 `trackedTransactionorigins` 的一个实例)
ytext.delete(0, 3) // 撤销更改

doc.transact(() => {
  ytext.insert(0, 'abc')
}, new CustomBinding())
undoManager.undo()
ytext.toString() // => '' (被跟踪，因为来源是 `CustomBinding`，并且
                 //        `CustomBinding` 在 `trackedTransactionorigins` 中)
```

#### 示例：向 StackItems 添加额外信息

在撤销或重做之前的操作时，通常期望恢复额外的元信息，如光标位置或文档视图。您可以将元信息分配给撤销/重做栈项。

```js
const ytext = doc.getText('text')
const undoManager = new Y.UndoManager(ytext, {
  trackedOrigins: new Set([42, CustomBinding])
})

undoManager.on('stack-item-added', event => {
  // 将当前光标位置保存到栈项中
  event.stackItem.meta.set('cursor-location', getRelativeCursorLocation())
})

undoManager.on('stack-item-popped', event => {
  // 恢复栈项中的当前光标位置
  restoreCursorLocation(event.stackItem.meta.get('cursor-location'))
})
```

## Yjs CRDT 算法

*无冲突复制数据类型*（CRDT）用于协作编辑，是*操作变换*（OT）的替代方法。两者的简单区分在于，OT 尝试转换索引位置以确保收敛（所有客户端最终拥有相同内容），而 CRDT 则使用通常不涉及索引转换的数学模型，例如链表。OT 目前是文本共享编辑的事实标准。支持无中央真实来源（中央服务器）的共享编辑的 OT 方法在实际操作中需要过多的记录管理，因而不太可行。CRDT 更适合分布式系统，提供了额外的保证，确保文档可以与远程客户端同步，并且不需要中央真实来源。

Yjs 实现了该算法的修改版，详细信息可参考 [这篇论文](https://www.researchgate.net/publication/310212186_Near_Real-Time_Peer-to-Peer_Shared_Editing_on_Extensible_Data_Types)。这篇 [文章](https://blog.kevinjahns.de/are-crdts-suitable-for-shared-editing/) 解释了 CRDT 模型的简单优化，并提供了有关 Yjs 性能特征的更多见解。关于具体实现的更多信息，请参见 [INTERNALS.md](./INTERNALS.md) 和 [Yjs 代码库的此指南](https://youtu.be/0l5XgnQ6rB4)。

适合共享文本编辑的 CRDT 存在只能不断增长的缺陷。虽然存在不增长的 CRDT，但它们不具备对共享文本编辑有利的特性（如意图保留）。Yjs 实现了许多对原始算法的改进，减轻了文档仅增长的缺陷。我们无法在确保结构唯一顺序的同时回收已删除的结构（墓碑）。但我们可以 1. 将前面的结构合并为单个结构，以减少元信息的数量，2. 如果内容被删除，则可以从结构中删除内容，3. 如果我们不再关心结构的顺序，则可以回收墓碑（例如，如果父级被删除）。

**示例：**

1. 如果用户按顺序插入元素，则结构将合并为一个单一结构。例如 `text.insert(0, 'a'), text.insert(1, 'b');` 首先表示为两个结构 (`[{id: {client, clock: 0}, content: 'a'}, {id: {client, clock: 1}, content: 'b'}]`)，然后合并为一个结构：`[{id: {client, clock: 0}, content: 'ab'}]`。
2. 当包含内容的结构（例如 `ItemString`）被删除时，该结构将被替换为不再包含内容的 `ItemDeleted`。
3. 当类型被删除时，所有子元素都会转换为 `GC` 结构。`GC` 结构仅表示结构的存在及其被删除。`GC` 结构可以与其他 `GC` 结构合并，只要它们的 id 相邻。

特别是在处理结构化内容时（例如在 ProseMirror 上进行共享编辑），这些改进在 [基准测试](https://github.com/dmonad/crdt-benchmarks) 随机文档编辑时表现出良好的结果。在实践中，它们显示出更好的效果，因为用户通常按顺序编辑文本，从而生成可以轻松合并的结构。基准测试表明，即使在用户从右到左编辑文本的最坏情况下，Yjs 对于大型文档也能保持良好的性能。

### 状态向量

Yjs 能够在同步两个客户端时仅交换差异。我们使用 Lamport 时间戳来标识结构，并跟踪客户端创建它们的顺序。每个结构都有一个 `struct.id = { client: number, clock: number}`，唯一标识一个结构。我们定义每个客户端的下一个预期 `clock` 为 *状态向量*。该数据结构类似于 [版本向量](https://en.wikipedia.org/wiki/Version_vector) 数据结构。但我们使用状态向量仅用于描述本地文档的状态，以便计算远程客户端缺失的结构。我们不使用它来跟踪因果关系。

## 许可证和作者

Yjs 和所有相关项目均为 [**MIT 许可证**](./LICENSE)。

Yjs 基于我在 [RWTH i5](http://dbis.rwth-aachen.de/) 学生时期的研究。现在我在业余时间从事 Yjs 的开发。

通过在 [GitHub Sponsors](https://github.com/sponsors/dmonad) 上捐赠或雇用 [我](https://github.com/dmonad) 作为您的协作应用程序的承包商来支持该项目。
