Symbol
===

概述
---

ES5 的对象属性名都是字符串，这容易造成属性名的冲突  
ES6 引入了一种新的原始数据类型Symbol，表示独一无二的值  
它是 JavaScript 语言的第七种数据类型，前六种是：undefined、null、布尔值（Boolean）、字符串（String）、数值（Number）、对象（Object）  
Symbol 值通过Symbol函数生成。这就是说，对象的属性名现在可以有两种类型，一种是原来就有的字符串，另一种就是新增的 Symbol 类型。凡是属性名属于 Symbol 类型，就都是独一无二的，可以保证不会与其他属性名产生冲突  
Symbol函数前不能使用new命令  
如果 Symbol 的参数是一个对象，就会调用该对象的toString方法，将其转为字符串，然后才生成一个 Symbol 值  
Symbol 值不能与其他类型的值进行运算，会报错  
Symbol 值可以显式转为字符串  
Symbol 值也可以转为布尔值，但是不能转为数值  


Symbol.prototype.description
---

ES2019 提供了一个实例属性description，直接返回 Symbol 的描述  


作为属性名的 Symbol
---


由于每一个 Symbol 值都是不相等的，这意味着 Symbol 值可以作为标识符，用于对象的属性名，就能保证不会出现同名的属性  
Symbol 值作为对象属性名时，不能用点运算符  
Symbol 值作为属性名时，该属性还是公开属性，不是私有属性  


实例：消除魔术字符串
---

魔术字符串指的是，在代码之中多次出现、与代码形成强耦合的某一个具体的字符串或者数值。风格良好的代码，应该尽量消除魔术字符串，改由含义清晰的变量代替   


属性名的遍历
---

Symbol 作为属性名，遍历对象的时候，该属性不会出现在for...in、for...of循环中，也不会被Object.keys()、Object.getOwnPropertyNames()、JSON.stringify()返回  
但是，它也不是私有属性，有一个Object.getOwnPropertySymbols()方法，可以获取指定对象的所有 Symbol 属性名。该方法返回一个数组，成员是当前对象的所有用作属性名的 Symbol 值  


Symbol.for()，Symbol.keyFor()
---


Symbol.for()方法可以做到重新使用同一个 Symbol 值  


内置的 Symbol 值
---

除了定义自己使用的 Symbol 值以外，ES6 还提供了 11 个内置的 Symbol 值，指向语言内部使用的方法  
对象的Symbol.hasInstance属性，指向一个内部方法  
对象的Symbol.isConcatSpreadable属性等于一个布尔值，表示该对象用于Array.prototype.concat()时，是否可以展开  
对象的Symbol.species属性，指向一个构造函数。创建衍生对象时，会使用该属性  
对象的Symbol.match属性，指向一个函数。当执行str.match(myObject)时，如果该属性存在，会调用它，返回该方法的返回值  
对象的Symbol.replace属性，指向一个方法，当该对象被String.prototype.replace方法调用时，会返回该方法的返回值  
对象的Symbol.search属性，指向一个方法，当该对象被String.prototype.search方法调用时，会返回该方法的返回值  
对象的Symbol.split属性，指向一个方法，当该对象被String.prototype.split方法调用时，会返回该方法的返回值  
对象的Symbol.iterator属性，指向该对象的默认遍历器方法  
对象的Symbol.toPrimitive属性，指向一个方法。该对象被转为原始类型的值时，会调用这个方法，返回该对象对应的原始类型值  
对象的Symbol.toStringTag属性，指向一个方法。在该对象上面调用Object.prototype.toString方法时，如果这个属性存在，它的返回值会出现在toString方法返回的字符串之中，表示对象的类型  
对象的Symbol.unscopables属性，指向一个对象。该对象指定了使用with关键字时，哪些属性会被with环境排除  
