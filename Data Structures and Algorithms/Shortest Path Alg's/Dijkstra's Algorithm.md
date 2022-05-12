# Dijkstra's Algorithm
[[Shortest Path Algorithms]].Does not work in the case of negative numbers. Implemented as a [[#Priority-first Search|PFS]] by replacing *PRIORITY* with *key[u] + weight(u, v)*.
Starts with a source vertex of weight 0, with all other vertexes to be infinity. If the path plus the weight of the root is lower than the current weight, replace the current weight of the node with this number. Do this for all nodes adjacent, take the root node out the PQ or heap, and replace the root with the lowest edge.
The assumption is: *you cannot reduce the weight of the shortest path, by adding additional edges.* This cannot hold if there exist negative edges.
![[Dijkstra's Heap|500]]
The key array always holds a collection of the upper bounds of the values we seek. This can be seen as the *best estimate*.

### Example
![[Dijkstra's Example|500]]
To go from one to the other, pick the node with the lowest weight associated with it, then update the lowest edges and repeat.
### Complexity
O($E\log$v) can be improved to O($E\log\log$v) by using a data structure called fibonacchi heap. If the graph is dense it is O($V^3 \log V$) and if it's sparse it is O($V^2 \log V$)