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

#### Specifications
**Constructor** 
`Bintree()`: creates an empty binary tree.

**Checkers** 
`isEmpty()`: returns true if the tree is empty, false otherwise. 
`isRoot(w)`: returns true if $w$ is over the root node (if there is one), false otherwise. 
`isExternal(w)`: returns true if $w$ is over an external node, false otherwise. 
`isLeaf(w)`: returns true if $w$ is over a leaf node, false otherwise. 

**Manipulators** 
`initialise(w)`: set $w$ to the window position of the single external node 
if the tree is empty, or the window position of the root otherwise. 
`insert(e,w)`: if $w$ is over an external node replace it with an internal 
node with value $e$ (and two external children) and leave $w$ over the 
internal node, otherwise throw an exception. 
`child(i,w)`: throw an exception if $w$ is over an external node or $i$ is not 
1 or 2, otherwise move the window to the $i^{th}$ child. 
`parent(w)`: throw an exception if the tree is empty or $w$ is over the root 
node, otherwise move the window to the parent node. 
`examine(w)`: if $w$ is over an internal node return the value at that node, 
otherwise throw an exception. 
`replace(e,w)`: if $w$ is over an internal node replace the value with $e$ and 
return the old value, otherwise throw an exception. 
`delete(w)`: throw an exception if $w$ is over an external node or an 
internal node with no external children, otherwise replace the node 
under $w$ with its internal child if it has one, or an external node if it 
doesn’t.

**Alternatives for child.** 
`left(w)`: throw an exception if $w$ is over an external node, otherwise 
move the window to the left (first) child. 
`right(w)`: throw an exception if $w$ is over an external node, otherwise 
move the window to the right (second) child.

#### Block Representation
Easy to implement, to find the left child, double parent node, and to find the right child, double parent node and add 1. All operations are in constant time, but limited space.

#### Recursive Representation
Like the [[Queues#Recursion Recursive Representation]] but with two successors per node as opposed to one.

```java
public class TreeCell {

	public Object nodeValue;  
	public TreeCell[] children;
	  
	public TreeCell(Object v, TreeCell tree1, TreeCell tree2) {  
		nodeValue = v;  
		children = new TreeCell[2];  
		children[0] = tree1;  
		children[1] = tree2;  
	}  
}
```

Alternatively, for BinTree's specifically:
```java
public class TreeCell {  

	public Object nodeValue;  
	public TreeCell left;  
	public TreeCell right;  
	
	public TreeCell(Object v, TreeCell tree1, TreeCell tree2) {  
		nodeValue = v;  
		left = tree1;  
		right = tree2;  
	}  
}
```

A companion window class is needed:
```java
public class TreeWindow {  
	public TreeCell parentnode;  
	public int childnum;  
	public TreeWindow () {}

	public void initialise(TreeWindow w) {  
		w.parentnode = beforeRoot;  
		w.childnum = 0;  
	}
}
```

External nodes can be distinguished from internal nodes by having their left child having a null reference. Or just by being a null reference in of itself.

```java
public BintreeLinked () {  
	beforeRoot = new TreeCell(null, null, null);  


	public boolean isEmpty() {return beforeRoot.children[0] == null;}  
	
	public boolean isExternal(TreeWindow w) {  
		return w.parentnode.children[w.childnum] == null;  
	}

	public boolean isLeaf(TreeWindow w) {  
		return !isExternal(w)  
		&& w.parentnode.children[w.childnum].children[0] == null  
		&& w.parentnode.children[w.childnum].children[1] == null;  
	}

	public Object examine(TreeWindow w) throws OutOfBounds {  
		if (!isExternal(w))
			return w.parentnode.children[w.childnum].nodeValue;
		else throw new OutOfBounds("examining external node");  
	}  
	public void insert(Object e, TreeWindow w) throws OutOfBounds {  
		if (isExternal(w))
			w.parentnode.children[w.childnum].nodeValue = e;
		else throw new OutOfBounds("inserting over internal node");  
	}
}
```

All operations but *parent* can be implemented in constant time. *parent* takes $O(n)$.