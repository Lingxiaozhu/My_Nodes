TypeScript是JavaScript的超集，用于补充JavaScript作为弱类型脚本语言的弱点，及增加静态类型标注。  

TypeScript拥有12种基本类型，分别是布尔值（Boolean）、数字（Number）、字符串（String）、数组、元组、枚举、Any、Void、Null、undefined、Never、Object。  

布尔值（Boolean）是最基本的数据类型，就是true/false。定义的方法为：  
```js
    let example1 : boolean = true;
    let example2 : boolean = false;
    //在声明变量的后面定义类型
```

数字（Number）和JavaScript一样都是浮点数，支持十进制、十六进制、二进制、八进制，其类型都是Number：
```js
    let example1 : number = 2;//十进制
    let example2 : number = 0xffff;//十六进制
    let example3 : number = 0b1212;//二进制
    let example4 : number = 0o5566;//八进制
```

字符串（String），和JavaScript一样可以使用单引号或者双引号表示字符串
```js
    let example1 : string = "Lingxiaozhu;";
    let example2 : string = 'Lingxiaozhu';
```
也可以使用模板字符串，模板字符串定义多行文本和内嵌表达式，这种表达式被反引号包围，以${example}形式嵌入表达式  
```js
    let example1 : string = `Ling`;
    let example2 : string = `my first Name is ${example1}`;
    //等价于
    let example3 : string = 'my first Name' + example1;
```

数组有两种方式定义：  
第一种：元素类型后面接[]  
```js
    let example : number[] = [1,2,3];
```
第二种：使用数组**泛型**：Array<number>  
```js
    let example : Array<number> = [1,2,3]
```

