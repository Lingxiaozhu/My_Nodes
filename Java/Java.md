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

### 1.2.2.变量和数据类型
两种变量：
1. 基本类型的变量  
2. 引用类型的变量

变量必须先定义后使用，可以定义的时候赋初始值  
```java
int a=1;
int b;//默认值0
```
变量的重要特点是可以重新赋值  
基本数据类型是CPU可以直接进行运算的类型  

Java的基本数据类型：  
* 整数类型： byte(1)，shot(2)，int(4)，long(8)  
* 浮点数类型： float(4)，double(8)  
* 字符类型： char(2)  
* 布尔类型： boolean(1或4) 

计算机内存最小的存储单元是字节（byte），一个字节就是一个8位的二进制数，即8个bit。它的二进制表示范围从`00000000-11111111`,换算成十进制`0-255`,换算成十六进制`00-ff`  
Java语言对布尔类型的存储并没有做规定，因为理论上存储布尔类型只需要1 bit，但是通常JVM内部会把boolean表示为4字节整数  

### 1.2.3.整数运算  
Java的整数运算遵循四则运算规则，可以任意嵌套小括号  
整数的数值是精确的，而且整数运算也是永远精确的  
整数存在范围，超出就会溢出  
整数的简写运算符：`+=`、`-+`、`*=`、`/=`  
自增/自减运算：`++`、`--`  
位运算：在计算机中，整数总是以二进制的形式表示`<<`、`>>`  
`byte`和`short` 类型进行位于时，会先转换为`int`类型再位移  
左移就是不断承2，右移就是不断除2  
位运算：与 `&` 、或 `|` 、非  ` 、异或 ^    
类型自动提升，运算时两个数类型不一致，就会自动转换为较大的整数类型  
类型强制转换:使用`（类型）`    
应该选择合适范围的整型（int或long），没有必要为了节省内存而使用byte和short进行整数运算  

### 1.2.4.浮点数运算  
浮点数只能进行加减乘除这些运算，不能进行位运算或者位移运算  
浮点数往往无法精确表示  
由于浮点数存在运算误差，所以比较时常常会出现错误的结果，正确的比较方法是比较两个浮点数之差的绝对值是否小于一个很小的数  
类型提升：参与运算的两个数其中一个是整数，那么整数会自动提升为浮点数。但在复杂的运算中不会提升    
溢出：整数除0时会报错，但浮点数除0时不会报错，会返回特殊的值：  
* `Nan`表示Not aNumber  
* `Infinity` 表示无穷大  
* `-Infinity` 表示无穷小  
强制类型转换：浮点数可以强制转换为整数，转换时小数部分会忽略，如果转换后超出了整数最大的表示范围，将返回整数的最大值   

### 1.2.5.布尔运算  
布尔类型：`true`、`false`  
布尔运算是一种关系运算  
关系运算：  
* 比较运算符： `>` , `>=` , `<` , `<=` , `==` , `!=`  
* 与运算：`&&`  
* 或运算：`||`  
* 非运算：`!`  

短路运算:与和或是短路运算  
三元运算符：`b ? X : Y`，类型必须相同，同时三元运算也是短路运算    

### 1.2.6.字符和字符串
字符和字符串是两个不同的类型  
字符类型：  
* 字符类型`char`是基本的数据类型  
* 一个`char`保存一个Unicode字符  
字符串类型：
字符串类型`string`是引用类型，用"..."表示  
转义字符`/`  
字符串连接：`+`  
用`+`链接字符串和其他类型的数据，会将其他类型的数据自动转型为字符串  
使用"""..."""表示多行字符串  
Java字符串除了是一个引用类型外，还用一个重要的特点是字符串不可变  
引用类型的变量可以是空值`null`   
空值`null`和空字符串`""`不同  

### 1.2.7.数组类型
Java数组的特点：  
*  数组所有元素初始化为默认值，整数都是0，浮点数都是0.0，布尔型都是false  
* 数组一旦创建后大小无法改变  
可以通过`数组变量.length`获取数组的大小  
数组是引用类型，在使用索引访问数组的时候，如果索引的值超出范围，运行时就会报错  
数组元素可以是值类型或引用类型，但数组本身是引用类型  

## 1.3.流程控制 
### 1.3.1.输入和输出  
输出：  
`System.out.println()`向屏幕输出内容，`println`是print line的缩写，表示输出并换行，不换行用`print`  
输入：  
Java提供Scanner对象来方便输入，读取对应的类型可以使用：`scanner.nextLine() / nextInt() / nextDouble()`  


### 1.3.2.if判断  
`if... else`可以做条件判断，else是可选的  
浮点数判断相等不能直接用==运算符   

### 1.3.3.switch多重选择  
`switch`语句可以做多重选择，然后执行匹配的`case`语句后续代码  
`switch`的计算结果必须是整型、字符串或枚举类型   
注意千万不要漏写`break`，建议打开`fall-through`警告
### 1.3.4.while循环  
`while`循环先判断循环条件是否满足，再执行循环语句  

### 1.3.5.do.while循环  
`do while`循环先执行循环，再判断条件   
`do while`循环会至少执行一次  

### 1.3.6.for循环  
`for`循环的用法是  
```java
for (初始条件; 循环检测条件; 循环后更新计数器) {
    // 执行语句
}
```
### 1.3.7.break和continue  
`break`语句跳出当前循环  
`ontinue`则是提前结束本次循环，直接继续执行下次循环  

## 1.4.数组操作
### 1.4.1.遍历数组   
遍历数组使用for循环  
使用`Arrays.toString()`可以快速获取数组内容  

### 1.4.2.数组排序  
常用的排序算法有冒泡排序、插入排序和快速排序等   
可以直接使用Java标准库提供的`Arrays.sort()`进行排序  
对数组排序会直接修改数组本身  

### 1.4.3.多维数组  
打印多维数组可以使用`Arrays.deepToString()`  
最常见的多维数组是二维数组，访问二维数组的一个元素使用`array[row][col]`  

### 1.4.4.命令行参数
Java程序的入口是main方法，而main方法可以接受一个命令行参数，它是一个`String[]`数组  
命令行参数由JVM接收用户输入并传给main方法  

# 2.面向对象编程
## 2.1.面向对象基础  
### 2.1.1.方法  
定义方法的语法是：  
```java
修饰符 方法返回类型 方法名(方法参数列表) {
    若干方法语句;
    return 方法返回值;
}
```
方法可以让外部代码安全地访问实例字段   
方法内部遇到return时返回，void表示不返回任何值（注意和返回null不同）  
外部代码通过public方法操作实例，内部代码可以调用private方法  

### 2.1.2.构造方法  
实例在创建时通过new操作符会调用其对应的构造方法，构造方法用于初始化实例  
可以在一个构造方法内部调用另一个构造方法，便于代码复用  

### 2.1.3.方法重载
方法重载是指多个方法的方法名相同，但各自的参数不同  
重载方法返回值类型相同  

### 2.1.4.继承  
继承是面向对象编程的一种强大的代码复用方式  
子类的构造方法可以通过super()调用父类的构造方法  

### 2.1.5.多态  
子类可以覆写父类的方法（Override），覆写在子类中改变了父类方法的行为  
Java的方法调用总是作用于运行期对象的实际类型，这种行为称为多态  

### 2.1.6.抽象类
通过abstract定义的方法是抽象方法，它只有定义，没有实现。抽象方法定义了子类必须实现的接口规范  
定义了抽象方法的class必须被定义为抽象类，从抽象类继承的子类必须实现抽象方法  

### 2.1.7.接口  
Java的接口（interface）定义了纯抽象规范，一个类可以实现多个接口  
接口也是数据类型，适用于向上转型和向下转型   
接口的所有方法都是抽象方法，接口不能定义实例字段  

### 2.1.8.静态字段和静态方法  
静态字段属于所有实例“共享”的字段，实际上是属于class的字段  
调用静态方法不需要实例，无法访问this，但可以访问静态字段和其他静态方法  

### 2.1.9.包
Java内建的package机制是为了避免class命名冲突  
JDK的核心类使用java.lang包，编译器会自动导入  

### 2.1.10.作用域  
Java内建的访问权限包括public、protected、private和package权限  
Java在方法内部定义的变量是局部变量，局部变量的作用域从变量声明开始，到一个块结束  
final修饰符不是访问权限，它可以修饰class、field和method  
一个.java文件只能包含一个public类，但可以包含多个非public类  

### 2.1.11.内部类  
Java的内部类可分为Inner Class、Anonymous Class和Static Nested Class三种  
Inner Class和Anonymous Class本质上是相同的，都必须依附于Outer Class的实例，即隐含地持有Outer.this实例，并拥有Outer Class的private访问权限  
Static Nested Class是独立类，但拥有Outer Class的private访问权限  

### 2.1.12.classpath和jar
JVM通过环境变量classpath决定搜索class的路径和顺序  
MANIFEST.MF文件可以提供jar包的信息，如Main-Class，这样可以直接运行jar包  

### 2.1.13.模块
使用模块可以按需打包JRE  

## 2.2.Java核心类
### 2.2.1.字符串和编码
Java字符串String是不可变对象  
字符串操作不改变原字符串内容，而是返回新字符串  
常用的字符串操作：提取子串、查找、替换、大小写转换等  
Java使用Unicode编码表示String和char   
转换编码就是将String和byte[]转换，需要指定编码  

### 2.2.2.StringBuilder
StringBuilder是可变对象，用来高效拼接字符串  
StringBuilder可以支持链式操作，实现链式操作的关键是返回实例本身  
StringBuffer是StringBuilder的线程安全版本，现在很少使用  

### 2.2.3.StringJoiner
用指定分隔符拼接字符串数组时，使用StringJoiner或者String.join()更方便  

### 2.2.4.包装类型
Java核心库提供的包装类型可以把基本类型包装为class  
自动装箱和自动拆箱都是在编译期完成的  
装箱和拆箱会影响执行效率，且拆箱时可能发生NullPointerException  
包装类型的比较必须使用equals()  
整数和浮点数的包装类型都继承自Number  

### 2.2.5.JavaBean
JavaBean是一种符合命名规范的class，它通过getter和setter来定义属性  
可以利用IDE快速生成getter和setter  
使用Introspector.getBeanInfo()可以获取属性列表  

### 2.2.6.枚举类
Java使用enum定义枚举类型，它被编译器编译为final class Xxx extends Enum { … }  
通过name()获取常量定义的字符串，注意不要使用toString()  
通过ordinal()返回常量定义的顺序（无实质意义）  
可以为enum编写构造方法、字段和方法  
enum的构造方法要声明为private，字段强烈建议声明为final  

### 2.2.7.记录类
Java 14开始，提供新的record关键字，可以非常方便地定义Data Class  
使用record定义的是不变类  
可以编写Compact Constructor对参数进行验证  
可以定义静态方法  

### 2.2.8.BigInteger
BigInteger用于表示任意大小的整数  
BigInteger是不变类，并且继承自Number  
将BigInteger转换成基本类型时可使用longValueExact()等方法保证结果准确

### 2.2.9.BigDecimal
BigDecimal用于表示精确的小数  
BigDecimal用于表示精确的小数，常用于财务计算  

# 3.异常处理 
## 3.1.Java异常
Java使用异常来表示错误，并通过try ... catch捕获异常  
Java的异常是class，并且从Throwable继承

## 3.2.捕获异常  
多个catch语句的匹配顺序非常重要，子类必须放在前面  
多个catch语句的匹配顺序非常重要，子类必须放在前面  
一个catch语句也可以匹配多个非继承关系的异常  

## 3.3.抛出异常  
调用printStackTrace()可以打印异常的传播栈，对于调试非常有用  
捕获异常并再次抛出新的异常时，应该持有原始异常信息  

## 3.4.自定义异常  
推荐从RuntimeException派生“根异常”，再派生出业务异常

## 3.5.NullPointerException   
NullPointerException是Java代码常见的逻辑错误，应当早暴露，早修复   
NullPointerException是Java代码常见的逻辑错误，应当早暴露，早修复  

## 3.6.使用断言  
断言是一种调试方式，断言失败会抛出AssertionError，只能在开发和测试阶段启用断言   

## 3.7.使用JDK Logging  
日志是为了替代System.out.println()，可以定义格式，重定向到文件等  
Java标准库提供了java.util.logging来实现日志功能

## 3.8. 使用Commons Logging  
Commons Logging是使用最广泛的日志模块  
Commons Logging的API非常简单  
Commons Logging可以自动检测并使用其他日志模块

## 3.9. 使用Log4j
通过Commons Logging实现日志，不需要修改代码即可使用Log4j  
使用Log4j只需要把log4j2.xml和相关jar放入classpath  
如果要更换Log4j，只需要移除log4j2.xml和相关jar  

## 3.10.使用SLF4J和Logback
SLF4J和Logback可以取代Commons Logging和Log4j  
始终使用SLF4J的接口写入日志，使用Logback只需要配置，不需要修改代码  

# 4.反射
## 4.1.Class类  
JVM为每个加载的class及interface创建了对应的Class实例来保存class及interface的所有信息  
获取一个class对应的Class实例后，就可以获取该class的所有信息  
通过Class实例获取class信息的方法称为反射（Reflection）  
JVM总是动态加载class，可以在运行期根据条件来控制加载class  

## 4.2.访问字段  
Java的反射API提供的Field类封装了字段的所有信息  
通过Class实例的方法可以获取Field实例：getField()，getFields()，getDeclaredField()，getDeclaredFields()  
通过Field实例可以获取字段信息：getName()，getType()，getModifiers()  
通过Field实例可以读取或设置某个对象的字段，如果存在访问限制，要首先调用setAccessible(true)来访问非public字段  
通过反射读写字段是一种非常规方法，它会破坏对象的封装  

## 4.3.调用方法  
通过Class实例的方法可以获取Method实例：getMethod()，getMethods()，getDeclaredMethod()，getDeclaredMethods()  
通过Method实例可以获取方法信息：getName()，getReturnType()，getParameterTypes()，getModifiers()  
通过Method实例可以调用某个对象的方法：Object invoke(Object instance, Object... parameters)  
通过设置setAccessible(true)来访问非public方法  

## 4.4.调用构造方法  
Constructor对象封装了构造方法的所有信息  
通过Class实例的方法可以获取Constructor实例：getConstructor()，getConstructors()，getDeclaredConstructor()，getDeclaredConstructors()  
通过Constructor实例可以创建一个实例对象：newInstance(Object... parameters)； 通过设置setAccessible(true)来访问非public构造方法  


## 4.5.获取继承关系  
通过Class对象可以获取继承关系：Class getSuperclass()：获取父类类型,Class[] getInterfaces()：获取当前类实现的所有接口    
通过Class对象的isAssignableFrom()方法可以判断一个向上转型是否可以实现

## 4.6.动态代理  
Java标准库提供了动态代理功能，允许在运行期动态创建一个接口的实例  
动态代理是通过Proxy创建代理对象，然后将接口方法“代理”给InvocationHandler完成的  

# 5.注解  
注解（Annotation）是Java语言用于工具处理的标注  
如果参数名称是value，且只有一个参数，那么可以省略参数名称   
Java使用@interface定义注解  
可定义多个参数和默认值，核心参数使用value名称  
可定义多个参数和默认值，核心参数使用value名称  
可以在运行期通过反射读取RUNTIME类型的注解，注意千万不要漏写@Retention(RetentionPolicy.RUNTIME)，否则运行期无法读取到该注解 


# 6.泛型  
## 6.1.什么是泛型  
泛型就是编写模板代码来适应任意类型  
泛型的好处是使用时不必对类型进行强制转换，它通过编译器对类型进行检查  
注意泛型的继承关系：可以把ArrayList<Integer>向上转型为List<Integer>（T不能变！），但不能把ArrayList<Integer>向上转型为ArrayList<Number>（T不能变成父类）  

## 6.2.使用泛型  
泛型就是编写模板代码来适应任意类型   

## 6.3.编写泛型  
编写泛型时，需要定义泛型类型<T>  
静态方法不能引用泛型类型<T>，必须定义其他类型（例如<K>）来实现静态泛型方法  
泛型可以同时定义多种类型，例如Map<K, V>  

## 6.4.擦拭法  
Java的泛型是采用擦拭法实现的  
擦拭法决定了泛型<T>  
子类可以获取父类的泛型类型<T>  

## 6.5.extends通配符  
使用extends通配符表示可以读，不能写  

## 6.6.super通配符  
super通配符表示只能写不能读  
extends和super通配符要遵循PECS原则

## 6.7.泛型与反射  
部分反射API是泛型  

# 7.集合  
## 7.1.Java集合简介   
Java的集合类定义在java.util包中，支持泛型，主要提供了3种集合类，包括List，Set和Map。Java集合使用统一的Iterator遍历，尽量不要使用遗留接口  

## 7.2.使用List  
List是按索引顺序访问的长度可变的有序表，优先使用ArrayList而不是LinkedList  
List可以和Array相互转换  

## 7.3.编写equals方法  
在List中查找元素时，List的实现类通过元素的equals()方法比较两个元素是否相等，因此，放入的元素必须正确覆写equals()方法，Java标准库提供的String、Integer等已经覆写了equals()方法  

## 7.4.使用Map  
Map是一种映射表，可以通过key快速查找value  
可以通过for each遍历keySet()，也可以通过for each遍历entrySet()，直接获取key-value  
最常用的一种Map实现是HashMap  

## 7.5.编写equals和hashCode  
要正确使用HashMap，作为key的类必须正确覆写equals()和hashCode()方法  

## 7.6.使用EnumMap  
Map的key是enum类型，使用EnumMap，既保证速度，也不浪费空间  
使用EnumMap的时候，应持有Map接口  

## 7.7.使用TreeMap  
SortedMap的Key必须实现Comparable接口，或者传入Comparator  

## 7.8.使用Properties  
Java集合库提供的Properties用于读写配置文件.properties。.properties文件可以使用UTF-8编码  
读写Properties时，注意仅使用getProperty()和setProperty()方法，不要调用继承而来的get()和put()等方法  


## 7.9.使用Set  
Set用于存储不重复的元素集合  
利用Set可以去除重复元素  

## 7.10.使用Queue  
队列Queue实现了一个先进先出（FIFO）的数据结构  
要避免把null添加到队列  

## 7.11.使用PriorityQueue  
PriorityQueue实现了一个优先队列：从队首获取元素时，总是获取优先级最高的元素  

## 7.12.使用Deque  
Deque实现了一个双端队列  

## 7.13.使用Stack  
栈（Stack）是一种后进先出（LIFO）的数据结构  

## 7.14.使用Iterator  
Iterator是一种抽象的数据访问模型  

## 7.15.使用Collections
Collections类提供了一组工具方法来方便使用集合类：  
* 创建空集合  
* 创建单元素集合  
* 创建不可变集合  
* 排序／洗牌等操作  

# 8. IO  
## 8.1. File对象  
Java标准库的java.io.File对象表示一个文件或者目录  

## 8.2. InputStream   
Java标准库的java.io.InputStream定义了所有输入流的超类

## 8.3. OutputStream 
Java标准库的java.io.OutputStream定义了所有输出流的超类

## 8.4. Filter模式   
Java的IO标准库使用Filter模式为InputStream和OutputStream增加功能

## 8.5. 操作Zip 
ZipInputStream可以读取zip格式的流，ZipOutputStream可以把多份数据写入zip包  
配合FileInputStream和FileOutputStream就可以读写zip文件  

## 8.6. 读取classpath资源   
资源存储在classpath中可以避免文件路径依赖  

## 8.7. 序列化   
可序列化的Java对象必须实现java.io.Serializable接口，类似Serializable这样的空接口被称为“标记接口”（Marker Interface）  

## 8.8. Reader   
Reader定义了所有字符输入流的超类   

## 8.9. Writer 
Writer定义了所有字符输出流的超类  
使用try (resource)保证Writer正确关闭   
Writer是基于OutputStream构造的，可以通过OutputStreamWriter将OutputStream转换为Writer，转换时需要指定编码  

## 8.10. PrintStream和PrintWriter   
PrintStream是一种能接收各种数据类型的输出，打印数据时比较方便  
PrintWriter是基于Writer的输出  

## 8.11. 使用Files   
简单的小文件读写操作，可以使用Files工具类简化代码  

# 9.日期与时间  
## 9.1.基本概念
计算机通过Locale来针对当地用户习惯格式化日期、时间、数字、货币等  

## 9.2.Date和Calendar
Java有两套日期和时间的API，分别位于java.util和java.time包中  

## 9.3.LocalDateTime
LocalDateTime可以非常方便地对日期和时间进行加减，或者调整日期和时间，它总是返回新对象  

## 9.4.ZonedDateTime
ZonedDateTime是带时区的日期和时间，可用于时区转换  
ZonedDateTime是带时区的日期和时间，可用于时区转换

## 9.5.DateTimeFormatter
对ZonedDateTime或LocalDateTime进行格式化，需要使用DateTimeFormatter类  

## 9.6.Instant
Instant表示高精度时间戳，它可以和ZonedDateTime以及long互相转换  

# 10.单元测试  
## 10.1.编写JUnit测试
JUnit是一个单元测试框架  

## 10.2.Fixture
Fixture是指针对每个@Test方法，编写@BeforeEach方法用于初始化测试资源，编写@AfterEach用于清理测试资源  

## 10.3.异常测试
测试异常使用assertThrows()，期待捕获到指定类型的异常  

## 10.4.条件测试
条件测试是根据某些注解，在运行期让JUnit自动忽略某些测试

# 11.正则表达式  
## 11.1.正则表达式简介
正则表达式是用字符串描述的一个匹配规则  


# 12.加密与安全  
## 12.1.编码算法
URL编码和Base64编码都是编码算法，它们不是加密算法   
Base64编码的目的是把任意二进制数据编码为文本，但编码后数据量会增加1/3。

## 12.2.哈希算法
哈希算法可用于验证数据完整性，具有防篡改检测的功能  

## 12.3.BouncyCastle
BouncyCastle提供了很多Java标准库没有提供的哈希算法和加密算法  

# 13.多线程  

# 14.Maven基础

# 15.网络编程

# 16.XML与JSON

# 17.JDBC编程

# 18.函数式编程

# 19.设计模式

# 20.Web开发

# 21.Spring开发

# 22.Spring Boot开发

# 23.Spring Cloud开发
