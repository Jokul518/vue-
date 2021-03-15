

# WebAssembly

> WebAssembly 或者 wasm 是一个可移植、体积小、加载快并且兼容 Web 的全新格式

## 简介

WebAssembly是一种运行在现代网络浏览器中的新型代码，并且提供新的性能特性和效果。它设计的目的不是为了手写代码而是为诸如C、C++和Rust等低级源语言提供一个高效的编译目标。对于前端来说，它能让客户端APP提供了一种在网络平台以接近本地运行多种编写语言的代码形式，并且性能达到本地原生性能。

例如我们使用c++、C、Rust等语言去编写，然后编译成WASM，丢给浏览器去运行，而浏览器会将它当成一个模块去运行。但是它的使用场合还是比较局限的，针对于前端来说，我们使用JavaScript去编写已经是足够了。但当我们对某些内容性能要求非常高的时候，比如说一些游戏、绘制比较复杂的canvas时它背后复杂的计算逻辑（它会拖慢图形绘制的界面）等场景是可以使用WebAssembly来提高性能。

## 特点

#### 高效

WebAssembly有一套完整的语义，实际上WebAssembly是体积小且加载快的二进制格式，其目标就是充分发挥硬件能力以达到原生执行效率。

#### 安全

WebAssembly 运行在一个沙箱化的[执行环境](https://www.wasm.com.cn/docs/semantics/#linear-memory)中，甚至可以在现有的 JavaScript 虚拟机中实现。在[web环境中](https://www.wasm.com.cn/docs/web/)，WebAssembly将会严格遵守同源策略以及浏览器安全策略。

#### 开发

WebAssembly是一门低阶语言，设计了一个非常规整的文本格式用来调试、测试、实验、优化、学习、教学或者编写程序。可以以这种文本格式在web页面上查看WebAssembly模块的源码。

#### 标准

WebAssembly在web中被设计成无版本、特性可测试、向后兼容的。WebAssembly可以被JavaScript调用，进行JavaScript的上下文，也可以想Web API一样调用浏览器的功能。当然，WebAssembly不仅可以运行在浏览器上，也可以运行在非web环境下。

##  底层的机制和原理

wasm的代码执行过程比js的执行过程短

JS  代码 ☞ V8引擎中，Parse语法解析 ☞ Complier编译成可执行的，比如说JIT ☞运行☞GC GC的工作线程和js的执行线程是不一样的 GC的时候。js的执行线程就会暂停

wasm将解析和编译的一部分工作进行前置到开发阶段，js的是解析和编译是在运行时进行的，这也是拖慢了js执行的一个原因。然后js的GC会造成js的执行卡顿，而wasm是没有GC的，它是随时回收的，不会影响js的执行。





[官方中文网站](https://www.wasm.com.cn/)



https://ke.qq.com/webcourse/index.html#cid=1647350&term_id=102813387&taid=10959330611897078&type=1024&vid=5285890809759641120



https://ke.qq.com/webcourse/index.html#cid=413448&term_id=103178285&taid=10190368255921928&type=1024&vid=5285890811888457213



https://ke.qq.com/webcourse/369301/100439493#taid=3010613161075349&vid=5285890790550590766
