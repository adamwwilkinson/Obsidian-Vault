# Insertion Sort
Works by inserting ith element into it's correct position. [[Algorithms|Algorithm:]]
```java
procedure INSERTION-SORT(A)
	for j <- 2 to length[A]
		do key <- A[j]
			// insert A[j] into the sorted sequence
			i = j - 1
			while i > 0 and A[i] > key
				do A[i + 1] <- A[i]
			A[i + 1] <- key
```

### Complexity
If sorting an array of $N$, the complexity is $O(N^2)$.