Created: 13/09/2022 at 10:21
Tags: 
Related:

Over long periods of time the centers of a program's memory reference cluster may move, but over short periods they remain largely static.

Program execution tends to be sequential, i.e. the next address we need is close to or even right after the pervious address.
For efficiency we want bits of related memory to be in the same memory partition/segment.

### Cache Memory
Holds larger blocks of memory, (whole pages of memory). Fetching from the cache is a lot faster then fetching the initial instructions from disk.

### Paging against [[Allocating Memory to Processes#Dynamic Memory Partitioning]]
As processes are swapped back in, it may occupy a different region in memory.

A process is broken into pages and these need not be contigous in physical memory.

#### Paging Advantages
- Now more (pieces of) processes may be maintaied in main physical memory. (**Ready/Running**)
- If the swapping space is larger than the physical memory, any single process may demand more memory than the amount of physical memory installed.

This last aspect gives the technique it's name: *virtual memory*

### Virtual Memory and Resident Working Sets
The principle of referential locality says that at any time, only a small subset of a process' instruction and data will be required.
We define a process' page in physical memory as its *resident/working set*.

#### Virtual Memory and Page Tables
In virtual memory page table entries must contain additional information, indicating if it is in physical memory (a *P* bit) and if the page has been modified since it was brought to physical memory (a *M* bit).
If the modified bit is flipped then it tells us we need to write to disk to update the instruction.

### Page Thrashing
If a page is evicted from physical memory just before it is required (pulling it back in to physical memory) *page thrashing* occurs.

We hope the OS is intelligent about which page in physical memory to discard for space.

### Fetching for Virtual Memory
- How should the OS decide when to pull a process' pages?

When a reference to that page is made, or intelligently predicting to next page to be called, *predictive pre-paging*.

- We also get the same issue from [[allocating-memory-to-processes]] about where it should be allocated.

- Which existing blocks should be replaced?

- How many processes to admit the Ready and Running states?
