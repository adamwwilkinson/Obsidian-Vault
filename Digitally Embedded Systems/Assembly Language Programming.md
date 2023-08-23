Created: 17/08/2023 at 15:20

### Machine Code
Computer comprises hardware and software.
Load program on hardware for a particular task.
![[Assembly Language Programming-1692257317061.jpeg]]

Very low level programming, difficult and error-prone, seldom used in practise.

### Assembler
![[Assembly Language Programming-1692257363553.jpeg]]

Translation of mnemonic codes to machine language, machine-dependent, line by line execution, symbolic address calculation, *cross assembler* if hardware1 != hardware2.
![[Assembly Language Programming-1692257453842.jpeg]]

### Compiler for C and C++
![[Assembly Language Programming-1692257552887.jpeg]]

Translation of C source code to machine language, *machine-independent*, use of variable and function names, *cross compiler* if hardware1 != hardware2.

### Atmel Assembly Commands
![[Assembly Language Programming-1692257651430.jpeg]]![[Assembly Language Programming-1692257679662.jpeg]]
#### Operands
![[Assembly Language Programming-1692257842686.jpeg]]![[Assembly Language Programming-1692257864137.jpeg]]
![[Assembly Language Programming-1692257967866.jpeg]]
![[Assembly Language Programming-1692258080508.jpeg]]

#### Registers
32 general purpose registers, 3 index registers. Status register *SREG*, 64 special registers for control and I/O.

### Examples
![[Assembly Language Programming-1692258246176.jpeg]]

### Jump and Branch
![[Assembly Language Programming-1692258506085.jpeg]]

With the compare command, the result is stored in the status register. The jump command can then be used to jump to a particular address depending on the result of the compare command.
![[Assembly Language Programming-1692258668660.jpeg]]
![[Assembly Language Programming-1692258731559.jpeg]]

### Subroutines and Stack
Similar to branch and jump, but the program counter is saved on the stack. Use `CALL` and `RET` to use them.
![[Assembly Language Programming-1692259224829.jpeg]]