# Heapsort
Uses the [[Heap]] data structure to implement an effective sorting procedure.
```java
int[] heapSort(int[] arr) {  
	// Create a priority queue  
	PQueue p = new PQueue();  
	// Add in the elements with themselves as the key  
	for (int i : arr) {  
		p.enqueue(i, i);  
	}  
	
	// Create a new array to store the result  
	int[] ans = new int[arr.length];  
	// Dequeue the elements from the priority queue into ans  
	for (int i = 0; i < ans.length; i++) {  
		ans[i] = p.dequeue();  
	}  
	return ans;  
}
```

