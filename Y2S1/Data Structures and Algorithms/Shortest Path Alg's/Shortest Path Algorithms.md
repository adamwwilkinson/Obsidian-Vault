# Shortest Path Algorithms
Shortest path [[Algorithms|algorithms]] are algorithms used to determine the shortest path. By shortest path, we mean that the minimum value going through the weights of nodes in a graph. In a unweighted graph, it is assumed each vertex has a weight of 1.

For specific examples of SPAs refer to [[Primm's Algorithm]], [[Dijkstra's Algorithm]], [[Bellman-Ford Algorithm]].
### Priority-first Search
Key-values or priorities associated for each vertex is called a *key*. We initialise key[v] to be $\infty$ and build a heap with the keys. Then we find source vertex s for the search and perform change(s,0) placing s at the top of the queue.

```java
procedure PFS(s)
	change(s,0)
	while Q != 0
		u <- Q.dequeue()
		for each v adjacent to u do
			if v element of Q ^ PRIORITY < key[v] then
				π[v] <- u
				change(Q,v,PRIORITY)
			end if
		end for
	end while
```

#### Complexity
O(V $\lg$V) with the main loop being executed V times (number of vertexes) and each **extractmin** operation occuring $\lg$V times.

