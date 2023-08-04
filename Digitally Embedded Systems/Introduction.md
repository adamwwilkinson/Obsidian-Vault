Created: 28/07/2023 at 15:43

### Digital
Comes from the word digit, *integer numbers* as opposed to *floating point*.

### Switches
All digital systems rely on switching between two logic states, **0** and **1**.

#### Mechanical
Complicated machiery were invented and built without electronics, just using mechanical parts.

They had a lot of problems, like being slow, large, unreliable, and expensive.

#### Electromagnetic Switches
The first automatic switches were *Relays*, and allows for electronic switching.
![[Introduction-1690530656353.jpeg]]

Silimar issues to mechanical switches, but faster.

#### Vacuum Tubes
Triode as electronic switching devices or amplifiears.
Faster and more reliable than relays.

#### Transistor
Semiconductor device, can be used as a switch or amplifier.

### Logic Gates
#### AND
Both inputs must be 1 for the output to be 1.
![[Introduction-1690530871941.jpeg]]
#### OR
At least one input must be 1 for the output to be 1.
![[Introduction-1690530885053.jpeg]]
#### NOT
Inverts the input.
![[Introduction-1690530910123.jpeg]]

### Logic Chain
![[Introduction-1690531150798.jpeg]]

### Microprocessors
A highly integrated general purpose digital circuitry with serveral inputs and outputs.

Cheaper, smaller, flexible and easier to use than discrete logic gates.

Changing the software on the microprocessor allows for different fucntionality.

### Moore's Law
Roughly every 1.5 years, there is a double in the number of components and speed. Every other technical system has only a few percent improvement per year.

This is due to *miniaturiazation* of components rather than any design improvements. Smaller components reduce signal runtime as well as allow more components to be packed into the same space.

### Embedded Systems
Conected to sensors and actuators, and are often programmed once.

A combination of hardware and software that is designed to perform a dedicated function.

#### Automobiles
Modern cars have 70 sensors, tradionally they had 50 different embedded controls.

Nowadays there is only 1 powerful car controller.

#### Cost
##### System on Chip
System on a chip, custom chip (SoC)
Production setup up to $1000000.

##### System on Board
More economical for smaller production runs

##### Chiplets
Between SoC and PCB

#### Performance
Slower than PCs but more resiliant.

#### Design of Embedded Systems
- Reliability (Continous operation, no reboot)
- Cost-effectiveness (Matching requirements, no over-design)
- Space (Limited phyical dimensions)
- Space (Limited memory, reduce program code and data)
- Energy (Limited battery life, reduce power consumption)
- Safety (No harm to people or environment)
- Security (Protection agains misuse, hard to do software updates)
