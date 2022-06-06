# [[Trees]] and [[Graphs]] Traversal
Why traverse?
- search for a particular item
- test equality
- copy
- create
- display

### Tree Traversal
All of the below take time complexity $O(n)$ as we have to touch $n$ nodes to traverse it.
#### Depth-first
Follow branches from root to leaves. Suits recursive approach, this requires memory. 
The following are for space which depends on height,
- worst case: skinny, size $n$ implies height $n$
- expected case: much better
- best case: perfect tree, $\log_2 n$
##### Preorder Traversal
Common “left to right” search.
```java
if(!t.isEmpty()) {  
	visit root of t;  
	perform preorder traversal of left subtree;  
	perform preorder traversal of right subtree;  
}
```

![[Preorder Drawing|400]]

##### Postorder Traversal
```java
if (!t.isEmmpty()) {
	perform postorder traversal of left subtree;
	perform postorder traversal of right subtree;
	visit root of t;
}
```

![[Postorder Drawing|400]]
##### Inorder Traversal
Easy to read, but ambiguous
```java
if(!t.isEmpty()) {  
	perform inorder traversal of left subtree;  
	visit root of t;  
	perform inorder traversal of right subtree;  
}
```

![[Inorder Drawing|400]]

#### Breadth-first
Start at root, visit nodes level by level.
Suits iterative approach. Requires a queue.
Following is for space which depends on width,
- best case: skinny, width 2
- worst case: perfect, width $n/2$
![[BFS Drawing|400]]

```java
while (!q.isEmpty()) {  
	dequeue first item;  
	if (!external node) {  
		visit its root node;  
		enqueue left subtree (root window);  
		enqueue right subtree (root window);  
	}  
}
```

### Graph Traversal
#### Breadth-first
More complicated than [[#Breadth-first]] because we must be careful not to touch the same node twice. It uses a [[Queues]] as it's main data structure.