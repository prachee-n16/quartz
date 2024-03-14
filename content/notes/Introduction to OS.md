---
title: Introduction to OS
tags:
  - "#OperatingSystems"
  - Areas
  - C
  - to-complete
  - ece252
---
Operating System: It sits between hardware and programs. 
**OS as a Resource Manager**, the "secretary" of the system
- Responsible for resource managements and allocation, cause resources (e.g. CPU time, memory) are limited
- Chooses the winner in the event of conflicting requests

**OS as an Environment Provider**, 
- Allows useful programs to run, while abstracting details of hardware (i.e. Imagine changing how to print Hello World for different hardware builds)

**OS as a Multitasker**,
- Resources (like Keyboard) are shared between multiple programs, and OS creates/enforces these rules

**Systems Programming**, programs include
- File Manipulation
- Communication
- Processes and Thread Management
OS will sometimes not allow programs to do things, and instead, we need to ask the OS to do it.

**Concurrency** - A program is said to be concurrent if it can support two or more actions in progress at the same time.
**Parallelism** - A program is said to run in parallel if it can have two or more actions execute simultaneously

Note, a program with concurrency problem will see the following errors:
1. Consistently the wrong answer every single time  
2. Different on consecutive runs with the same input, or  
3. Correct some of the time but incorrect some of the time
