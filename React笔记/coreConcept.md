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







