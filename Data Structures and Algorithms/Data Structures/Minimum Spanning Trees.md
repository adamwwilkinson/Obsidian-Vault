# Minimum Spanning Trees
A *minimum spanning tree* is a [[Graphs#Subgraphs]] that is (1) spanning, (2) a tree, and (3) has a lower weight than any other spanning tree.

### Greedy Algorithms
An [[Algorithms|algorithm]] in which a locally optimal choice is made at each stage. A hill climber using a greedy methodology would take each step in the steepest direction, ignoring any strategy that may be faster getting to the top. In general, greedy methods have limited use, but useful for finding a minimum spanning tree.

### Kruskal's Method
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