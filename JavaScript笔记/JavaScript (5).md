1. JavaScript 提升（Hoisting）  
    提升（Hoisting）是 JavaScript 将声明移至顶部的默认行为  
    Hoisting 是 JavaScript 将所有声明提升到当前作用域顶部的默认行为（提升到当前脚本或当前函数的顶部）  
    用 let 或 const 声明的变量和常量不会被提升  

2. JavaScript Use Strict  
    "use strict"; 定义 JavaScript 代码应该以“严格模式”执行  
    通过在脚本或函数的开头添加 "use strict"; 来声明严格模式  
    **严格模式中不允许的事项:**
    > 在不声明变量的情况下使用变量，是不允许的  
    > 在不声明对象的情况下使用对象也是不允许的(对象也是变量)  
    > 删除变量（或对象）是不允许的  
    > 删除函数是不允许的  
    > 重复参数名是不允许的  
    > 八进制数值文本是不允许的  
    > 转义字符是不允许的  
    > 写入只读属性是不允许的  
    > 写入只能获取的属性是不允许的  
    > 删除不可删除的属性是不允许的  
    > 字符串 "eval" 不可用作变量  
    > 字符串 "arguments" 不可用作变量  
    > with 语句是不允许的  
    > 处于安全考虑，不允许 eval() 在其被调用的作用域中创建变量  

3. JavaScript this 关键词   
    JavaScript this 关键词指的是它所属的对象  
    **它拥有不同的值，具体取决于它的使用位置：**  
    >在方法中，this 指的是所有者对象  
    >单独的情况下，this 指的是全局对象  
    >在函数中，this 指的是全局对象  
    >在函数中，严格模式下，this 是 undefined  
    >在事件中，this 指的是接收事件的元素  

4. JavaScript Let  
    **全局作用域：**  
    全局（在函数之外）声明的变量拥有全局作用域  
    **函数作用域：**  
    局部（函数内）声明的变量拥有函数作用域  
    **块作用域：**  
    在块 {} 内声明的变量无法从块外访问  

5. JavaScript Const  
    JavaScript const 变量必须在声明时赋值  
    不是真正的常数  
    常量对象可以更改  
    常量数组可以更改  

6. JavaScript 调试  
    console.log() 方法  
    debugger 关键词  

7. JavaScript 最佳实践 
    避免全局变量  
    始终声明局部变量  
    