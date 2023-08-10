Created: 05/08/2023 at 10:08

### Overview
#### Combinatorial Circuits
- Only logic gates, no feedback, no memory
- No states
- Equivalent to maths function

#### Sequential Circuits
- Logic gates with feedback and memory
- States
- Equivalent to computer program

## Modules (Building blocks for a CPU)
### Combinatorial Circuits
Arbitrarily complex circuitrs can be built from logic gates.
The output only depends on the input lines nad thre is no memory.
#### Decoder
Decodes the binary number, and outputs the matching decimal output.
![[Combinatorial and Sequential Circuits-1691201678564.jpeg]]

#### Encoder
Encodes the decimal number, and outputs the matching binary output.
![[Combinatorial and Sequential Circuits-1691201786579.jpeg]]

#### Multiplexer
Selects one of the inputs to be the output.
![[Combinatorial and Sequential Circuits-1691201985435.jpeg]]

##### 4-way Multiplexer
![[Combinatorial and Sequential Circuits-1691202092514.jpeg]]

#### Multiplexer with Multiple Lines
![[Combinatorial and Sequential Circuits-1691202182413.jpeg]]

#### Demultiplexer
Selects one of the outputs to be the input.
![[Combinatorial and Sequential Circuits-1691202269347.jpeg]]

#### Half Adder
Add two binary digits, and outputs the sum and carry.
![[Combinatorial and Sequential Circuits-1691202410617.jpeg]]

#### Full Adder
Add three binary digits, and outputs the sum and carry.
![[Combinatorial and Sequential Circuits-1691202527997.jpeg]]

##### Full Adder (n Stages)
![[Combinatorial and Sequential Circuits-1691202573231.jpeg]]

#### Tri-State
Electrically isolates the output from the input.
![[Combinatorial and Sequential Circuits-1691202760898.jpeg]]

### Sequential Circuits
Memory can also be added to a circuit using *latches* and *flip-flops*.
Introducing a *feedback* loop allows to trap a signle bit of information.

#### Smallest Cell of Memory
![[Combinatorial and Sequential Circuits-1691203146786.jpeg]]

#### Changing Cell of Memory
Using a NOR gate, the output can be changed.
![[Combinatorial and Sequential Circuits-1691203282637.jpeg]]
The $S$ input is the *set* input (to 1), and the $R$ input is the *reset* input (to 0).

#### RS Latch
![[Combinatorial and Sequential Circuits-1691203477173.jpeg]]

#### D-Latch with Enable
![[Combinatorial and Sequential Circuits-1691203507572.jpeg]]

#### Edge Triggered Flip-Flops
If edge triggered it is called a flip-flop, otherwise if level triggered it is called a latch.
![[Combinatorial and Sequential Circuits-1691203707253.jpeg]]

If the hollow triangle is coloured in, it triggers on falling edge.

#### Backup
![[Combinatorial and Sequential Circuits-1691203892257.jpeg]]

#### Registers
Several flip-flops can make a register, a n-bit register is a group of n binary cells (flip-flops).
![[Combinatorial and Sequential Circuits-1691285719168.jpeg]]
![[Combinatorial and Sequential Circuits-1691285867268.jpeg]]

#### Clock
![[Combinatorial and Sequential Circuits-1691286002653.jpeg]]

#### Real Hardware
##### Breadboard
Fore experimenting with real hardware, a breadboard is used.
![[Combinatorial and Sequential Circuits-1691286032026.jpeg]]

##### LEDs and Resistors
![[Combinatorial and Sequential Circuits-1691286063148.jpeg]]