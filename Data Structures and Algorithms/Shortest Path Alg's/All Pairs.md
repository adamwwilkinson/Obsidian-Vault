# All Pairs
Uses [[Dynamic Programming]], and finds the minimum distance between every pair of vertices.

### The Initial Step
Let $d_ij^m$ denote the distance from $i$ to $j$ using at most $m$ edges, define $D^(m)$ to be the matrix whose $ij$-entry is the valued $d_ij^m$.

The matrix $D^V-^1)$ contains the table of all-pairs shortest paths.
Our overall plan therefore is to use $D(1)$ to compute $D(2)$, then use $D(2)$to compute $D(3)$ and so on.

$D(1)$ is just the adjacency matrix $A$. as it is just the weight from edge $i$ to $j$.

### The Inductive Step
What is the smallest weight of the path that uses at most *m* edges? Either:
1. A path uses less than *m* edges
2. A path that uses exactly *m* edges, composed of a path using *m - 1* edges from *i* to vertex *k* and edge *(k, j)*.

#status/todo/drawing 05 May 2022, 01:11