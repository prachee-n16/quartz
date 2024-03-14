---
tags:
  - C
  - Programming
  - completed
title: Fundamentals of C
---

**Overview of C**
- It is a procedural language.
	- It has functions but it's not a functional programming language, unlike C++ which has object-oriented capabilities. 
- Header files are imported into a program using precompiler directive as follows:
```cpp
#include <stdio.h>
#include <stdlib.h>

/* 
In C, there is no bool type and often, we use int 0/1 to denote true or false.
Alternative, include below header file for bool type
*/
#include <stdbool.h> 
```
- In old versions of C, two-passes were too time-taking so it's limited to one. This means functions can't be used before they are declared.
	- Alternative: Use a function prototype, promising an implementation exists below
- Structs are a grouping of variables
```
struct color {
	int r;
	int g;
	int b;
	int a;
}

typedef struct color {
	int r;
	int g;
	int b;
	int a;
} color_t;
```

How to make an array of boxes in C++?
```
box* boxes = new box[10]
```

... but this syntax changes in C as follows. Specifically, it needs details on memory allocation:
```
box* boxes = malloc(10*sizeof(box))
```

The idea is: I want you to allocate memory equal to `10 * sizeOf(1 box)`
- Malloc is suitable when memory content initialization is not necessary, and the program is dealing with a single block of memory. 
- Calloc is useful when the program requires multiple blocks of memory, especially when handling arrays or structures that need to be initialized to zero.

To delete this object in C++, the syntax is `delete[] boxes;` while in C, it is,
```
free(boxes)
```
How does C realize how much memory to free? When memory is first allocated, the computer keeps track of it. Prior to the pointer of the object, it keeps information on the size of the block. Also, free(var) does not actually erase the memory so it needs to be set as nullptr or undefined in the right context.
- Use after free is **a vulnerability related to incorrect use of dynamic memory during program operation**.

Assigning values in these arrays works like this:
```
boxes[0].height = 10;
boxes[0].width = 10;

boxes->height = 10;
```

Note,
```
%% If we attempt to print an uninitialized memory block, the value is undefined %%
printf("%d\n", boxes[0].width)
```
*Calloc will help eliminate this issue!*

This line looks at boxes, which starts at 0 and will look at the next element `boxes[1]` and perform the change.
```
(boxes+1)->height = 12
```
Hence, equivalent to:
```
boxes[1].height = 12
```

**Notes on printing**
In C++, `std::cout << boxes[0].width << std::endl;` but the issue in C, is that `std::cout` does not exist despite the elegance. 
```
printf("%d\n", boxes[0].height)
```
The newline character in C is done through special character `\n`
Review: Conversion Specifiers in https://man7.org/linux/man-pages/man3/printf.3.html

When specifying main in C, 
```
int main( int argc, char* argv[]) { ... }
```

In C, a string a string of characters and ends in a null character. The parameters to main are:
```
char* hello = "hi";
printf("%s %s\n", hello, argv[1])
%% Take hello, and the first line argument from the command line and append it %%
```
Note, declarations of variables must be at the top of the file.

```
#include "string.h"

const char* hello = "hi";
const char* test = "murray";

%% Strlen includes the number of chars in string not including null char %%
%% Both hello and test %%
greeting = malloc(strlen(hello) + strlen(test) + 1);
strncpy(greeting, hello, strlen(hello) + strlen(test) + 1);
strncat(greeting, test, strlen(test) + 1);
free(greeting);
```

Extra:
- The difference between new and new[]: 
	- If type is a non-array type, the name of the function is operator new . If type is an array type, the name of the function is operator new[] 