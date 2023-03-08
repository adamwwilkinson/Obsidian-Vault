Created: 06/03/2023 at 11:57

![[Pasted image 20230306115731.png]]

### Assumptions
*Circuit/Network theory* is based on the assumption all circuit elements can be [[Fundamentals Of Electrical Engineering#Lumped Circuit Abstraction | lumped]], although in the case they aren't lumped some can be solved with circuit theory.

#### Axioms
- the net charge inside the lumped elements forming a system is always zero
- electrical components interact solely through wires
- an element is described by only 2 directed variables
- the relationship between two variables are characteristic of the element and independent of all other elements in the network
- [[Kirchhoff's Laws|KCL and KVL]]

### Terminology
**Ports** - the pair of *terminals* on an element

### One Port Element Examples
![[Pasted image 20230306121647.png]]
![[Pasted image 20230306121732.png]]

### Series and Parallel Laws
![[Energy Storage Circuit Elements#Series Combination]]
![[Energy Storage Circuit Elements#Parallel Combination]]
![[Energy Storage Circuit Elements#Series Combination of Capacitors]]
![[Energy Storage Circuit Elements#Parallel Combination of Capacitors]]

### 2 Port Network Elements
Has 4 variables in respect to time.
Transformers and transistors are 2 port elements.

### Linearity
![[Superposition and Equivelent Circuits#Linearity]]

because of this we can use,
![[Superposition and Equivelent Circuits#The Superposition Principle]]

### Capacitor Circuits
$$i(t)= C \frac {dv}{dt}$$

Current through a capacitor is zero if voltage across the capacitor is constant. It is therefore an **open circuit** at *DC*.

#### First-order RC Circuit
Consist of a capacitor and a resistor. Called so because it's described by a first order differential equation.

![[Pasted image 20230308111042.png]]

#### Step Response
$$v(t) = V_0e^{\frac {-t} \tau} + V_s(1-e^{\frac {-t} \tau})$$
The first term is the natural response (stored energy) and the second term is the forced response (independent source)o

![[Energy Storage Circuit Elements#Capacitors]]

### Inductor Circuits
Also a passive element, energy is stored in the magnetic field created by flowing current.

$$\lambda = Li$$
$$\text{magnetic flux linkage = inductance} \times \text {current}$$

$$v = L \frac {di} {dt}$$
Across a DC circuit, the inductor is a *short circuit*.

![[Energy Storage Circuit Elements#Inductors]]