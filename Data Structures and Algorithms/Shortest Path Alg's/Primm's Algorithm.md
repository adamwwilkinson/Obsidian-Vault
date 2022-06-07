# Prim's Algorithm
[[Shortest Path Algorithms]]. Given a priority tree, construct a spanning tree. Can be expressed as priority-first search by observing the priority of a vertex is the weight of the shortest edge joining the vertex to the rest of the tree. 
Impemented as a [[Shortest Path Algorithms#Priority-first Search|PFS]] by replacing *PRIORITY* with *weight(u, v)*.

Can read more in [[Minimum Spanning Trees#Primm's Algorithm]]

### How it works
Pick a source node at random, then  pick the smallest weighted edge that connects to an unvisited node. Repeat this until every node is reached, or if disconnected tree is realised.
![[Prim Drawing Example|500]]

### Complexity
If using a priority heap, $O(V \log V + E \log V)$, otherwise if using an adjacency matrix, $O(V^2)$.

