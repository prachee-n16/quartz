---
title: "Elementary Graph Algorithms."
---

- A graph $G = (V, E)$ is composed of $V$, a set of vertices and $E \in V \times V$ 

- The two standard way of representing a graph is:
	- Adjacency List
		- Good idea when representing sparse graphs i.e. $|E| << |V|^2$ where number of edges is a lot less than the possible connections between all vertices
		- Pros
			- Easy to transform into a weighted graph, given a weighted function
			- Amount of memory for both directed/undirected is $\theta(V+E)$
		- Cons
			- No easy way to determine if an edge exists
	- Adjacency Matrix
		- Good idea when representing dense graphs i.e. $|E| < |V|^2$ where number of edges is close to the most number of connections between all vertices
		- Pros
			- Easier to use then adjacency list, where undefined edges can be represented as 0, `null`, `undefined` etc.
		- Cons
			- Amount of memory for directed and undirected is $\theta(V^2)$, can be optimized to lose diagonal if no self-loops
				- In undirected, we can lose half this space since $(u, v) = (v, u)$
		- To determine how to fill up the matrix,
$$
\begin{equation}
a_{i,j} =

\begin{array}{lr}

1 & \text{if } i, j \in E\\

0, & \text{otherwise } 

\end{array}

\end{equation}$$
