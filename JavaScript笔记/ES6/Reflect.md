Reflect
===

概述
---

Reflect对象与Proxy对象一样，也是 ES6 为了操作对象而提供的新 API。Reflect对象的设计目的有这样几个  
将Object对象的一些明显属于语言内部的方法（比如Object.defineProperty），放到Reflect对象上  
修改某些Object方法的返回结果，让其变得更合理   
让Object操作都变成函数行为  
Reflect对象的方法与Proxy对象的方法一一对应，只要是Proxy对象的方法，就能在Reflect对象上找到对应的方法  

