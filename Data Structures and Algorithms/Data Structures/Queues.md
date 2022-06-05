# Queues
Similar to a [[Stack]] but items are deleted from the front, and added to the back.

### Specifications 
- `Queue()`: create an empty queue
- `isEmpty()`: return true if the queue is empty, false otherwise 
- `enqueue(e)`: e is added as the last item in the queue 
- `examine()`: return the first item in the queue, or throw an exception if the queue is empty 
- `dequeue()`: remove and return the first item in the queue, or throw an exception if the queue is empty

### Block Representation
- sequence of elements stored in array
- the simplest representation, although queue would be bounded
- indices (counters) indicating the first and last element
- **full** when `first == last + 1`



#### Cyclic Queue
The problem with the normal block representation is that as elements are deleted, the space of the array is eroded as it isn't reused.
Solved by looping the counters around by using the %("mod") operation. 
I.e. `last = (last + 1) % items.length;`

##### Empty?
Queue is now empty is `first == (last + 1) % items.length`.
But this represents the condition of a full queue.

One option is we define the queue as full when it contains `items.length - 1` elements and use the condition:
`first == (last + 2) % items.length`

But now the queue can only hold n - 1 objects.

Another option is, we can keep one index for the element increment, and count the size of the queue.

### [[Recursion|Recursive]] Representation
```java
/**  
* Linked list representation of a queue of characters.  
*/  
public class QueueLinked implements Queue {  
	/**  
	* the front of the queue, or null if queue’s empty  
	*/  
	private Link first;  
	/**  
	* the back of the queue, or null if queue’s empty  
	*/  
	private Link last;  

	/**  
	* initialise a new Queue  
	*/  
	public QueueLinked () {  
	first = null;  
	last = null;  
	}  
	/**  
	* test whether the queue is empty  
	* @return true if the queue is empty, false otherwise  
	*/  
	public boolean isEmpty () {return first == null;}

	public Object examine () throws Underflow {  
	if (!isEmpty()) return first.item;  
	else throw new Underflow("examining empty queue");  
	}

	public Object dequeue () throws Underflow {  
	if (!isEmpty()) {  
		Object o = first.item;  
		first = first.successor;  
		if (isEmpty()) last = null;  
		return o;  
	}  
	else throw new Underflow("dequeuing from empty queue");  
	}

	public void enqueue (Object a) {  
	if (isEmpty()) {  
		first = new LinkChar(a,null);  
		last = first;  
	}  
	else {  
		last.successor = new LinkChar(a,null);  
		last = last.successor;  
	}
}
```
- unbounded
- no space wasted
- no erosion of space