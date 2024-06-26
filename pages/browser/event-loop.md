---
level: 2
clicks: 3
---

# 事件循环 Event Loop

_Q. JavaScript 为什么要有事件循环？事件循环的机制是什么？_

<div class="flex gap-x-4">

<div class="w-80">

#### 下面的输出是什么？

```js
console.log('script start');

setTimeout(function() {
  console.log('setTimeout');
}, 0);

Promise.resolve().then(function() {
  console.log('promise1');
}).then(function() {
  console.log('promise2');
});

console.log('script end');
```

<v-click at="1">

```js
// script start
// script end
// promise1
// promise2
// setTimeout
```

</v-click>

</div>

<div class="flex-1">

<template v-if="$clicks === 2">

#### 为什么要有事件循环？

<div class="mt-2"></div>

- JavaScript 是一个单线程的语言，这就意味着它一次只会执行一个任务。如果有一个线程阻塞的话，整个程序都会被阻塞。
- 为了解决这个问题，JavaScript 引入了**事件循环**机制，它允许 JavaScript 在执行任务的同时，处理异步操作。

</template>

<template v-if="$clicks === 3">

#### 事件循环的机制是什么？

<div class="mt-2"></div>

- 执行栈（FILO）：每一次执行任务的时候，都会将任务放到执行栈中去执行；
- 同步任务和异步任务：同步任务会直接放到执行栈中执行，异步任务会放到**任务队列**中等待执行；
- 任务队列：分为**宏任务队列**和**微任务队列**；
- 宏任务（macro task）：包括**主进程**，`setTimeout`，`setInterval`，I/O，UI 渲染；
- 微任务（micro task）：`Promise.then`，`process.nextTick`，`MutationObserver`;
- 每个宏任务执行完之后，会清空微任务队列，再执行下一个宏任务;

</template>

</div>


</div>