---
level: 2
---

# 事件冒泡、捕获的使用场景

_Q. 【委托】假设父元素 `<div id="parent">` 内有 100 个 `button` 和 100 个 `p` 标签，如何给其中 100 个 `button` 进行事件绑定？_

<v-click>

```js {all|3|4}
const parent = document.getElementById("parent");

parent.addEventListener("click", function (event) {
  if (event.target.tagName.toUpperCase() === "BUTTON") {
    console.log("Hello, button!");
  }
});
```

</v-click>

<v-click>

_Q. 【拦截】假设在不改变这 100 个 `button` 的 click 事件的代码的前提下，点击 `button` 时打印 `console.log('this is a button.')`？_

</v-click>

<v-click>

```js {all|7}
const parent = document.getElementById("parent");

parent.addEventListener("click", function (event) {
  if (event.target.tagName.toUpperCase() === "BUTTON") {
    console.log("this is a button.");
  }
}, true);
```

</v-click>
