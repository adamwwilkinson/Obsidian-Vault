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