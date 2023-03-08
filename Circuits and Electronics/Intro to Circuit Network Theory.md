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
The first term is the natural response (stored energy) and the second term is the forced response (independent source).

[[Energy Storage Circuit Elements#Capacitors]]

### Inductor Circuits
Also a passive element, energy is stored in the magnetic field created by flowing current.

$$\lambda = Li$$
$$\text{magnetic flux linkage = inductance} \times \text {current}$$

$$v = L \frac {di} {dt}$$
Across a DC circuit, the inductor is a *short circuit*.

[[Energy Storage Circuit Elements#Inductors]]

### RLC Circuits
![[Pasted image 20230308114351.png]]
Using *KCL* for this circuit wil give us one equation.
![[Pasted image 20230308114845.png]]

$$C \frac{d^2v} {dt^2} + \frac 1 R \frac {dv} {dt} + \frac 1 Lv = 0$$
![[Pasted image 20230308121214.png]]

In general, the solution of $v(t)$ is given by the linear combination.
$$v(t) = A_1 e^{s_1t} + A_2e^{s_2t}$$
This is a natural response of the d.e. as there is no forcing function.
![[Pasted image 20230308122438.png]]
![[Pasted image 20230308122450.png]]

#### Three Distinct Forms of Solution
##### Overdamped
Characterised by $\alpha > \omega_0$ we get two negative real values for $s_1, s_2$

##### Critically Damped
Characterised by $\alpha = \omega_0$. And we only got one root.

##### Underdamped
![[Pasted image 20230308123055.png]]
![[Pasted image 20230308123241.png]]
Characterised by $\alpha < \omega_0$, leads to two complex values for $s_1, s_2$/

#### Damping Ratio Zeta
Given by 
$$\zeta = \frac \alpha {\omega_0}$$
$\zeta > 1$ overdamped 
$\zeta > 1$ critically damped
$\zeta > 1$ under damped 