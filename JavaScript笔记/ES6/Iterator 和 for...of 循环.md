Iterator 和 for...of 循环
===

Iterator（遍历器）的概念
---

JavaScript 原有的表示“集合”的数据结构，主要是数组（Array）和对象（Object），ES6 又添加了Map和Set   
Iterator 的作用有三个：  
1. 为各种数据结构，提供一个统一的、简便的访问接口  
2. 使得数据结构的成员能够按某种次序排列  
3. ES6 创造了一种新的遍历命令for...of循环，Iterator 接口主要供for...of循环  

默认 Iterator 接口 
---

Iterator 接口的目的，就是为所有数据结构，提供了一种统一的访问机制，即for...of循环   
一种数据结构只要部署了 Iterator 接口，我们就称这种数据结构是“可遍历的”（iterable）   
ES6 规定，默认的 Iterator 接口部署在数据结构的Symbol.iterator属性，或者说，一个数据结构只要具有Symbol.iterator属性，就可以认为是“可遍历的”    
原生具备 Iterator 接口的数据结构：  
Array  
Map  
Set  
String  
TypedArray  
函数的 arguments 对象  
NodeList 对象  

对象（Object）之所以没有默认部署 Iterator 接口，是因为对象的哪个属性先遍历，哪个属性后遍历是不确定的，需要开发者手动指定  


调用 Iterator 接口的场合
---
解构赋值  
扩展运算符  
yield*    
for...of  
Array.from()  
Map(), Set(), WeakMap(), WeakSet()（比如new Map([['a',1],['b',2]])）  
Promise.all()  
Promise.race()  

字符串的 Iterator 接口  
---

字符串是一个类似数组的对象，原生具有 Iterator 接口  

遍历器对象的 return()，throw()
---

遍历器对象除了具有next()方法，还可以具有return()方法和throw()方法。如果你自己写遍历器对象生成函数，那么next()方法是必须部署的，return()方法和throw()方法是否部署是可选的  




