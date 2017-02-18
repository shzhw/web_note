## Node
#### 客户端的Javascript是怎样的
- 什么是Javascript
	+ 脚本语言
	+ 运行在浏览器中
	+ 一般用来做客户端页面的交互（Interactive）
- Javascript的运行环境
	+ 运行在浏览器内核中的**JS引擎**
- 浏览器中的JavaScript可以做什么？
	+ 操作DOM（对DOM的增删改查）
	+ ajax/跨域
	+ BOM（页面跳转、历史记录、console.log、alert）
	+ ECMAScript
- 浏览器中的JavaScript不可以做什么？
	+ 文件操作（文件和文件夹的CRUD）
	+ 操作系统信息
		* 由于运行环境特殊(我们写的代码是在陌生人的浏览器中运行的)
- JavaScript只能运行在浏览器中吗？
	+ 不是
	+ 能运行在哪取决于，这个环境有没有特定的平台
- 在开发人员能力相同的情况下编程语言的能力取决于什么？
	+ 语言本身只是提供定义变量、定义函数、流程控制之类的操作
	+ **取决于运行该语言的平台（环境）**
		* Java既是语言也是平台，Java运行在Java虚拟机（Java虚拟机可以跨平台/操作系统）
		* C#语言运行在.NET framework平台，C#可以运行在别的平台 —— MONO平台
		* PHP既是语言也是平台
	+ 对于js来说，我们常说的js实际上是ES，大部分能力都是由浏览器的执行引擎决定的
	+ DOM和BOM可以说是浏览器开放出来的接口
	+ 比如：Cordova中提供JS调用摄像头，操作本地文件的API

##### *语言的能力一定是取决于平台的*
## Node简介
- js运行环境，在服务端工作
- Node.js是一个轻内核（本身没什么功能），所有的功能都需要功能包来提供
- node官方提供了一些最基础的包

## Node用途
##### 开发Web应用程序
- 做动态网站
- 开发提供数据的服务端API

##### 前端开发工具基础
- Node.js给前端乃至整个开发行业带来了一场工业革命
- 结束了刀耕火种

	<small>REPL环境（控制台环境）</small>

#### REPL环境
- Read Eval Print Loop
- `$ node`进入REPL环境
- `$ node --use_strict`启用严格模式
- `$ .exit`退出REPL
- `$ _`上一次执行的结果
- `node -e 'console.log(1);'`执行脚本字符串

#### 全局对象
- `global`类似于客户端JavaScript运行环境中的window
- `process`
	+ `process.argv`输入参数
	+ `process.env`输出系统环境变量
	+ `process.stdin`
	+ `process.stdout`
- `console`
- 调试
	+ `$ node debug test.js`
	+ VS Code
	+ 第三方模块提供的调试工具
		* `$ npm install node-inspector -g`
		* `$ npm install devtool -g`
- 事件
	+ sigint
		* process.exit()
ss
## 文件系统操作
#### fs

#### path
###### 在文件操作过程中，都“必须”使用物理路径（绝对路径）

#### readline
- 用于读取大文件，一行一行读

#### fs-extra()

## 事件驱动和非阻塞机制 
- 事件队列
- Node平台将一个任务连同该任务的回调函数放到一个事件循环系统中
- 事件循环高效的管理系统线程池同时高效执行每个任务
- 当任务执行完成过后自动执行回调函数
- 总结
	+ Node中将所有的阻塞操作交给了内部实现的线程池
	+ Node本身主线程主要就是不断的**往返调度**
- 不同平台之间的实现差异
- 非阻塞的优势
	+ 提高代码的响应效率
	+ 充分利用单核CPU的优势
	+ 改善I/O的不可预测带来的问题
	+ 提高一个人的工作效率

## 回调函数
- 回调函数一定作为最后一个参数出现

```
function func(name,age,callback){

}
```

- 回调函数的第一个参数默认接受错误信息，第二个参数才是真正的回调数据（便于外界获取调用的错误情况）

```
func("name",19,function(error,data){
	if(error) throw error;
	console.log(data);
});
```
> **错误优先**
> 因为之后的操作大多数都是异步的方式，无法通过`try catch`捕获异常，so
> 错误优先的回调函数 - 第一个参数为上一步得到的错误信息优先

## node常用内置模块清单
- `path`：处理文件路径
- `fs`：操作（crud）文件系统
- `child_process`：新建子进程
- `util`：提供一系列实用小工具
- `http`：提供http服务器功能
- `url`：用于解析URL
- `querystring`：解析URL中的查询字符串
- `crypto`：提供加密和解密功能

>[nodejs文档](https://nodejs.org/api)

## 进程和线程
- 多线程 —— CPU制约
	+ 线程之间共享某些数据，同步某个状态都很麻烦
	+ 更致命的
		* 创建线程耗费
		* 线程数量有限
		* CPU 在不同线程之间转换，有上下文的转换，这个转换非常耗时间
- 单线程
	+ v8引擎是单线程的

#### require
- 缓存
	+ require.cache
- 删除缓存
```
	object.keys(require.cache).forEach((key)=>{
		delete require.cache[key];
	})
```

	+  一般不删除缓存，可以使用暴露行为的方式来达到同样的功能

	```
		module.exports=()=>{
			console.log("data module exec");
			return new Date();
		}
	```
- 自己实现缓存机制

---

## 模块化开发
- 为什么
  + 协同
    * 技术手段  less sass 
    * 约定
  + 代码复用
  + 解决问题 —— 可以解决痛点的东西才是好东西
    * http://github.com/seajs/seajs/issues/547
    * 大量的文件引入
    * 命名冲突
    * 文件依赖
- 如何实现模块化开发
  + 全局函数
  + 封装对象
  + 私有空间的划分
  + 模块化的扩展和维护
  + 第三方依赖管理
- 高内聚低耦合原则 —— 模块内部相关性强，模块之间没有过多相互牵连
- 开闭原则 —— 对新增开放，对修改关闭
- 使用
-规范
  + Commonjs
    * 服务器端js模块化编码规范
    * require
    * exports
  + AMD
    * 异步模块定义
  + CMD
    * 通用模块定义
    * seajs
- seajs使用
  + 使用步骤
    * 在页面中引入sea.js文件
    * 定义一个主模块文件，比如：main.js
    * 在主模块文件中通过define的方式定义一个模块，并导出公共成员
    * 在页面的行内脚本中通过seajs.use("path",fn)的方式使用模块，这种方式一般用于入口模块，一般只出现一次；模块与模块之间的一般用require
    * 回调函数的参数传过来的就是模块中导出的成员对象
  + 在seajs中模块的引入需要相对路径的完整写法，或者绝对路径

#### 模块的定义
- 一个新的js文件就是一个模块
- 一个合格的模块应该是有导出成员的，否则模块就失去了定义的价值
- 模块内部是一个独立（封闭）的作用域（模块与模块之间不会冲突）
- 模块之间必须通过导出或导入的方式协同
- 导出方式
  + exports.name = value
  + module.exports = {name:value}

#### 包
- 与核心模块类似，就是将一些预先设计好的功能（API）封装到一个文件夹，提供给开发者使用
- 包名
  + 先在系统核心（优先级最高）的模块中找
  + 然后再在当前项目中的node_modules中
- NPM 

#### 模块化开发流程
- 创建模块 ` new calc.js `
- 导出成员 ` module.exports={} `
- 载入模块 ` var calc=require("./calc.js") `
- 使用模块 ` calc.add(1,2) `

#### 模块中的全局成员
- `_ _dirname` 当前脚本所在路径
- `_ _filename` 文件路径
- module
```
if(module.parent){
  //当前文件被别的文件加载
}else{
  //入口文件
}
```

- exports
  + 映射到`module.exports`中的别名
- require
- 每个模块的内部都是一个私有空间



