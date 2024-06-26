---
level: 2
---

# 盒模型

_Q. 浏览器 HTML 的元素是以什么方向排列布局的？_

<v-click>

- **从上到下**
- **从左到右**

那么接下来我们所讲的内容，均以此为基准。

</v-click>

<v-click>

盒模型是 CSS 中的一个重要概念，它定义了 HTML 元素的布局方式。

<div class="flex gap-x-4">

<div class="inline-block bg-white p-4 rounded">

<img src="/assets/images/box.png" class="h-40" />

</div>

<div class="flex justify-center items-center">

- **Content**：内容区域，宽高由 `width` 和 `height` 定义；
- **Padding**：内边距，由 `padding` 定义；
- **Border**：边框，由 `border` 定义；
- **Margin**：外边距，元素与元素之间的距离，由 `margin` 定义。

</div>

</div>

</v-click>

---
level: 2
hideInToc: true
---

# 盒模型

_Q. 默认的盒模型 `box-sizing` 是什么？_

<v-click>

默认的盒模型是 `content-box`，也称为 W3C 标准盒模型。

</v-click>

<v-click>

_Q. 如何设置 `box-sizing`？_

</v-click>

<v-click>

```css
.box {
  /* 设置盒模型为 border-box */
  box-sizing: border-box;
  /* 设置盒模型为 content-box */
  box-sizing: content-box;
}
```

- **`content-box`**：默认值，`width` 和 `height` 只包含内容，不包含 `padding` 和 `border`；
- **`border-box`**：`width` 和 `height` 包含 `padding` 和 `border`。

</v-click>

<v-click>

_Q. `padding` 和 `margin` 如果设置为 `50%` 的话，是基于什么计算的？_

</v-click>

<v-click>

是基于当前元素的父元素的宽度计算的。_想一想为什么？_

</v-click>