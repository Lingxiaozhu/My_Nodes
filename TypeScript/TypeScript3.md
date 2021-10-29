# 接口

接口的作用是为类型命名和我的代码或第三方代码奠定契约  
```js
    interface TypeName{
        name : string;
    }
    function printName(name : TypeName){
        reture name;
    }
    printName("Ling")
```

可选属性

选属性名字定义的后面加一个?符号  


只读属性   

在属性名前用 readonly来指定只读属性  


判断使用const还是readonly，主要判断方法是当变量使用还是当属性使用  

额外的属性检查  
使用`[propName: string]: any;`
