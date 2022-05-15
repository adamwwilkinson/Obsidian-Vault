# Sets and Tables
Sets are usually displayed as a *venn diagram*.

### Definitions
**Set**  
- used when set-theoretic operations are required  
-  elements may or may not be ordered  
- includes “membership” operations: *isEmpty*, *insert*, *delete*, *isMember*  
-  includes “set-theoretic” operations: *union*, *intersection*, *difference*, *size*, *complement*  

**Table**  
- simpler version of Set without the set-theoretic operations  
-  elements assumed to be unordered  

**Dictionary**  
- like Table but assumes elements are totally ordered  
-  includes “order related” operations: *isPredecessor* , *isSuccessor* ,  *predecessor* , *successor* , *range*

**Elements** - single items with unique *keys*

### Set Specification  
 **Constructors**  
 *Set()*: create an empty set.  
 
 **Checkers**  
 *isEmpty()*: returns true if the set is empty, false otherwise.  
 *isMember(e)*: returns true if e is a member of the set, false otherwise.  


**Manipulators**  
*size()*: returns the cardinality of (number of elements in) the set.  
*complement()*: returns the complement of the set (only defined for finite  universes).  
*insert(e)*: forms the union of the set with the singleton {e}  
*delete(e)*: removes e from the set  
*union(t)*: returns the union of the set with t.  
*intersection(t)*: returns the intersection of the set with t.  
*difference(t)*: returns the set obtained by removing any items that  appear in t.  
*enumerate()*: returns the “next” element of the set. Successive calls to  enumerate should return successive elements until the set is exhausted.

### Set Represntation

#### Characteristic Fuction representation
Not good if universe is very large, and sets are very small.
Define by:
$
 f(e) = \begin{cases} 
          true & e\in 0 \\
        false & otherwise \\
       \end{cases}$

##### Advantages
Translates set operations into efficient bit operations, *(1 means membership, 0 means not a member)*.
- *insert* — *or* the appropriate bit with 1  
- *delete* — *and* the appropriate bit with 0  
- *isMember* — is the (boolean) value of the appropriate bit  
- *complement* — complement of a bit vector  
- *union* — *or* two bit vectors  
- *intersection* — *and* two bit vectors  
- *difference* — *complement* and *intersection*