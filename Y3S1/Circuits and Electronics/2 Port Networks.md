Created: 30/03/2023 at 21:20

Two port networks have 4 directed variables associated with it. The terminals of each port are located close together, so axioms of circuit theory apply. However, the ports themselves may be separated over large distances.

They can represent a *subnetwork or functional block* (amplifier or filter).

![[2 Port Networks-1681208729672.jpeg]]

### Consider
![[2 Port Networks-1681208756393.jpeg]]
$I_1(s)$ can be considered a superposition of two components, one caused by $V_1(s)$ and the other caused by $V_2(s)$. The same can be said for $I_2(s)$. Only two of the four variables are independent. We can express any two of the four in terms of the other two.

There are 6 ways we can express two of the variables in terms of the other two. Which ways depend on the application of the two ports and how the physical component modelled can be measured.

#### Matrix Form
![[2 Port Networks-1680184695394.jpeg]]

 Voltage matrix, impedance matrix, current matrix are the names for the things above.

### Z-parameters
![[2 Port Networks-1680184975594.jpeg]]

### Y-parameters
![[2 Port Networks-1681208795007.jpeg]]

### Connecting Two Ports Together
#### Series
Useful with impedance parameters.
![[2 Port Networks-1681208938452.jpeg]]
![[2 Port Networks-1680185293936.jpeg]]

#### Parallel
Useful with admittance parameters.
![[2 Port Networks-1681208966229.jpeg]]
![[2 Port Networks-1680185331742.jpeg]]

#### Transmission Parameters
![[2 Port Networks-1681209010787.jpeg]]

A.K.A. ABCD parameters.
![[2 Port Networks-1681209030415.jpeg]]

##### Cascading two ABCD Networks
![[2 Port Networks-1680335944302.jpeg]]

### Miller Effect
Consider a network which provides voltage amplification $K$. If we have an impedance $Z$ connected between input and output ports, they can be replaced by equivalent impedance $Z_1$ and $Z_2$.
![[2 Port Networks-1680185672766.jpeg]]
![[2 Port Networks-1680185606041.jpeg]]

#### Caveats
Used where there is capacitive feedback. $K$ is assumed to be frequency independent, and the output resistance is assumed to be zero.

#### Proof
![[2 Port Networks-1680185945633.jpeg]]

### Bisection Theorem
Used to simplify the analysis of a circuit with two input ports, no internal independent sources, and exhibit mirror symmetry.

![[2 Port Networks-1680330648372.jpeg]]

![[2 Port Networks-1680330733243.jpeg]]

![[2 Port Networks-1680330775611.jpeg]]

The original $V_x$ can then by found by,
$$V_x = V_{xd} + V_{xc}$$