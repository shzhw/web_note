#### 组件
#### 组件嵌套
#### 组件状态 state
- getInitialState
- .forceUpdate()
- .setState(obj)

#### 组件参数 props
- getDefaultProps
- propTypes

```
propTypes:{
	messages:React.Proptypes.array.isRequired,
},
getDefaultProps:function(){
	return {
		messages:["默认的子消息"]
	}
},
render:function(){
	...
}
```
#### 事件 event
- e.target

#### 指向 ref

#### 双向数据流
- React.addons.LinkedStateMixin
- valueLink={this.linkState("message")}
```
var EasyForm=React.createClass({
		mixins:[React.addons.LinkedStateMixin],
		getInitialState:function(){
			return {
				message:"react is awesone!",
				isReactAwesons:true
			}
		},
		render:function(){

			return (
				<div>
					<h1>我想说：{this.state.message}</h1>
					<h2>React是不是很好用？{this.state.isReactAwesons?"非常好用":"一般。。"}</h2>
					<input type="text" valueLink={this.linkState("message")}/>
					<input type="checkbox" checkedLink={this.linkState("isReactAwesons");}/>
				</div>
			)
		}
	});
```

#### 组件的生命周期
- getDefaultProps  *
- componentWillMount
- componentDidMount
- componentWillReceiveProps
- componentDidReceiveProps
- shouldComponentUpdate
- componentWillUpdate
- componentDidUpdate
- componentWillUnmount
- componentDidUnmount


#### Mixins



************


