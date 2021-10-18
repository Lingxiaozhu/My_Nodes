# JaveScript基础1
1. JavaScript可以改变HTML内容。（可以使用大括号或者小括号）,能够改变 HTML 属性,能够改变 HTML 样式 (CSS)  
例子：  
```js
    document.getElementById("demo").innerHTML = "Hello JavaScript"  
    document.getElementById('myImage').src='/i/eg_bulboff.gif'
    document.getElementById("demo").style.fontSize = "50px"

    在HTML文档中，JavaScript 代码放于 `<script>` 与`</script>` 标签之间   

    可以放在`<head>` 或 `<body>`中,type 属性不是必需的

    **当JavaScript放在外部文件时，不能包含 `<script>` 标签**

    JavaScript 文件的文件扩展名是 .js
```

    

2. JavaScript输出4种方式：  
    `window.alert()` 写入警告框  
    `document.write()` 写入 HTML 输出 （在文档完全加载后使用将删除所有已有的 HTML ）  
    `innerHTML` 写入 HTML 元素  
    `console.log()` 写入浏览器控制台   
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
例子：  
```js
    let str = "The full name of China is the People's Republic of China.";
    let pos = str.indexOf("China");//17
```

lastIndexOf() 方法向后进行检索（从尾到头）  
返回指定文本在字符串中**最后**一次出现的索引   
例子：  
```js
let str = "The full name of China is the People's Republic of China.";
let pos = str.lastIndexOf("China");//51
```
如果未找到文本， indexOf() 和 lastIndexOf() 均返回 -1  
两种方法都接受作为检索起始位置的第二个参数  
例子：  
```js
let str = "The full name of China is the People's Republic of China.";  
let pos = str.indexOf("China",18);//51
let pos = str.lastIndexOf("China",50);//17
```

search() 方法搜索特定值的字符串，并返回匹配的位置  
例子：    
```js
let str = "The full name of China is the People's Republic of China."; 
let pos = str.search("China");
```

search()与indexOf()区别：  
> search() 方法无法设置第二个开始位置参数。
> indexOf() 方法无法设置更强大的搜索值（正则表达式）。

有三种提取部分字符串的方法：  
>  slice(start, end)  
>  substring(start, end)  
>  substr(start, length)    

slice例子：  
```js
let a="my name is Lingxiaozhu";
let b=a.slice(3,7)//name
//如果某个参数为负，则从字符串的结尾开始计数
let b=a.slice(-19,-15)//name
//如果省略第二个参数，则该方法将裁剪字符串的剩余部分
let b=a.slice(7)//name is Lingxiaozhu
//或者从结尾计数
let b=a.slice(-19)//name is Lingxiaozhu
```
substring例子：  
```js
//substring() 类似于 slice(),不同之处在于 substring() 无法接受负的索引
let a="my name is Lingxiaozhu";
let b=a.substring(3,7)//name
//省略第二个参数，则该 substring() 将裁剪字符串的剩余部分
let b=a.substring(3)//name is Lingxiaozhu
```
substr例子：
核心:第二个参数提取长度
```js
//substr() 类似于 slice(),不同之处在于第二个参数规定被提取部分的长度
let a="my name is Lingxiaozhu";
let b=a.slice(3,4)//name
//首个参数为负，则从字符串的结尾计算位置
let b=a.slice(-19,4)//name
```

替换字符串内容:  
replace() 方法  
例子：  
```js
let a="my name is Lingxiaozhu";
let b=a.replace("Lingxiaozhu","Xiaokeai")//my name is Xiaokeai
```
replace() 方法不会改变调用它的字符串,它返回的是新字符串  
**默认地，replace() 只替换首个匹配**  
replace() 对大小写敏感  
可以结合正则表达式一起使用  
例子：  
```js
let a="my name is Lingxiaozhu";
//大小写不敏感
let b=a.replace(/lingxiaozhu/i,"Xiaokeai")//my name is Xiaokeai
//全局搜索
let b=a.replace(/i/g,"I")//my name Is LIngxIaozhu
```

转换为大写和小写：  
> toUpperCase() 把字符串转换为大写  
> toLowerCase() 把字符串转换为小写  
例子：  
```js
let a='Ling';
let b=a.toUpperCase()//LING
let c=a.toLowerCase()//ling
```

concat() 连接两个或多个字符串  
例子：  
```js
let a='hello';
let b='world';
let c=a.concat(" ",b);//hello world
let c=a.concat(b);//helloworld
```
所有字符串方法都会返回新字符串。它们不会修改原始字符串   
正式地说：字符串是不可变的：字符串不能更改，只能替换  


trim() 方法删除字符串两端的空白符   
例子：  
```js
let a="   abc   ";
b=a.trim()//abc
```

提取字符串字符：  
> charAt()   
> charCodeAt()  //返回字符串中指定索引的字符 unicode 编码  
例子：  
```js
let a="Lingxiaozhu";
b=a.charAt(0)//L
c.a.charCodeAt(0)//76  返回字符串中指定索引的字符 unicode 编码
```

8. JavaScript 数字  
JavaScript 数值始终是 64 位的浮点数  
整数（不使用指数或科学计数法）会被精确到 15 位  
NaN 属于 JavaScript 保留词，指示某个数不是合法数  
在数学运算中使用了NaN，则结果也将是 NaN  
Infinity （或 -Infinity）是在计算数时超出最大可能数范围时返回的值  

9. JavaScript 数值方法  
toString() 以字符串返回数值    
例子：
```js
let a=123;
let b=a.toString()//"123"
```

toExponential() 返回字符串值，它包含已被四舍五入并使用指数计数法的数字  
参数定义小数点后的字符数  
例子：  
```js
let a=8.666;
let b=a.toExponential(2);//8.67e+0
```
该参数是可选的。如果您没有设置它，JavaScript 不会对数字进行舍入  


toFixed() 返回字符串值，它包含了指定位数小数的数字  
例子：  
```js
let a=123;
let b=a.toFixed(3);//123.000
```

toPrecision() 返回字符串值，它包含了指定长度的数字  
例子：  
```js
let a=123;
let b=a.toPrecision(4);//123.0
```

valueOf() 以数值返回数值   
例子：
```js
(123).valueOf(); // 从文本 123 返回 123
```

将变量转换为数字的方法：
> Number() 方法  
> parseInt() 方法  
> parseFloat() 方法  

Number例子：  
```js
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
parseInt例子：  
```js
//parseInt() 解析一段字符串并返回数值。允许空格。只返回首个数字
parseInt("10");         // 返回 10
parseInt("10.33");      // 返回 10
parseInt("10 20 30");   // 返回 10
parseInt("10 years");   // 返回 10
parseInt("years 10");   // 返回 NaN
```

parseFloat例子：  
```js
//parseFloat() 解析一段字符串并返回数值。允许空格。只返回首个数字
parseFloat("10");        // 返回 10
parseFloat("10.33");     // 返回 10.33
parseFloat("10 20 30");  // 返回 10
parseFloat("10 years");  // 返回 10
parseFloat("years 10");  // 返回 NaN
```

**MAX_VALUE** 返回 JavaScript 中可能的最大数字  

10. JavaScript 数组  
数组用于在单一变量中存储多个值  
数组是对象  
数组属性和方法:  
> length 属性  
可以使用 Array.foreach() 函数  
向数组添加新元素的最佳方法是使用 push() 方法   
判断是否是数组： Array.isArray()  
     
