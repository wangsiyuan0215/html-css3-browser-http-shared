---
level: 2
---

# HTTP

_Q. 什么是 HTTP？_

<v-click>

简单来说，HTTP 是一种用作获取诸如 HTML 文档这类资源的协议，它是无状态的。

[点击这里你会了解的更多](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Overview)

</v-click>

<v-click>

_Q. 无状态是什么意思？_

</v-click>

<v-click>

在同一个连接中，两个执行成功的请求之间是没有关系的。

这就带来了一个问题，用户没有办法在同一个网站中进行连贯的交互，比如在电商网站中使用购物车功能。

尽管 HTTP 根本上来说是无状态的，但借助 HTTP Cookie 就可使用有状态的会话。

</v-click>

---
level: 2
hideInToc: true
---

# HTTP 版本的演变

<v-clicks>

- HTTP/0.9：**只有 GET 请求**，且无状态，每次请求都需要重新建立连接、释放连接。
- HTTP/1.0：
  - 支持 **POST、PUT、DELETE** 等方法，同时新增了**请求头和响应头**;
  - 不再局限于纯文本，扩充了传输内容的格式。
- HTTP/1.1：
  - **长连接**：复用 TCP 连接，保持连接不断开；
  - **管道化**：基于长连接，异步发送请求，但是响应的顺序按照请求顺序返回；
  - 缓存；
  - 断点传输；
- HTTP/2.0：
  - 二进制**分帧**：将传输的信息分割为更小的帧，并采用二进制进行编码；
  - 多路复用：在复用的 TCP 连接上同时发送请求和接收数据；
  - 头部压缩：差量更新头部信息；
  - **服务器推送**（融合了 websocket）；

</v-clicks>

---
level: 2
hideInToc: true
---

# HTTP _vs_ HTTPS

_Q. HTTP 和 HTTPS 有什么区别？_

<v-click>

- HTTP 是**明文传输**，不安全；
- HTTPS 是**加密传输**，它使用 SSL 或 TLS 协议来加密客户端和服务器之间所有的通信，安全；
- HTTPS 需要**证书**，而 HTTP 不需要。

</v-click>