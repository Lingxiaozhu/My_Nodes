JSON 知识
===

JSON: JavaScript Object Notation（JavaScript 对象标记法）  
JSON 是一种存储和交换数据的语法  
JSON 是通过 JavaScript 对象标记法书写的文本  

在存储数据时，数据必须是某种具体的格式，并且无论您选择在何处存储它，文本永远是合法格式之一  
JSON 让 JavaScript 对象存储为文本成为可能  
JSON 语法是 JavaScript 语法的子集  

JSON 语法衍生于 JavaScript 对象标记法语法：  
数据在名称/值对中  
数据由逗号分隔  
花括号容纳对象  
方括号容纳数组  

JSON 名称需要双引号  
例子：  
```js
{ "name":"World" }
```
```js
{"employees":[
    { "firstName":"Bill", "lastName":"Gates" },
    { "firstName":"Steve", "lastName":"Jobs" },
    { "firstName":"Elon", "lastName":"Musk" }
]}
```

**JSON 文件**  
JSON 文件的文件类型是 ".json"  
JSON 文本的 MIME 类型是 "application/json"   

在 JSON 中，值必须是以下数据类型之一：  
1. 字符串  
2. 数字  
3. 对象（JSON 对象）  
4. 数组  
5. 布尔  
6. null  
JSON 的值不可以是以下数据类型之一：  
> 函数  
> 日期  
> undefined  

JSON 中的字符串必须用双引号包围  
例子：  
```js
{ "name":"World" }
```  

JSON 中的数字必须是整数或浮点数,不需要括号    
例子：  
```js
{ "age":30 }
``` 

JSON 中的值可以是对象  
JSON 中作为值的对象必须遵守与 JSON 对象相同的规则
例子：  
```js
{
"employee":{ "name":"Bill Gates", "age":62, "city":"Seattle" }
}
```

JSON 中的值可以是数组  
例子：  
```js
{
"employees":[ "Bill", "Steve", "David" ]
}
```  

JSON 中的值可以是 true/false  
例子：  
```js
{ "sale":true }
``` 

JSON 中的值可以是 null  
例子：  
```js
{ "middlename":null }
``` 

JSON.parse()
===
在从 web 服务器接收数据时，数据永远是字符串  
通过 JSON.parse() 解析数据，这些数据会成为 JavaScript 对象  


JavaScript 函数 JSON.parse() 把文本转换为 JavaScript 对象  
例子：  
```js
{ "middlename":null }
转换成JavaScript对象
var obj = JSON.parse('{ "middlename":null }');
``` 

JSON.stringify()  
===
通过 JSON.stringify() 把 JavaScript 对象转换为字符串  
```js
let a={name:'li',age:30}
转换成JSON
var obj = JSON.stringify(a);
``` 

在 JSON 中，不允许日期对象。JSON.stringify() 函数将把任何日期转换为字符串  
在 JSON 中，不允许函数作为对象值  


访问对象值
---
您可以通过使用点号（.）来访问对象值  
```js
let a={"name":"li","age":30}
let b=a.name
let b=a["name"]
```
**能够使用点号来修改 JSON 对象中的任何值**  

使用 delete 关键词来删除 JSON 对象的属性  
```js
let a={"name":"li","age":30}
delete a.name
```