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

*2-universal* hash function has the form
$$h(i) = ((c_1i+c_2)\mod p)\mod m$$
$(c_1i+c_2)\mod p)$ : *scrambles* $i$
$\mod m$ : maps onto block

This works for integer, but what about non-integers.

#### Strings
Options:
- length of each word (lots of collisions)
- ordinality of the first character (fewer collision but still poor)
- sum of ordinality
- weighting each character, than summing ordinality (very rare collisions)

A typical hash function of strings is to treat the characters as digits of an integer to base $b$. 
$$[ord(s_1)b^{k-1}+ord(s_2)b^{k-2}+...+ord(s_k)b^0]\mod 2^B$$
$b$ is a small odd number, like 37, $\mod 2^B$ gives the least significant $B$ bits

### Collision Resolution Techniques
#### Bucketing and separate chaining
Allow more than one item to be stored at each position in the hash table; associate a list with each hash table call.
- simple to implement
- slows down table access
- extra space
- performance deteriorates as chain length extends

Worst case is $O(n)$.

#### Open addressing
- store all item in hash table
- deal with collision by incrementing hash table index, with wrap around
Can be *linear probing* by going down until item or *null* is found.
Or by *double hashing* by hashing again.
- all space is used
- space is now limited
- deletions are more complicated, *erosion of space*
### Dynamic Tables - Linear Hashing
There are methods that allow a hash table to be dynamic rather than static.
*Linear hashing* is an extension of separate chaining, although we limit the size of the bucket
- *insertion* - if the average chain exceeds the bound, split the bucket, and hash the items in the bucket with double the previous bucket
- *deletion* - if the bucket size drops below a predefined minimum, shrink the table