# JaveScript基础
1. JavaScript可以改变HTML内容,能够改变 HTML 属性,能够改变 HTML 样式 (CSS)  
例子：  
```js
    document.getElementById("demo").innerHTML = "Hello JavaScript"  
    document.getElementById('myImage').src='/i/eg_bulboff.gif'
    document.getElementById("demo").style.fontSize = "50px"

    在HTML文档中，JavaScript 代码放于<script>与</script>标签之间   

    可以放在<head> 或 <body>中,type 属性不是必需的

    当JavaScript放在外部文件时，不能包含<script>标签

    JavaScript 文件的文件扩展名是 .js
```

    

2. JavaScript输出4种方式：  
    window.alert() 写入警告框  
    document.write() 写入 HTML 输出 （在文档完全加载后使用将删除所有已有的 HTML ）  
    innerHTML 写入 HTML 元素  
    console.log() 写入浏览器控制台   
例子：  
```js
    <script>
    window.alert(5 + 6);
    alert('hello');
    document.write(5 + 6);
    document.getElementById("demo").innerHTML = 5 + 6;
    console.log('hello');
    </script>
```

2. JavaScript 语句由**值、运算符、表达式、关键词和注释**构成,JavaScript 语句可以用花括号（{...}）组合在代码块中  
例子：  
```js
    <script>
        function myFunction() {
            console.log('hello');
            console.log('world');
        }
    </script>
```

3. JavaScript 语句定义两种类型的值：混合值（**字面量（literal）**）和变量值（**变量**）  
***变量用于存储数据值***  


    注释:单行注释以 // 开头  多行注释以 /* 开头,以 */ 结尾  


4. JavaScript 标识符:  
所有 JavaScript 变量必须以唯一的名称的标识,这些唯一的名称称为标识符  
    构造变量名称（唯一标识符）的通用规则是：  
    > 名称可包含字母、数字、下划线和美元符号  

    > 名称不能以数字开头  

    > 名称对大小写敏感  

    > 保留字不能用作标识符  


5. JavaScript 算数运算符 

    |运算符|描述|
    |---|---|  
    |`+`|加|
    |`—`|减|
    |`*`|乘|
    |`/`|除|
    |`%`|取模|
    |`++`|自加|
    |`--`|自减|
    |`**`|幂|


6. JavaScript 赋值运算符    
    运算符	
    > =	  

    > +=  

    > -=  	

    > *=  

    > /=  	

    > %=	

    > **=  

7. JavaScript 比较运算符

    |运算符|描述|
    |---|---|
    |`==`|等于|
    |`===`|等值等型|
    |`!=`|不相等|
    |`!==`|不等值或不等型|
    |`>`|大于|
    |`<`|小于|
    |`>=`|大于或等于|
    |`<=`|小于或等于|
    |`?：`|三元运算符|

8. JavaScript 逻辑运算符

    |运算符|描述|
    |---|---|
    |`&&`|逻辑与|
    |  &#124; &#124; |逻辑或|
    |`!`|逻辑非|
    

9. JavaScript 数据类型  
    string  
    number  
    boolean  
    undefined  
    null  
    function  
    object  
    Symbol  

    Undefined 与 null 的值相等，但类型不相等

10. JavaScript 函数  

函数通过 function 关键词进行定义，其后是函数名和括号 ()
例子：  
```js
    function all(){
        ···
    }
```

11. JavaScript 对象  

    通过 {  } 来定义  
    有两种方法访问属性：  
        > objectName.propertyName  
        > objectName["propertyName"]  

例子：  
```js
    let a={name:'hong',age:20};
    let b=a.name;
    let c=a["age"];
```

12. 常见的 HTML 事件  
***onchange、onclick***、onmouseover、onmouseout、onkeydown、onload  

13. JavaScript 字符串  

    可以使用单引号或双引号  
    内建属性 length 可返回字符串的长度  
    例子：  
```js
    let a = txt.length; 
    反斜杠转义字符把特殊字符转换为字符串字符  
    字符串可通过关键词 new 定义为对象  
```

14. JavaScript 字符串方法  

    length 属性返回字符串的长度  
    indexOf() 方法返回字符串中**指定文本首次**出现的索引（位置） 
```js
    let str = "The full name of China is the People's Republic of China.";
    let pos = str.indexOf("China");//17
```
        lastIndexOf() 方法向后进行检索（从尾到头）返回指定文本在字符串中最后一次出现的索引   
        
```js
    let str = "The full name of China is the People's Republic of China.";
    let pos = str.lastIndexOf("China");//51
```
        如果未找到文本， indexOf() 和 lastIndexOf() 均返回 -1 ,两种方法都接受作为检索起始位置的第二个参数  
    
```js
    let str = "The full name of China is the People's Republic of China.";  
    let pos = str.indexOf("China",18);//51
    let pos = str.lastIndexOf("China",50);//17
```

        search() 方法搜索特定值的字符串，并返回匹配的位置  
   
```js
    let str = "The full name of China is the People's Republic of China."; 
    let pos = str.search("China");
```

        search()与indexOf()区别： 
            search() 方法无法设置第二个开始位置参数  
            indexOf() 方法无法设置更强大的搜索值（正则表达式）

        有三种提取部分字符串的方法：  
            slice(start, end)  
            substring(start, end)  
            substr(start, length)    

          
```js
    slice例子：
        let a="my name is Lingxiaozhu";
        let b=a.slice(3,7)//name
        //如果某个参数为负，则从字符串的结尾开始计数
        let b=a.slice(-19,-15)//name
        //如果省略第二个参数，则该方法将裁剪字符串的剩余部分
        let b=a.slice(7)//name is Lingxiaozhu
        //或者从结尾计数
        let b=a.slice(-19)//name is Lingxiaozhu
```
  
```js
    substring例子：
        //substring() 类似于 slice(),不同之处在于 substring() 无法接受负的索引
        let a="my name is Lingxiaozhu";
        let b=a.substring(3,7)//name
        //省略第二个参数，则该 substring() 将裁剪字符串的剩余部分
        let b=a.substring(3)//name is Lingxiaozhu
```

```js
    substr例子：
    核心:第二个参数提取长度
        //substr() 类似于 slice(),不同之处在于第二个参数规定被提取部分的长度
        let a="my name is Lingxiaozhu";
        let b=a.slice(3,4)//name
        //首个参数为负，则从字符串的结尾计算位置
        let b=a.slice(-19,4)//name
```

 
```js
    替换字符串内容:  replace() 方法 
        let a="my name is Lingxiaozhu";
        let b=a.replace("Lingxiaozhu","Xiaokeai")//my name is Xiaokeai
```
  
```js
    replace() 方法不会改变调用它的字符串,它返回的是新字符串  
    默认地，replace() 只替换首个匹配  
    replace() 对大小写敏感  
    可以结合正则表达式一起使用  
        let a="my name is Lingxiaozhu";
        //大小写不敏感
        let b=a.replace(/lingxiaozhu/i,"Xiaokeai")//my name is Xiaokeai
        //全局搜索
        let b=a.replace(/i/g,"I")//my name Is LIngxIaozhu
```


  
```js
    转换为大写和小写：  
        toUpperCase() 把字符串转换为大写  
        toLowerCase() 把字符串转换为小写  
            let a='Ling';
            let b=a.toUpperCase()//LING
            let c=a.toLowerCase()//ling
```*


```js
    concat() 连接两个或多个字符串  
        let a='hello';
        let b='world';
        let c=a.concat(" ",b);//hello world
        let c=a.concat(b);//helloworld
```
        所有字符串方法都会返回新字符串。它们不会修改原始字符串   
        正式地说：字符串是不可变的：字符串不能更改，只能替换  

  
```js
    trim() 方法删除字符串两端的空白符   
        let a="   abc   ";
        b=a.trim()//abc
```

```js
    提取字符串字符：  
    charAt()   
    charCodeAt()  //返回字符串中指定索引的字符 unicode 编码  
        let a="Lingxiaozhu";
        b=a.charAt(0)//L
        c.a.charCodeAt(0)//76  返回字符串中指定索引的字符 unicode 编码
```

15. JavaScript 数字  

    JavaScript 数值始终是 64 位的浮点数  
    整数（不使用指数或科学计数法）会被精确到 15 位  
    NaN 属于 JavaScript 保留词，指示某个数不是合法数  
    在数学运算中使用了NaN，则结果也将是 NaN  
    Infinity （或 -Infinity）是在计算数时超出最大可能数范围时返回的值  

16. JavaScript 数值方法  
   
```js
    toString() 以字符串返回数值 
        let a=123;
        let b=a.toString()//"123"
```


```js
    toExponential() 返回字符串值，它包含已被四舍五入并使用指数计数法的数字  
    参数定义小数点后的字符数  
        let a=8.666;
        let b=a.toExponential(2);//8.67e+0
    该参数是可选的。如果您没有设置它，JavaScript 不会对数字进行舍入  
```

```js
    toFixed() 返回字符串值，它包含了指定位数小数的数字
        let a=123;
        let b=a.toFixed(3);//123.000
```

  
```js
    toPrecision() 返回字符串值，它包含了指定长度的数字
        let a=123;
        let b=a.toPrecision(4);//123.0
```

```js
    valueOf() 以数值返回数值
        (123).valueOf(); // 从文本 123 返回 123
```

        将变量转换为数字的方法：
        > Number() 方法  
        > parseInt() 方法  
        > parseFloat() 方法  


```js
    Number例子：  
        x = true;
        Number(x);        // 返回 1
        x = false;     
        Number(x);        // 返回 0
        x = new Date();
        Number(x);        // 返回 1404568027739
        x = "10"
        Number(x);        // 返回 10
        x = "10 20"
        Number(x);        // 返回 NaN
```
  
```js
    parseInt例子：
        //parseInt() 解析一段字符串并返回数值。允许空格。只返回首个数字
        parseInt("10");         // 返回 10
        parseInt("10.33");      // 返回 10
        parseInt("10 20 30");   // 返回 10
        parseInt("10 years");   // 返回 10
        parseInt("years 10");   // 返回 NaN
```

  
```js
    parseFloat例子：   
        //parseFloat() 解析一段字符串并返回数值。允许空格。只返回首个数字
        parseFloat("10");        // 返回 10
        parseFloat("10.33");     // 返回 10.33
        parseFloat("10 20 30");  // 返回 10
        parseFloat("10 years");  // 返回 10
        parseFloat("years 10");  // 返回 NaN
```

        MAX_VALUE返回 JavaScript 中可能的最大数字  

17. JavaScript 数组  
数组用于在单一变量中存储多个值  
数组是对象  
数组属性和方法:  
    > length 属性  
    可以使用 Array.foreach() 函数  
    向数组添加新元素的最佳方法是使用 push() 方法   
    判断是否是数组： Array.isArray()  
     
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
    