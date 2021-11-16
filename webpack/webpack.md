# **webpack学习笔记**
中文文档地址：https://www.webpackjs.com/concepts/    

## 1.概念  
webpack是一个JavaScript应用程序的静态模块打包器（module bundler）  
当webpack处理应用程序时，它会递归地构建一个依赖关系图（dependency graph），其中包含应用程序需要的每个模块，然后将所用的这些模块打包成为一个或者多个bundle  

入口：  
entry指示webpack应该使用哪个模块来作为构建其内部依赖图的开始  
进入入口后webpack会找出哪些模块和库时入口起点（直接和间接）的依赖  

出口：  
output告诉webpack在哪里输出它所创建的bundles，以及如何命名这些文件，默认值为`.dist`  

loader：  
loader让webpack可以处理哪些非JavaScript文件（webpack自身只能理解JavaScript）  
loader可以将所有类型的文件转换为webpack能够理解的有效模块，然后就可以利用webpack的打包能力，对它们进行处理  
本质上，webpack loader将所有类型的文件转换为应用程序的依赖图（和最终的bundle）可以直接引用的模块  
loader有两个属性：`test`和`use`  	 
在定义webpack配置中定义loader时，要定义在module.rules中，而不是rules中  

## 2.入口起点(entry points)  
webpack配置中有多种方式定义`entry`属性  
单个入口（简写）语法：  
用法：`entry :  string | Array <string>`  

对象写法：  
用法：`entry:{ [ entryChunkName : string ] : string | Array <string> }`   

## 3.输出(output)  
output选项可以控制webpack如何向硬盘写入编译文件。即使有多个入口起点，但最终都只能指定一个输出配置  
用法：  
配置output的最低要求是将它设置成一个对象，包括以下两点    
* `filename`用于输出文件的文件名  
* 目标输出目录`path`的绝对路径  

多个入口起点：  
配置创建了多个单独的“chunk”则应该使用占位符（substitutions）来确保每个文件具有唯一的名称  

## 4.模式(mode)  
提供`mode`配置选项，告诉webpack使用对应的模式内置优化  
用法：`mode:development/production`  
只设置`NODE_ENV`，则不会自动设置`mode`    

## 5.loader  
loader用于对模块的源代码进行转换    
loader可以在`import`或加载的时候预处理文件  
loader可以将文件从不同语言转换为JavaScript，或将内联图像转换为data URL  
loader甚至允许你直接在JavaScript模块中`import` CSS文件  

**使用loader：**  
* 配置：在webpack.config.js文件中指定loader  
* 内联：在每个`import`语句中显示指定的loader  
* CLI：在shell命令中指定它们（ CLI：command-line interface，命令行界面）   

配置：`module.rules`允许webpack配置中指定多个loader   
内联：在`import`语句或任何等效于`import`的方式中指定loader，使用`!`将资源中的loader分开，分开的每个部分都相当与当前目录解析  
	尽可能使用 module.rules，因为这样可以减少源码中的代码量，并且可以在出错时，更快地调试和定位 loader 中的问题  
CLI：可以通过CLI使用loader  

loader特性：  
* loader支持链式传递  
* loader可以是同步的，也可以是异步的  
* loader运行在Node.js中，并且能够执行任何可能的操作  
* loader接收查找参数，用于对loader传递配置  
* loader也能够使用`option`对象进行配置  
* 除了使用package.json常见的main属性，还可以将普通的npm模块导出为loader，做法是在package.json里定义一个loader字段  
* 插件（plugin）可以为loader带来更多的特性  
* loader能够产生额外的任意文件  

loader通过（loader）预处理函数，为JavaScript生态系统提供了更多能力    

解析loader：  
loader遵循标准的模块解析  
loader模块需要导出一个函数，并且使用Node.js兼容JavaScript编写  

## 6.插件(plugins)  
插件时webpack的支柱功能  

刨析：  
webpack插件是一个具有`apply`属性的JavaScript对象,`apply`属性会被`webpack compoler`调用，并且compiler对象可在整个编译生命周期访问   

用法：  
插件可以携带参数/选项  

配置：  
webpack.config.js中配置  

## 7.配置(configuration)  
webpack配置是标准的Node.js CommonJS模块：  
* 通过`require(...)`导入其他文件  
* 通过`require(...)`使用npm的工具函数  
* 使用JavaScript控制流表达式  
* 对常用值使用常量或变量  
* 编写并执行函数来生成部分配置  

webpack配置可以用很多格式和风格，但为了自己能够理解和维护，建议始终采用同一种用法、格式、和风格  

## 8.模块(modules)    
在模块化编程中，开发者将程序分解成离散功能块，并称之为模块  
每个模块具有比较完整程序更小的接触面，使得校验、调试、测试轻而易举  

## 9.模块解析(module resolution)   
resolve是一个库（library），用于帮助找到模块的绝对路径  
一个模块可以作为另一个模块的依赖模块，然后被后者引用    

webpack中的解析规则：  
* 绝对路径  
* 相对路径  
* 模块路径  

绝对路径：  
以获取绝对路径，不需要进一步解析  

相对路径：  
需要解析，拿到绝对路径  

模块路径：  
模块将在`resolve.modules`中指定所有的目录内搜索  
