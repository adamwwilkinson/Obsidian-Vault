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
