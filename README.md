#### webpack 的构建流程主要有哪些环节？如果可以请尽可能详细描述webpackd打包的整个过程
1.根据配置，识别入口文件
2.逐层识别模块（包括commonJs,AMD,或者ES6的import等，都会被识别分析）
3.webpack主要工作就是分析代码，转换、编译代码
4.打包输出以上步骤编译的代码
webpack 打包过程：
初始化参数  进行编译  确定入口  编译模块 完成模块编译并且输出

#### Loader 和 Plugin 有哪些不同？请描述一下开发Loader和Plugin的思路
什么是Loader ：
loader 是文件加载器 能够加载资源文件 并对这些文件进行一些处理 诸如编译 压缩等 最终一起打包到指定的文件中。处理一个文件可以使用多个loader loader的执行顺序是相反的，即最后一个loader最先执行，第一个loader最后执行。第一个执行的loader 接收源文件内容为参数，其他loader 接收前一个执行的loader的返回值作为参数，最后执行的loader会返回此模块的JS源码。
什么是Plugin:
在webpack运行的生命周期中会产生许多时间，plugin可以监听这些事件 在合适的时机通过webpack提供的API改变输出的结果。
两者之间的区别：
对于loader是一个转换器， 将A文件编译转换为B文件
plugin 是一个扩展器 丰富了webpack本身，针对loader结束后，webpack打包的整个过程，它并不直接操作文件，会监听webpack打包过程中的某些节点，执行广泛的任务。
