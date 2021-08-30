### 原理
基于 Google V8 引擎的 JavaScript 运行时环境，同时结合 Libuv 扩展了 JavaScript 功能，使之支持 io、fs 等只有语言才有的特性，使得 JavaScript 能够同时具有 DOM 操作(浏览器)和 I/O、文件读写、操作数据库(服务器端)等能力，是目前最简单的全栈式语言。
- JavaScript为单线程，通过node构建机制，通过异步来解决并发问题

### 用途
后端开发、前端库开发（vue、react、webpack）

### 优点
Node.js通常被用来开发低延迟的网络应用，也就是那些需要在服务器端环境和前端实时收集和交换数据的应用（API、即时聊天、微服务）。

### 缺点
    - 回调太多难于控制（俗称回调地狱）------Callback、Promise 到 Async函数
    - CPU 密集任务处理的不是很好。
    
### 架构
Node.js 是基于 Chrome V8引擎构建的，采用 C/C++ 编写，由事件循环（Event Loop）分发 I/O 任务，最终工作线程（Work Thread）将任务丢到线程池（Thread Pool）里去执行，而事件循环只要等待执行结果就可以了。
![image](https://github.com/destinyoung/Node/blob/main/img/12451299-5ab469048a470_fix732.png)

在Node.js Bindings层做的事儿就是将 Chrome V8 等暴露的 C/C++ 接口转成JavaScript Api，并且结合这些 Api 编写了 Node.js 标准库，所有这些 Api 统称为 Node.js SDK
