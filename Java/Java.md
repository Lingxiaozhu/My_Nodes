# 1.了解
## 1.1.Java简介了解
### 1.1.1.安装JSK
1. Java程序必须运行在JVM上，所以需要安装JDK
2. 安装JVM后需要配置环境变量（JAVA_HOME）  

JAVA_HOME的bin里有很多可执行的文件
> java:可行性程序（就是JVM）运行Java程序就是启动JVM，然后让JVM执行指定的编译后的代码  
> javac:编译器，把Java源码文件（以`.java`后缀结尾）编译成Java字节码文件（以`.class`后缀结尾）  
> jar:打包，将一组`.class`文件打包成一个`.jar`文件，方便发布  
> javadoc:生成文档，从Java源码中自动提取注释并自动生成文档  
> jdb:调试器，用于开发阶段的运行调试  

### 1.1.2.一个Java程序
```java
public class Hello{
    //这是一个类，类名是Hello（大小写敏感）public、class是Java的关键词
    public static void main(string[] args){
        //这是一个方法，有一个参数
        System.out.printIn("Hello,world!")；//代码以分号结尾
    }
}
//Java规定public static void main(string[] args)是程序入口
//文件名要与定义的类名相同
```
运行Java程序`.java`->`.class`->Run on JVM  
> 一个Java源码只能定义一个`public`类型的类，并且类名必须与文件名一致  
> 用`javac`可以将`.java`的源码编译成`.class`的字节码文件  
> 使用`java`可以运行一个以编译的Java程序，参数名是类名  

### 1.1.3.Java代码助手
Java代码助手可以在线输入Java代码，然后远程运行结果页面显示  

### 1.1.4.使用IDE
IDE是集成开发环境：Integrated Development Environment  
使用IDE的好处，可以将编写代码、组织项目、编译、运行、调试等放到一个环境中  

## 1.2.Java程序基础
### 1.2.1.基本结构
一个完整的Java程序  
```java
/**
* 可以用来自动创建文档的注释，public是访问修饰符
*/
public class Hello {//Java是面向对象的语言，一个程序的基本单位就是class
    public static void main(String[] args) {//方法定义了一组执行语句，方法内部的代码将会被依次顺序执行
        // 向屏幕输出文本:
        System.out.println("Hello, world!");
        //在方法内部，语句才是真正的执行代码。Java的每一行语句必须以分号结束
        /* 多行注释开始
        注释内容
        注释结束 */
    }
} // class定义结束
```
类名要求：  
* 必须英文字母开头，后可接字母、数字和下划线
* 习惯以大写字母开头  

方法名要求：  
* 必须英文字母开头，后可接字母、数字和下划线
* 首字母小写  

三种注释：  
* 单行注释，以双斜线`//`开头  
* 多行注释以`/*`开头和以`*/`结尾
* 特色的多行注释以`/**`开头和以`*/`结尾,如果有多行，每行通常以星号`*`开头(自动创建文档)
