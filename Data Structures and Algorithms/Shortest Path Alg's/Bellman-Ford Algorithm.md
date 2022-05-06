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

### Complexity
O(EV), in worst case  O(V$^3$).