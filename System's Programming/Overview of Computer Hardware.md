Created: 08/08/2022 at 14:10
Tags: #topic/hardware 
Related: [[Operating Systems]]

### Central Processing Unit
Controls the computer itself, as well as handling I/O operations.

#### Handling and Data Fetching
The CPU *fetches* a copy of the contents in the MAR (memory address register).
Then depending on if the contents are a value or instructions, it either operates on the value as data, or carry out the instructions. Can also copy the contents in I/O devices.

#### Interrupts
A form of communication between the software and hardware within a CPU. Can also tell the CPU an error has occured.

The CPU chugs along until a change, or interrupt, occurs to inform it to perform an action.

### Ram
Stores instruction and data. Short term volatile storage that is fast.

### Secondary Storage
Move data to and from the other components, usually to provide persistent long term storage.

### Registers
High speed memory in the CPU. Several roles, general purpose to hold arithmetic values. Different registers handle logic, or arithmetic instructions.

#### Control and Status Registers
*Instruction register* holds the current instruction being executed, while the *program counter* holds the memory address of the next instruction to be executed.

### Communication Bus
Provides a "highway" on which data can travel between components.

### Memory Heirachy
![[Screen Shot 2022-08-08 at 2.41.23 pm.png]]