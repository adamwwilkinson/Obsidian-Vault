# Fundamentals Of Electrical Engineering
Created: 28/07/2022 at 16:19
Tags:  #introductory 
Related:

### Analogue vs Digital Electronics
If a 'movement' is continuous then it is an analogue, while if it is discrete it is digital. Analogue is cheap, which digital isn't, digital is also an approximation of analogue electronics.

$$ V = I \times R$$
$$ I = \frac{V} {R}$$

### Lumped Circuit Abstraction
We don't care about how current flows, its temperature, shape, or orientation. This we can replace the bulb with a discrete resistor and allow for easy calculation. We can make these assumptions because we know the electric signals travel near the speed of light. Which means we can approximate every point of the system being reached simultaneously.

#### Assumptions
$\lambda = \frac{c}{f_{max}} \gg \delta$ (at least 10 times) where $\delta$ is the dimension of the circuit.

### Non-lumped Circuits
If a circuit doesn't hold the [[#Assumptions]], then it is called a distributed circuit. A distributed circuit can be seen as a limit of sequences of lumped circuits.

A distributed circuit is one where the *terminal voltages* and *currents* are functions of *position* and time.

### Transmission Lines 
Specialised structures to transfer electricity from one point to another.
#todo/excalidraw

### More Lumped Assumptions
The net charge inside the lumped elements forming a system is always zero.
Electrical components interact solely through wires.

### Models
A model expresses the *relationship* among *voltages* and *currents*. These can be linear or non-linear.

#### Electron Properties
$m_e = 9.11 \times 10 ^ {-31}$kg
$q_e = -1.6 \times 10 ^ {-19}$C

#### Current
the flow of charge in regards to time
$$i(t) = \frac {\mathrm{d}Q(t)}{\mathrm{d}t}$$
The Q has the unit of Coulomb.
Can be inverted to calculate the total charge passed throguh any location:
$$Q(t) = Q(0) + \int_0^t \! i(t) \mathrm{d}t$$

*Conventional Current* - the flow of 'positive charge'

#todo/examples

#### Voltage
The voltage (potential difference) between two points is one volt if it requires one joule of energy to move one coloumb of charge between the two points.
$$V = \frac{W}{Q}$$

The negative charge from the electron is already considered in the defiition for voltage.

A $+$ sign in a circuit denotes the point of higher potential, and the $-$ sign denotes the point of lower potential. Even if that lower potential is a postive number.