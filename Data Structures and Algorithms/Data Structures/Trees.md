# Trees
### Definitions
Let $w_1$, $w_2$ be the roots of subtrees $u_1$, $u_1$ of $u$:
- $u$ is the parent of $w_1, w_2$
- $w_1, w_2$ is the children $u$
- $w_1, w_2$ are siblings

Leaf: an internal node whose left and right children are empty (external nodes)
Frontier: the external nodes of a tree define it
Descendant: if a node is related to another downwards
Ancestor: if a node is related to another upwards
Height: the length of the longest chain of descendants
Skinny Trees: every node has at most one child
Complete (Fat) Trees: leaves appear on at most two adjacent levels
Forest: (possibly empty) set of trees
Orchard: (possibly empty) queue or list of trees
Directed: Each vertex has one directed edge leading into it

### Binary Trees
A binary tree is defined recursively either:
- empty, if n = 0, or
- consist of a *root node u* and two binary trees $u(1)$ and $u(2)$

#### Relationships between Height and Size
1. A binary tree of height $h$ has size at least $h$
2. A binary tree of height $h$ has size at most $2^h - 1$
3. A binary tree of size $n$ has height at most $n$
4. A binary tree of size $n$ has height at least $\log (n + 1)$ 
