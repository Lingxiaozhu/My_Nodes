1.jsx的简介
===

JSX，是一个 JavaScript 的语法扩展
例子：  
```js
    const element = <h1>Hello, world!</h1>;  
```
  
在 JSX 语法中，可以在大括号内放置任何有效的 JavaScript 表达式   
例子：  
```js
    const name = 'Josh Perez';  
    const element = <h1>Hello, {name}</h1>;  
```

JSX 特定属性:  
> 可以通过使用引号，来将属性值指定为字符串字面量
例子：  
```js
const element = <div tabIndex="0"></div>;
```
> 可以使用大括号，来在属性值中插入一个 JavaScript 表达式  
例子：  
```js
const element = <img src={user.avatarUrl}></img>;
```

Babel 会把 JSX 转译成一个名为 React.createElement() 函数调用

2.元素渲染
===

React 元素是创建开销极小的**普通对象**  
描述了你在屏幕上想看到的内容    
React 元素是不可变对象。一旦被创建，你就无法更改它的子元素或者属性  

3.组件 & Props 发
===

函数组件
---
```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

ES6 的 class 组件  
---
```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
**注意： 组件名称必须以大写字母开头**  


生命周期
---
广义上分为三个阶段：挂载、渲染、卸载

**挂载：**
1. constructor()  
  constructor中完成了React数据的初始化，它接受两个参数：props和context，当想在函数内部使用这两个数时，需使用super()传入这两个参数  
  注意：只要使用了constructor()就必须写super(),否则会导致this指向错误  

2. componentWillMount()  
  componentWillMount用的比较少，它代表的过程是组件已经经历了constructor()初始化数据后，但是还未渲染DOM时  

3. componentDidMount()  
  组件第一次渲染完成，此时dom节点已经生成，可以在这里调用ajax请求，返回数据setState后组件会重新渲染  

**渲染：**  

4. componentWillReceiveProps (nextProps)    
  在接受父组件改变后的props需要重新渲染组件时用到的比较多接收参数nextProps，通过对比nextProps和this.props，将nextProps的state为当前组件的state，从而重新渲染组件

5. shouldComponentUpdate(nextProps,nextState)  
  主要用于性能优化(部分更新)，唯一用于控制组件重新渲染的生命周期，由于在react中，setState以后，state发生变化，组件会进入重新渲染的流程，在这里return false可以阻止组件的更新，因为react父组件的重新渲染会导致其所有子组件的重新渲染，这个时候其实我们是不需要所有子组件都跟着重新渲染的，因此需要在子组件的该生命周期中做判断

6. componentWillUpdate (nextProps,nextState)  
  shouldComponentUpdate返回true以后，组件进入重新渲染的流程，进入componentWillUpdate,这里同样可以拿nextProps和nextState

8. componentDidUpdate(prevProps,prevState)  
  组件更新完毕后，react只会在第一次初始化成功会进入componentDidmount,之后每次重新渲染后都会进入这个生命周期，这里可以拿到prevProps和prevState，即更新前的props和state   

9. render()  
  render函数会插入jsx生成的dom结构，react会生成一份虚拟dom树，在每一次组件更新时，在此react会通过其diff算法比较更新前后的新旧DOM树，比较以后，找到最小的有差异的DOM节点，并重新渲染  

**卸载：**

10. componentWillUnmount ()  
在此处完成组件的卸载和数据的销毁，clear你在组建中所有的setTimeout,setInterval，移除所有组建中的监听 removeEventListener











