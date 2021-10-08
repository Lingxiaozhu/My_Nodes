JavaScript 数组方法  
---

toString() 把数组转换为数组值（逗号分隔）的字符串   
例子：  
```js
let a=['a','b','c','d'];
let b=a.toString();//a,b,c,d
```
    
join() 方法也可将所有数组元素结合为一个字符串,可以规定分隔符  
例子：  
```js
let a=['a','b','c','d'];
let b=a.join();//a,b,c,d
```
```js
let a=['a','b','c','d'];
let c=a.join("*");//a*b*c*d
```
    
pop() 方法从数组中删除最后一个元素   
例子：  
```js
let a=['a','b','c','d'];
a.pop();//a=['a','b','c']
```
```js
let a=['a','b','c','d'];
let b=a.pop();//b=d 返回被删除的元素
```

push() 方法（在数组结尾处）向数组添加一个新的元素  
例子：  
```js
let a=['a','b','c','d'];
a.push('aa');//a=['a','b','c','d','aa']
```
```js
let a=['a','b','c','d'];
let b=a.push('bb')//b=5 返回新数组长度
```

shift() 方法会删除首个数组元素，并把所有其他元素“位移”到更低的索引   
例子：  
```js
let a=['a','b','c','d'];
a.shift();//a=['b','c','d']
```
```js
let a=['a','b','c','d'];
let b=a.shift();//b=a 返回出的值
```

unshift() 方法（在开头）向数组添加新元素，并“反向位移”旧元素  
例子：  
```js
let a=['a','b','c','d'];
a.unshift("aa");//a=['aa','a','b','c','d']
```
```js
let a=['a','b','c','d'];
let b=a.unshift('aa');//b=6
```

length 属性提供了向数组追加新元素的简易方法  
例子：  
```js
let a=['a','b','c','d'];
a[a.length]="aa"//a=['a','b','c','d','aa']
//length 是长度，而数组下标是从0开始，所以长度永远是数组最大下标+1
```

可以使用 JavaScript delete 运算符来删除  
例子：  
```js
let a=['a','b','c','d'];
a.delete[0]//a=[undefined,'b','c','d']
//delete 会在数组留下未定义的空洞
```

splice() 方法可用于向数组添加新项(拼接数组)  
例子：  
```js
let a=['a','b','c','d'];
a.splice(2,0,'aa','bb')//a=['a','b','aa','bb','c','d']
```
```js
let a=['a','b','c','d'];
a.splice(2,1,'aa','bb')//a=['a','b','aa','bb','d']
//第一个参数定义了应添加新元素的位置（拼接)
//第二个参数定义应删除多少元素
//其余参数定义要添加的新元素
```
***使用 splice() 来删除元素***
```js
let a=['a','b','c','d'];
a.splice(0,1)//a=['b','c','d']
```

JavaScript 数组排序   
---

sort() 方法以字母顺序对数组进行排序  
例子：  
```js
let a=['b','a','c','d'];
a.sort();//a=['a','b','c','d'];
//sort() 方法按照字符串顺序对值进行排序,所以在对数值排序时会产生不正确的结果
```

reverse() 方法反转数组中的元素  
```js
let a=['a','b','c','d'];
a.reverse();//a=['d','c','b','a'];
//通过组合 sort() 和 reverse()，可以按降序对数组进行排序
```

JavaScript 数组迭代方法   
---

forEach() 方法为每个数组元素调用一次函数（回调函数）    
```js
let a=['a','b','c','d'];
a.forEach((value, index, array)=>{......})
```   

Array.map()  
```js
let a=['a','b','c','d'];
a.map((value, index, array)=>{......})
//map方法的作用就是将原数组按照一定的规则映射成一个新的数组。再将其返回，是返回一个新的数组，而不是将原数组直接改变
```

filter() 方法创建一个包含通过测试的数组元素的新数组  
```js
//用法和参数跟map差不多
let a=['a','b','c','d'];
a.filter((value, index, array)=>{......})
//与map方法不同的是，filter方法的callback函数需要返回弱等于true或false的值。如果为true，则通过，否则，不通过
```

some()方法是只要数组中的某个值，符合你给定的判断条件就返回true；否则，返回false  

reduce() 方法在每个数组元素上运行函数，以生成（减少它）单个值  

JavaScript 日期   
---

默认情况下，JavaScript 将使用浏览器的时区并将日期显示为全文本字符串   
```js
Wed Sep 29 2021 22:10:13 GMT+0800 (中国标准时间)
```

date 对象由新的 Date() 构造函数创建  
1. new Date()  
2. new Date(year, month, day, hours, minutes, seconds, milliseconds)  
3. new Date(milliseconds)  
4. new Date(date string)  

JavaScript 从 0 到 11 计算月份  

JavaScript 日期格式化   
---

ISO 日期  
```js
	"2021-10-01" （国际标准）
```

短日期  
```js
	"10/01/2021" 或者 "2021/10/01"
```

长日期  
```js
    "Fri 01 2021" 或者 "01 Fri 2021"
```

完整日期  
```js
	"Friday October 01 2021"
```

JavaScript 获取日期方法   
---

    getDate()  
    getDay()  
    getFullYear()
    getHours()  
    getMilliseconds()  
    getMinutes()
    getMonth()
    getSeconds()  
    getTime()  

JavaScript 设置日期方法   
---

    setDate()  
    setFullYear()  
    setHours()  
    setMilliseconds()  
    setMinutes()  
    setMonth()  
    setSeconds()  
    setTime()  

JavaScript Math 对象   
---

    Math 对象允许您对数字执行数学任务  
    Math.round(x) 的返回值是 x 四舍五入为最接近的整数  
    Math.pow(x, y) 的返回值是 x 的 y 次幂  
    Math.sqrt(x) 返回 x 的平方根  
    Math.abs(x) 返回 x 的绝对（正）值  
    Math.ceil(x) 的返回值是x向上舍入最接近的整数  
    Math.floor(x) 的返回值是 x 向下舍入最接近的整数  
    Math.sin(x) 返回角 x（以弧度计）的正弦（介于 -1 与 1 之间的值）  
    Math.cos(x) 返回角 x（以弧度计）的余弦（介于 -1 与 1 之间的值）  
    Math.min() 和 Math.max() 可用于查找参数列表中的最低或最高值  
    Math.random() 返回介于 0（包括） 与 1（不包括） 之间的随机数  

JavaScript 随机   
---

Math.random() 返回 0（包括） 至 1（不包括） 之间的随机数  
```js
let a=Math.random();//0.27537782864981435
//Math.random() 总是返回小于 1 的数
```

Math.random() 与 Math.floor() 一起使用用于返回随机整数   
```js
//返回0至9整数
let a=Math.floor(Math.random()*10)//3
//返回0至99整数
let a=Math.floor(Math.random()*100)//39
//返回1至10整数
let a=Math.floor(Math.random()*10)+1//7
//返回1至100整数
let a=Math.floor(Math.random()*100)+1//56
```

返回介于 min和 max之间的随机数  
```js
//介于 min（包括）和 max（不包括）
let a= Math.floor(Math.random() * (max - min) ) + min
//介于 min 和 max（都包括）
let a= Math.floor(Math.random() * (max - min+1) ) + min
```

JavaScript 逻辑   
---
    JavaScript 布尔（逻辑）代表两个值之一：true 或 false   
    Boolean() 函数来确定表达式（或变量）是否为真  
    