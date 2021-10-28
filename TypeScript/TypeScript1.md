# 基础类型

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

元组，是一个明确知道数量，明确知道类型数组，该数组之间的元素类型不必相同。  
```js
    //元组定义使用[]，方括号里面写确定类型
    let example : [string,number];
    example = ["Ling",2];//正确
    example = [2,"Ling"];//错误
    //访问已知元素会得到正确的类型
    console.log(example[0].substr(1))//可以拿到string的方法
    console.log(example[1].substr(1))//错误，number类型没有substr方法
    //访问跨界元素，会使用联合类型替代
    example[2] = 6;//类型为（string|number）
```

枚举（enum）为一组数值赋名字，是对JavaScript标准类型的一个补充  
```js
    //定义方法
    enum Color {Red,Green,Blue};
    let example : Color = Color.Blue;
```
默认情况下，枚举元素从0开始编号，可以手动更改，也可以完全手动赋值。  
```js
    enum Color {Red = 1，Green,Blue};
    enum Color {Red = 2, Green = 4 , Blue = 6}
```
枚举可以通过枚举的值的到它的名字
```js
    enum Color {Red,Green,Blue};
    let example : string =Color[2];//如果您给定的数值没有与之对应的枚举项，那么结果就是 undefined
```

**使用枚举时如何定义变量的类型?**

Any 在编译阶段不清楚类型时使用  
any与object的区别：Object类型的变量只是允许你给它赋任意值，但是却不能够在它上面调用任意的方法，即便它真的有这些方法，any类型可以  

Void表示没有任何类型    
声明一个void类型的变量只能为它赋予undefined和null  

Null和Undefined，是所以类型的子类型  

Never表示永远不存在的类型  
注意：Never类型是任何类型的子类型，可以赋给任何类型，但是没有类型是Never的子类型，any也不是。所以除了Never本身外任何类型都不能赋给Never类型 

Object表示非原始类型（number、string、boolean、symbol、null、undefined外的类型）  

类型断言，在你明确知道一个实例，比现有类型更确切的类型时使用  
```js
    // 方法一,使用尖括号
    let example1 : any = 'Ling';
    let example2 : number = (<string>example1).length;

    // 方法二，使用as语法
    let example2 : number = (example1 as string).length;
```
注意：TypeScript里使用JSX时，只有as语法断言是被允许的