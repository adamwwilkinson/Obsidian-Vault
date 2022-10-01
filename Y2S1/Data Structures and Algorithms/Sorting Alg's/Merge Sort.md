# Merge Sort
Works by dividing the array in half, multiple times until you get each element by itself, then it merges the arrays, sorting as it goes. [[Recursion|Recursive]].
[[Algorithms|Algorithm:]]
```java
procedure MERGESORT(a, p, r)
	if p < r then
		q <- (p + r)/2
		MERGESORT(a, p, q)
		MERGESORT(a, q + 1, r)
		MERGE(a, p, q, r)

procedure MERGE(a, p, q, r)
	n1 <- q - p + 1
	n2 <- r - q
	for i <- 1 to n1, do L[i] <- a[p + i - 1]
	for j <- 1 to n2, do R[j] <- a[q + j]
	i <- 1
	j <- 1
	k <- p
	while i <= n1 and j <= n2 do
		if L[i] <= R[j] then a[k++] <- L[i++]
		else a[k++] <- R[j++]
	while i <= n1 do a[k++] <- L[i++]
	while j <= n2 do a[k++] <- R[i++]
```

### Complexity
$O(n \log n)$

For reccurence relation look at [[Aysptotic Complexity#Recurrence Relation]]