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
#### Bucketing and seperate chaining
Allow more than one item to be stored at each position in the hash table; associate a list with each hash table call.
- simple to implement
- slows down table access
- extra space
- performance deterioates as chain length extends

Worst case is $O(n)$.

#status/todo finish lecture (55 mins in)