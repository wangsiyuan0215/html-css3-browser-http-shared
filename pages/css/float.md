---
level: 2
---

# 浮动

实现如下效果，你会怎么做？

<div class="flex gap-x-8">

<div class="flex-1">

<!-- ./components/Counter.vue -->
<TextAround />

</div>

<div class="flex-1">

<!-- ./components/Counter.vue -->
<TextAround :circle="true" />

</div>

</div>

---
level: 2
hideInToc: true
---

# 浮动 & BFC

上述效果的技术关键点：

- `float` 浮动；
- `shape-outside` 定义了一个可以是非矩形的形状，相邻的<span v-mark.underline.orange>内联内容</span>应围绕该形状进行包装。

<v-click>

_Q. 如何清除浮动？_

</v-click>

<v-click>

使用 `clear: both;` 清除浮动。

</v-click>

<v-click>

_Q. 什么是 BFC（格式化上下文）？_

</v-click>

<v-click>

BFC 是指浏览器中创建了一个独立的渲染区域，并且拥有一套渲染规则，他决定了其子元素如何定位，以及与其他元素的相互关系和作用。

具有 BFC 特性的元素可以看作是隔离了的独立容器，<span v-mark.orange>容器里面的元素不会在布局上影响到外面的元素</span>。

可以解决**浮动元素引起的高度塌陷**、**外边距重叠**等问题。

</v-click>

---
level: 2
hideInToc: true
---

# BFC

如何设置元素为 BFC？

- `float` 不为 `none`；
- `position` 为 `absolute` 或 `fixed`；
- `display` 为 `inline-block`, `table-cell`, `table-caption`, `flex`, `inline-flex`；
- `overflow` 不为 `visible`。