---
level: 2
---

# 语义化标签

<div class="flex gap-x-4">
<div class="flex-1">

这是一段糟糕的 HTML 代码。

```html {all|2-9|4-8|10|11-16}
<body class="...">
  <div class="header">
    <div class="logo"><img src="/img/logo.svg" /></div>
    <div class="nav">
      <div><a href="#">Home</a></div>
      <div><a href="#">About</a></div>
      <!-- ... -->
    </div>
  </div>
  <div class="body"><!-- .... --></div>
  <div class="footer">
    <div class="footer-nav">
      <div><a href="#">Home</a></div>
      <!-- ... -->
    </div>
  </div>
</body>
```

</div>

<div class="flex-1">

这是一段具有语义化的 HTML 代码。

```html {all}
<body>
  <header>
    <div><img src="/img/logo.svg" /></div>
    <nav>
      <a href="#">Home</a>
      <a href="#">About</a>
      <!-- ... -->
    </nav>
  </header>
  <main><!-- .... --></main>
  <footer>
    <nav>
      <a href="#">Home</a>
      <!-- ... -->
    </nav>
  </footer>
</body>
```

</div>
</div>

---
level: 2
hideInToc: true
---

# 语义化标签

写语义标签都有哪些好处呢？

<v-click>

- SEO 优化；
- 提高用户体验（无障碍），好的语义化结构会帮助视力受限的用户更好的使用我们的页面；
- 提高开发和维护的效率，语义化标签可以让代码更具可读性，更容易维护；
- 语义命名反映了正确的自定义元素/组件命名。

</v-click>

<v-click>

那么具备语义化的标签都有哪些呢？

</v-click>

<div v-click class="flex gap-x-4">
<div>

- `<article>`
- `<aside>`
- `<details>`
- `<figcaption>`
- `<figure>`

</div>

<div>

- `<footer>`
- `<header>`
- `<main>`
- `<mark>`
- `<nav>`

</div>

<div>

- `<section>`
- `<summary>`
- `<time>`
- `<header>`
- `<main>`

</div>

<div>

- `<mark>`
- `<nav>`
- `<section>`
- `<summary>`
- `<time>`

</div>

<div>

- `<自定义标签>`

</div>

</div>

<v-click>

具体每个都代表着什么？[HTML 语义化标签](https://developer.mozilla.org/zh-CN/docs/Glossary/Semantics#%E8%AF%AD%E4%B9%89%E5%8C%96%E5%85%83%E7%B4%A0)

</v-click>
