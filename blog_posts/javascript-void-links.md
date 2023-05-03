---
title: "Tip: Avoid \"javascript:void(0)\" for empty links"
type: tip
tags: javascript,browser,accessibility
authors: chalarangelo
cover: blog_images/white-flower.jpg
excerpt: There are various ways to create an empty link, but some options are more appropriate than others. Learn the best way to handle empty links with this quick tip.
firstSeen: 2020-11-15T11:46:42+02:00
lastUpdated: 2021-06-12T19:30:41+03:00
---

There are various ways to create an empty link, but some options are more appropriate than others. One of the most common debates about it is if one should use `href=""`, `href="#"` or `href="javascript:void(0)"`.

Generally, you want to avoid `href="javascript:void(0)"`, as it will cause the browser to parse the value of the link URL, which is both costly and unnecessary. It also introduces a potential XSS security vulnerability, as `javascript:` URLs violate Content Security Policy (CSP).

With that out of the way, it's clear that `href=""` or `href="#"` should be preferred in most cases. One key difference between the two is that `href="#"` points to the top of the page whereas `href=""` points to the current page. This can have unwanted side-effects, such as scrolling to the top of the page or issues with link styling respectively. To prevent either one of them from acting as links, you can use `Event.preventDefault()` and handle them appropriately using JavaScript.

Finally, when creating an empty link, one should always consider more semantically appropriate alternatives, such as a `<button>`, `<div>` or `<span>` tag. After all, a link should always behave like a link and hijacking it with JavaScript or any other means is bound to run into some accessibility problems sooner or later.
