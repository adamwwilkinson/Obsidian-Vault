# Search Trees
### Dictionaries
#### Specifications
*insert(e)* - add *e* to a dictionary
*predecessor(e)* - returns largest element that is smaller than *e*
*successor(e)* - returns smallest element that is larger than *e*
*range(p, s)* - returns a dictionary that contains all elements between *p*  and *s* including
*delete(e)* - removes item *e*

### Binary Search Tree
A binary tree whose nodes are labelled with elements or keys that satisfy *binary search tree condition*:
**For every internal node $u$, all nodes in $u$'s left subtree precede $u$ in the ordering and all nodes in $u$'s right subtree succeeds it.**

#### Search Algorithm
*Divide and conquer* algorithm.
```java
if (t.isEmpty()) terminate unsucessfully;
else {
	r becomes the element on the root node t;
	if (c == r) terminate successfully;
	else if (e < r) repeat search on left subtree;
	else repeat search on right subtree
}
```

#### Complexity
Best case is a perfect binary tree $O(\log n)$ while worst case is a skinny binary tree $O(n)$.

#### insert and delete
*insert* is straightforward:
- perform a search for the element
- if the element is found, do nothing
- if an empty node is reached, insert a new node containing the element

*delete* is straightforward if element is found on a node with at least one external child, just standard **Bintree** *delete*, else:
- replace deleted element with predecessor
- delete predecessor

#### Balancing Tree's
*delete* has the tendency to *screw* the tree right, it is beneficial to keep the tree balanced

### Self-balancing Trees
#### AVL Trees
Where the height of the left subtree differs to the right subtree by at most *1*
They have order of $O(\log n)$ for *searching, inserting, deleting*.

##### Operations
To *insert* an element:
- insert element into an external node
- starting with it's parent, check each ancestor of the new node to ensure the *left and right subtree* heights differ by at most one
- if we find an node that doesn't satisfy this, we perform a *rotation*

To *delete* an element:
- delete the element
- starting with it's *parent*, check each ancestor of the new node to make sure it's balanced
- if not perform a *rotation* 
- carry on upwards until the root

Complexity of $O(\log n)$
##### Rotation
![[Rotation Drawing]]
Constant time operation.

#### B Trees
A [[#B Trees]] is a data structure that allows *searching, insertion, deletion* in *amortized log time*.
Each node of a [[#B Trees]] can contain *multiple* items and *multiple* children.

#### Red-black trees
Another variation of a [[#Binary Search Tree]] that is more efficient than the aforementioned variations. Each node is coloured red or black to satisfy the properties: 
- root is black
- every external node is black
- the children of a red node is black
- every external node has the same number of black ancestors