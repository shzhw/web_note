## let
##### let在for循环中的问题
```
for(let i=0;i<3;i++){
	let i="abc"
	console.log(i);
}
```
执行结果为

```
abc
abc
abc
```
循环外的i和内部的i是分离的
##### 不存在声明提前
##### 暂时性死区
- 只要已进入当前作用域，所要使用的变量就已经存在了，但是不可获取的
- 只有声明之后才能使用
- typeof 不安全性
##### 不允许重复声明
```
//报错
function(){
	let a = 10;
	var a = 1;
}
//报错
function(arg){
	let arg = 10;
}
//不报错
function(arg){
	{
		leg arg;
	}
}
```

## 块级作用域
##### 原因
- 内层变量覆盖外层变量
- 循环计数泄露

##### 替代了自执行函数（IIFE）
##### 块级作用域与函数声明 *?*
- ES5规定函数只能在全局作用域和函数作用域声明
- ES6在块级作用域内声明函数，类似于`let`

## do表达式
## const
##### 声明的同时，必须初始化
##### 作用域和`let`相同
##### 对于符合类型的变量，变量名指向的是**地址**，例如：对象
- 如果想将对象彻底冻结,使用`Object.freeze`

```
var constantize = (obj) => {
  Object.freeze(obj);
  Object.keys(obj).forEach( (key, value) => {
    if ( typeof obj[key] === 'object' ) {
      constantize( obj[key] );
    }
  });
};
```

## 顶层对象的属性










##### 箭头函数

```
var func = (parameter) => {
	
}
```

##### 模板字符串
```
	var msg="hello";
	console.log(`${msg} world`)
```

- 可以在``中随意的回车换行
- 可以直接取变量 `${name}`
- 类似于PHP的`“”`
