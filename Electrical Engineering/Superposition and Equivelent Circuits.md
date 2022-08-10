# Superposition and Equivelent Circuits
Created: 09/08/2022 at 11:04
Tags: #topic/physics 
Related: [[Systematic Approaches]], [[Kirchhoff's Laws]]

### Tools
Volt-meters: measures voltage across a device, to be accurate need $R_M \gg R_2$ where $R_M$ is the resistance of the meter. This is because,
$$V_2 = \frac{R_2}{R_1+R_2}V_S$$


Current-meters: measures current through a device, to be accurate $R_M \ll R_2$ where $R_M$ is the resistance of the meter. This is because,
$$i_2 = \frac{R_1}{R_1 + R_2 + R_M}i_S$$

### Combining Voltage Sources
#### Adding in Series
Easy to do with KVL.

#### Adding in Parallel
KVL is invalidated as it would require $V_1 = V_2$ which is not guaranteed.

### Combining Current Sources
#### Adding in Parallel
Easy to do with KCL.

#### Adding in Series
KCL is invalidated as it would require $i_1 = i_2$ which is not guaranteed.

### Power Source Internals
In real life power sources have a resistive circuit within them, this can also be seen as an ideal power source with resistance.

This means a voltage-current graph in real life does not look like a linear graph due to the "dynamic" resistance in the non-ideal power source.

### [[Practical Sources| Further Reading of Practical Sources]]

## Superposition
#### Linearity
A system is said to be linear if it has the *properties* of **Homogeneity** and **Additivity**

##### Homogeneity
Given $f(u)$ is the output of system $u$, the system has **homogeneity** if the input $au$ with scalar $a$ has the output $af(u)$. I.e. $af(u) = f(au)$.

##### Additivity
Given $f(u)$ is the output of system $u$, the system has **additivity** if the input $u + v$ has the output $f(u) + f(v)$.

By these two definitions,
$$y = 2x + 5$$
is not linear.

### Linear Dependent Source
![[Dependent Source Drawing]]
One whose output current or voltage is proportional to some current or voltage variables in the circuit, or the sum of such quantities.

### Linear Circuits
A circuit composed entirely of independent sources, linear dependent sources, and linear elements.

The superposition principle can be applied to a linear circuit.

### The Superpostition Principle
In any linear resistive network containing several sources, the voltage across or the current though any resistor or source can be calculated by adding algebraically all the individual voltages or currents by each independent source acting alone, with all other ...

#### Steps to the Superposition Principle
1. Turn off all independent sources except one. To turn off a current source make it open-circuit, to turn off a voltage source make it short-circuit.
2. Calculate the required output due to the single active source.
3. Repeat the previous steps for the remaining independent sources.
4.  FInd the true output of the original circuit by adding the individual outputs.