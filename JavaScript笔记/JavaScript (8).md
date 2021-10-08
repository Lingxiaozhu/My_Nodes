JavaScript 函数
===
1.JavaScript 函数定义
---
函数声明:  
```js
function functionName(parameters) {
    要执行的代码
}
```
JavaScript 函数也可以使用表达式来定义 (匿名函数) 
```js
var x = function (a, b) {return a * b};
```
函数也可以通过名为 Function() 的内建 JavaScript 函数构造器来定义  
大多数情况下，可以避免使用 new 关键词  


Hoisting 是 JavaScript 将声明移动到当前作用域顶端的默认行为  


自调用函数  
自调用表达式是自动被调用（开始）的，在不进行调用的情况下,函数表达式会自动执行  
函数周围添加括号，以指示它是一个函数表达式  

```js
(function () {
    let x = "Hello!!";   
})();
```

箭头函数  
```js
// ES6
const x = (x, y) => x * y;
```

2.JavaScript 函数参数
---
JavaScript 函数不会对参数值进行任何检查  
**参数规则**  
>JavaScript 函数定义不会为参数（parameter)规定数据类型  
>JavaScript 函数不会对所传递的参（argument）实行类型检查  
>JavaScript 函数不会检查所接收参（argument）的数量  

3.JavaScript 函数 Call
---- 
使用 call() 方法，您可以编写能够在不同对象上使用的方法   
call() 方法可接受参数  

4.JavaScript 函数 Apply  
---
apply() 方法能够编写用于不同对象的方法   

**call() 和 apply() 之间的区别不同之处是：**  

    call() 方法分别接受参数  
    apply() 方法接受数组形式的参数  

