---
level: 2
---

# Font-size 字体大小

_Q. `em` 和 `rem` 各自是什么？它们的区别是什么？_

<v-click>

- `em`：相对于父元素的 `font-size`_（这是在网上大多数的回答）_；
- `rem`：相对于根元素的 `font-size`。

</v-click>

<v-click>

实际上，由于 `font-size` 是可继承的，大家都忽略了元素本身的 `font-size`，所以更准确的是 `em` 是基于当前元素的 `font-size`。

</v-click>

<v-click>

_Q. 当我们设定 `font-size` 是设定了文字的什么？是文字的宽高吗？_

</v-click>

<v-click>

`font-size` 设定的值真正改变的是字体的 “外边框” 的**高**的大小，也就是 `em square` 或 `em box`。

<div class="p-4 bg-white absolute">

<img src="/assets/images/font-size.png" class="h-30"/>

</div>

</v-click>

<!-- 字体，em 和 rem 的区别（**特别是 em 继承的是当前元素的 font-size**），当我们设定 font-size 是设定了文字的什么？宽高吗？（em square） -->