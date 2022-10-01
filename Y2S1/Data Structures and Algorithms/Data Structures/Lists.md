# Lists
Can be defined [[Recursion|recursively]] as:
- an empty list is a list (base case)
- an item followed by a list is a list (recursive case)

Useful for:
- text editors
- bibliography
- addresses

### Windows
A window refers to a specific position in the list. Allowing multiple windows in one instance can introduce problems, as things can be deleted and windows will be lost.

```java
public class WindowBlock {  
	public int index;  
	public WindowBlock () {}  
}
```

### Specification
**Constructors**
`List()`: Initialises an empty list with two associated window positions, before first and after last.

**Checkers**
`isEmpty()`: Returns true if the list is empty.
`isBeforeFirst(w)`: True if w is over the before first position.
`isAfterLast(w)`: True if w is over the after last position.

**Manipulators**
`beforeFirst(w)`: Initialises w to the before first position.
`afterLast(w)`: Initialises w to the after last position. 
`next(w)`: Throws an exception if w is over the after last position, otherwise moves w to the next window position. May be after last.
`previous(w)`: Throws an exception if w over is the before first position,
otherwise moves w to the previous window position. 
`insertAfter(e,w)`: Throws an exception if w is over the after last position, otherwise an extra element e is added to the list after w. 
`insertBefore(e,w)`: Throws an exception if w is over the before first
position, otherwise an extra element e is added to the list before w. 
`examine(w)`: Throws an exception if w is in the before first or after last 
position, otherwise returns the element under w. 
`replace(e,w)`: Throws an exception if w is in the before first or after last
position, otherwise replaces the element under w with e and returns  
the old element. 
`delete(w)`: Throws an exception if w is in the before first or after last 
position, otherwise deletes and returns the element under w, and places 
w over the next element.

### Block Representation
```java
public class ListBlock {  
	private Object[] block; // Holds general objects  
	private int before; // An index to the before first position  
	private int after; // iAn ndex to the after last position

	public ListBlock (int size) {  
		block = new Object[size];  
		before = -1;  
		after = 0;  
	}

	public void next (WindowBlock w) throws OutOfBounds {  
	if (!isAfterLast(w)) w.index++;  
	else  
	throw new OutOfBounds("Calling next after list end.");  
	}

	public void beforeFirst (WindowBlock w) {w.index = before;}

	public void insertBefore (Object e, WindowBlock w) throws  
	OutOfBounds, Overflow {  
		if (!isFull()) {  
			if (!isBeforeFirst(w)) {  
				for (int i = after-1; i >= w.index; i--)  
					block[i+1] = block[i];  
				after++;  
				block[w.index] = e;  
				w.index++;  
			}  
		else throw new OutOfBounds ("Inserting before start.");  
		}  
		else throw new Overflow("Inserting in full list.");  
	}
}
```

### Singly Linked Representation
*previous* and *next* always well-defined due to use of sentinel cells. Only keeps track of the next link.

```java
public class ListLinked {  
	private Link before;  
	private Link after;  
	public ListLinked () {  
	after = new Link(null, null);  
	before = new Link(null, after);  
	}  
	public boolean isEmpty () {return before.successor == after;}

	public void insertBefore (Object e, WindowLinked w) throws 
	OutOfBounds {  
	if (!isBeforeFirst(w)) {  
		w.link.successor = new Link(w.link.item, w.link.successor);  
		if (isAfterLast(w)) after = w.link.successor;  
		w.link.item = e;  
		w.link = w.link.successor;  
		}  
	else throw new OutOfBounds ("inserting before start of list");  
	}

	public void previous (WindowLinked w) throws OutOfBounds {  
		if (!isBeforeFirst(w)) {  
			Link current = before.successor;  
			Link previous = before;  
			while (current != w.link) {  
				previous = current;  
				current = current.successor;  
			}  
			w.link = previous;  
		}  
		else throw new OutOfBounds ("Calling previous before start of" 
									"list.");  
	}
}
```

### Doubly Linked Representation
For a [[#Singly Linked Representation]] *previous* is $O(n)$, can be solved by referencing in both directions. The downside is extra storage is required for each cell, and more references to update.

We can link the pointers around to create a *circulatly linked list*. And this means we only need a reference to the first sentinal cell.

### Complexity
| Operation       | [[#Block Representation]] | [[#Singly Linked Representation]] | [[#Doubly Linked Representation]] |
| --------------- | ------------------------- | --------------------------------- | --------------------------------- |
| `List`          | 1                         | 1                                 | 1                                 |
| `isEmpty`       | 1                         | 1                                 | 1                                 |
| `isBeforeFirst` | 1                         | 1                                 | 1                                 |
| `isAfterLast`   | 1                         | 1                                 | 1                                 |
| `beforeFirst`   | 1                         | 1                                 | 1                                 |
| `afterLast`     | 1                         | 1                                 | 1                                 |
| `next`          | 1                         | 1                                 | 1                                 |
| `previous`      | 1                         | *n*                                 | 1                                 |
| `insertAfter`   | *n*                       | 1                                 | 1                                 |
| `insertBefore`  | *n*                       | 1                                 | 1                                 |
| `examine`       | 1                         | 1                                 | 1                                 |
| `replace`       | 1                         | 1                                 | 1                                 |
| `delete`        | *n*                       | 1                                 | 1                                  |
