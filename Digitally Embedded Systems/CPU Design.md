Created: 12/08/2023 at 10:20

### Function Units
Either a single input or two inputs to a single output. Dealing with words (8 bits) at a time.
![[CPU Design-1691807230333.jpeg]]![[CPU Design-1691807386783.jpeg]]![[CPU Design-1691807995780.jpeg]]

### Registers
- All bits change at the same clock signal
- Can have different sizes
![[CPU Design-1691808229359.jpeg]]

### Central Processing Unit (CPU)
Has 2 parts, the ALU (Arithmetic Logic Unit) and the Control Unit
The control unit has an output that provides addresses to the memory, and the ALU crunches data to and from memory.

### Arithmetic Logic Unit ALU
![[CPU Design-1691808362342.jpeg]]

#### Function Block
![[CPU Design-1691808389397.jpeg]]

### Control Unit
- Program counter (PC) - holds the address of the next instruction to be executed
- Sequencer - generates the control signals to the other parts of the CPU
![[CPU Design-1691808552596.jpeg]]

### Simple CPU
![[CPU Design-1691808661306.jpeg]]

#### Timing
![[CPU Design-1691808791134.jpeg]]

### Machine Code
Program to compute 1 and 2
![[CPU Design-1691808885699.jpeg]]

NOP is for no operation.

#### Restrictions
- Program never stops (cannot branch/loop)
- Calculate with constant values only (cannot load/store data to/from memory)
