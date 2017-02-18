## canvas
#### 应用领域
- **可视化数据**
- **banner广告**
- 游戏
- 图形编辑器
- =>模拟器
- =>远程计算机控制
- **完整的canvas移动化应用**
#### canvas语法
###### 标签
- 用标签属性或js设置画布大小，不要用CSS设置
		* `canvas.width = 600; canvas.height = 600`
- 兼容性：IE9+
###### canvas上下文 `var ctx=canvas.getContext("2d")`
- `canvas`为html中的canvas标签对象
- `webgl` 3D参数
###### API
- 线
	+ `ctx.moveTo(x,y)`
	+ `ctx.lineTo(x,y)`
	+ `ctx.closePath()` 闭合
	+ `ctx.lineWidth = 4`
	+ `ctx.strokeStyle = "rgba(255,255,0,.8)"` 描边颜色
	+ `ctx.stroke()` 描边
	+ `ctx.fillStyle = "blue"`
	+ `ctx.fill()` 填充,默认黑色
-通用
	+ `ctx.beginPath()` 开启一个新状态
		* 绘制不同样式的形状前需要加
