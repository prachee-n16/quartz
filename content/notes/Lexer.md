---
title: Lexer
tags:
  - C
  - Programming
  - Areas
  - to-complete
---
Lexing, short for lexical analysis, takes in source code as series of characters and creates a series of chunks called **tokens**. In fact, "lexical" means a word in isolation from the sentence that contains it. 

Consider the following C++ code:
```cpp
for(int i = 0; i < 10; ++i)
```
Here, `for` is a keyword that tells us we are starting a for loop, `int` is an identifier token and more. Tokens are data structures, allows source code to be converted into data structures. It helps us ignore whitespaces that aren't relevant to the code. It doesn't care about grammar, it cares about the meaning of the words itself.

There are two steps to the process:
1. Scanning
	Scanner does the work of reading the source file, one character at a time. This includes spaces, punctuations and EOL. Then, it figures out the words in the sentence by using space, newline and EOF to mark the lexemes.
2. Evaluating
	 Next, we evaluate the words and see if they mean anything relevant to the programming language. Here, we determine what type of token is found, which is a pair of the token name and value. 

How do we split characters into tokens? Pattern-matching where:
- Certain keywords such as `String` is not a variable name but an identifier. So, we need a priority when matching patterns.
- For `StringInt`, we don't want to consider this as two different words: `String` and `Int` but one. 

