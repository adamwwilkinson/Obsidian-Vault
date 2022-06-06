# Heap
Based on the [[Trees#Binary Trees]] where every node contains an *element* and *key*. The heap has the added priority that the key associated with any node is greater than or equal to the key associated with either of its children.
- root of the binary tree has the largest key

Similar to [[Trees#Block Representation]].

### Heapify
Many operation we perform on the heap will alter the [[Data Structures|data structure]]. It will have to be restored by the heapify method.

We continue recursively down the tree checking the swapped child until we restore the heap property. 

Complexity of heapify is $O(\log n)$, this is same for *enqueue* and *dequeue*. *examine* has linear time.