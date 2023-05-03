---
title: What is the difference between synchronous and asynchronous code in JavaScript?
type: question
tags: javascript,function,promise
authors: chalarangelo
cover: blog_images/pineapple-on-green.jpg
excerpt: Understanding the differences between synchronous and asynchronous code is a crucial piece of knowledge for every web developer.
firstSeen: 2021-11-14T05:00:00-04:00
---

Synchronous code runs in sequence. This means that each operation must wait for the previous one to complete before executing.

```js
console.log('One');
console.log('Two');
console.log('Three');
// LOGS: 'One', 'Two', 'Three'
```

Asynchronous code runs in parallel. This means that an operation can occur while another one is still being processed.

```js
console.log('One');
setTimeout(() => console.log('Two'), 100);
console.log('Three');
// LOGS: 'One', 'Three', 'Two'
```

Asynchronous code execution is often preferable in situations where execution can be blocked indefinitely. Some examples of this are network requests, long-running calculations, file system operations etc. Using asynchronous code in the browser ensures the page remains responsive and the user experience is mostly unaffected.
