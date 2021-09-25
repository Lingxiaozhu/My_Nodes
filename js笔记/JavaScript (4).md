1. JavaScript 比较和逻辑运算符  
    比较和逻辑运算符用于测试 true 或 false  
    比较运算符：  
    |运算符|  
    |-----|  
    |==|  
    |===|  
    |！=|  
    |！==|  
    |>|  
    |<|  
    |>=|  
    |<=|  

    逻辑运算符：  
    |运算符|描述|  
    |----|---|  
    |&&| 与|  
    | &#124; &#124;|或|  
    |！|非|  

    三元运算符：  
    variablename = (condition) ? value1:value2

2. JavaScript If...Else 语句  
    if语句：  
    ```js
        if (条件) {
            如果条件为 true 时执行的代码
        } 
    ```

    if else语句：  
    ```js 
        if (条件) {
            条件为 true 时执行的代码块
        } else { 
            条件为 false 时执行的代码块
        }
    ```

    else if语句：  
    ```js  
        if (条件 1) {
            条件 1 为 true 时执行的代码块
        } else if (条件 2) {
            条件 1 为 false 而条件 2 为 true 时执行的代码块
        } else {
            条件 1 和条件 2 同时为 false 时执行的代码块
        }
    ```  

3. JavaScript Switch 语句  
    ```js  
        switch(表达式) {
            case n:
                代码块
                break;
            case n:
                代码块
                break;
            default:
                默认代码块
        } 
    ```
    如果 JavaScript 遇到 break 关键词，它会跳出 switch 代码块  
    default 关键词规定不存在 case 匹配时所运行的代码  
    Switch case 使用严格比较（===）  

4. JavaScript For 循环  
    ```js 
        for (语句 1; 语句 2; 语句 3) {
            要执行的代码块
        }
    ```
    JavaScript for/in 语句遍历对象的属性  

5. JavaScript While 循环  
    while 循环会一直循环代码块，只要指定的条件为 true  
    ```js
        while (条件) {
            要执行的代码块
        }
    ```

    Do/While 循环  
    ```js  
        do {
            text += "The number is " + i;
            i++;
        }
        while (i < 100);
    ```

6. JavaScript Break 和 Continue  
    break 语句“跳出”循环  
    continue 语句“跳过”循环中的一个迭代  

7. JavaScript 类型转换  
    `Number()` 转换数值  
    `String()` 转换字符串  
    `Boolean()` 转换布尔值  

    **JavaScript 中有五种可包含值的数据类型：**  
    字符串（string）  
    数字（number）  
    布尔（boolean）    
    对象（object）  
    函数（function）  
    **有三种对象类型：**   
    对象（Object）  
    日期（Date）  
    数组（Array）  
    **同时有两种不能包含值的数据类型：**  
    null  
    undefined  

    可以使用 `typeof` 运算符来确定 JavaScript 变量的数据类型  
    constructor 属性返回所有 JavaScript 变量的构造器函数  

8. JavaScript 正则表达式  
    正则表达式是构成搜索模式的字符序列  
    语法:  
    /pattern/modifiers;  

    |修饰符	|描述|      
    |----|----|  
    | i |执行对大小写不敏感的匹配|  
    |g|执行全局匹配（查找所有）|  
    |m|执行多行匹配|  

    正则表达式模式：   
    |表达式|描述 |  
    |----|----|  
    |[abc]|查找方括号之间的任何字符|  
    |[0-9]|查找任何从 0 至 9 的数字|  
    |(x|y)|查找由 | 分隔的任何选项|  

    元字符:
    拥有特殊含义的字符  
    |元字符|描述|  
    |----|----|  
    |&#124;d|查找数字|  
    |&#124;s|查找空白字符|  
    |&#124;b|匹配单词边界|  
    |&#124;uxxxx|查找以十六进制数 xxxx 规定的 Unicode 字符|  

    Quantifiers 定义量词：  
    |量词|描述|  
    |----|---|  
    |n+	|匹配任何包含至少一个 n 的字符串|  
    |n*	|匹配任何包含零个或多个 n 的字符串|  
    |n?	|匹配任何包含零个或一个 n 的字符串|  


9. JavaScript 错误 - Throw 和 Try to Catch  Finally  
    > try 语句使您能够测试代码块中的错误  
    > catch 语句允许您处理错误  
    > throw 语句允许您创建自定义错误  
    >finally 使您能够执行代码，在 try 和 catch 之后，无论结果如何  

10. JavaScript 作用域  
    作用域指的是您有权访问的变量集合  
    在 JavaScript 中有两种作用域类型：
    > 局部作用域
    > 全局作用域