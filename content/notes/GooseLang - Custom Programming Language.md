---
title: GooseLang - Custom Programming Language
tags:
  - C
  - Programming
  - Projects
  - to-complete
---
*Note: Made in good fun, and having your own programming language is cool~*

Over the past month, I've been working on creating my own programming language, GooseLang. It has nothing to do with geese - just has all the things I love about Python, C, Java etc compiled into one! Here are the features I've implemented so far:
- Working on [[Lexer]]

Note: I am not an expert, I'm just interested in learning more about language development! Before starting, here is some research I did on the topic (that led to some design decisions later on):
- [[Compiled and Interpreted Languages]]: GooseLang is going to be an Interpreted language for an easier development time, written in C++ (also, interpreted)
- High-level pipeline: [[Lexer|Lexing]]-[[Parsing]]-[[Action Tree]]

Here are some design choice I've made:
- Building my own lexer and parser, as opposed to using Flex and Bison (or even [[LLVM]] compiler) respectively. 
- Static typing over dynamic typing: GooseLang promotes type safety!
- General-purpose programming language: Allows me to play with OOP and other styles! 

Sample code of how GooseLang would work:
```
fn sum(x: int, y: int) -> int {
	return x + y;
}

fn main() {
	print("Sum is", sum(2, 4));
}
```

References:
- [Creating the Bolt Compiler by Mukul Rathi](https://mukulrathi.com/create-your-own-programming-language/intro-to-compiler/)