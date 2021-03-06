## AngularJS
- 优秀的前端高级js框架

- 由Misko Hevery等人创建
- 09年Google收购
- 轻松构建SPA（单一页面应用程序）
  + 单一页面应用程序
    * 只有一个页面（整个应用的一个载体）  
    * 内容全部是由Ajax方式呈现的

## 为什么使用AngularJS 
- 带领当前市面上的框架走向模式化或者架构化
- ng最大程度的减少了页面上的DOM操作，还原了JS的本质
- 业务逻辑更

## AngularJS四个特性
- MVC
- 模块化
- 自动化双向数据绑定
- 指令系统

## MVC
- 一种开发思想，一种手段，不是设计模式
  + 切分职责
  + 复用
  + 后期维护方便
  + 最终目的：模块化和复用
- 前端MVC的困难
  + DOM操作必须等待页面加载完毕
  + 文件之间的依赖
  + 原型继承
- 将应用程序的组成划分为三个部分：Model    View   Controller
  + Model 处理数据        
    * 数据库中所有用户的信息
    * 接收控制器传来的用户名和密码进行校验的业务逻辑并返回true/false 
  + Controller                     
    * 接收用户在界面上填写的用户信息    
    * 将用户名和密码交给模型
  + View
    * 给用户呈现一个表单
    * 接受用户输入内容，并将其提交给控制器
    * 根据控制器返回的数据，响应用户页面
- 登录案例

## 模块（Module）
- 集合
- 划分应用程序结构
- 我们可以通过angular.module创建一个模块
- angular.module方法传递俩个参数是创建，一个参数是获取
- 注册模块 通过module函数  angular.module（“”，[ ]）
  +  第一个参数是这个模块的名字
  +！！！第二个参数是这个模块所依赖的模块
  + 如果不依赖任何模块也必须传递第二个参数，如果没有传递第二个参数angular.module就不是创建一个模块
  + angular.module 返回 刚刚创建的模块对象

##控制器
- 控制器是必须出现在某个模块下的，想创建一个控制器先创建模块
- app.controller方法用于创建一个控制器
- ng在执行控制器函数时，会根据参数的名字（\$scope，\$http...）去自动注入
  + $watch只能监视$scope的内容
- 用途
  + 暴露数据
  + 暴露行为
  + 监视数据变化
- 如果控制器中需要用到一个不存在的对象，都尝试使用注入的方式
- 不要再controller中操作DOM
- 不在controller中做数据格式化和数据过滤
- Controller之间不互相调用，他们之间的交互通过事件来进行

## 表达式

## 指令
> 官方文档 - directive

- Angular中最重要的概念是指令（directive）
- ng-model 是双向数据绑定的指令，效果就是将当前元素的value属性和模型中的user.name建立绑定关系
- 表达式{{user.name}}是单向数据绑定
- ng 基本不用操作DOM，如果必要，可以使用ng提供的jqlite

##### 常用内置指令（63）
- ng-app    
  + 一个页面使用一个（推荐）

  + 创建多个ng-app时默认只能执行第一个，后面的需要手动引导：angular.bootstrap()

```
  var myApp1=angular.module('myApp1', []);
  myApp1.controller("app1Controller",["$scope",function($scope){
    $scope.do1=function(){
      console.log(1);
    }
  }]);


var myApp2=angular.module('myApp2', []);
myApp2.controller("app2Ctrl",["$scope",function($scope){
  $scope.do2=function(){
    console.log(2);
  }
}]);

// 方式一
//angular.bootstrap(document.querySelector('[ng-app="myApp2"]'),['myApp2'])

//方式二
angular.module("myApp",["myApp1","myApp2"])

```

- ng-bind   
    + 在绑定的值包含HTML时会自动转义  —— *原因*——  为了安全（跨站脚本攻击）


- ng-bind-html    
  + angular-sanitize  引入脚本文件
  + angular.module("myApp"  ,["ngSanitize"]);
    * 使用自定义的模块才可以依赖别的包里面定义的模块，angular定义的默认模块没有依赖任何模块
    * 尽可能不在页面中绑定HTML （跨站脚本攻击）

- ng-repeat
    + 遍历一个数组重复创建当前元素
    + track by  跟随一个不重复的值
      * ng-repeat = " name in students track by $index"
- ng-class
    + ng-class = " { red : $even , green : $odd } "      
    + 根据当前设置对象的属性和属性值决定是否添加特定类名
- ng-cloak  
    + ng执行完该属性会被删除
- ng-show
    + 决定一个元素是否显示
- ng-hide
- ng-if
    + 决定一个元素是否存在
- ng-href
- ng-src
- ng- switch

```
<div ng-switch="myVar">
  <div ng-switch-when="wedn">...</div>
  <div ng-switch-when="google">...</div>
  <div ng-switch-when="baidu">...</div>
  <div ng-switch-default>...</div>
</div>

```
- ng-checked   单选/复选    不会双向绑定      有时可以用ng-model替代   
- ng-delected    选中       不会双向绑定      有时 可以用ng-model替代 
- ng-disabled    禁用
- ng-readonly    只读
- ng-blur
- ng-change
- ng-copy
- ng-click
- ng-dblclick
- ng-focus
- ng-submit

##### 自定义指令    customDirective
- 封装一些常用的而且公用的东西
    + ng任然还有一些DOM操作的可能，所有的DOM操作都应该集中在自定义指令中
- 指令的名字，应该使用驼峰命名法，使用的时候用 “ - ”
- ng-transclude    转置
- scope的绑定策略
  + `@` 将当前属性作为字符串传递
  + `=` 与父scope的属性进行双向绑定
  + `&` 传递一个来自父scope的函数

```
  ... 
app.directive("btn",[function(){
  return {
    scope:{
      primary:"@",
      lg:"@",
      block:"@",
      value:"@"
    },
    transclude:true,
    replace:true,
    template:'<button class="{{primary==\'true\'?\'btn-primary\':\'\'}}" ng-transclude></button>'
    //templateUrl: 'breadcrumb.html',
  }

}])
```

## 依赖注入
## 过滤器
- 数据筛选
- 数据格式化
  + 引用angular语言包可以显示中文格式  angular-locale_zh-hans.js
- 过滤器-自定义比较
  + 默认的$filter是模糊匹配
```
  angular.module("app",[])
  .filter("filterName",function(){
    return function(input,style){
      //过滤器需要实现的功能代码
        ...
      }
    }
  })

```

## $scope
- 指向应用model的object，是表达式的执行上下文，类似DOM结构层次
#### $apply 触发脏检查，并更新view
#### $watch 
- $watch(watchVar,func(now,old){}[,deepWatch])
  + watchVar：监听变量
  + func：变化后执行函数
  + deepWatch：检查被监控的**对象**的每个属性时候发生变化


## angular-loader
- 就是在使用一些异步加载脚本的库的时候，自动控制依赖顺序

## 路由
- Ajax不会留下History

#### 传统路由
- 分发诉求  核心——路由表

#### 前端路由
- 哈希# —— 页内导航
- H5中新的history API
- 路由的核心是给应用定义“状态”
- 使用路由机制会影响到应用的整体编码方式（需要预先定义好状态）
- 优雅降级

##### ng-route
- ng中路由是单独提供的功能模块ngRoute，也是一个单独发型的文件
- 安装或者下载angular-route的包
  + npm install angular-route --save
- 引入
- 添加ngRoute依赖
- 配置路由规则
  + 就是指：什么样的请求，找什么样的控制器

```
  myApp.config(['$routeProvider',function($routeProvider) {
    $routeProvider
     .when("/:status?",{
      templateUrl:"main_tmpl",
      controller:"MainController"
    })
    .otherwise({
      redirectTo:"main_tmpl"
      })
  }])
```

- `:` 表示这是一个占位符
- `？`表示这位可以省略
- $routeParams
- $route
  + updateParams()

> **$location**

- constant 定义一些永恒不变的量
  + 直接在controller中注入
  + 公共模块中定义的控制器和指令在子模块中是得不到的，但constant是可以得到的

```
.constant("name",{
  pageSize:10,
  listApiAddress:"http://...",
  detailApiAddress:"http://..."
  ...
})
```

### angular-ui.github.io

## 使用
- 下载AngularJS的包
- 使用CDN上的ng
- 使用Bower安装
- 使用npm安装 

## 本地运行NG文档
- http-server  npm包里
  + 命令行   hs -o

















