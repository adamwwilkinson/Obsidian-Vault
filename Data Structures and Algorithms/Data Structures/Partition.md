# Partition
Also known as disjoint sets. A partition of a set is a collection of disjoint subsets (cells) that cover the entire set.

### Specifications
`Union(cell, cell)`: create a new partition by merging two cells
`Find(element)`: finds the cell containing a given element

### Naive Partitions
One simple way to represent a partition is to choose one element in the cell to be a leader. Then we can keep an array $\pi$ of length $n$ with $\pi (x)$ containing the leader in that partition.

![[Partition Drawing|400]]

This gives the `Find` operation a complexity of $O(1)$.

#### Updating
Naively can be done in $O(n)$, but with we adjust the pointers of one leader to the leader of the other merging element (still $O(n)$).

But if look at...

#### Union-by-rank Heuristic
Let the *rank* of the root node of a tree be it's height, the *union-by-rank heuristic* tries to keep the tree *balanced* at all times. When a merging operation needs to be done, the root of the shorter tree points to the root of the taller tree. This means the height is always the same (unless merging two same height trees together, which means the height is h++).

#### Path Compression Heuristic
Based on the idea that when we perform a `Find` operation, we have to follow a path from $x$ to the root of the tree. As we are touching every node, why not simply make all elements point *directly* to the tree, as opposed to each other.