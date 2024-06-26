---
level: 2
---

# 存储

_Q. Cookie / LocalStorage / SessionStorage / IndexedDB / WebSQL 有什么区别？_

<v-click>

- Cookie: **4KB**，每次请求都会携带，不安全；
- LocalStorage: **2.5MB - 10MB**，在不同的浏览器中存储空间会有所不同；
- SessionStorage: **5MB**，会话级别存储，关闭页面即失效；
- IndexedDB: **无限制**，异步 API，支持事务，支持**存储大量结构化数据**；
- WebSQL: 浏览器本地数据库， 存储容量有限，已废弃。

</v-click>