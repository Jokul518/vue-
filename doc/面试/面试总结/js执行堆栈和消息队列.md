栈

JavaScript是单线程语言，主线程执行同步代码。 
函数调用时， 便会在内存形成了一个“调用记录”， 又称“调用帧”， 保存调用位置和内部变量等信息。 如果函数内部还调用了其他函数，那么在调用记录上方又会形成一个调用记录， 所有的调用记录就形成一个“调用栈”。

（尾调用、尾递归优化）

堆

对象被分配在一个堆中，一个用以表示一个内存中大的未被组织的区域。

消息队列与事件循环Event Loop

一个 JavaScript 运行时包含了一个待处理的消息队列（异步任务），（内部是不进入主线程，而进入”任务队列”（task queue）的任务。比如UI事件、ajax网络请求、定时器setTimeout和setInterval等。 
每一个消息都与一个函数（回调函数callback）相关联。当栈为空时，从队列中取出一个消息进行处理。这个处理过程包含了调用与这个消息相关联的函数（以及因而创建了一个初始堆栈帧）。当栈再次为空的时候，也就意味着消息处理结束。

这个过程是循环不断的，所以整个的这种运行机制又称为Event Loop（事件循环）。

小结

JS是单线程， 主线程执行同步代码， 事件、I/O操作等异步任务，将会进入任务队列执行，异步执行有结果之后，就会变为等待状态， 形成一个先进先出的执行栈，主线程的同步代码执行完之后，再从”任务队列”中读取事件， 执行事件异步任务的回调。 
这就是为什么执行顺序是， 同步 > 异步 > 回调 
##### 总结：只要主线程空了（同步），就会去读取”任务队列”（异步），这就是JavaScript的运行机制。
<https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/EventLoop>