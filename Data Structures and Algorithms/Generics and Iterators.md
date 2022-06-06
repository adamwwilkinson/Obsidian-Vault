# Generics and Iterators
### Casting
Used to assign down the 'hierarchy'.
```java
Object t = 2
String st = (String) (t)
```

### Generics
Allow us to specify the type of collection class.
```java
Stack<String> ss = new Stack<String>();
String s = "OK, I’m going in!";  
ss.push(s);  
s = ss.pop()
```

#### Writing Generic Classes
```java
/**  
* A simple generic block stack for  
* holding object of type E  
**/  
class Stack<E> {  
	private Object[] block;  
	private int size;  
	public Stack(int size) {block = new Object[size];}  
	public E pop() {return (E) block[--size];}  
	public void push(E el) {block[size++] = el;}  
}
```

#### Using Generic Classes
```java
public static void main(String[] args){  
	//create a Stack of Strings  
	Stack<String> s = new Stack<String>(10);  
	s.push("abc");  
	System.out.println(s.pop());
	
	//create a stack of Integers  
	Stack<Integer> t = new Stack<Integer>(1);  
	t.push(7);  
	System.out.println(t.pop());  
}
```

### Iterators
Often necessary to *traverse* a collection. An iterator is a companion class to a collection, that allows us to do this.

#### Specification
`boolean hasNext()`: return true if the iterator has more items 
`E next()`: if there is a next item, return that item and advance to the next position, otherwise throw an exception 
`void remove()`: remove from the underlying collection the last item returned by the iterator. Throws an exception if the immediately preceding operation was not next.

#### Fail-Fast
What happens if a backing collection is changed during use of an iterator?

**One Solution**: disallow further use of an iterator is a modification to the backing collection has occurred. This would require for the backing collection to have a field which tracked how many times it's been modified, and the iterator to have a field which takes that integer as a field that is constantly checked against each other.