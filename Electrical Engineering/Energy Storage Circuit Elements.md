# Energy Storage Circuit Elements
Created: 23/08/2022 at 11:21
Tags: 
Related: [[Equivalent Circuits]]

## Capacitors
Stores energy in an electric field. 
![[Capacitor Drawing]]
Capacitance relates the voltage $v$ applied to the charge $q$ generated,
$$C = \frac{q}{v}$$
$$i = \frac{\mathrm d q}{\mathrm d t} = C \frac{\mathrm d v}{\mathrm d t}$$
$$E(t) = C \times \frac{v^2_{c(t)}}{2}$$

When connected directly to an ideal voltage source, an ideal capacitor with have a non-zero current onluy when the voltage is changing.
In otherwords, if the voltage is constant, the current is 0.

### Unit of Capacitance
Measured in **Farad** $(F)$

### Symbol
![[Capacitor Symbol Drawing]]

### Parallel Combination of Capacitors
$$C_{T} = C_{1} = C_{2}$$

### Series Combination of Capacitors
$$\frac{1}C_{T} = \frac{1}C_{1} + \frac{1}C_{2}$$

### Deriving Voltage
$$v(t) = \frac 1 C \int_0^t i(t) \mathrm d t + v_0$$

### Capacitor States
When the charge in the capacitor increases or decreases it is called *transient* state.
When the charge in the capicitor is full charge it is called *steady-state*.

### First-order $RC$ Circuit
#### DC Steady-state Analysis
A steady-state capacitor acts as an *open circuit*.

#### Transient Analysis
##### Charging
$$v(t) = V_S + (V_0 - V_S)e^{\frac {-t} {RC}}$$
Where $V_S$, $V_0$ are the final and intial value for $V(t)$.

##### Discharging
Capacitor discharges it's ions to the resistor which powers it and gives away energy as heat.

#### $RC$?
$RC$ is also known as $\tau$ and is a time constant. After $\tau$ amount of time, the capacitor is charged 66.6%.

#### Procedure to Find Response
#todo read previous slides
1. Remove all independent sources to determine $R_{eq}, C_{eq}$
2. With C set as an open circuit, use dc-analysis to find the initial capacitor voltage prior to discontinuity.
3. With C set as an open circuit use dc-analysis of the capacitor voltage with $t = \inf$, this is $V_{inf}$.
$$v(t) = V_\inf + (V_0 - V_{inf})\exp^{-t}{\tau}$$

## Inductors
A current carrying conductor will generate a magnetic field around it to store energy.

**Flux Linkage** - $\lambda= \int B \mathrm d S$ (integrated magnetic flux density over an area enclosed by a conductor)

### Inductance
Relates flux linkage to the current in the conductor.
$$\lambda = L \times i$$

A conductor placed in a time-varying magnetic field (as a result of a time-varying current) will have a voltage **induced** such that,
$$v = \frac {\mathrm d \lambda} {\mathrm d t} = L \frac {\mathrm d i} {\mathrm d t}$$

Equivalent of Ohm's law for an inductor.

#### Henry $(H)$
The unit for inductance.

### Symbol
![[Inductor Drawing]]

### Series Combination
$$L_T = \sum_{i = 1}^N L_i$$

### Parallel Combination
$$\frac {1} {L_T} = \sum{i = 1}^N \frac {1} {L_T}$$

### First-order RL Circuits
#### DC Steady-state
$$E_L(t) = \int P_L (t) \mathrm d t = \frac 1 2 Li_L^2(t)$$

At steady-state a inductor behaves as a short circuit.
