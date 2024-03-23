---
title: Heaps
tags:
  - to-complete
  - C
  - Programming
  - DSA
---
Heap: Data structure, array object that can be represented as a binary tree.
- Each element of the array is a node on the tree
	- To compute indices of the:
		- parent of node $i$: Floor of $\frac{i}{2}$
		- Left child of node $i$: $2i$
		- Right child of node $i$: $2i + 1$
	- Each of these can be computed in 1-2 instructions e.g. $2i$ by simply shifting $i$ left by one position
- All levels of the tree are filled, except the lowest
- There are two kinds of heap: max-heap or min-heap where the root of the tree is either the maximum or minimum value, and subtrees will have values less/greater than the node
	- [[notes/Heap Sort]] uses max-heap and [[Priority Queues]] use min-heap
- The height of a heap is the height of the root i.e. longest path from root to leaf. Most operations run proportional to height of tree
