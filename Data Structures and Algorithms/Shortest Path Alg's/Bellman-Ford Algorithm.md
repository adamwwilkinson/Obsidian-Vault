# Bellman-Ford Algorithm
[[Relaxing Edges]] the edge (v-1) rounds then once more again and sees if any weight changes (from cycles or negative weights). **IF** it does it reports it's unable to get shortest path.
```java
for i = 1 to |V(G)| - 1 do
	for each edge(u,v) element of E(G) do
		d[v] <- min(d[v], d[u] + w(u, v))
	end for each
end for

// single check to determine failure
for each edge(u, v) element of E(G) do
	if d[v] > d[u] + w(u, v) then
		FAIL
	end if
end for each
```

### Correctness
**Property 1**
Consider an edge $(u, v)$ that lies on the shortest path from $s \text{ to } v$. If the sequence of relaxations includes relaxing $(u, v)$ at a stage when $d[u] = \delta (s, u)$, then $d[v]$ is set to $\delta(s, v)$ and never changes after that.

Now consider a path from $s$ to $v$:
$$s \sim v_1 \sim v_2 --- v_k \sim v$$

Now at the initialization stage $d[s] = 0$ and it always remains the same. After
one pass through the main loop the edge $(s, v_1)$ is relaxed and by Property 1, $d[v_1 ] = \delta(s, v_1)$ and it remains at that value. After the second pass the edge  
$(v_1 , v_2 )$ is relaxed and after this relaxation we have $d[v 2 ] = \delta(s, v_2)$and it remains  
at this value.  
As the number of edges in the path is at most $|V (G)| − 1$, after all the loops have  
been performed $d[v] = \delta(s, v)$.
### Complexity
O(EV), in worst case O(V$^3$).