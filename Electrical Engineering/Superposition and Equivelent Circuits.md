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