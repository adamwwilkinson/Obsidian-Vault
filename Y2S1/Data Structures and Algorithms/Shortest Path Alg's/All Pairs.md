# All Pairs
Uses [[Dynamic Programming]], and finds the minimum distance between every pair of vertices.

### The Initial Step
Let $d_ij^m$ denote the distance from $i$ to $j$ using at most $m$ edges, define $D^(m)$ to be the matrix whose $ij$-entry is the valued $d_{ij}^m$.

The matrix $D^{V-1}$ contains the table of all-pairs shortest paths.
Our overall plan therefore is to use $D(1)$ to compute $D(2)$, then use $D(2)$to compute $D(3)$ and so on.

$D(1)$ is just the adjacency matrix $A$. as it is just the weight from edge $i$ to $j$.

### The Inductive Step
What is the smallest weight of the path that uses at most *m* edges? Either:
1. A path uses less than *m* edges
2. A path that uses exactly *m* edges, composed of a path using *m - 1* edges from *i* to vertex *k* and edge *(k, j)*.

### Matrix Multiplication Algorithm
$D(2)$ can be calculated by $D(1)$  \* $D(1)$ and that will calculate the shortest path with at least 2 edges. *Where \* is the operation to add up and compare, similar to dot product, but instead of multiplying and adding, you add and compare, recording the lowest.*

$D(3)$ can be calculated by $D(2)$ * $D(1)$ and that will calculate the shortest path with at least 3 edges.

We get the generic step:
$$D^m = D^{m-1} * A$$

```java
d_ij^m <- inf
for k = 1 to V do
	d_ij^m = min(d_ij^m, d_ik^m-1 + w(k, j))
```

### Complexity
We have to iterate $V - 1$ times, for updating one entry it is O(V) and there are O($V^2$) vertexes. Therefore, total complexity is **$O(V^4)$**.

#### Improvements
We don't need to compute all intermediate products $D^1$, $D^2$, as we are only interested in $D^V-^1$. Therefore, we can just compute:
$$D^2 = A * A$$
$$D^4 = D^2 * D^2$$
$$D^8 = D^4 * D^4$$
And we get **$O(V^3\lceil\log V\rceil)$**.