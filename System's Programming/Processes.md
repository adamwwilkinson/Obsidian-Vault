# Processes
Created: 14/08/2022 at 21:43
Tags: 
Related: [[Operating Systems]]

### What
#### Naively
- a program under execution
- an existence of a program
- an identifiable entity executed on a processor by the operating system

#### Operating System-ly
- an executable instance of a program
- the associated data operated upon by a program
- the program's execution context

The fundamental activity of an [[Operating Systems]] is the *creation, manangement, * and *termination* of processes.

### Process States
#### Processor's View
Execute machine instruction from main memory, unaware how these instruction provided by the program counter are linked, or how they make up an entity we call a process.

#### Process' View
Either being executed by the processor, or is waiting to be executed.

Therefore there are two possible process states: **Running** and **Ready**.

Can a process determine itself what state it is in?

### Process Transitions
OS's role is to manage the execution of existing and new processes by moving them between the two states until they finish
