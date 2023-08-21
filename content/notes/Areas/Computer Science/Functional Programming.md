---
title: "Functional Programming"
---

*What is Functional Programming?* A [[Programming Paradigm]].

The main focus is on "what are we trying to solve", rather than "how are we trying to solve" - It's a declarative type of programming
- A nice way to imagine this is when jump into a cab, we tell the driver where we want to go. We don't give him turn-by-turn instructions i.e. imperative approach.
It is based on <ins>Lambda Calculus</ins>: 
- Lambda Calculus is about studying computations with functions, which can also be used to simulate Turing Machine
	- In this logic system, functions are anonymous. We do not give them explicit names. $square\_sum(x,y) = x^2 + y^2$ rewritten as $(x,y) \rightarrow x^2 + y^2$    
	- Uses function of a single input, so the above example can be reworked:  $(x,y) \rightarrow x^2 + y^2$  to $x \rightarrow (y \rightarrow x^2 + y^2)$. This is also now an example of a [[Higher-Order Functions]]

