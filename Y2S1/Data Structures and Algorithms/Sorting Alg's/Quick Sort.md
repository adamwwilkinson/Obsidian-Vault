# Quick Sort
Works by setting a pivot point and placing every element less than the pivot to the left of it, and everything more than the pivot to the right.
![[Quick Sort Drawing|800]]
[[Algorithms|Algorithm:]]
```java
procedure QUICKSORT(a, p, r)
	if p < r
		then q <- PARTITION(a, p, r)
			QUICKSORT(a, p, q - 1)
			QUICKSORT(a, q + 1, r)

procedure PARTITION(a, p, r)
	x <- a[r]
	i <- p - 1
	for j <- p to r - 1
		do if a[j] <= x
			then i++
				exchange a[i] <-> a[j]
	exchange a[i + 1] <-> a[r]
	return i + 1
```

### Complexity
The worst case complexity is worse than [[Merge Sort]] but is faster on average. Complexity of $O(n^2)$.

#concept/abstract 