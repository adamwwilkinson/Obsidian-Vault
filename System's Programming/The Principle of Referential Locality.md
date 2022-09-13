# The Principle of Referential Locality
Created: 13/09/2022 at 10:21
Tags: 
Related:

Over long periods of time the centers of a program's memory reference cluster may move, but over short periods they remain largely static.

Program execution tends to be sequential, i.e. the next address we need is close to or even right after the pervious address.
For efficiency we want bits of related memory to be in the same memory partition/segment.

### Cache Memory
Holds larger blocks of memory, (whole pages of memory). Fetching from the cache is a lot faster then fetching the initial instructions.

### Paging against [[allocating-memory-to-processes#dynamic-memory-partitioning]] 

