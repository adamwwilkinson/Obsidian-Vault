# Allocating Memory to Processes
Created: 12/09/2022 at 16:29
Tags: 
Related:

### Memory Management
The task of allocating memory to processes, and efficiently ensuring that processes have their instructions and data in main memory when needed.

An important goal of the OS is to keep as many processes executable as possible, and it achieves this only when processes have the available memory they require.

### Virtual Memory
If processes get hungry and there is not enough physical memory (RAM) we can use secondary memory.

### Requirements of Memory Management
#### Local Organisation
Programs are seldom written or executed in a way which occupy linear sequences of addresses.

Ideally, all references from one module to another are resolved at run-time, maintaining their independence

#### Physical Organisation
A programmer cannot predict the size nor location of the process' memory. The task of moving information between main and secondary memory is on the OS.

#### Sharing
There is a need to allow processes to share memory.

#### Relocation
Where processes start off in a location of memory and is moved to another. I.e. a processbeing suspended and restarted.

The OS has the responsibility to tell the process where it is in memory, and where it's variables are in memory.

#### Protection
Each process must be protected from either accidental or deliberate "inteferences" from other processses.

### Initial Memory Allocation Using Partitioning
The OS itself occupies a fixed portion of main memory. The remainder is used for processes. This leftover memory is seperated using fix-sized partitions, either equal or unequal.

### Dynamic Memory Partitioning
Overcomes any shortcomings of fixed partitioning but can lead to gaps of unused memory, too small to hold a new process. Even if the total amount of free memory exist.
#todo/excalidraw

#### Algorithms
##### First-fit
Find the first unused block of memory that can contain the process

##### Best-fit
Find the smallest unused block that can contain the process.

##### Next-fit
Remember where the last process was allocated and find the first unused block that can contain that process.
