Set 和 Map 数据结构
===

Set
---

ES6 提供了新的数据结构 Set。它类似于数组，但是成员的值都是唯一的，没有重复的值  
Set本身是一个构造函数，用来生成 Set 数据结构  
Set函数可以接受一个数组（或者具有 iterable 接口的其他数据结构）作为参数，用来初始化  
向 Set 加入值的时候，不会发生类型转换  
在 Set 内部，两个NaN是相等的，两个对象总是不相等的  

**Set 实例的属性和方法：**  
Set 结构的实例有以下属性：  
> Set.prototype.constructor：构造函数，默认就是Set函数  
> Set.prototype.size：返回Set实例的成员总数   
Set 实例的方法分为两大类：操作方法（用于操作数据）和遍历方法（用于遍历成员）  
操作方法:    
> Set.prototype.add(value)：添加某个值，返回 Set 结构本身    
> Set.prototype.delete(value)：删除某个值，返回一个布尔值，表示删除是否成功  
> Set.prototype.has(value)：返回一个布尔值，表示该值是否为Set的成员    
> Set.prototype.clear()：清除所有成员，没有返回值    

Array.from方法可以将 Set 结构转为数组  

遍历方法:  
> Set.prototype.keys()：返回键名的遍历器  
> Set.prototype.values()：返回键值的遍历器  
> Set.prototype.entries()：返回键值对的遍历器   
> Set.prototype.forEach()：使用回调函数遍历每个成员  

Set的遍历顺序就是插入顺序  

keys()，values()，entries():  
由于 Set 结构没有键名，只有键值（或者说键名和键值是同一个值），所以keys方法和values方法的行为完全一致  
Set 结构的实例默认可遍历，它的默认遍历器生成函数就是它的values方法  
entries方法返回的遍历器，同时包括键名和键值，所以每次输出一个数组，它的两个成员完全相等  

forEach():  
forEach方法，用于对每个成员执行某种操作，没有返回值  
forEach方法还可以有第二个参数，表示绑定处理函数内部的this对象  

遍历的应用:   
扩展运算符（...）内部使用for...of循环,可以用于 Set 结构  
扩展运算符和 Set 结构相结合，就可以去除数组的重复成员  
数组的map和filter方法也可以间接用于 Set   


WeakSet 
---

WeakSet 结构与 Set 类似，也是不重复的值的集合。但是，它与 Set 有两个区别    
首先，WeakSet 的成员只能是对象，而不能是其他类型的值    
其次，WeakSet 中的对象都是弱引用，即垃圾回收机制不考虑 WeakSet 对该对象的引用，也就是说，如果其他对象都不再引用该对象，那么垃圾回收机制会自动回收该对象所占用的内存，不考虑该对象还存在于 WeakSet 之中    
WeakSet 结构有以下三个方法:  
> WeakSet.prototype.add(value)：向 WeakSet 实例添加一个新成员    
> WeakSet.prototype.delete(value)：清除 WeakSet 实例的指定成员  
> WeakSet.prototype.has(value)：返回一个布尔值，表示某个值是否在  


Map
---

ES6 提供了 Map 数据结构。它类似于对象，也是键值对的集合，但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键  
也就是说，Object 结构提供了“字符串—值”的对应，Map 结构提供了“值—值”的对应，是一种更完善的 Hash 结构实现。如果你需要“键值对”的数据结构，Map 比 Object 更合适  

Map 结构的属性和操作方法:  
size属性返回 Map 结构的成员总数  
set方法设置键名key对应的键值为value，然后返回整个 Map 结构。如果key已经有值，则键值会被更新，否则就新生成该键  
get方法读取key对应的键值，如果找不到key，返回undefined  
has方法返回一个布尔值，表示某个键是否在当前 Map 对象之中  
delete方法删除某个键，返回true。如果删除失败，返回false  
clear方法清除所有成员，没有返回值  

Map 结构提供三个遍历器生成函数和一个遍历方法:  
> Map.prototype.keys()：返回键名的遍历器  
> Map.prototype.values()：返回键值的遍历器  
> Map.prototype.entries()：返回所有成员的遍历器  
> Map.prototype.forEach()：遍历 Map 的所有成员  

Map 转为数组:  
Map 转为数组最方便的方法，就是使用扩展运算符（...）  

数组 转为 Map:  
数组传入 Map 构造函数，就可以转为 Map  

Map 转为对象:  
如果所有 Map 的键都是字符串，它可以无损地转为对象  
如果有非字符串的键名，那么这个键名会被转成字符串，再作为对象的键名  

对象转为 Map:  
对象转为 Map 可以通过Object.entries()  

Map 转为 JSON:  
Map 转为 JSON 要区分两种情况。一种情况是，Map 的键名都是字符串，这时可以选择转为对象 JSON  

JSON 转为 Map:  
JSON 转为 Map，正常情况下，所有键名都是字符串  


WeakMap
---

WeakMap结构与Map结构类似，也是用于生成键值对的集合  
WeakMap与Map的区别有两点:  
> 首先，WeakMap只接受对象作为键名（null除外），不接受其他类型的值作为键名  
> 其次，WeakMap的键名所指向的对象，不计入垃圾回收机制  


WeakRef
---

WeakSet 和 WeakMap 是基于弱引用的数据结构，ES2021 更进一步，提供了 WeakRef 对象，用于直接创建对象的弱引用  


FinalizationRegistry
---

ES2021 引入了清理器注册表功能 FinalizationRegistry，用来指定目标对象被垃圾回收机制清除以后，所要执行的回调函数  



