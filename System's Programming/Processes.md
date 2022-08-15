# Processes
Created: 14/08/2022 at 21:43
Tags: #topic/software 
Related: [[Operating Systems]]

### What
Historically processes were expensive, ran on tapes or paper.

#### Naively
- a program under execution
- an existence of a program
- an identifiable entity executed on a processor by the operating system

#### Operating System-ly
- an executable instance of a program
- the associated data operated upon by a program
- the program's execution context

The fundamental activity of an [[Operating Systems]] is the *creation, management, * and *termination* of processes.

### Process States
#### Processor's View
Execute machine instruction from main memory, unaware how these instructions provided by the program counter are linked, or how they make up an entity we call a process.

#### Process' View
Either being executed by the processor, or is waiting to be executed.

Therefore, there are two possible process states: **Running** and **Ready**.

*Can a process determine itself what state it is in?*

### Process Transitions
OS's role is to manage the execution of existing and new processes by moving them between the two states until they finish.

#todo/excalidraw 2 state process model and queuing diagram

When there are no process the OS created an *idle process* which it does while waiting for another process.
### Process Creation
In the creation of a new process, the operating system must allocate space for both the process and the OS.

**Real time** - guarantees a timeframe within a process will be done.

Where do they come from?
- new process from a batch queue
- a user logging on to a terminal
- existing process may request new processes
- the OS may create a process itself

### Timer Interrupts
A *hardware timer* will periodically generate an interrupt. Between the execution of any two instructions, the processor will look for interrupts, calling the *interrupt handler* when it finds one. The handler will increment and examine the accumulated time for the currently executing process, moving it from **Running** to **Ready**.

**Time Quantum** - the maximum time a process is permitted to run.

### Blocking of Processes
**Compute-bound** processes, those who continually execute until the end of their time quanta, are rare.

Most processes will request some input or output (I/O) from a slow source (disk drive, tape, keyboard, mouse, or clock). This means the process will have to wait for the request to be satisfied.

This gives us a new state **Blocked** which means it is not **Ready** until its I/O request is satisfied.

### 5-State Model of Process Execution
#todo/excalidraw 
Includes two new states: **New** for processes not yet been admitted to **Ready** for resource reasons and **Exit** for terminated processes whose return result or resources are required for other processes.

### Supporting Multiple Blocked States
Maintain a queue for each possible event type.
#todo/excalidraw 

### Swapping of Processes
When none of the processes in main memory is **Ready**, the OS swaps the memory of some **Blocked processes** to recover memory. These processes are moved to a new state, **Suspend** which is a queue of processes that have been kicked out.

#todo/excalidraw  