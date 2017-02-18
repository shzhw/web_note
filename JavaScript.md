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
- constructor 判断实例的构造函数是谁
 + `console.log(arr.constructor === Array)`

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
- length
- indexOf
- lastIndexOf
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
- toUpperCase 大写
- toLowerCase	小写
- charAt
- charCodeAt
- subString 截取
- split 分割
- startWith
- forEach *IE中没有*

## 对象
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
- \w 字母或数字 ，等价于[a-zA-Z0-9]
- \W 非字母或非数字，等价于[^a-zA-Z0-9]
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

#### 正则API
- 支持正则的字符串API
	+ indexOf/lastIndexOf
	+ search
		* 不支持g，找到第一个停止
	+ match
		* 返回数组
	+ replace
	+ split
- RegExp.API
	+ exec
	+ test

#### replace进阶
- 分组匹配
- 函数作为参数，对匹配的字符串进行二次操作

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

## eval

## JSON
- `JSON.parse()` 反序列化
- `JSON.stringify()` 序列化

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

