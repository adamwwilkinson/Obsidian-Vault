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

### Matrix Multiplication
$D(2)$ can be calculated by $D(1)$  * $D(1)$ and that will calculate the shortest path with at least 2 edges. 

$D(3)$ can be calculated by $D(2)$ * $D(1)$ and that will calculate the shortest path with at least 3 edges.

### Complexity
We have to iterate V - 1 times, for updating one enrtry it is O(V) and there are O($V^2$) vertexes. Therefore total complexity if **$O(V^2)$**.

#### Improvements
We don't need to compute all intermediate products $D^1$, $D^2$, as we are only interested in $D^V-^1$. Therfore we can just compute
$$D^2 = A * A$$
$$D^4 = D^2 * D^2$$
$$D^8 = D^4 * D^4$$
And we get **$O(V^3[\log V])$**.