# Priority Queues
Extension of [[Queues]] what also has a *priority assigned to it*. 
Used in:
- scheduling service
- optimisation algorithms
- sorting
- backbone routers of internet

### Specifications
**Constructors** 
`PQueue()`: initialises an empty priority queue. 

**Checkers** 
`isEmpty()`: returns true if the priority queue is empty. 
**Manipulators** 
`enqueue(e, k)`: places e in the priority queue with key (or priority) k, 
or throws an exception if k is negative. The item is placed in front of 
all elements with lesser priority, but behind all others.  
`examine()`: returns the element at the front of the queue, or throws an 
exception if the queue is empty. 
`dequeue()`: removes the element at the front of the queue and returns 
it, or throws an exception if the queue is empty.

### Linked Representation
```java
/**  
* A Linked Priority Queue for the generic type E  
**/  
public class PQueueLinked<E> {  
	// Only one link is required!  
	private Link<E> front;  
	// Constructor  
	public PQueueLinked() {  
		front = null;  
	}

	public boolean isEmpty() {return front == null;} 
	
	public E examine() throws Exception {  
		if (!isEmpty()) {  
			return (E) front.element;  
		} else throw new Exception("Empty Queue");  
		}  
		
	public E dequeue() throws Exception {  
		if (!isEmpty()) {  
			E temp = (E) front.element;  
			front = front.next;  
			return temp;  
		} else throw new Exception("Empty Queue");  
	}

	public void enqueue(E e, int p) {  
		if (isEmpty() || p > front.priority) {  
			front = new Link<E>(e, p, front);  
		} else {  
			Link<E> l = front;  
			while (l.next != null && l.next.priority >= p) {  
				l = l.next;  
			}  
			l.next = new Link<E>(e, p, l.next);  
		}  
	}
	
	/**  
	* An inner class to hold the element, the successor,  
	* and the priority  
	**/  
	private class Link<E> {  
	E element;  
	int priority;  
	Link<E> next;  
	
	public Link(E e, int p, Link<E> n) {  
		this.element = e;  
		this.priority = p;  
		this.next = n;  
	}  
}
```
*enqueue* is $O(n)$ every other method is constant time.

### Heap Implementation
Uses [[Heapsort]] and has complexity for *enqueue, dequeue* being $O(n \log n)$.