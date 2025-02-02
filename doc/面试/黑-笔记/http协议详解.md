# http协议详解

## 什么是协议

计算机中的协议和现实中的协议是一样的，一式双份/多份，双方/多方都遵从的一个规范，这个规范就可以称之为协议，计算机之所以能全世界互通，协议是功不可没的，如果没有协议，计算机各说各话，根本谁都听不懂谁。

协议类型有：ftp/http/stmp/ppp/tcp/ip等

http既然是一种协议，那么只要满足这种协议，什么工具都可以发送。

## http协议的工作原理

### http请求信息和响应头的格式

请求：

-  请求行
- 请求头信息（key:value）
- 请求主体信息（可以没有）

（头信息结束后和主体信息之间要空一行）

请求行又份3部分

- 请求方法
- 请求路径（url的一部分）
- 所用协议

请求方法

- GET
- POST
- PUT
- DELETE
- TRACE
- OPTIONS
- HEAD

注意：这些请求方式虽然HTTP里规定的，但是web server未必允许或者支持这些方法。

head跟get基本一致，只是不返回内容，比如我们只是确认一个内容（比如照片）还正常存在，不需要返回照片的内容，这时候用head比较合适，trace是你用了代理上网，比如用代理访问百度，想看看代理有没有修改你的http请求，可以用trace来测试一下，百度的服务器会把最后收到的请求返回回来，options是返回服务器可用的请求方法。

响应行分三部分

- 协议版本
- 状态码
- 状态文字

响应头信息

Key:value

Key:value

Content-length:接下来主体的长度

状态码：状态文字

状态码是反映服务器响应情况的。

常见的：

- 200 OK
- 404 NOT FOUND 
- 301/302 永久/临时重定向
- 503 服务器暂时不可用
- 500 服务器内部错误
- 304 未修改（从缓存中取）
- 307 重定向中还保留原始请求数据

状态文字是用来描述状态码的，便于人观察。

