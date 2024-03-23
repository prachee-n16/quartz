---
title: Compiled and Interpreted Languages
tags:
  - Programming
  - Areas
---
All in all, both compilers and interpreters will convert human-readable code (unless it's brainfuck) and convert it to computer-readable machine code. The difference exists in when the translation happens.
- In a compiled language, the program is directly translated into machine code that is executed
	- There's a build step, and every change requires a rebuild: This step is translating code into machine code before the user can run it
	- This is faster so allows for better memory management and CPU usage.
- In a interpreted language, the program reads and executes code step-by-step
	- This is slower but that difference is shrinking with just-in-time compilation
