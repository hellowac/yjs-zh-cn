# 入门

**Getting Started**

=== "中文"

    使用您喜欢的包管理器安装 Yjs 和提供者：

    ```sh
    npm i yjs y-websocket
    ```
    
    启动 y-websocket 服务器：
    
    ```sh
    PORT=1234 node ./node_modules/y-websocket/bin/server.cjs
    ```

=== "英文"

    Install Yjs and a provider with your favorite package manager:
    
    ```sh
    npm i yjs y-websocket
    ```
    
    Start the y-websocket server:
    
    ```sh
    PORT=1234 node ./node_modules/y-websocket/bin/server.cjs
    ```

## 示例：观察类型

**Example: Observe types**


=== "中文"
    
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

=== "英文"

    ```js
    import * as Y from 'yjs';
    
    const doc = new Y.Doc();
    const yarray = doc.getArray('my-array')
    yarray.observe(event => {
      console.log('yarray was modified')
    })
    // every time a local or remote client modifies yarray, the observer is called
    yarray.insert(0, ['val']) // => "yarray was modified"
    ```

## 示例：嵌套类型

**Example: Nest types**

=== "中文"

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

=== "英文"

    Remember, shared types are just plain old data types. The only limitation is
    that a shared type must exist only once in the shared document.
    
    ```js
    const ymap = doc.getMap('map')
    const foodArray = new Y.Array()
    foodArray.insert(0, ['apple', 'banana'])
    ymap.set('food', foodArray)
    ymap.get('food') === foodArray // => true
    ymap.set('fruit', foodArray) // => Error! foodArray is already defined
    ```
    
    Now you understand how types are defined on a shared document. Next you can jump
    to the [demo repository](https://github.com/yjs/yjs-demos) or continue reading
    the API docs.

## 示例：使用和组合提供者

**Example: Using and combining providers**

=== "中文"

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

=== "英文"
    
    Any of the Yjs providers can be combined with each other. So you can sync data
    over different network technologies.
    
    In most cases you want to use a network provider (like y-websocket or y-webrtc)
    in combination with a persistence provider (y-indexeddb in the browser).
    Persistence allows you to load the document faster and to persist data that is
    created while offline.
    
    For the sake of this demo we combine two different network providers with a
    persistence provider.
    
    ```js
    import * as Y from 'yjs'
    import { WebrtcProvider } from 'y-webrtc'
    import { WebsocketProvider } from 'y-websocket'
    import { IndexeddbPersistence } from 'y-indexeddb'
    
    const ydoc = new Y.Doc()
    
    // this allows you to instantly get the (cached) documents data
    const indexeddbProvider = new IndexeddbPersistence('count-demo', ydoc)
    indexeddbProvider.whenSynced.then(() => {
      console.log('loaded data from indexed db')
    })
    
    // Sync clients with the y-webrtc provider.
    const webrtcProvider = new WebrtcProvider('count-demo', ydoc)
    
    // Sync clients with the y-websocket provider
    const websocketProvider = new WebsocketProvider(
      'wss://demos.yjs.dev', 'count-demo', ydoc
    )
    
    // array of numbers which produce a sum
    const yarray = ydoc.getArray('count')
    
    // observe changes of the sum
    yarray.observe(event => {
      // print updates when the data changes
      console.log('new sum: ' + yarray.toArray().reduce((a,b) => a + b))
    })
    
    // add 1 to the sum
    yarray.push([1]) // => "new sum: 1"
    ```