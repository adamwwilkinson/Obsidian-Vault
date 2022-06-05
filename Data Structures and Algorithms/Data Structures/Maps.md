### Relation
![[Domain and Codomain Drawing]]

### Map
A map is a binary relation where each element of the domain pairs with only one element in the codomain (*many-to-one*).
Shorthand : *affiliation(x in domain) = y in codomain*

#### Why Study Maps
Any Java method is a function or map, why implement our own map as an ADT?
- create, modify and delete maps in runtime
- a map of affiliation may change over time, Java programs cannot modify themselves
- Java methods return a result, we may want more functionality

#### Specification
**Constructor**
*Map()* : create a new map that is undefined for all elements

**Checkers**
*isEmpty()*
*isDefined(d)*

**Manipulators** 
*assign(d, c)* : assign *c* as the image of *d*
*image(d)*: returns the image of *d*
*deassign(d)*: return the image of *d* and make it undefined

### List-based Representation
A map can be considered a list of pairs.

#### Implementation
```java
private class MapLinked {
	private ListLinked list;

	public MapLinked (){
		list = new ListLinked();
	}
}
```

##### Pairs
```java
public class Pair {

	public Object item1; //domain
	public Object item2; //codomain

	public Pair (Object i1, Object i2) {
		item1 = i1;
		item2 = i2;
	}
	
	// determine whether this pair is the same as the object passed
	public boolean equals(Object o) {
		if (o == null) return false;
		else if (!(o instance of Pair)) return false;
		else return item1.equals( ((Pair)o). item1) &&
					item2.equals( ((Pair)o).item2);
	}
	
	// generate a string representation of the pair
	public String toString() {
		return "< "+item1.toString()+" , "+item2.toString()+" >";
	}
}
```

##### Image
```java
public Object image (Object d) throws ItemNotFound {
	WindowLinked w = new WindowLinked();
	list.beforeFirst(w);
	list.next(w);
	while (!list.AfterLast(w)) &&
		   !((Pair))list.examine(w).item1.equals(d) ) list.next(w);
	if (!list.isAfterLast(w)) return ((Pair)list.examin(w)).item2;
	else throw new ItemNotFound("no image for object passed");
}
```

#### Performance
*Map* and *isEmpty* make trivial constant time calls, the other operations require a sequential search and take *O(n)*.

### Sorted-block Representation
Is you use a *Binary Search*, which requires the objects to be ordered, you can have better performance.

#### Binary Search
```java
private Pair[] block;

protected int bSearch (Object d, int l, int u) {  
	if (l == u) {  
		if (d.toString().compareTo(block[l].item1.toString()) == 0)  
			return l;  
		else return -1;  
	}  
	
	else {  
		int m = (l + u) / 2;  
		if (d.toString().compareTo(block[m].item1.toString()) <= 0)  
			return bSearch(d,l,m);  
		else return bSearch(d,m+1,u);  
	}  
}
```
Complexity of $O(\log n)$. Assign and deassign may need to move items around to maintian order, this means they are $O(n)$.

| Operation   | Linked List | Sorted Block |
| ----------- | ----------- | ------------ |
| *Map*       | 1           | 1            |
| *isEmpty*   | 1           | 1            |
| *isDefined* | $n$         | $\log n$     |
| *assign*    | $n$         | $n$          |
| *image*     | $n$         | $\log n$     |
| *deassign*  | $n$         | $n$             |

[[#Sorted-block Representation]] may be best choice if:
1. map has fixed maximum size
2. domain is tottaly ordered
3. map is static - mostly readoing done rather than writing
Otherwise [[#List-based Representation]] is better.