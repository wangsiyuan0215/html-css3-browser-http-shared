---
level: 2
---

# Selector 选择器

CSS 选择器有很多种：

<div class="flex gap-x-8">

<v-click>

- 内联
- ID 选择器
- 元素选择器
- 类选择器
- 属性选择器 ?

</v-click>

<v-click>

- 伪类选择器
- 伪元素选择器
- 子元素选择器
- 兄弟选择器 ?
- 通用选择器

</v-click>

</div>

<v-click>

<br />

#### CSS 选择器优先级是？

</v-click>

<v-click>

<div class="inline-block py-1 px-2 rounded mt-4 bg-gray-600">

<p class="!my-0"><code>!important</code> > 行内样式 (<code>style="..."</code>) > ID 选择器 > 类选择器 > 元素选择器 > 通用选择器</p>

</div>

其中，`!important` 为最高优先级，它会覆盖页面内任何位置定义的元素样式，

若两个相同 CSS 均拥有 `!important` 则还需要通过 CSS 权重来判断。

行内样式（也成内联样式）优先级次之，但是该方式会造成 CSS 难以管理，**不推荐使用**。

</v-click>

---
level: 2
hideInToc: true
---

# 选择器权重

当多个 CSS 样式作用于同一个元素时，如何确定哪个 CSS 样式作为最终的元素的样式？

<v-click>

- 行内样式：1000
- ID 选择器：100
- 类选择器：10
- 元素选择器：1

</v-click>

<v-click>

比如：`#id .class p` 它的权重值是多少？为什么它会比 `#id p` 的权重值高？

</v-click>

<v-click>

权重的计算规则：

- 每出现一次行内样式，权重值加 1000；
- 每出现一次 ID 选择器，权重值加 100；
- 每出现一次类选择器，权重值加 10；
- 每出现一次元素选择器，权重值加 1；
- 如果权重相同，后定义的规则优先。

</v-click>

---
level: 2
hideInToc: true
---

# CSS 解析定位 HTML 元素的算法

CSS 解析器会根据选择器的权重来确定最终的样式，但是它是如何定位到 HTML 元素的呢？

- 从右向左解析 <v-click at="1"><carbon-arrow-left class="text-orange-600" /></v-click>
- 从左向右解析

<v-click >

<div class="flex gap-x-4 mt-4">

```html
<div class="container">
  <header class="title">
    <span class="tip">this is `Header`.</span>
  </header>
  <div class="body">
    <h2 class="title">
      <span class="subtitle">this is `Body`.</span>
    </h2>
  </div>
  <div class="footer">
    <h3 class="title">
      <span class="tip">this is `Footer`.</span>
    </h3>
  </div>
</div>
```

<div class="flex justify-center items-center">

<carbon-arrow-right class="text-orange-600 text-10" />

</div>

<div class="flex justify-center items-center">

<div class="p-2 bg-white rounded">

<img src="/assets/images/selector-html-tree.png" class="h-66">

</div>

</div>

</div>

</v-click>

---
level: 2
hideInToc: true
---

# CSS 解析定位 HTML 元素的算法

描述以下 CSS 选择器的解析过程：

<div class="flex gap-x-4 mt-4">

<div class="flex-1">

```css {all|1|1|1|5|5|5}
.title .tip {
  color: blue;
}

.container .footer p {
  color: white;
}
```

<div v-if="$clicks < 3">

<v-click  at="2">

从左向右解析：

- `.container` -> `.header` -> `.tip`；
- `.container` -> `.body` -> 无 `.tip` 回溯；
- `.container` -> `.footer` -> 无 `.tip` 回溯；

</v-click>

</div>

<div v-if="$clicks >= 3 && $clicks < 4">

<v-click at="3">

从右向左解析：

- 遍历所有的 `.tip`，仅找到 1 个；
- `.tip` -> `.header` 结束。

</v-click>

</div>

<div v-if="$clicks >= 4 && $clicks < 5">

<v-click  at="4">

从左向右解析：

- `.container` -> `.header` -> 无 `p` 回溯；
- `.container` -> `.body` -> 无 `p` 回溯；
- `.container` -> `.footer` -> 无 `p` 回溯。

</v-click>

</div>

<div v-if="$clicks >= 5">

<v-click at="5">

从右向左解析：

- 遍历所有的 `p`，没找到，结束。

</v-click>

</div>

</div>

<div class="flex items-start">

<div class="p-2 bg-white rounded">

<img src="/assets/images/selector-html-tree.png" class="h-66">

</div>

</div>

</div>

<v-click at="6">

CSS 解析器从右向左解析的好处是：**当 HTML 树比较复杂的时候，能够有效的减少回溯的次数。**

_从右向左解析并不是没有消耗，在一棵树中找到所有的目标节点也会有性能消耗，但是要比回溯小得多。_

</v-click>
