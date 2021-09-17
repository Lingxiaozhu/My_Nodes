1. JavaScript 赋值运算符
    |运算符|
    |---|
    |=|
    |+=|
    |-=|
    |*=|
    |/=|
    |%=|
    |**=|

2. JavaScript 数据类型
    string  
    number  
    boolean  
    undefined  
    null  
    function  
    object  
    Undefined 与 null 的值相等，但类型不相等

3. JavaScript 函数  
    函数通过 function 关键词进行定义，其后是函数名和括号 ()

4. JavaScript 对象  
    通过{}来定义  
    有两种方法访问属性：  
        > objectName.propertyName  
        > objectName["propertyName"]  

5. 常见的 HTML 事件  
    onchange、onclick、onmouseover、onmouseout、onkeydown、onload  

6. JavaScript 字符串  
    可以使用单引号或双引号  
    内建属性 length 可返回字符串的长度  
        例子：  
        var sln = txt.length;  
    反斜杠转义字符把特殊字符转换为字符串字符  
    字符串可通过关键词 new 定义为对象  

7. JavaScript 字符串方法  
    length 属性返回字符串的长度  
    indexOf() 方法返回字符串中指定文本首次出现的索引（位置）  
    lastIndexOf() 方法向后进行检索（从尾到头）  
    search() 方法搜索特定值的字符串，并返回匹配的位置  
    有三种提取部分字符串的方法：  
        >  slice()  
        >  substring()  
        >  substr()   
    替换字符串内容:  
    replace() 方法  
    replace() 方法不会改变调用它的字符串,它返回的是新字符串  
    默认地，replace() 只替换首个匹配  
    replace() 对大小写敏感  
    可以结合正则表达式一起使用  
    转换为大写和小写：  
        > toUpperCase() 把字符串转换为大写  
        > toLowerCase() 把字符串转换为小写  
    concat() 连接两个或多个字符串  
    trim() 方法删除字符串两端的空白符  
    提取字符串字符：  
        > charAt()   
        > charCodeAt()  

8. JavaScript 数字  
    JavaScript 数值始终是 64 位的浮点数  
    整数（不使用指数或科学计数法）会被精确到 15 位  
    NaN 属于 JavaScript 保留词，指示某个数不是合法数  
    在数学运算中使用了NaN，则结果也将是 NaN  
    Infinity （或 -Infinity）是在计算数时超出最大可能数范围时返回的值  

9. JavaScript 数值方法  
    toString() 以字符串返回数值    
    toExponential() 返回字符串值，它包含已被四舍五入并使用指数计数法的数字   
    toFixed() 返回字符串值，它包含了指定位数小数的数字  
    toPrecision() 返回字符串值，它包含了指定长度的数字  
    valueOf() 以数值返回数值  
    将变量转换为数字的方法：
        > Number() 方法  
        > parseInt() 方法  
        > parseFloat() 方法  
    MAX_VALUE 返回 JavaScript 中可能的最大数字  

10. JavaScript 数组  
    数组用于在单一变量中存储多个值  
    数组是对象  
    数组属性和方法:  
        > length 属性  
    可以使用 Array.foreach() 函数  
    向数组添加新元素的最佳方法是使用 push() 方法   
    判断是否是数组： Array.isArray()  
     