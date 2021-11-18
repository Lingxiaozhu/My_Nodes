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
