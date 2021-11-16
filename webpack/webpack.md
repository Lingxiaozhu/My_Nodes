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
