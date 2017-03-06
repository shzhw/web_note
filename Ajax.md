## 计算机运行机制
## 通信协议
## Aajax
#### 详解
- Ajax asyncchronous javascript and XML

#### 原生ajax

#### 语法
- 定义对象 XMLHttpRequest
	+ IE中是 ActiveXObject("Microsoft.XMLHTTP")
- 初始化 open
	+ 第一个参数
		* `get` 参数写在连接中

		```
		url="index.php?username="+encodeURIComponet(username)+"&password="+password
		```

		* `post` 参数在请求体中

	+ 第二个参数
		* 准备发送的目标地址

	+ 第三个参数
	 	* 同步函数异步

- 请求完成后回调函数
	+ onreadystatechange
	+ readyState 服务器响应http值
	+ status 请求状态

- 发送请求
	+ send

## 数据格式
#### XML
#### Json
- javascript object notation
- JSON.parse(xhr.responseText) 序列化

## jQuery中的Ajax



#### 调错
- 表单元素的默认事件
- localhost

## 动态网站




