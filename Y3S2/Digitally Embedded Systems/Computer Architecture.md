Created: 25/08/2023 at 10:40

### CPU Buses
Has three buses:
- Data Bus
- Address Bus
- Control Bus

### Von Neumann Architecture
- CPU
- Memory (1 for both data and instructions)
- I/O
![[Computer Architecture-1692931269438.jpeg]]

### Harvard Architecture
- CPU
- Memory (separate for data and instructions)
- I/O
![[Computer Architecture-1692931315879.jpeg]]

### Microcontrollers vs Microprocessors
- Microcontrollers have all the components of a computer on a single chip. (CPU, Timers, I/O, Memory, etc.)
- Microprocessors are just the CPU.

### Chip Packaging Technology
- Dual In-line Package (DIP)
- Surface Mount Technology (SMT)
- Ball Grid Array (BGA)

### Input and Output
I/O implementation can be:
- Memory Mapped I/O
- Port Mapped I/O
- Direct Memory Access (DMA)

#### Memory Mapped I/O
- I/O devices are treated as memory locations.
- I/O devices are accessed using the same instructions as memory.

#### Port Mapped I/O
- I/O devices are treated as separate ports.
- I/O devices are accessed using special I/O instructions.

### Connecting Multiple Memory Modules
Multiple memory chips, serial access:
- Extends the address range
- One memory chip active at a time
 ![[Computer Architecture-1692931833654.jpeg]]

Multiple memory chips, parallel access:
- Increases the data bus width
- Several memory chips active at the same time
![[Computer Architecture-1692932022944.jpeg]]

#### Consequences of Parallel Access
- Read and write operations for 16 bit words must use *even addresses*
- All 16 bit data must start at even adresses

- In 32 bit systems, 32 bit data must start at addresses divisible by 4

### Addresses
![[Computer Architecture-1692932393471.jpeg]]

### Chip Select Example (Traditional Architecture)
![[Computer Architecture-1692932483557.jpeg]]
![[Computer Architecture-1692932542030.jpeg]]

### Memory Foldback
With incomplete address decoding (dropping any the bits), the memory is mirrored in the address space.
E.g. 20 address lines, then
\$0000 - \$1FFFF is the same as \$80000 - \$9FFFF

If this is a problem (not really) can be avoided by using all higher address lines.

### Modern Chip Select
Tell systems sizes of memory modules, and the system will automatically decode the addresses using programmable chip select.

### External Ports
- Use of an external latch chip
- Latch chip needs to be connected to the address bus and the data bus
- Latch chip can be used for 8 bit output or 8 bit input but not mixed

### Complete System
![[Computer Architecture-1692933196556.jpeg]]

### Single Chip Solutions
- cheaper because less chips
- cheaper because simpler PCB
- cheaper because less labor
- smaller because less chips

- limited and not extendible
- not data/address bus on pins
- chip has to match application
