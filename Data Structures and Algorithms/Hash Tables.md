# Hash Tables
Works by:
- setting aside a big enough block for all possible data items
- spacing these so that the address of any item can be found by a simple calculation from its ordinality
- 
What if we use a block not big enough for all items?
- addressing function must map all items into the space (*hash function*)
- some items may get mapped to the same position (*collision*)

### Hash Functions
$h(a)$ is called the *home address* of a.
A hash function that maps each item to a unique position is called *perfect*.