# Sets

### Attributes
- mutable
- collection of unorderted, distinct items
- very fast $O(1)$, refer to [[Algorithms#Complexity]]
- uses [[Hash Tables|hashing]]

### Methods
```python
empty_set = set()
```
- union(), creates a new set containg items in both sets
- intersection(), creates a new set from items only in both
- difference(), creates a new set without items in the argument
- symmetricdifference(), opposite of intersection
- isSubset()
- isSuperset() 

### Frozen Sets
Frozen set turns a mutable set into an immutable set, now we can have set of sets (remember a set's elements must be immutable).