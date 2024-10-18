# API

```js
import * as Y from 'yjs'
```

## 共享类型

**Shared Types**

### Y.Array

=== "中文"

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

=== "英文"

    <p>
    A shareable Array-like type that supports efficient insert/delete of elements
    at any position. Internally it uses a linked list of Arrays that is split when
    necessary.
    </p>
    <pre>const yarray = new Y.Array()</pre>
    <dl>
    <b><code>
    Y.Array.from(Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;):
    Y.Array
    </code></b>
    <dd>An alternative factory function to create a Y.Array based on existing content.</dd>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;)</code></b>
    <dd>
    Insert content at <var>index</var>. Note that content is an array of elements.
    I.e. <code>array.insert(0, [1])</code> splices the list and inserts 1 at
    position 0.
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
    <dd>Retrieve a range of content</dd>
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
    Clone all values into a fresh Y.Array instance. The returned type can be
    included into the Yjs document.
    </dd>
    <b><code>toArray():Array&lt;object|boolean|Array|string|number|null|Uint8Array|Y.Type&gt;</code></b>
    <dd>Copies the content of this YArray to a new Array.</dd>
    <b><code>toJSON():Array&lt;Object|boolean|Array|string|number|null&gt;</code></b>
    <dd>
    Copies the content of this YArray to a new Array. It transforms all child types
    to JSON using their <code>toJSON</code> method.
    </dd>
    <b><code>[Symbol.Iterator]</code></b>
    <dd>
        Returns an YArray Iterator that contains the values for each index in the array.
        <pre>for (let value of yarray) { .. }</pre>
    </dd>
    <b><code>observe(function(YArrayEvent, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type is modified. In the case this type is modified in the event listener,
    the event listener will be called again after the current event listener returns.
    </dd>
    <b><code>unobserve(function(YArrayEvent, Transaction):void)</code></b>
    <dd>
        Removes an <code>observe</code> event listener from this type.
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type or any of its children is modified. In the case this type is modified
    in the event listener, the event listener will be called again after the current
    event listener returns. The event listener receives all Events created by itself
    or any of its children.
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
        Removes an <code>observeDeep</code> event listener from this type.
    </dd>
    </dl>

### Y.Map

=== "中文"

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

=== "英文"

    <p>
    A shareable Map type.
    </p>
    <pre><code>const ymap = new Y.Map()</code></pre>
    <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>size: number</code></b>
    <dd>Total number of key/value pairs.</dd>
    <b><code>get(key:string):object|boolean|string|number|null|Uint8Array|Y.Type</code></b>
    <dd></dd>
    <b><code>set(key:string, value:object|boolean|string|number|null|Uint8Array|Y.Type)</code></b>
    <dd></dd>
    <b><code>delete(key:string)</code></b>
    <dd></dd>
    <b><code>has(key:string):boolean</code></b>
    <dd></dd>
    <b><code>clear()</code></b>
    <dd>Removes all elements from this YMap.</dd>
    <b><code>clone():Y.Map</code></b>
    <dd>Clone this type into a fresh Yjs type.</dd>
    <b><code>toJSON():Object&lt;string, Object|boolean|Array|string|number|null|Uint8Array&gt;</code></b>
    <dd>
    Copies the <code>[key,value]</code> pairs of this YMap to a new Object.It
    transforms all child types to JSON using their <code>toJSON</code> method.
    </dd>
    <b><code>forEach(function(value:object|boolean|Array|string|number|null|Uint8Array|Y.Type,
    key:string, map: Y.Map))</code></b>
    <dd>
        Execute the provided function once for every key-value pair.
    </dd>
    <b><code>[Symbol.Iterator]</code></b>
    <dd>
        Returns an Iterator of <code>[key, value]</code> pairs.
        <pre>for (let [key, value] of ymap) { .. }</pre>
    </dd>
    <b><code>entries()</code></b>
    <dd>
        Returns an Iterator of <code>[key, value]</code> pairs.
    </dd>
    <b><code>values()</code></b>
    <dd>
        Returns an Iterator of all values.
    </dd>
    <b><code>keys()</code></b>
    <dd>
        Returns an Iterator of all keys.
    </dd>
    <b><code>observe(function(YMapEvent, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type is modified. In the case this type is modified in the event listener,
    the event listener will be called again after the current event listener returns.
    </dd>
    <b><code>unobserve(function(YMapEvent, Transaction):void)</code></b>
    <dd>
        Removes an <code>observe</code> event listener from this type.
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type or any of its children is modified. In the case this type is modified
    in the event listener, the event listener will be called again after the current
    event listener returns. The event listener receives all Events created by itself
    or any of its children.
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
        Removes an <code>observeDeep</code> event listener from this type.
    </dd>
    </dl>

### Y.Text

=== "中文"

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

=== "英文"

    <p>
    A shareable type that is optimized for shared editing on text. It allows to
    assign properties to ranges in the text. This makes it possible to implement
    rich-text bindings to this type.
    </p>
    <p>
    This type can also be transformed to the
    <a href="https://quilljs.com/docs/delta">delta format</a>. Similarly the
    YTextEvents compute changes as deltas.
    </p>
    <pre>const ytext = new Y.Text()</pre>
    <dl>
    <b><code>parent:Y.AbstractType|null</code></b>
    <dd></dd>
    <b><code>insert(index:number, content:string, [formattingAttributes:Object&lt;string,string&gt;])</code></b>
    <dd>
        Insert a string at <var>index</var> and assign formatting attributes to it.
        <pre>ytext.insert(0, 'bold text', { bold: true })</pre>
    </dd>
    <b><code>delete(index:number, length:number)</code></b>
    <dd></dd>
    <b><code>format(index:number, length:number, formattingAttributes:Object&lt;string,string&gt;)</code></b>
    <dd>Assign formatting attributes to a range in the text</dd>
    <b><code>applyDelta(delta: Delta, opts:Object&lt;string,any&gt;)</code></b>
    <dd>
        See <a href="https://quilljs.com/docs/delta/">Quill Delta</a>
        Can set options for preventing remove ending newLines, default is true.
        <pre>ytext.applyDelta(delta, { sanitize: false })</pre>
    </dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b><code>toString():string</code></b>
    <dd>Transforms this type, without formatting options, into a string.</dd>
    <b><code>toJSON():string</code></b>
    <dd>See <code>toString</code></dd>
    <b><code>toDelta():Delta</code></b>
    <dd>
    Transforms this type to a <a href="https://quilljs.com/docs/delta/">Quill Delta</a>
    </dd>
    <b><code>observe(function(YTextEvent, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type is modified. In the case this type is modified in the event listener,
    the event listener will be called again after the current event listener returns.
    </dd>
    <b><code>unobserve(function(YTextEvent, Transaction):void)</code></b>
    <dd>
        Removes an <code>observe</code> event listener from this type.
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type or any of its children is modified. In the case this type is modified
    in the event listener, the event listener will be called again after the current
    event listener returns. The event listener receives all Events created by itself
    or any of its children.
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
        Removes an <code>observeDeep</code> event listener from this type.
    </dd>
    </dl>

### Y.XmlFragment

=== "中文"

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

=== "英文"

    <p>
    A container that holds an Array of Y.XmlElements.
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
    <dd>Retrieve a range of content</dd>
    <b><code>length:number</code></b>
    <dd></dd>
    <b><code>clone():Y.XmlFragment</code></b>
    <dd>Clone this type into a fresh Yjs type.</dd>
    <b><code>toArray():Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>Copies the children to a new Array.</dd>
    <b><code>toDOM():DocumentFragment</code></b>
    <dd>Transforms this type and all children to new DOM elements.</dd>
    <b><code>toString():string</code></b>
    <dd>Get the XML serialization of all descendants.</dd>
    <b><code>toJSON():string</code></b>
    <dd>See <code>toString</code>.</dd>
    <b><code>createTreeWalker(filter: function(AbstractType&lt;any&gt;):boolean):Iterable</code></b>
    <dd>Create an Iterable that walks through the children.</dd>
    <b><code>observe(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type is modified. In the case this type is modified in the event listener,
    the event listener will be called again after the current event listener returns.
    </dd>
    <b><code>unobserve(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
        Removes an <code>observe</code> event listener from this type.
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type or any of its children is modified. In the case this type is modified
    in the event listener, the event listener will be called again after the current
    event listener returns. The event listener receives all Events created by itself
    or any of its children.
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
        Removes an <code>observeDeep</code> event listener from this type.
    </dd>
    </dl>

### Y.XmlElement

=== "中文"

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

=== "英文"

    <p>
    A shareable type that represents an XML Element. It has a <code>nodeName</code>,
    attributes, and a list of children. But it makes no effort to validate its
    content and be actually XML compliant.
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
    <dd>Retrieve the i-th element.</dd>
    <b><code>slice(start:number, end:number):Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>Retrieve a range of content</dd>
    <b><code>clone():Y.XmlElement</code></b>
    <dd>Clone this type into a fresh Yjs type.</dd>
    <b><code>toArray():Array&lt;Y.XmlElement|Y.XmlText&gt;</code></b>
    <dd>Copies the children to a new Array.</dd>
    <b><code>toDOM():Element</code></b>
    <dd>Transforms this type and all children to a new DOM element.</dd>
    <b><code>toString():string</code></b>
    <dd>Get the XML serialization of all descendants.</dd>
    <b><code>toJSON():string</code></b>
    <dd>See <code>toString</code>.</dd>
    <b><code>observe(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every
    time this type is modified. In the case this type is modified in the event
    listener, the event listener will be called again after the current event
    listener returns.
    </dd>
    <b><code>unobserve(function(YXmlEvent, Transaction):void)</code></b>
    <dd>
        Removes an <code>observe</code> event listener from this type.
    </dd>
    <b><code>observeDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
    Adds an event listener to this type that will be called synchronously every time
    this type or any of its children is modified. In the case this type is modified
    in the event listener, the event listener will be called again after the current
    event listener returns. The event listener receives all Events created by itself
    or any of its children.
    </dd>
    <b><code>unobserveDeep(function(Array&lt;YEvent&gt;, Transaction):void)</code></b>
    <dd>
        Removes an <code>observeDeep</code> event listener from this type.
    </dd>
    </dl>

## Y.Doc

=== "中文"

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

=== "英文"

    ```js
    const doc = new Y.Doc()
    ```
    
    <dl>
      <b><code>clientID</code></b>
      <dd>A unique id that identifies this client. (readonly)</dd>
      <b><code>gc</code></b>
      <dd>
    Whether garbage collection is enabled on this doc instance. Set `doc.gc = false`
    in order to disable gc and be able to restore old content. See https://github.com/yjs/yjs#yjs-crdt-algorithm
    for more information about gc in Yjs.
      </dd>
      <b><code>transact(function(Transaction):void [, origin:any])</code></b>
      <dd>
    Every change on the shared document happens in a transaction. Observer calls and
    the <code>update</code> event are called after each transaction. You should
    <i>bundle</i> changes into a single transaction to reduce the amount of event
    calls. I.e. <code>doc.transact(() => { yarray.insert(..); ymap.set(..) })</code>
    triggers a single change event. <br>You can specify an optional <code>origin</code>
    parameter that is stored on <code>transaction.origin</code> and
    <code>on('update', (update, origin) => ..)</code>.
      </dd>
      <b><code>toJSON():any</code></b>
      <dd>
    Deprecated: It is recommended to call toJSON directly on the shared types.
    Converts the entire document into a js object, recursively traversing each yjs
    type. Doesn't log types that have not been defined (using
    <code>ydoc.getType(..)</code>).
      </dd>
      <b><code>get(string, Y.[TypeClass]):[Type]</code></b>
      <dd>Define a shared type.</dd>
      <b><code>getArray(string):Y.Array</code></b>
      <dd>Define a shared Y.Array type. Is equivalent to <code>y.get(string, Y.Array)</code>.</dd>
      <b><code>getMap(string):Y.Map</code></b>
      <dd>Define a shared Y.Map type. Is equivalent to <code>y.get(string, Y.Map)</code>.</dd>
      <b><code>getText(string):Y.Text</code></b>
      <dd>Define a shared Y.Text type. Is equivalent to <code>y.get(string, Y.Text)</code>.</dd>
      <b><code>getXmlElement(string, string):Y.XmlElement</code></b>
      <dd>Define a shared Y.XmlElement type. Is equivalent to <code>y.get(string, Y.XmlElement)</code>.</dd>
      <b><code>getXmlFragment(string):Y.XmlFragment</code></b>
      <dd>Define a shared Y.XmlFragment type. Is equivalent to <code>y.get(string, Y.XmlFragment)</code>.</dd>
      <b><code>on(string, function)</code></b>
      <dd>Register an event listener on the shared type</dd>
      <b><code>off(string, function)</code></b>
      <dd>Unregister an event listener from the shared type</dd>
    </dl>

### Y.Doc 事件

=== "中文"

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

=== "英文"

    <dl>
      <b><code>on('update', function(updateMessage:Uint8Array, origin:any, Y.Doc):void)</code></b>
      <dd>
    Listen to document updates. Document updates must be transmitted to all other
    peers. You can apply document updates in any order and multiple times. Use `updateV2`
    to receive V2 events.
      </dd>
      <b><code>on('beforeTransaction', function(Y.Transaction, Y.Doc):void)</code></b>
      <dd>Emitted before each transaction.</dd>
      <b><code>on('afterTransaction', function(Y.Transaction, Y.Doc):void)</code></b>
      <dd>Emitted after each transaction.</dd>
      <b><code>on('beforeAllTransactions', function(Y.Doc):void)</code></b>
      <dd>
    Transactions can be nested (e.g. when an event within a transaction calls another
    transaction). Emitted before the first transaction.
      </dd>
      <b><code>on('afterAllTransactions', function(Y.Doc, Array&lt;Y.Transaction&gt;):void)</code></b>
      <dd>Emitted after the last transaction is cleaned up.</dd>
    </dl>

## 文档更新

**Document Updates**

=== "中文"
    
    对共享文档的更改被编码为 *文档更新*。文档更新是 *交换律* 和 *幂等* 的。这意味着它们可以以任何顺序和多次应用。

=== "英文"

    Changes on the shared document are encoded into *document updates*. Document
    updates are *commutative* and *idempotent*. This means that they can be applied
    in any order and multiple times.

### 示例：监听更新事件并在远程客户端上应用

**Example: Sync two clients by exchanging the complete document structure**

=== "中文"

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
    

=== "英文"

    ```js
    const doc1 = new Y.Doc()
    const doc2 = new Y.Doc()
    
    doc1.on('update', update => {
      Y.applyUpdate(doc2, update)
    })
    
    doc2.on('update', update => {
      Y.applyUpdate(doc1, update)
    })
    
    // All changes are also applied to the other document
    doc1.getArray('myarray').insert(0, ['Hello doc2, you got this?'])
    doc2.getArray('myarray').get(0) // => 'Hello doc2, you got this?'
    ```
    
    Yjs internally maintains a [state vector](#state-vector) that denotes the next
    expected clock from each client. In a different interpretation it holds the
    number of structs created by each client. When two clients sync, you can either
    exchange the complete document structure or only the differences by sending the
    state vector to compute the differences.

### 示例：通过交换完整文档结构同步两个客户端

**Example: Sync two clients by exchanging the complete document structure**

```js
const state1 = Y.encodeStateAsUpdate(ydoc1)
const state2 = Y.encodeStateAsUpdate(ydoc2)
Y.applyUpdate(ydoc1, state2)
Y.applyUpdate(ydoc2, state1)
```

### 示例：通过计算差异同步两个客户端

**Example: Sync two clients by computing the differences**

=== "中文"

    此示例演示如何通过仅使用远程客户端的状态向量计算差异，以最小的数据交换量同步两个客户端。使用状态向量同步客户端需要额外的往返，但可以节省大量带宽。

    ```js
    const stateVector1 = Y.encodeStateVector(ydoc1)
    const stateVector2 = Y.encodeStateVector(ydoc2)
    const diff1 = Y.encodeStateAsUpdate(ydoc1, stateVector2)
    const diff2 = Y.encodeStateAsUpdate(ydoc2, stateVector1)
    Y.applyUpdate(ydoc1, diff2)
    Y.applyUpdate(ydoc2, diff1)
    ```

=== "英文"

    This example shows how to sync two clients with the minimal amount of exchanged
    data by computing only the differences using the state vector of the remote
    client. Syncing clients using the state vector requires another roundtrip, but
    can save a lot of bandwidth.
    
    ```js
    const stateVector1 = Y.encodeStateVector(ydoc1)
    const stateVector2 = Y.encodeStateVector(ydoc2)
    const diff1 = Y.encodeStateAsUpdate(ydoc1, stateVector2)
    const diff2 = Y.encodeStateAsUpdate(ydoc2, stateVector1)
    Y.applyUpdate(ydoc1, diff2)
    Y.applyUpdate(ydoc2, diff1)
    ```

### 示例：在不加载 Y.Doc 的情况下同步客户端

**Example: Syncing clients without loading the Y.Doc**

=== "中文"

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

=== "英文"

    It is possible to sync clients and compute delta updates without loading the Yjs
    document to memory. Yjs exposes an API to compute the differences directly on the
    binary document updates.
    
    ```js
    // encode the current state as a binary buffer
    let currentState1 = Y.encodeStateAsUpdate(ydoc1)
    let currentState2 = Y.encodeStateAsUpdate(ydoc2)
    // now we can continue syncing clients using state vectors without using the Y.Doc
    ydoc1.destroy()
    ydoc2.destroy()
    
    const stateVector1 = Y.encodeStateVectorFromUpdate(currentState1)
    const stateVector2 = Y.encodeStateVectorFromUpdate(currentState2)
    const diff1 = Y.diffUpdate(currentState1, stateVector2)
    const diff2 = Y.diffUpdate(currentState2, stateVector1)
    
    // sync clients
    currentState1 = Y.mergeUpdates([currentState1, diff2])
    currentState2 = Y.mergeUpdates([currentState2, diff1])
    ```

### 混淆更新

**Obfuscating Updates**

=== "中文"

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

=== "英文"

    If one of your users runs into a weird bug (e.g. the rich-text editor throws
    error messages), then you don't have to request the full document from your
    user. Instead, they can obfuscate the document (i.e. replace the content with
    meaningless generated content) before sending it to you. Note that someone might
    still deduce the type of content by looking at the general structure of the
    document. But this is much better than requesting the original document.
    
    Obfuscated updates contain all the CRDT-related data that is required for
    merging. So it is safe to merge obfuscated updates.
    
    ```javascript
    const ydoc = new Y.Doc()
    // perform some changes..
    ydoc.getText().insert(0, 'hello world')
    const update = Y.encodeStateAsUpdate(ydoc)
    // the below update contains scrambled data
    const obfuscatedUpdate = Y.obfuscateUpdate(update)
    const ydoc2 = new Y.Doc()
    Y.applyUpdate(ydoc2, obfuscatedUpdate)
    ydoc2.getText().toString() // => "00000000000"
    ```

### 使用 V2 更新格式

**Using V2 update format**

=== "中文"
    
    Yjs 实现了两种更新格式。默认情况下，您使用的是 V1 更新格式。您可以选择使用 V2 更新格式，该格式提供了更好的压缩效果。并非所有提供者都使用它。不过，如果您正在构建自己的提供者，您已经可以使用它。所有以下函数都有后缀 "V2"。例如 `Y.applyUpdate` ⇒ `Y.applyUpdateV2`。此外，在监听更新时，您需要特别监听 V2 事件，例如 `yDoc.on('updateV2', …)`。我们还支持两种格式之间的转换函数：`Y.convertUpdateFormatV1ToV2` 和 `Y.convertUpdateFormatV2ToV1`。    
    

=== "英文"

    Yjs implements two update formats. By default you are using the V1 update format.
    You can opt-in into the V2 update format which provides much better compression.
    It is not yet used by all providers. However, you can already use it if
    you are building your own provider. All below functions are available with the
    suffix "V2". E.g. `Y.applyUpdate` ⇒ `Y.applyUpdateV2`. Also when listening to updates
    you need to specifically need listen for V2 events e.g. `yDoc.on('updateV2', …)`.
    We also support conversion functions between both formats:
    `Y.convertUpdateFormatV1ToV2` & `Y.convertUpdateFormatV2ToV1`.

### 更新 API

**Update API**

=== "中文"

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

=== "英文"

    <dl>
      <b><code>Y.applyUpdate(Y.Doc, update:Uint8Array, [transactionOrigin:any])</code></b>
      <dd>
    Apply a document update on the shared document. Optionally you can specify
    <code>transactionOrigin</code> that will be stored on
    <code>transaction.origin</code>
    and <code>ydoc.on('update', (update, origin) => ..)</code>.
      </dd>
      <b><code>Y.encodeStateAsUpdate(Y.Doc, [encodedTargetStateVector:Uint8Array]):Uint8Array</code></b>
      <dd>
    Encode the document state as a single update message that can be applied on the
    remote document. Optionally specify the target state vector to only write the
    differences to the update message.
      </dd>
      <b><code>Y.encodeStateVector(Y.Doc):Uint8Array</code></b>
      <dd>Computes the state vector and encodes it into an Uint8Array.</dd>
      <b><code>Y.mergeUpdates(Array&lt;Uint8Array&gt;)</code></b>
      <dd>
    Merge several document updates into a single document update while removing
    duplicate information. The merged document update is always smaller than
    the separate updates because of the compressed encoding.
      </dd>
      <b><code>Y.encodeStateVectorFromUpdate(Uint8Array): Uint8Array</code></b>
      <dd>
    Computes the state vector from a document update and encodes it into an Uint8Array.
      </dd>
      <b><code>Y.diffUpdate(update: Uint8Array, stateVector: Uint8Array): Uint8Array</code></b>
      <dd>
    Encode the missing differences to another update message. This function works
    similarly to <code>Y.encodeStateAsUpdate(ydoc, stateVector)</code> but works
    on updates instead.
      </dd>
      <b><code>convertUpdateFormatV1ToV2</code></b>
      <dd>
    Convert V1 update format to the V2 update format.
      </dd>
      <b><code>convertUpdateFormatV2ToV1</code></b>
      <dd>
    Convert V2 update format to the V1 update format.
      </dd>
    </dl>

## 相对位置

**Relative Positions**

=== "中文"

    在处理协作文档时，我们经常需要处理位置。位置可以表示光标位置、选择范围，甚至将评论分配给一段文本。正常的索引位置（以整数表示）不方便使用，因为一旦远程更改操作文档，索引范围就会失效。相对位置为您提供了一个强大的 API 来表达位置。
    
    相对位置固定于共享文档中的一个元素，并且不受远程更改的影响。即给定文档 `"a|c"`，相对位置附加到 `c`。当远程用户通过在光标之前插入一个字符来修改文档时，光标将保持附加在字符 `c` 上。`insert(1, 'x')("a|c") = "ax|c"`。当相对位置设置在文档末尾时，它将保持附加在文档的末尾。

=== "英文"

    When working with collaborative documents, we often need to work with positions.
    Positions may represent cursor locations, selection ranges, or even assign a
    comment to a range of text. Normal index-positions (expressed as integers) are
    not convenient to use because the index-range is invalidated as soon as a remote
    change manipulates the document. Relative positions give you a powerful API to
    express positions.
    
    A relative position is fixated to an element in the shared document and is not
    affected by remote changes. I.e. given the document `"a|c"`, the relative
    position is attached to `c`. When a remote user modifies the document by
    inserting a character before the cursor, the cursor will stay attached to the
    character `c`. `insert(1, 'x')("a|c") = "ax|c"`. When the relative position is
    set to the end of the document, it will stay attached to the end of the
    document.

### 示例：转换为相对位置并返回

**Example: Transform to RelativePosition and back**

```js
const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
const pos = Y.createAbsolutePositionFromRelativePosition(relPos, doc)
pos.type === ytext // => true
pos.index === 2 // => true
```

### 示例：将相对位置发送给远程客户端（json）

**Example: Send relative position to remote client (json)**

```js
const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
const encodedRelPos = JSON.stringify(relPos)
// 将 encodedRelPos 发送给远程客户端..
const parsedRelPos = JSON.parse(encodedRelPos)
const pos = Y.createAbsolutePositionFromRelativePosition(parsedRelPos, remoteDoc)
pos.type === remoteytext // => true
pos.index === 2 // => true
```

### 示例：将相对位置发送给远程客户端（Uint8Array）

=== "中文"

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

=== "英文"

    ```js
    const relPos = Y.createRelativePositionFromTypeIndex(ytext, 2)
    const encodedRelPos = Y.encodeRelativePosition(relPos)
    // send encodedRelPos to remote client..
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
    Create a relative position fixated to the i-th element in any sequence-like
    shared type (if <code>assoc >= 0</code>). By default, the position associates
    with the character that comes after the specified index position. If
    <code>assoc < 0</code>, then the relative position associates with the character
    before the specified index position.
      </dd>
      <b><code>
    Y.createAbsolutePositionFromRelativePosition(RelativePosition, Y.Doc):
    { type: Y.AbstractType, index: number, assoc: number } | null
      </code></b>
      <dd>
    Create an absolute position from a relative position. If the relative position
    cannot be referenced, or the type is deleted, then the result is null.
      </dd>
      <b><code>
    Y.encodeRelativePosition(RelativePosition):Uint8Array
      </code></b>
      <dd>
    Encode a relative position to an Uint8Array. Binary data is the preferred
    encoding format for document updates. If you prefer JSON encoding, you can
    simply JSON.stringify / JSON.parse the relative position instead.
      </dd>
      <b><code>Y.decodeRelativePosition(Uint8Array):RelativePosition</code></b>
      <dd>Decode a binary-encoded relative position to a RelativePositon object.</dd>
    </dl>

## Y.UndoManager

=== "中文"

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

=== "英文"

    Yjs ships with an Undo/Redo manager for selective undo/redo of changes on a
    Yjs type. The changes can be optionally scoped to transaction origins.
    
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
      <dd>Accepts either single type as scope or an array of types.</dd>
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
    Register an event that is called when a <code>StackItem</code> is added to the
    undo- or the redo-stack.
      </dd>
      <b>
        <code>
    on('stack-item-updated', { stackItem: { meta: Map&lt;any,any&gt; }, type: 'undo'
    | 'redo' })
        </code>
      </b>
      <dd>
    Register an event that is called when an existing <code>StackItem</code> is updated.
    This happens when two changes happen within a "captureInterval".
      </dd>
      <b>
        <code>
    on('stack-item-popped', { stackItem: { meta: Map&lt;any,any&gt; }, type: 'undo'
    | 'redo' })
        </code>
      </b>
      <dd>
    Register an event that is called when a <code>StackItem</code> is popped from
    the undo- or the redo-stack.
      </dd>
      <b>
        <code>
    on('stack-cleared', { undoStackCleared: boolean, redoStackCleared: boolean })
        </code>
      </b>
      <dd>
    Register an event that is called when the undo- and/or the redo-stack is cleared.
      </dd>
    </dl>

### 示例：停止捕获

**Example: Stop Capturing**

=== "中文"

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

=== "英文"

    UndoManager merges Undo-StackItems if they are created within time-gap
    smaller than `options.captureTimeout`. Call `um.stopCapturing()` so that the next
    StackItem won't be merged.
    
    ```js
    // without stopCapturing
    ytext.insert(0, 'a')
    ytext.insert(1, 'b')
    undoManager.undo()
    ytext.toString() // => '' (note that 'ab' was removed)
    // with stopCapturing
    ytext.insert(0, 'a')
    undoManager.stopCapturing()
    ytext.insert(0, 'b')
    undoManager.undo()
    ytext.toString() // => 'a' (note that only 'b' was removed)
    ```

### 示例：指定跟踪来源

**Example: Specify tracked origins**

=== "中文"

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

=== "英文"

    Every change on the shared document has an origin. If no origin was specified,
    it defaults to `null`. By specifying `trackedOrigins` you can
    selectively specify which changes should be tracked by `UndoManager`. The
    UndoManager instance is always added to `trackedOrigins`.
    
    ```js
    class CustomBinding {}
    
    const ytext = doc.getText('text')
    const undoManager = new Y.UndoManager(ytext, {
      trackedOrigins: new Set([42, CustomBinding])
    })
    
    ytext.insert(0, 'abc')
    undoManager.undo()
    ytext.toString() // => 'abc' (does not track because origin `null` and not part
                     //           of `trackedTransactionOrigins`)
    ytext.delete(0, 3) // revert change
    
    doc.transact(() => {
      ytext.insert(0, 'abc')
    }, 42)
    undoManager.undo()
    ytext.toString() // => '' (tracked because origin is an instance of `trackedTransactionorigins`)
    
    doc.transact(() => {
      ytext.insert(0, 'abc')
    }, 41)
    undoManager.undo()
    ytext.toString() // => 'abc' (not tracked because 41 is not an instance of
                     //        `trackedTransactionorigins`)
    ytext.delete(0, 3) // revert change
    
    doc.transact(() => {
      ytext.insert(0, 'abc')
    }, new CustomBinding())
    undoManager.undo()
    ytext.toString() // => '' (tracked because origin is a `CustomBinding` and
                     //        `CustomBinding` is in `trackedTransactionorigins`)
    ```

### 示例：向 StackItems 添加额外信息

**Example: Add additional information to the StackItems**


=== "中文"

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

=== "英文"

    When undoing or redoing a previous action, it is often expected to restore
    additional meta information like the cursor location or the view on the
    document. You can assign meta-information to Undo-/Redo-StackItems.
    
    ```js
    const ytext = doc.getText('text')
    const undoManager = new Y.UndoManager(ytext, {
      trackedOrigins: new Set([42, CustomBinding])
    })
    
    undoManager.on('stack-item-added', event => {
      // save the current cursor location on the stack-item
      event.stackItem.meta.set('cursor-location', getRelativeCursorLocation())
    })
    
    undoManager.on('stack-item-popped', event => {
      // restore the current cursor location on the stack-item
      restoreCursorLocation(event.stackItem.meta.get('cursor-location'))
    })
    ```