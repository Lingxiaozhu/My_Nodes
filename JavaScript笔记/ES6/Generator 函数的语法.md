Generator 函数的语法
===

简介
---

Generator 函数是 ES6 提供的一种异步编程解决方案，语法行为与传统函数完全不同   
Generator 函数有多种理解角度。语法上，首先可以把它理解成，Generator 函数是一个状态机，封装了多个内部状态  
执行 Generator 函数会返回一个遍历器对象，也就是说，Generator 函数除了状态机，还是一个遍历器对象生成函数。返回的遍历器对象，可以依次遍历 Generator 函数内部的每一个状态  
形式上，Generator 函数是一个普通函数，但是有两个特征。一是，function关键字与函数名之间有一个星号；二是，函数体内部使用yield表达式，定义不同的内部状态（yield在英语里的意思就是“产出”）  


next 方法的参数
---

yield表达式本身没有返回值，或者说总是返回undefined。next方法可以带一个参数，该参数就会被当作上一个yield表达式的返回值  


for...of 循环
---

for...of循环可以自动遍历 Generator 函数运行时生成的Iterator对象，且此时不再需要调用next方法  


Generator.prototype.throw()
---

Generator 函数返回的遍历器对象，都有一个throw方法，可以在函数体外抛出错误，然后在 Generator 函数体内捕获  


Generator.prototype.return()
---

Generator 函数返回的遍历器对象，还有一个return()方法，可以返回给定的值，并且终结遍历 Generator 函数  


next()、throw()、return() 的共同点  
---

next()、throw()、return()这三个方法本质上是同一件事，可以放在一起理解。它们的作用都是让 Generator 函数恢复执行，并且使用不同的语句替换yield表达式  
next()是将yield表达式替换成一个值  
throw()是将yield表达式替换成一个throw语句  
return()是将yield表达式替换成一个return语句  






