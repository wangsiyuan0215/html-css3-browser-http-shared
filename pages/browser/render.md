---
level: 2
---

# 从浏览器地址栏输入 url 到显示页面的过程

_Q. 请尽可能的详细描述出这个过程？_

<v-click>

总的来说，这个过程分为四个部分：

- DNS 解析（逐级查找、广播的方式）；
- 获取资源前，先检查浏览器缓存；
- 与服务器建立连接，TCP 3 次握手/4 次挥手；
- 获取目标地址的资源，浏览器加载渲染；

</v-click>

<v-click>

</v-click>

---
level: 2
hideInToc: true
---

# DNS 解析

DNS 解析是将域名解析为 IP 地址的过程。

<v-click>

_Q. 什么是域名？以 `.` 分隔的目的是什么？_

</v-click>

<v-click>

- 比如 `www.baidu.com` 就是域名，它比 IP 地址更具有可读性；
- `.` 分隔的目的是为了逐级查找，从而找到对应的 IP 地址。

以 `www.baidu.com.` 为例：

- 最右侧的 `.` 为根域名，只不过在浏览器中可以省略。；
- `com` 是顶级域名；
- `baidu` 是二级域名；
- `www` 是三级域名。

</v-click>

---
level: 2
hideInToc: true
---

# DNS 解析

_Q. DNS 解析的具体过程？以 `www.baidu.com.` 为例_

<v-click>

<div class="flex gap-x-8">

<div class="flex-1">

1. 检查浏览器*缓存*中是否存在该域名与 IP 地址的映射关系，没有则继续；
2. 到*操作系统*查找映射关系，一般在 hosts 文件中，否则继续；
3. 到*本地域名服务器*去查询，否则继续；
4. 本地域名服务器会先去**根域名服务器**查找，找到对应的顶级域名服务器（比如 `.com`），返回给本地域名服务器；
5. 本地域名服务器会根据域名**从右往左**逐级查找对应的域名服务器，否则继续；
6. 上述 4 步骤（逐级查找）中，是通过**广播**的方式进行查找。如果找到映射关系，本地域名服务器将映射关系存储到自身的映射表中，同时返回给该用户，否则报错；

</div>

<div class="w-70">

<h5 class="mb-4">域名服务器是分布式层次树状结构：</h5>

<div class="inline-block p-4 bg-white rounded">

<img src="/assets/images/DNS.png" class="w-full" />

</div>

</div>

</div>

</v-click>

---
level: 2
hideInToc: true
---

# _\[Homework\]_ 与服务器建立连接

_Q. TCP 3 次握手 / 4 次挥手_

通过查阅资料，了解 TCP 3 次握手 / 4 次挥手的过程，并尝试用自己的语言描述出来（拒绝 `ctrl c+v`)。

并解释为何 TCP 建立连接时要 3 次握手，而断开连接时要 4 次挥手。

---
level: 2
hideInToc: true
---

# 浏览器渲染

_Q. 请描述浏览器渲染的过程？_

<v-click>

<div class="flex gap-x-8">

<div class="w-1/2 truncate">

浏览器渲染的过程主要分为以下几个步骤：

1. **HTML 解析**：解析 HTML 标签，构建 DOM 树；
2. **CSS 解析**：解析 CSS 样式，构建 CSSOM 树；
3. **合并 DOM 树和 CSSOM 树**，构建渲染树；
4. **布局**：计算元素的位置和大小；
5. **绘制**：绘制页面元素；
6. **重绘和回流**：根据用户的操作，重新绘制页面元素。
7. **渲染完成**。

</div>

<div class="flex-1">

<img src="/assets/images/html-render.png" class="mt-4 w-full" />

</div>

</div>

_在解析 HTML 生成 DOM 树的阶段，加载 JS 文件会阻塞其进程，因此不建议将 `<script>` 标签放在 `<head>` 中。_

</v-click>