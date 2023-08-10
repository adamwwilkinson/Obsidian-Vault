Created: 06/08/2023 at 10:05

### Types
- ROM: Read Only Memory (Keeps data when power is off)
- RAM: Random Access Memory (Loses data when power is off)

### ROM
Contents cannot be changed, used for system booting and firmware.
![[Memory-1691287626816.jpeg]]
This ROM cell has $8 \times 2^{10}$ memory cells.

#### Types
##### ROM (Read Only Memory)
- Mask ROM: Manufactured with data already stored
- Mass Production
- Can never be changed

##### PROM (Programmable Read Only Memory)
- Comes 'empty'
- Can be programmed once
- Once a bit has been flipepd, it cannot be flipped back

##### EPROM (Erasable Programmable Read Only Memory)
- Can be erased by exposing to UV light

##### EEPROM (Electrically Erasable Programmable Read Only Memory)
- Can be erased by applying an electric field

#### Implementation
![[Memory-1691288776264.jpeg]]
![[Memory-1691288835791.jpeg]]

### RAM
- Will lose content when powered off
- Can store programs and data
- Writing data to an address overwrites the previous data
![[Memory-1691289317605.jpeg]]

#### Types
##### SRAM (Static Random Access Memory)
Keeps data as long as power is on

##### DRAM (Dynamic Random Access Memory)
'Leaks' memory content over time, needs to be refreshed

### Memory Size
1 byte = 8 bits (8 flip-flops)

![[Memory-1691289808697.jpeg]]

Can only enable one at a time using tri-state gates.
![[Memory-1691289854016.jpeg]]![[Memory-1691290974256.jpeg]]![[Memory-1691290993585.jpeg]]
### Memory Control
![[Memory-1691291085574.jpeg]]

### Memory and CPU
![[Memory-1691291144373.jpeg]]

### Addresses
![[Memory-1691291178857.jpeg]]

#### Address Space
Memory Size:
- kilobyte (kB): $2^{10} = 1024$ bytes
- megabyte (MB): $2^{20} = 1024 \times 1024$ bytes
- gigabyte (GB): $2^{30} = 1024 \times 1024 \times 1024$ bytes
- terabyte (TB): $2^{40} = 1024 \times 1024 \times 1024 \times 1024$ bytes

Size of memory module is the number of cells times the size of each cell.
![[Memory-1691291259642.jpeg]]
![[Memory-1691293188065.jpeg]]
