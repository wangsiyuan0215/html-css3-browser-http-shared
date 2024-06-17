---
level: 2
---

# 定位

定位的方式有以下几类：

<v-click>

- `static`：默认值，元素按照文档流排列；
- `relative`：相对定位，元素相对于自身原来的位置进行定位；
- `absolute`：绝对定位，元素相对于<span v-mark.underline.orange="3">最近的非 `static` 定位</span>的父元素进行定位；
- `fixed`：固定定位，元素相对于浏览器窗口进行定位；
- `sticky`：粘性定位，元素在跨越特定阈值前为相对定位，之后为固定定位。

</v-click>

<v-click>

_Q. `absolute` 相对于什么进行定位？_

</v-click>

<v-click at="4">

_Q. 如何影响定位为 `fixed` 的元素？_

</v-click>

<v-click at="5">

`fixed` 固定定位会受到父元素的影响，如果父元素设置了 `transform`、`perspective` 或 `filter` 属性，那么 `fixed` 元素会相对于该父元素进行定位。

</v-click>