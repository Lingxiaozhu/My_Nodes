Promise 对象
===

Promise 的含义
---

Promise 是异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理和更强大  
所谓Promise，简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果  
Promise对象有两个特点：  
> 对象的状态不受外界影响  
> 一旦状态改变，就不会再变，任何时候都可以得到这个结果  
Promise也有一些缺点。首先，无法取消Promise，一旦新建它就会立即执行，无法中途取消。其次，如果不设置回调函数，Promise内部抛出的错误，不会反应到外部。第三，当处于pending状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）  

基本用法
---

ES6 规定，Promise对象是一个构造函数，用来生成Promise实例  
Promise构造函数接受一个函数作为参数，该函数的两个参数分别是resolve和reject。它们是两个函数，由 JavaScript 引擎提供，不用自己部署  


Promise.prototype.then()
---

Promise 实例具有then方法，也就是说，then方法是定义在原型对象Promise.prototype上的。它的作用是为 Promise 实例添加状态改变时的回调函数  
then方法的第一个参数是resolved状态的回调函数，第二个参数是rejected状态的回调函数，它们都是可选的  
then方法返回的是一个新的Promise实例（注意，不是原来那个Promise实例）。因此可以采用链式写法，即then方法后面再调用另一个then方法  


Promise.prototype.catch()
---

Promise.prototype.catch()方法是.then(null, rejection)或.then(undefined, rejection)的别名，用于指定发生错误时的回调函数  


Promise.prototype.finally()
---

finally()方法用于指定不管 Promise 对象最后状态如何，都会执行的操作。该方法是 ES2018 引入标准的  


Promise.all() 
---

Promise.all()方法用于将多个 Promise 实例，包装成一个新的 Promise 实例  


Promise.race()
---

Promise.race()方法同样是将多个 Promise 实例，包装成一个新的 Promise 实例  
Promise.race()方法的参数与Promise.all()方法一样，如果不是 Promise 实例，就会先调用下面讲到的Promise.resolve()方法，将参数转为 Promise 实例，再进一步处理  


Promise.allSettled()
---

ES2020 引入了Promise.allSettled()方法，用来确定一组异步操作是否都结束了（不管成功或失败）。所以，它的名字叫做”Settled“，包含了”fulfilled“和”rejected“两种情况  
Promise.allSettled()方法接受一个数组作为参数，数组的每个成员都是一个 Promise 对象，并返回一个新的 Promise 对象。只有等到参数数组的所有 Promise 对象都发生状态变更（不管是fulfilled还是rejected），返回的 Promise 对象才会发生状态变更  


Promise.any()
---

ES2021 引入了Promise.any()方法。该方法接受一组 Promise 实例作为参数，包装成一个新的 Promise 实例返回  
Promise.any()跟Promise.race()方法很像，只有一点不同，就是Promise.any()不会因为某个 Promise 变成rejected状态而结束，必须等到所有参数 Promise 变成rejected状态才会结束  


Promise.resolve() 
---

Promise.resolve()方法将现有对象转为 Promise 对象  
Promise.resolve()方法的参数分成四种情况:  
> 参数是一个 Promise 实例   
> 参数是一个thenable对象  
> 参数不是具有then()方法的对象，或根本就不是对象  
> 不带有任何参数  


Promise.reject()
---

Promise.reject(reason)方法也会返回一个新的 Promise 实例，该实例的状态为rejected  


Promise.try()
---

















