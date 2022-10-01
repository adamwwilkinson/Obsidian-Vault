# Stack
[[Recursion|Recursive]] data structure that allows us to insert, delete, and examine **only** the *first* element in the [[Lists|list]].
Conceptually, the successor of a stack is a stack.

### Operations
- *Stack()*: create an empty stack 
- *isEmpty()*: return true if the stack is empty, false otherwise 
- *push(e)*: item e is pushed onto the top of the stack 
- *peek()*: return the item on the top of the stack, or throw an exception if the stack is empty 
- *pop()*: remove and return the item on the top of the stack, or throw an exception if the stack is empty
### The Code
```java
public class LinkedStack {  
	/**  
	* Reference to the first link in the stack, or null if  
	* the stack is empty.  
	*/  
	private Link first; // Private - users cannot access  
	// this directly.  
	/**  
	* Create an empty stack.  
	*/  
	public LinkedStack() {first = null;} // The constructor.  
	/**  
	* Test whether the stack is empty.  
	* @return true if the stack is empty, false otherwise  
	*/  
	public boolean isEmpty () {return first == null;}  
	/**  
	* Insert an item at the front of the stack.  
	* @param o the Object to insert  
	*/  
	public void insert (Object o) {first = new Link(o, first);}  
	
	
	/**  
	* Examine the first item in the stack.  
	* @return the first item in the stack  
	* @exception Underflow if the stack is empty  
	*/  
	public Object examine () throws Underflow {  
	if (!isEmpty()) return first.item;  
	else throw new Underflow("examining empty list");  
	}  
	// Underflow is an example of an exception that  
	// occurs (or is ‘‘thrown’’) if the list is empty.  
	/**  
	* Delete the first item in the stack.  
	* @exception Underflow if the stack is empty  
	*/  
	public void delete () throws Underflow {  
	if (!isEmpty()) first = first.successor;  
	else throw new Underflow("deleting from empty list");

	private class Link {
	Object head;
	Link tail;
	public Link(Object o, Link l) {
		head = o;
		tail = l;
	}
}
```

### What It Looks Like
![[List Drawing|600]]