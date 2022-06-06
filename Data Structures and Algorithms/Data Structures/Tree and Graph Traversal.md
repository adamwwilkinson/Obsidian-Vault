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
Both the following methods take time complexity $O(V + E)$.
#### Breadth-first
More complicated than [[#Breadth-first]] because we must be careful not to touch the same node twice. It uses a [[Queues]] as it's main data structure. Useful for determining if a graph is connected, or finding the distanced between two vertexes. Visits nearest nodes to the source first.

##### Initialisation
We mark every vertex as *white* with the queue being empty. Initialise an array $\pi [x]$ called the parent array. This keeps track of the parent of $x$. Then we mark the initial vertex as *gray* and have $\pi [v]$ to be undefined.

##### Procedure
```java
procedure BFS(v)  
	Push v on to the tail of Q  
	while Q is not empty  
		Pop vertex w from the head of Q  
		for each vertex x adjacent to w do  
			if colour[x] is white then  
				π[x] ← w  
				colour[x] ← grey  
				Push x on to the tail of Q  
			end if  
		end for  
		colour[w] ← black  
	end while
```
At the end of the search, every vertex becomes *black*, and the parent array $\pi$ will contain details of the breadth-first search tree.

##### Finding Distances Variation
```java
procedure BFSdist(v)
	while Q is not empty  
		Pop vertex w from the head of Q  
		for each vertex x adjacent to w do  
			if colour[x] is white then  
				dist[x] ← dist[w]+1  
				π[x] ← w  
				colour[x] ← grey  
				Push x on to the tail of Q  
			end if  
		end for  
		colour[w] ← black  
	end while
```

#### Depth-first
Naturally recursive, follows down the path of vertexes until it reaches a dead end, then backtracks. Visits furthest nodes to the source first. Came be used to find **strongly connected components** (from any two vertices there is a directed path from one to the other both ways), as well as **articulation points** (a vertex whose removal disconnects the graph).

```java
procedure DFS(w)  
	colour[w] ← grey  
	for each vertex x adjacent to w do  
		if colour[x] is white then  
			π[x] ← w  
			DFS(x)  
		end if  
	end for  
	colour[w] ← black
```

##### Non-recursive Variation
Requires a [[Stack]].
```java
procedure DFS(w)  
	initialize stack S  
	push w onto S  
	while S not empty do  
		x ← pop off S  
		if colour[x]=white then  
			colour[x] ← black  
			for each vertex y adjacent to x do  
				if colour[y] is white then  
					push y onto S  
					π[y] ← x  
				end if  
			end for  
		end if  
	end while
```

##### Discovery Variation
Tracks the time a vertex is discovered, and when it's finished.
```java
procedure DFS(w)  
	colour[w] ← grey  
	discovery[w] ← time  
	time ← time+1  
	for each vertex x adjacent to w do  
		if colour[x] is white then  
			π[x] ← w  
			DFS(x)  
		end if  
	end for  
	colour[w] ← black  
	finish[w] ← time  
	time ← time+1
```

### Topological Sort
Definition: A *directed acyclic graph (dag)* is a directed graph with no directed cycles

#### Algorithm
Apply the [[#Depth-first]] search procedure to find the finishing times of each vertex. As each vertex finishes put it on the front of a linked list.

At the end of the [[#Depth-first]] it will contain vertices in topologically sorted order.

Time complexity of $O(V + E)$.