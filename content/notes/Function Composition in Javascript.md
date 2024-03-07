---
title: Function Composition in JavaScript
tags:
  - Areas
---

JavaScript is a multi-paradigm programming language - it has supports for several [[Programming Paradigm]], including [[Functional Programming]].

Function Piping vs. Composition
- It's a matter of how functions are being executed: If functions are executed from left to right, that's a pipe while right to left is called compose

Note: Functional Programming is about working with pure functions (functions with no side effects). However, that's not possible in real-life applications that deal with state and side-effects - that's where MONAD, a design pattern comes in. 

In monadic composition, we add an extra requirement: It needs to explain how it got to the end result. Let's build a math expression
```
// The actual function attached with a description
const add6 = x => [x+5, '+6']
const multiply6 = x => [x*6, '*6']
```