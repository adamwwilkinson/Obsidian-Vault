# Minimum Spanning Trees
A *minimum spanning tree* is a [[Graphs#Subgraphs]] that is (1) spanning, (2) a tree, and (3) has a lower weight than any other spanning tree.

### Greedy Algorithms
An [[Algorithms|algorithm]] in which a locally optimal choice is made at each stage. A hill climber using a greedy methodology would take each step in the steepest direction, ignoring any strategy that may be faster getting to the top. In general, greedy methods have limited use, but useful for finding a minimum spanning tree.

### Kruskal's Algorithm
Based on building a [[Trees#Definitions|forest]] of the lowest possible weight and continuing to add edges until it becomes a spanning tree.

Initialise $F$ to be the forest with all the vertices of $G$ but none of the edges.

```java
repeat  
Pick an edge e of minimum possible weight  
if F ∪ {e} is a forest then  
	F ← F ∪ {e}  
end if  
until F contains n − 1 edges
```

![[Kruskal's Drawing|500]]

#### Implementation
Main problem is to decide whether the next edge is allowable – that is, does it create a cycle or not.

When picking the next shortest edge is an algorithm there is two possibilities with the two vertexes:

$x$, $y$ lie in different trees of $F$: merges two trees of $F$

$x$, $y$ lie in the same tree of $F$: adding an edge creates a cycle and thus should not be added

We need a [[Data Structures]] which allows us to quickly find the tree to which an element belongs, and quickly merge it.

### [[Primm's Algorithm]]
Grow a minimum spanning tree edge-by-edge by always adding the shortest edge that touches a vertex to the current tree. The difference between Kruskal's and Primm's is that Kruskal always maintains a spanning subgraph that only becomes a tree at the end, while Primm's always maintains a tree which only becomes spanning at the final stage.

![[Prim Drawing Example]]