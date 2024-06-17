---
level: 2
---

# “首屏加载优化” 在 HTML 中我们能做什么？

_Q. 影响首屏加载时间的因素都有哪些？_

<div v-click>

- **网络请求**：网络请求是首屏加载时间的主要因素，因此减少网络请求次数和请求资源大小是提升首屏加载速度的关键;
- **资源**：资源的体积、加载的顺序和加载的方式都会影响首屏加载速度；
- **CSS/JS 脚本堵塞**：加载 CSS/JS 脚本会阻塞页面的渲染；
- **HTML 解析**：HTML 解析也会影响首屏加载速度；

</div>

<div v-click>

那么我们在 HTML 中可以做哪些优化呢？

</div>

<div v-click>

- HTML 解析
- **资源的加载** <carbon-arrow-left class="text-orange-600" />

</div>

---
level: 2
hideInToc: true
---

# “首屏加载优化” 在 HTML 中我们能做什么？

目前有两种**资源加载**的解决方案：

- `prefetch` <v-click>加载未来可能会用到的资源，浏览器会在空闲时间去加载对应的资源。</v-click>
- `preload` <v-click>**预**加载必要的资源，当资源被使用的时候立即执行，无需网络消耗。</v-click>

<v-click>

二者的使用方式都是一样的，在兼容性上 `prefetch` 比 `preload` 更好，覆盖面可以达到将近 80%。

```html
<link rel="preload" href="style.css" as="style" />
<link rel="prefetch" href="image.png" />
```

</v-click>

<v-click>

其他的加载方式： `async` 和 `defer`。

</v-click>

<v-click>

<div class="inline-block p-2 bg-gray-300 rounded">
  <img src="/assets/images/defer_async.png" class="h-30" />
</div>

</v-click>
