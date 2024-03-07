---
title: Higher-Order Functions
tags:
  - Areas
---

A higher-order function is a function which takes a function as a parameter or which returns the function or both. In JavaScript, an example of this is setTimeout() where one of the parameters is a function we run after some time is passed. 
```
setTimeout(() => {
	console.log('')
}, time)
```