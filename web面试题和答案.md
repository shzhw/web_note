## HTML
#### 语义化
- html语义化就是让页面的内容结构化
- 使阅读代码的人更容易将网站内容分块，便于阅读维护理解。
- 没有css样式的情况下也以一种文档格式显示，并且是容易阅读的
- 搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，*利于SEO（搜索引擎优化）*
- 便于浏览器、搜索引擎的解析
- 对搜索引擎的抓取有好处
- 用正确的标签做正确的事
- H5结构化标签

#### 结构化的语义标签

#### web标准
- web标准不是某一个标准，而是一系列标准的集合
- 网页可以分为三个部分：
	+ 结构层
		* 结构化的标准语言主要是xhtml和xml
	+ 表现层
		* 表现标准语言主要是css
	+ 行为层
		* 行为标准主要包括：对象模型（DOM/W3C）、ECMAScript
 	+ 并要求这三部分分离
- 这些标准大部分是由W3C起草和发布的，也有一些是其他标准组织制定的：ECMAScript标准
- *web标准的好处*

#### 浏览器标准模式和怪异模式
#### 严格模式和混杂模式
#### doctype
- <!doctype>声明位于整个文档的第一行，用来告知浏览器解析器以什么文档类型来解析该篇文档
- <!doctype>不存在或格式不正确，会导致文档以混杂模式来呈现

#### title和alt

#### 超链接
- <a href="#">空连接</a>
- <a href="www.baidu.com">普通连接</a>
- <a hreg="1.zip">下载</a>
- <a href="email@163.com">邮箱连接</a>
- <a href="javascript:...">js功能</a>

#### 浏览器的内核
- Trident 
- Gecko	—— Moziall浏览器
- Webkit —— Safari浏览器
- Blink —— Chrome浏览器，opera浏览器

#### 行内元素、块级元素、空元素
- 行：a,b,span,img,strong,em,input,select
- 块：div,p,ul,li,ol,dl,dt,dd,h1~h6
- 空：link,meta,br,hr,input,img
	+ base、col、command、source、keygen、wbr

#### link和@import
- link属于xhtml标签，@import是css提供的
- link会在网页加载时同时被加载，@import会在网页加载完毕后才开始加载
- link的权重高于@import
- @importIE5以上识别，link没有兼容性问题

#### xhtml和html
- HTML是一种基本的web网页设计语言，xhtml是一种基于XML的置标语言
- xhtml标签必须被正确嵌套
- xhtml标签必须小写
- xhtml标签必须关闭
- xhtml必须拥有根元素

##### h5有哪些新特性、移除了那些元素
- H5已经不是SGML的子集，主要是对图像、位置、存储、多任务等功能的增加。
	+ 画布canvas，video，audio，本地离线存储localStorage、sessionStorage
	+ 语义化更好的内容元素...
	+ 表单控件:calendar,date,time,email,url,search
	+ 一些新技术webworker,websockt,Geolocation
- 移除的元素
	+ 纯表现的元素：big,center,font,s,tt,u
	+ 对可用性产生负面影响的元素：frame,frameset,noframes

##### 如何区分HTML和HTML5

##### H5有哪些不同类型的存储，区别
- localStorage
	+ 持久化存储，数据不过期，关闭浏览器也不会丢失
- sessionStorage
	+ 同一个会话页面才能访问，会话结束随之销毁

##### H5提供的API
- Media api
- History api

##### H5新增的表单属性
- Datalist
- datatime
- output
- keygen
- date
- month
- week
- time
- number
- range
- email
- url

##### svg && canvas
- SVG可缩放矢量图形
	+ 不依赖分辨率
	+ 支持事件处理器
	+ 复杂度越高，渲染越慢
	+ 不适合游戏开发
- canvas 直接在html上进行图形操作
	+ 依赖分辨率
	+ 不支持事件处理器
	+ 文本渲染能力弱
	+ 能以 .png 或 .jpg 格式保存结果图像
	+ 适合图像密集型游戏

##### iframe缺点

*******
## CSS
##### 定位机制
- 浮动定位 	float
- 相对定位	relative
- 绝对定位	absolute
- 固定定位	fixed

##### 属性继承
- 文本相关的属性
	+ font
	+ font-family
	+ font-size
	+ font-style
	+ color
	+ line-height
	+ text-align
	+ word-spacing
	+ font-variant

- 列表相关属性
	+ list-style
	+ list-style-image
	+ list-style-position
	+ list-style- type

- 表格
	+ border-collapse
	+ table-layout

- 其他
	+ cursor
	+ visibility

#### css样式表的层叠性
- css使用层叠的原则来考虑继承、层叠次序和优先级等重要特征
- 继承
- 层叠
- 优先级
	+ 浏览器缺省
	+ 外部样式表
	+ 内部样式表
	+ 内联样式
	+ !important

#### cellpadding与cellspacing
#### display与visibility
#### table-layout
#### border-collapse
#### target属性
- _top ：顶层window
- _parent ：当前frame的父window中
- _blank ：新窗口中打开
- _self : 默认，在相同的框架中打开
- main、left、top是由Dreamwerver生成的主左上框架的框架默认名

#### 盒子模型
- IE盒子
	+ content部分包含了border和padding
- 标准W3C盒子模型
	+ 内容（content）、填充（padding）、边框（border）、边界（margin）

#### css reset
#### css sprites
#### 清除浮动
- clear:both
- overflow:auto
	+ `zoom:1` 兼容IE   
- after伪元素

#### css选择器
- id选择器
- 类选择器
- 标签选择器
- 相邻选择器
- 子选择器
- 后代选择器
- 通配符选择器
- 属性选择器 a[rel="external"]
- 伪类选择器 a:hover,li:nth-child

#### css3新增伪类
- p:first-of-type
- p:last-of-type
- p:only-of-type
- p:only-child
- p:nth-child(2)
- :enabled  :disabled 控制表单控件的禁用状态
- :checked 单选框或复选框被选中。

#### display的值
- block
- none
- inline-block
- list-item
- table

#### position的值
- absolute
- relative
- fixed
- static
- inherit

#### css3新特性
- 圆角
- 阴影
- 线性渐变
- 选择器
- rgba

#### BFC规范
#### 媒体查询
- 根据媒体特性执行不同的CSS文件
`<link media="screen and (min-width:768px)and(max-width:"991px)" rel="" href=""/>`
- 在某段css样式声明中，只针对部分样式使用媒体查询
`@media screen and (min-width:768px)and(max-width:991px){}`

#### css预处理器
#### 手写动画最小时间间隔 `1/60*1000ms`，多数显示器的频率是60Hz
#### display:inline-block显示间隙
- 移除空格
- margin负值
- font-size:0
- letter-spacing
- word-spacing

#### a连接hover样式问题
- 点击过后样式不在具有hover和active
- L-V-H-A
	+ link
	+ visited
	+ hover
	+ active


****

## JavaScipt
#### this
- 函数执行
- 对象调用
- call/apply
- new 
- 箭头函数
- bind

#### 冒泡排序
#### 创建对象
- new Object()
- Object.create();
- 构造函数和原型
- 工厂

#### 创建函数
#### 全局函数
- parseInt
- parseFloat
- isNaN
- eval
- encodeURI
- decodeURI

#### 数据类型
- 原始类型5
- 引用类型
- typeof
- toString.call
- instanceof
- constructor

#### 阻止表单提交
#### string.match和RegExp.exec
- exec
	+ 可以获取源字符串
	+ 匹配字符在源字符串的索引

#### trim
#### js中操作cookie
- `document.cookie`

#### innerHTML、outerHTML、innerText、textContent
- innerHTML是W3C的，不包含标签
- outerHTML是元素节点内所有子节点和当前节点组成的HTML代码，包含标签
- textContent和innerText是IE独有的
- textContent属性读取或设置指定节点的文本内容，所包含的所有子节点的文本内容组合 **w3c**
- innerText是元素节点内所有的文本节点
- nodeValue通过属性的方式读取或设置指定节点的文本内容，只适用于文本类型的节点

#### array中添加数据的方法 4
#### js内置对象
- Math
- Global 浏览器环境中Global就是window

#### js本地对象
- Object、Function、Array、String、Boolean
- RangeError、ReferenceError、SyntaxError、TypeError、URIError

#### Ajax
- 客户端向服务器端发送请求，而无需刷新页面的技术
- 包含的技术：HTML、css、JavaScript、XML和XMLHttpRequest
- XMLHttpRequest对象是Ajax的核心，是实现异步通信的根本
- XMLHttpRequest不是W3C的标准，但是被主流浏览器支持
- IE6中使用ActiveXObject("Microsoft.XMLHTTP")
- Ajax语法：创建对象，初始化，发送请求，回调函数
- 优点：
	+ 页面局部刷新，提高用户体验
	+ 异步与服务器通信，更加迅捷
	+ 减轻服务器的负担
	+ 基于标准，被广泛支持
- 缺点
	+ 不支持浏览器back按钮
	+ 安全问题
	+ 对搜索引擎的支持比较弱，SEO无法实现

#### Ajax乱码
- 统一页面和服务器的编码
- 对请求和响应的 Content-Type 设置正确编码
- 对请求参数进行编码处理

#### Ajax如何解析JSON数据
#### get和post请求的区别

#### JSON
- 一种轻量级的数据交换格式
- 功能类似XML
- 语法和js中对象字面量形式非常相近
- 在前端领域代替XML

#### 如何从服务器获取复杂数据
- json
- xml

#### javascipt同源策略
- 一段js代码只能读取来自同一来源的窗口和文档的属性
- 来源：主机名、协议和端口号的组合

#### 跨域
- js中支持跨域的标签
	+ img
	+ iframe
	+ link
	+ script

#### 为什么要用jQ
- 浏览器兼容
- DOM
- 事件注册
- Ajax数据解析

#### jQ中注册事件
- bind 
- on
- delegate
- live

#### 获取HTML内容，属性值，input，创建新节点
- html()
- text()
- attr()
- val()
- jQuery()
***
- append()
- addClass()
- css()
***
- position()
- offset()
***
- hover
- bind
- unbind
*** 
- extend()

#### onload()和 $(document).ready()的区别
- document.onload是在结构和样式加载完才执行js
- $().ready()可以多次使用
- $().ready()在页面DOM元素加载完成后被调用
- onload在所有关联资源（图像、音视频）加载完后才被调用

#### jQ选择器
- 基本选择器
- 层次选择器/路劲选择器
- 过滤选择器

#### ajax、get、post、ajaxSetup、getJSON
#### jQuery绑定事件
- bind()
- on()
- delegate()
- live()

#### 网页与服务器的即时通信
- websockets

#### DOM获取元素属性值
- element.getAttributes[index].value
- element.getAttributes["属性名"].value
- emenent.getAttributeNode("属性名").value
- element.getAttribute("属性名")

#### DOM查找元素
#### 判断数据类型
- typeof
- toString.call
- instanceof
- constructor


#### 添加 删除 替换 插入节点的方法
- obj.appendChild()
- obj.innersetBefore
- obj.replaceChild
- obj.removeChild

#### js本地对象，内置对象，宿主对象
- 内置对象2
- 本地对象15
- 宿主对象
	+ 所有的BOM和DOM对象都是宿主对象

#### eval
- 将字符串解析成js代码执行
- 不安全
- 非常耗性能，解析一次，执行一次

#### null,undefined
- null是一个空对象，`type of` 返回`object`
- undefined:全局对象的一个特殊属性，值是未定义

#### IE和DOM事件流的区别
- 执行顺序不一样
- 参数不一样
- 事件加不加on
- this指向问题

#### IE和火狐的事件机制
- IE是事件冒泡
- 火狐是事件捕获

#### 事件委托
- 利用事件冒泡的原理，自己所触发的事件，让他的父元素代替执行

#### IE和标准的兼容性写法
- `var ev = ev || window.event` 
- `var target = ev.srcElement , ev.target ` 
- `document.documentElement.clientWidth , document.body.clientWidth`

#### node.js
- 高并发
- 聊天
- 实时消息推送
- 基于事件驱动和无阻塞

#### Node的优点和缺点
- 基于事件驱动和无阻赛，适合处理高并发的请求
- 不稳定

#### map
#### hasOwnProperty，执行对象查找时，永远不会去查找原型
#### js延迟加载的方式
- defer 只支持IE
- asunc
- 动态创建DOM，加载完后callback

#### 跨域
- jsonp
- iframe
- window.name
- window.postMessage
- 服务器上设置代理页面

#### AMD和CMD
- AMD是RequireJS在推广过程中对模块定义的规范化产出；CMD是SeaJS在推广过程中对模块定义的规范化产出。
- 对于依赖的模块，AMD是提前执行的，CMD是延迟执行。
- ReuireJs从2.0开始，也改成了延迟执行
- AMD推崇依赖前置，CMD推崇依赖就近
- AMD的API默认是一个当多个用，CMD的API严格区分，职责单一

#### call和apply
#### web worker
- 异步执行js文件
- 不能修改HTML元素，可以自由使用js数据类型
- var worker=new Worker(.js)
- worker.terminate() 终止webworker

#### 内存泄露
- setTimeout第一个参数是字符串时
- 闭包
- 控制台日志
- 递归

#### 页面跳转和刷新
- a
- 表单提交
- location.href="url"
- location.assign("url")
- location.replace()
- location.reload()
- window.open("url")
- history.go()

#### http状态码
- 200 成功
- 303
- 400 请求接受，但处理未完成
- 404 资源不存在
- 500 服务器错误

*****

## 兼容
#### IE和FF
- window.event
- 获取事件源
	+ srcElement IE 
	+ target FF
- 添加，去除事件
	+ IE
		* element.attachEvent("onclick",function)
		* element.detachEvent("onclick",function)
	+ FF
		* element.addEventListener("click",function,true)
		* element.removeEventListener("clcik",function,true)
- 阻止默认事件
	+ `preventDefault()` W3C
	+ `window.event.returnValue = false` IE
- 获取标签的自定义属性
	+ IE
		* div.value
		* div["value"]
	+ FF
		*	div.getAttribute("value")
- document.getElementByName()和document.all[name]
	+ IE 都不可以
	+ FF可以
- input.type属性
	+ IE input.type 只读
	+ FF input.type 可读写
- innerText、outerHTML、textContent
- id代替HTML元素
	+ IE 可以
	+ FF 不可以

#### 浏览器兼容
- 浏览器的类型和版本不同会造成CSS效果不尽相同
- 对于低版本的IE可以编写特定前缀的代码，实现版本识别
```
.bb{
	background-color:#e4393c;/*所有识别*/
	.background-color:#e4393c;/*IE6.7.8*/
	+background-color:#e4393c;/*IE6.7*/
	_background-color:#e4393c;/*IE6*/
}
```
- css reset
- IE低版本不识别auto，父元素加text-align
- 外边距溢出
- 外边距合并
- 条件注释（缺点增加额外的请求）

#### 常见兼容
- IE6双倍边距 （横向margin） _display
- 超链接点击失效
- z-index 
- IE6 png24  做成png8
- min-height
- 常规属性获取方法和getAttribute()
- even对象的
	+ IE:x，y
	+ FF:pageX，pageY
- chrome中文小于12px默认强制12px，-webkit-text-size-adjust:none;

#### 如何处理h5新标签和浏览器之间的兼容性
#### 火狐浏览器无法撑开固定高度容器
- `div{ height:auto !important; height:200px; min-height:200px}`
#### [常见的兼容性]( http://www.cnblogs.com/lgmcolin/archive/2013/02/12/2910179.html)

## 优化
#### 从输入URL到页面呈现
- 输入URL地址或者点击URL的连接
- 浏览器根据URL地址，结合DNS，解析出RUL对应的IP地址
- 发送HTTP请求
- 开始连接请求的服务器并且请求相关的内容
- 浏览器解析从服务器端返回的内容，并且把页面呈现出来

#### 前端优化
- 减少HTTP请求
	+ 合并文件
	+ css精灵
- 使用浏览器缓存
	+ \*
- 使用压缩组件
- 图片、JS的预载入
	+ 可以在登录页面做预载入
- 将脚本放在底部
- 将样式文件放在顶部
- 使用外部的JS和css
- 切分组件到多个域
	+ 提高并行下载能力
	+ 但不要跨太多域名，建议采用2个子域名
- 精简JS和css
- 精简图片和Flash

#### 程序优化
#### 数据库优化

#### jQ优化
- 用id选择器替代class选择器
- 缓存DOM操作，或使用jquery链式调用

#### js优化
- for循环中，提前保存arr.length
- 使用DocuementFragment优化多次appendChild
- 使用模板元素clone，替代createElement
- 使用firstChild和nextSibling替代childNodes遍历dom元素
- 使用三目替代条件分支
- 使用重复执行时，优先使用setInterval



