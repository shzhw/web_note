## javascript
#### 运行环境
- js解析器

#### 构成
- ECMAScript
- DOM
- BOM

#### 特点
- 弱类型语言
- 无需编译

#### 语法
- 严格区分大小写

## 变量
#### 命名规范
- 字母、数字、下划线
- 不能以数字开头

## 运算符
#### 数学运算符
- `+，-，*，/ , % ,++ , --`

#### 关系运算符
- `> 	< 	<=	>=	!= ==	===	!==`
- `!==` 全不等

#### 逻辑运算符
- `|| && ！`
- 短路逻辑

#### 位运算符
- >>    <<
	+ 左移：m<<n 将m的二进制数左移n位，相当于*2的n次方
	+ 右移：m>>n 将m的二进制数右移n位，相当于/2的n次方
- ~ 取反

#### 扩展运算符
- `+=  -=  /=  *=  %=`

## 常量 const
## 数据类型
#### 数据类型
1. 原始类型/值类型
	- string , number , boolean , undefined , null
2. 引用类型
	- object , function , array

#### 数据类型转换
1. 隐式转换
2. 显示转换
	- 转换函数
		+ toString() 将任何数据类型的数据转换成字符串,不能转null或undefined
		+ parseInt() 整数部分
		+ parseFloat() 
		+ String() 万能的
		+ Number()   非数字 ==> NaN
		+ Boolean()
			* `0，NaN,undefined,“”,null----------->false`

#### 数据类型检查
- typeof 
	+ 不完美性   {}和[]
- toString.call() *
- instanceof
- constructor 判断原型对象的构造函数是谁
 	+ `Array.prototype.constructor === Array`
 	+ `arr.constructor === Array`

## 分支和循环
#### 分支结构
1. if...else
3. switch `case...default`

#### 循环结构
1. while
2. do..while
3. for
4. for..in

## 数组
#### 一维数组
- 索引数组
- 关联数组
- 数组定义
	+ `var arr=[]`
	+ `var arr=[1,2,3]`
	+ `var arr=new Array()`
	+ `var arr=new Array(3)`
	+ `var arr=new Array(1,2,3)`

#### 二维数组

## API
#### 数组API
- length
- indexOf
- lastIndexOf 不支持正则
- toString()
- join 
	+ `arr.join("连接符")`		
- concat
- slice 截取
- splice 替换
- sort
- reverse 倒置数组
- push
- pop
- shift
- unshift
- forEach *IE中没有*
- map 映射
	+ 功能和forEach类似 
	+ array.map(callback,[thisObject]);
	+ callback需要有return值
```
IE6,7,8支持需要扩展
if (typeof Array.prototype.map != "function") {
  Array.prototype.map = function (fn, context) {
    var arr = [];
    if (typeof fn === "function") {
      for (var k = 0, length = this.length; k < length; k++) {      
         arr.push(fn.call(context, this[k], k, this));
      }
    }
    return arr;
  };
}
```

#### 字符串API
- length
- indexOf
	+ 返回索引
- lastIndexOf 
- search
	+ 返回索引
- match
	+ 返回数组
- replace
- concat
- slice 截取
- toUpperCase 大写
- toLowerCase	小写
- charAt
- charCodeAt
- subString 截取
- startsWith
- split 分割 String.split

#### 正则API
- 支持正则的字符串API
	+ search
		* 不支持g，找到第一个停止
		* 没有返回-1
	+ match
		* 区别于exec，一次返回所有匹配
	+ replace
	+ split
		* 支持模式匹配
- RegExp.API
	+ exec 返回数组
		* 和test执行模式一样
	+ test 判断是否存在
		* `regExpObject.test(str)`
		* 返回Boolean
		* 设置了全局标志 `g` ，最多也只查找一个匹配，需要再次调用才能继续往下查找
		* 原因：
			1. test()函数是从属性 `regExpObject.lastIndex` 所指定的索引开始查找
			2. 找到第一个时，`regExpObject.lastIndex` 的值将成为本次匹配内容的最后一个字符的下一个索引位值
			3. 如果执行一次过后需要再次**从头查找**,需要手动将`regExpObject.lastIndex`重置为零

#### replace进阶
- 分组匹配
- 函数作为参数，对匹配的字符串进行二次操作
#### call和apply

## 函数
#### 概念
- 完成一定功能的一段预定义好的代码
- 工具
- 单一职责原则
- 工具

## 对象
#### 概念
- 属性和方法的集合体
- 把类似功能的函数放在一起管理
- 工具包
- 万物皆对象
- 双对象原则

#### 创建对象
- `new Object()`
- `Object.create()`
- 构造和原型混合模式
- 工厂模式
	+ 一种解决问题的方式
	+ 不需要 new
	+　产出物——实例
	+ 好处：不需要考虑实例化的问题，
- 混合方式
- 字面量形式
- 拷贝模式
- 第三方框架

#### 栈和堆
- 内存的声明周期
	+ 内存分配
	+ 内存使用
	+ 内存回收
		* 栈：函数执行完自动回收
		* 堆：引用计数
- 内存泄露

## 正则
#### 正则语法
- ^ 开始
- $ 结束
- \b 单词边界
- \B 和\b相反，非单词边界
	+ `/er\b/` 能匹配 `"verb"` 中的er，但是不能匹配`"never"`中的er
---
- \d 数字，[0-9]
- \D 非数字，[^0-9]
- \s 空格
- \S 非空格 
- \w 字母或数字下划线 ，等价于[a-zA-Z0-9_]
- \W 非字母或非数字非下划线，等价于[^a-zA-Z0-9_]
---
- g 全局匹配
- i 不区分大小写
---
- ? 0~1
- \* 0~多
- \+ 1~多
- {n,m} n~m
- {n,} n~多
- {,m} 0~m
- {n} n
---
- [] 集合
	+ `[a-zA-Z]`
- () 分组
- `.` 除换行

#### 模式
- 贪婪模式 
	+ `.*` `.+`
- 懒惰模式
	+ `.*?` 

#### 预判
- `?!`
- `?=`

## DOM
#### 节点树
- 节点对象的类型
	+ 根节点：文档类型document
	+ 元素节点：元素类型
	+ 文本节点：
	+ 属性节点：
	+ 注释：
- 所有节点对象的父对象：Node（所有的节点对象继承至Node.prototype）
	+ node.nodeType
	+ node.nodeName
	+ node.nodeValue

#### 查找元素
- 按HTML属性找
	+ document.getElementById()
	+ document.getElementsByTagName()
	+ document.getElementsByClassName()
	+ document.getElementsByName()
	+ parent.querySelector()
	+ parent.querySelectorAll()
- 按节点间的关系
	+ 父子关系
		* node.parentNode
		* node.childNodes
		* node.firstChild
		* node.lastChild
		* node.Children
	+ 兄弟关系
		* previousSibling
		* nextSibling
	> 除了`parentNode`,都会受到看不见的空格、换行等制表符的影响
- 元素树（IE9+）
	+ 父子关系
		* node.parentElementNode
		* node.children
		* node.firstElementChild
		* node.lastElementChild
	+ 兄弟关系
		* node.previousSibling
		* node.nextSibling

#### 读取和修改节点对象
- 元素内容
	+ HTML内容
		* innerHTML
		* outerHTML
	+ 文本内容
		* textContent *IE8不兼容*
		* innerText
- 元素属性
	+ attributes[i]
	+ attributes["属性名"]
	+ getAttribute("属性名")
	+ setAttribute("属性名","值")
	+ getAttributeNode(属性节点对象)
	+ setAttributeNode(属性节点对象).value
	+ hasAttribute("属性名")
	+ removeAttribute("属性名")
- 修改样式
	+ node.style.属性=值
	+ node.style.cssText=""
- 获取元素最终应用所有样式
	+ getComputedStyle(node)
- 修改样式表中的样式
- node.dataset.属性名

#### 创建和删除节点
- document.createElement("标签名")
- parent.appendChild(node)
- parent.inserBefore(node,oldNode)
	* 插入oldNode之前
- parent.replaceChild(node,oldNode)
- parent.removeChild(node);
- 文档片段

#### 遍历 DOM
- Nodeiterator
	+ 创建遍历器
	+ 使用循环推动遍历器到每个节点
		```
		var iterator = document.createNodeiterator{
			开始节点对象,
			[NodeFilter.SHOW_ALL],
			[NoderFilter.SHOW_ELEMENT],
			null,
			false
		}
		```

- TreeWalker

## JSON
- `JSON.parse()` 反序列化
- `JSON.stringify()` 序列化

## 事件对象
#### event
- `var btn.onclick=function(event){}`
- event就是事件对象，这里指向onclick
- 包含了事件的所有信息
- 兼容
	+ `var event = event || window.event`
- clientX、pageX、screenX
	+ screen 电脑屏幕为基准点
	+ pageX 文档为基准点 （IE6,7,8不兼容） 
	+ clientX 当前窗口（可视区）

## 事件流
#### 事件冒泡
- 当一个元素事件被触发，同样的事件将会在那个元素的所有祖先元素中被依次触发
- 这个事件会一直冒泡到DOM树最上层
- blur、focus、load、unload
- IE 5.5: `div -> body -> document`
- IE 6.0: `div -> body -> html -> document`

#### 事件捕获
- 事件捕获是一个和事件冒泡完全相反的过程，即事件由祖先元素（最不精确）向子元素（最精确）传播
- `document -> div`

#### DOM事件流
- 同时支持捕获和冒泡，捕获先发生
- 两种事件流会触及DOM中的所有对象，从document对象开始，也在document对象结束，文本节点也触发（IE中不会）
- W3C DOM: `window -> document -> body -> div -> (text)` `-> div -> body -> document -> window`
- IE: `window -> document -> body -> div` `-> body -> document -> window`

#### 绑定事件
- 程序猿可以选择绑定事件采用捕获还是冒泡
	+ `ele.addEventListener("click",function,true)`
	+ 第三个参数 ：`true`为捕获 —— `false`为冒泡
- 传统的绑定事件方式
	+ 在一个支持W3C DOM的浏览器中，像这样一般的绑定事件方式，是采用的事件冒泡方式。
		* `ele.onclick=function`
- IE只支持事件冒泡，不支持事件捕获，它也不支持addEventListener函数，不会用第三个参数来表示是冒泡还是捕获，它提供了另一个函数attachEvent。
	+ `ele.attachEvent("onclick", doSomething2)`

#### 阻止事件传播
- 阻止冒泡
	+ `event.stopPropagation()` W3C
	+ `event.cancelBubble = true` IE

#### 阻止事件默认行为
- `preventDefault()` W3C
- `window.event.returnValue = false` IE

## BOM
#### Window
- IE9+
	+ window.innerWidth
- 标准模式
	+ document.documentElement.clientWidth
- 怪异模式
	+ document.body.clientWidth
- window.screen.width 电脑分辨率，和浏览器没关系
#### Location
#### History
#### screen
#### Navigator


## window.onload VS $
- onload
	+ 页面全部加载完才开始执行，包括图片
- $
	+ 忽略图片

## 判断IE和标准浏览器  window.ActiveXObject
- node.text
- node.textContent

## 开发补充
##### 所有的文件操作都必须是绝对路径（物理路径）
##### config对象
##### 后台返回的标志位
##### 动画原理
- 步长
- offsetLeft+步长

## javascript进阶
#### 函数和变量
- 变量声明**早于**代码运行（声明提前）
- 函数声明**高于**变量声明
- 给基本类型数据添加属性，不报错，但值为undefined

#### 自执行函数
#### this
- 函数的四种调用模式
	+ 函数执行模式
		* `this` ---> global，浏览器中指向window
	+ 对象方法的调用模式
		* `this` ---> 调用方法的对象
	+ 构造器的调用模式（没有return）
	 	* `this` --->  构造出来实例的对象
	+ call和apply调用模式
		* call 借用时将被借用者的this指向借用者
- this指向
	+ global
	+ 调用对象
	+ call、apply
	+ bind
	+ new
	+ 箭头函数

#### new
- 在内存中开一块空间
- 创建一个新空对象
- 把 this 指向这个新对象
- 把空对象的__proto__指向构造函数的原型对象
- 当构造函数执行完成，没有return，那么将空对象返回
- 如果构造函数有return

#### eval

#### console.time();
- 测试一段程序的执行时间
	+ console.time("main")
	+ console.timeEnd("main");
