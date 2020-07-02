### 什么是`Vue.js`

`Vue.js`是最火的前端框架，`React`是最流行的前端框架

`Vue.js`是前端的主流框架之一，和`Angular.js`、`React.js`一起并称前端三大主流框架

`Vue.js`是一套构建用户见面的框架。只关注视图层，有配套的第三方类库。主要用来制作前端页面



### `vue.js`的优点

```html
1.体积小

2.更高的运行效率

3.双向的数据绑定

4.虚拟dom，预处理操作

5.生态丰富，学习成本低

6.渐进式框架
```





#### 回顾

```
1.原生的`js`产生了什么问题？

2.`jQuery`解决了什么问题？

`Vue.js`解决了什么问题？

能够减少不必要的`DOM`操作，让用户不在操作`DOM`元素

框架和库的区别

框架是一套完整的解决方案

库（插件）：一个某一个小功能，对项目的侵入性较小，如果某个库无法完成某些需求，可以很容易奇幻到其他库实现需求
```



#### `MVC`和`MVVM`之间的区别

```
MVC是后端开发的概念

MVVM是

View界面

App.js入口

router.js专门负责路由

Controller业务处理

Model操纵数据库

MVVM是前端视图层的分层开发思想。主要把每个页面分为VM是MVVM的思想核心：因为VM是M和V的调度者。
```



### 安装

#### [CDN](https://cn.vuejs.org/v2/guide/installation.html#CDN)

```html
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

```html
<!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.0"></script>
```

#### [NPM](https://cn.vuejs.org/v2/guide/installation.html#NPM)

```shell
# 大型应用 最新稳定版
$ npm install vue
```

##### [命令行工具 (CLI)](https://cn.vuejs.org/v2/guide/installation.html#%E5%91%BD%E4%BB%A4%E8%A1%8C%E5%B7%A5%E5%85%B7-CLI)

```
熟悉 Vue 本身之后再使用 CLI
```

#### [对不同构建版本的解释](https://cn.vuejs.org/v2/guide/installation.html#%E5%AF%B9%E4%B8%8D%E5%90%8C%E6%9E%84%E5%BB%BA%E7%89%88%E6%9C%AC%E7%9A%84%E8%A7%A3%E9%87%8A)

**完整版**：

#### [术语](https://cn.vuejs.org/v2/guide/installation.html#%E6%9C%AF%E8%AF%AD)



#### [运行时 + 编译器 vs. 只包含运行时](https://cn.vuejs.org/v2/guide/installation.html#%E8%BF%90%E8%A1%8C%E6%97%B6-%E7%BC%96%E8%AF%91%E5%99%A8-vs-%E5%8F%AA%E5%8C%85%E5%90%AB%E8%BF%90%E8%A1%8C%E6%97%B6)

#### [开发环境 vs. 生产环境模式](https://cn.vuejs.org/v2/guide/installation.html#%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83-vs-%E7%94%9F%E4%BA%A7%E7%8E%AF%E5%A2%83%E6%A8%A1%E5%BC%8F)

#### [CSP 环境](https://cn.vuejs.org/v2/guide/installation.html#CSP-%E7%8E%AF%E5%A2%83)

#### [开发版本](https://cn.vuejs.org/v2/guide/installation.html#%E5%BC%80%E5%8F%91%E7%89%88%E6%9C%AC)

### 介绍

[`MVX`框架的演变以及`Vue`的优缺点](<https://blog.csdn.net/gao_xu_520/article/details/76020365>)

#### 1.依赖

```html
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

#### 2.[声明式渲染](https://cn.vuejs.org/v2/guide/index.html#%E5%A3%B0%E6%98%8E%E5%BC%8F%E6%B8%B2%E6%9F%93)和响应式布局

```html
// Vue 实例所控制的这个元素区域，就是V
<div id="app">
  {{ message }}
</div>
```

```js
// 当创建一个Vue实例，浏览器的内存中就多了一个Vue构造函数。
// new 出来的 vm对象 就是MVVM中的vm调度者
var app = new Vue({
  el: '#app',// 表示当前创建的Vue实例需要控制页面上的哪个区域。
   // 这里的data 就是MVVM中的M，专门用来保存页面的数据的
  data: {	// data属性中，存放的是el中要用到的数据
    message: 'Hello Vue!' // 通过vue指令将数据渲染到页面上，不需要程序员手动操纵DOM元素
  }
})
```



#### 3.**指令**



```html
<div id="app-2">
  <span v-bind:title="message">
    鼠标悬停几秒钟查看此处动态绑定的提示信息！
  </span>
</div>
```

```js
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: '页面加载于 ' + new Date().toLocaleString() 
  }
})
```

状态修改`app3.seen = false`

#### 4.[条件与循环](https://cn.vuejs.org/v2/guide/index.html#%E6%9D%A1%E4%BB%B6%E4%B8%8E%E5%BE%AA%E7%8E%AF)

```html
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
```

`v-for` 指令可以绑定数组的数据来渲染一个项目列表

```js
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: '学习 JavaScript' },
      { text: '学习 Vue' },
      { text: '整个牛项目' }
    ]
  }
})
```

添加新`app4.todos.push({ text: '新项目' })`列

#### 5.处理用户输入

```html
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">反转消息</button>
</div>
```

`v-on`添加事件监听器

```js
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: { // methods中定义了Vue中所有实例可用的方法，然后再标签中用v-on指令绑定方法
    reverseMessage: function () {
        // 获取Vue实例中的数据或者方法必须通过this.属性名来访问。this表示当前的Vue实例
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```

#### 6.双向绑定

```html
<div id="app-6">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
```

```js
var app6 = new Vue({
  el: '#app-6',
  data: {
    message: 'Hello Vue!'
  }
})
```

`v-model` 指令实现表单输入和应用状态之间的双向绑定

#### 7.[组件化应用构建](https://cn.vuejs.org/v2/guide/index.html#%E7%BB%84%E4%BB%B6%E5%8C%96%E5%BA%94%E7%94%A8%E6%9E%84%E5%BB%BA)

组件的注册

```js
// 定义名为 todo-item 的新组件
Vue.component('todo-item', {
  template: '<li>这是个待办项</li>'
})
```

利用组件构建模板

```html
<ol>
  <!-- 创建一个 todo-item 组件的实例 -->
  <todo-item></todo-item>
</ol>
```

从父作用域将数据传到子组件

```js
Vue.component('todo-item', {
  // todo-item 组件现在接受一个
  // "prop"，类似于一个自定义特性。
  // 这个 prop 名为 todo。
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
```

```html
<div id="app-7">
  <ol>
    <!--
      现在我们为每个 todo-item 提供 todo 对象
      todo 对象是变量，即其内容可以是动态的。
      我们也需要为每个组件提供一个“key”，稍后再
      作详细解释。
    -->
    <todo-item
      v-for="item in groceryList"
      v-bind:todo="item"
      v-bind:key="item.id"
    ></todo-item>
  </ol>
</div>
```

```js
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})

var app7 = new Vue({
  el: '#app-7',
  data: {
    groceryList: [
      { id: 0, text: '蔬菜' },
      { id: 1, text: '奶酪' },
      { id: 2, text: '随便其它什么人吃的东西' }
    ]
  }
})
```

#### 8.todo应用的组件树

```
根实例
└─ TodoList
   ├─ TodoItem
   │  ├─ DeleteTodoButton
   │  └─ EditTodoButton
   └─ TodoListFooter
      ├─ ClearTodosButton
      └─ TodoListStatistics
```

#### 9.数据和方法

```js
// 我们的数据对象
var data = { a: 1 }

// 该对象被加入到一个 Vue 实例中
var vm = new Vue({
  data: data
})

// 获得这个实例上的属性
// 返回源数据中对应的字段
vm.a == data.a // => true

// 设置属性也会影响到原始数据
vm.a = 2
data.a // => 2

// ……反之亦然
data.a = 3
vm.a // => 3
```

#### 10.数据的初始化

```js
data: {
  newTodoText: '',
  visitCount: 0,
  hideCompletedTodos: false,
  todos: [],
  error: null
}
```

`Object.freeze()`会阻止修改现有的属性

[实例属性与方法`$`](https://cn.vuejs.org/v2/api/#%E5%AE%9E%E4%BE%8B%E5%B1%9E%E6%80%A7)



#### 11.实例生命周期钩子

钩子：创建一个`Vue`时候有一个时间的过程，在这个过程产生各样的事件，侦听事件，方便在各个事件的阶段添加代码。

注意：不要在选项属性或回调上使用[箭头函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/Arrow_functions)，因为箭头函数并没有 `this`

![Pandao editor.md](https://cn.vuejs.org/images/lifecycle.png "生命周期钩子图示")

在创建Vue对象的时候默认调用生命周期钩子，不能使用箭头函数

beforeCreate:在数据实例化之后，数据观测（data observer）和 event/watcher事件配置之前被调用

created:在实例创建完成之后被立即调用，实例已经完成配置：数据观测（data observer），属性和方法的运算，watch/event事件回调。当然，挂载阶段还没有开始，$el属性目前不可见

beforeMout:在挂载开始之前被调用，相关的渲染函数首次被调用

beforeUpdate ：数据更新之前被调用，数据变化之前

updated:组件DOM已经更新，组件更新完毕

activated：keeep-alive组件激活时调用

deactivated:组件停用之前被调用

beforeDestroy:组件销毁之前被调用

errorCaptured：捕获子组件错误的时候被调用

setTimeout

#### 12.模板语法

`Vue.js `使用了基于` HTML `的模板语法，允许开发者声明式地将` DOM `绑定至底层` Vue `实例的数据。所有 `Vue.js `的模板都是合法的` HTML `，所以能被遵循规范的浏览器和`HTML` 解析器解析。

在底层的实现上，`Vue `将模板编译成虚拟 `DOM` 渲染函数。结合响应系统，`Vue` 能够智能地计算出最少需要重新渲染多少组件，并把 `DOM` 操作次数减到最少。

#### 13.插值

##### [文本](https://cn.vuejs.org/v2/guide/syntax.html#%E6%96%87%E6%9C%AC)插值`Mustache`

双大括号会将数据解释为普通文本

```js
<span>Message: {{ msg }}</span>
<span v-once>这个将不会改变: {{ msg }}</span>
```

为了输出真正的 HTML，你需要使用 `v-html` 指令：

```html
<p>Using mustaches: {{ rawHtml }}</p>
<p>Using v-html directive: <span v-html="rawHtml"></span></p>
```

#### 14.指令

`v-cloak`：能够解决插值表达式的闪烁问题。当网络速度比较缓慢时候会看到插值表达式的`{{msg}}`

```html
①在插值表达式所在的标签增加一个v-cload属性
②增加样式
[v-cloak]{
	display:none;
}
```



`v-test`和插值表达式没有太大的区别。

```html
默认v-test是没有闪烁问题的。
v-test会覆盖掉原来标签体中的内容。
而插值表达式不会覆盖标签体的内容，只会替换当前位置的占位符。
```



`v-html`:会将数据原本的输出，不会转移内容。插值表达式将数据解释为普通文本，而不是`HTML`代码。为了输出真正的`HTML`用`v-html`

指令 `(Directives)` 是带有 `v-` 前缀的特殊特性。指令特性的值预期是**单个 JavaScript 表达式**

v-if：条件渲染，懒渲染

 [v-once](https://cn.vuejs.org/v2/api/#v-once):只进行一次一次插值



`v-bind`：`mwstache`语法不能作用在`html`特性上，`v-bind`可以绑定属性,省略写法，直接保留冒号，`v-bind`中可以写合法的`js`表达式。

v-esle-if

v-show:v-show="表达式"，不管是什么条件都渲染

v-for

`v-on`

```
用在便签属性。用来绑定事件
v-on:click="函数名"

事件修饰符
.stop 阻止冒泡 有两个div堆叠了点击事件的时候 用法@click.stop阻止冒泡
.prevent阻止默认行为
.capture添加事件侦听器使用事件捕获模式
.self 只有自己的时候才会触发的事件
.once事件只会触发一次
事件修饰符可以串联
stop和self的区别
	self只会阻止自己的冒泡
	stop阻止了所有的冒泡
:class	用属性绑定的方法添加样式，需要传入的是字符串的类名 ：是v-bind的缩写 
:class = "[flag?'active':'']"	可以在数组中写三元表达式
:class = "[{'active':flag}]"	可以在里面传对象代替三元表达式提高可读性	对象就是无序键值对的集合，如果属性里面包含“-”那么属性名必须加一个单引号
:class = "{active:true}"		也可以直接传对象 对象的属性是类名，对象的属性可以带引号也可以不带引号，后面是标识符
```



`v-model`双向数据绑定

```
v-bind只能实现数据的单向绑定。无法实现数据的双向绑定
v-modle只能运用在表单元素中。用法v-modle=“变量名”
input	(radio.text.address.email )	select chechbox textarea
```



#### 15.动态参数

方括号括起来的 JavaScript 表达式作为一个指令的参数会被作为一个 JavaScript 表达式进行动态求值，求得的值将会作为最终的参数来使用

```js
<!--
注意，参数表达式的写法存在一些约束，如之后的“对动态参数表达式的约束”章节所述。
-->
<a v-bind:[attributeName]="url"> ... </a>
```

 Vue 实例有一个 `data` 属性 `attributeName`，其值为 `"href"`，那么这个绑定将等价于 `v-bind:href`

##### 对动态参数的值的约束

动态参数预期会求出一个字符串，异常情况下值为 `null`。这个特殊的 `null` 值可以被显性地用于移除绑定。任何其它非字符串类型的值都将会触发一个警告。

##### 对动态参数表达式的约束



#### 指令的修饰符

@click="函数名"

.stop当前的事件完成之后会停止，不会传播

#### 对象语法

动态绑定class和style

#### 列表渲染

v-for

#### 维护状态

#### 事件处理

v-on

#### 事件修饰符

dblclick

#### 表单输入绑定

v-model双向绑定

#### JavaScript表达式

三元运算

split().reverser().join()

基础知识体系

```html
基本的Vue代码结构
插值表达式和v-text
v-cloak
v-html
v-bind	用于事件的绑定机制	缩写：
v-on	用于事件的绑定机制	缩写@
```

#### 箭头函数

```
箭头函数中的this指向当前实例的Vue，解决了函数体中的内部this指向外部的this
```



