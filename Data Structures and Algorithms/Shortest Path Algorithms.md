# Shortest Path Algorithms
Shortest path [[Algorithms|algorithms]] are algorithms used to determine the shortest path. By shortest path, we mean that the minimum value going through the weights of nodes in a graph. In a unweighted graph, it is assumed each vertex has a weight of 1.

### Priority-first Search
Key-values or priorities associated for each vertex is called a *key*. We initialise key[v] to be $\infty$ and build a heap with the keys. Then we find source vertex s for the search and perform change(s,0) placing s at the top of the queue.

```psuedo
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

### Prim's Algorithm
Given a priority tree, construct a spanning tree. Can be expressed as priority-first search by observing the priority of a vertex is the weight of the shortest edge joining the vertex to the rest of the tree. 
Impemented as a [[#Priority-first Search|PFS]] by replacing *PRIORITY* with *weight(u, v)*.
#status/todo


### Dijkstra's Algorithm
Does not work in the case of negative numbers. Impemented as a [[#Priority-first Search|PFS]] by replacing *PRIORITY* with *key[u] + weight(u, v)*.
#status/todo could be made longer and more understood :)

#### Complexity
O(E$\log$v) can be imporved to O(E$\log\log$v) by using a data structure called fibonacchi heap. 
