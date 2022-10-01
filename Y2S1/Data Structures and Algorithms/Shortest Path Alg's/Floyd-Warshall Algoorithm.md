Floyd-Warshall algorithm uses a different [[Dynamic Programming]] formalism. This is the optimal algorithm for the [[All Pairs]] problem.

### Definitions
We shall define $d_{ij}^k$ to be the shortest path from $i$ to $j$ with all intermediate vertices like in the set {1 to $k$}. We define $D^k$ as the matrix whose entries are $d_{ij}^k$.

### The Initial Case
The matrix $D^0$ has length of shortest path from $i$ to $j$ with *no* intermediate vertexes. This is just the *adjacency matrix*.
![[Dynamic Programming Example]]

### The Inductive Step
We assume matrix $D^{k-1}$ is already found and we wish to construct matrix $D^k$.
![[Floyd-Warshall Inductive Drawing]]

### The Code
```java
D^0 <- A
for k = 1 to V  do
	for i = 1 to V do
		for j = 1 to V do
			d_ij^k = min(d_ij^k-1, d_ik^k-1+d_kj^k-1)
		end for j
	end for i
end for k
```
At the end of this we have matrix $D^V$ whose $(i, j)$ entry contains the length of the shortest path from $i$ to $j$.
### Complexity
Most efficient All-Pairs algorithm with overall complexity being $O(V^3)$.

### Finding the actual shortest paths
So far all we found it the length of the shortest path of all pairs, and not the path to take. In order to do this, we need to keep all the arrays created to keep data on the predecessors of the edge.


















