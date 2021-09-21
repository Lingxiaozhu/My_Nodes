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









