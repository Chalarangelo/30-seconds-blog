---
title: Javascript Array.from() second argument
type: story
tags: javascript,array
expertise: beginner
author: maciv
cover: blog_images/colors-mural.jpg
excerpt: Did you know that `Array.from()` accepts an optional second argument which can work as a map function on ever element of the array being created?
firstSeen: 2022-09-21T05:00:00-04:00
---

`Array.from()` is a method that creates a new array from an array-like or iterable object. However, one property that is often overlooked is that the method can accept a mapping function as a second argument. This map function is called on every element of the array that is being generated. 
Basically, `Array.from()` with a function as a second argument is equivalent to `Array.from().map()` only that it does not create an intermediate array.

```js
console.log(Array.from([1, 2, 3], x => x + x)); // [2, 4, 6]
```

One very simple use case for this is to create an array of a specific length and fill it with an arithmetic sequence. For example, if you want to create an array of 5 elements and fill it with the value 1 to 5, you can do it like this:

```js
const arr = Array.from({ length: 5 }, (v, i) => i + 1);
console.log(arr); // [1, 2, 3, 4, 5]
```

A similar example is the [arithmeticProgression](/js/s/arithmetic-progression) snippet or for a more complex use case, like splitting an array into n chunks, have a look at the [chunkIntoN](/js/s/chunk-into-n).
