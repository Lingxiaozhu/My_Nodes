# JaveScript基础1
1. JavaScript可以改变HTML内容。（可以使用大括号或者小括号）
    例子：  
    document.getElementById("demo").innerHTML = "Hello JavaScript"  
    document.getElementById("demo").innerHTML = 'Hello JavaScript'

2. JavaScript 能够改变 HTML 属性
    例子：  
    document.getElementById('myImage').src='/i/eg_bulboff.gif'  
    document.getElementById('myImage').src='/i/eg_bulbon.gif'  

3. JavaScript 能够改变 HTML 样式 (CSS)  
    例子：  
    document.getElementById("demo").style.fontSize = "50px"  

4. 在HTML文档中，JavaScript 代码必须位于 `<script>` 与`</script>` 标签之间，type 属性不是必需的，可以放在`<head>` 或 `<body>`中**当JavaScript放在外部文件时，不能包含 `<script>` 标签**，JavaScript 文件的文件扩展名是 .js

5. JavaScript输出4种方式：
    > 使用 `window.alert()` 写入警告框
    > 使用 `document.write()` 写入 HTML 输出**在 HTML 文档完全加载后使用 document.write() 将删除所有已有的 HTML **
    > 使用 `innerHTML` 写入 HTML 元素
    > 使用 `console.log()` 写入浏览器控制台 
例子：  
```js
<script>
window.alert(5 + 6);
alert('hello');
</script>

<script>
document.write(5 + 6);
</script>

<script>
 document.getElementById("demo").innerHTML = 5 + 6;
</script>

<script>
console.log('hello');
</script>

```

6. JavaScript 语句由**值、运算符、表达式、关键词和注释**构成,JavaScript 语句可以用花括号（{...}）组合在代码块中  
例子：  
```js
<script>
function myFunction() {
    console.log('hello');
    console.log('world');
}
</script>
```

7. JavaScript 语句定义两种类型的值：混合值（**字面量（literal）**）和变量值（**变量**）  
变量用于存储数据值  

8. 注释:
    > 单行注释以 // 开头
    > 多行注释以 /* 开头,以 */ 结尾

9. JavaScript 标识符:
    > 所有 JavaScript 变量必须以唯一的名称的标识,这些唯一的名称称为标识符
    > 构造变量名称（唯一标识符）的通用规则是：
        > 名称可包含字母、数字、下划线和美元符号
        > 名称不能以数字开头
        > 名称对大小写敏感
        > 保留字不能用作标识符


10. JavaScript 算数运算符 
 
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


11. JavaScript 赋值运算符    
    运算符	
    > =	
    > +=	
    > -=	
    > *=	
    > /=	
    > %=	

12. JavaScript 比较运算符

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

13. JavaScript 逻辑运算符

    |运算符|描述|
    |---|---|
    |`&&`|逻辑与|
    |  &#124; &#124; |逻辑或|
    |`!`|逻辑非|
    
