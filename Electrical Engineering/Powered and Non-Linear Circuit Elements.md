# Powered and Non-Linear Circuit Elements
Created: 16/08/2022 at 10:59
Tags: #topic/physics
Related: [[Superposition and Equivelent Circuits]], [[Circuit Analysis Techniques]]

### What are Non-Linear Circuit Elements
Components have nonlinear I-V relationhips, and nonlinear circuits are described by nonlinear equations.
A circuit is nonlinear if there is atleast one nonlinear element in the circuit.

### In Relation to [[Circuit Analysis Techniques]]
KVL, KCL, NTD, and Mesh analysis makes no assummption on linearity. All these techniques can be applied **ensuring use of appropriate I-V relationships** can be used on nonlinear circuits.

### Incremental/Dynamic Resistance
In a linear domain, $$R = \frac v i$$.
In a nonlinear domain, #todo/excalidraw
$$R(i) = \frac{\mathrm d v(i)}{\mathrm d i} = \frac{\Delta v}{\Delta i}$$
Where $R(i)$ is "incremental" resistance.

### Nonlinear Sources
All sources in real life are nonlinear, although we use them in their "linear range". #todo/excalidraw graph
If output power raises over maximum power a voltage source is rated, the voltage will drop to maintain rated power as it approaches a higher current.

## Graphical (Load-Line) Analysis of Non-linear Circuit
#todo/excalidraw
Assume the nonlinear load has the following i-v characteristic:
#todo/latex
$$\begin{cases} i = I_0(e^{\alpha v} -1) & \text{if $v \gre 0} \\
\end{cases}$$

By using KVL, we have:
$$v_T = R_T i_x+v_x \rightarrow i_x = - \frac 1 R_T v_x + \frac v_t R_T$$

### Diodes
#todo/excalidraw symbol and graph see what he added in lectures

The current vs voltage behaviour depends on the direction the diode is inserted into the circuit.

A doubling in voltage does not result in a doubling of amperes.

Silicone diodes is the one we focus on for the unit.

#### Types of Diode
- Signal diode
- Power diodes
- Special purpose diodes

**Semiconductor junction diodes** consists of a junction between two different semiconductor types (n-type and p-types).

#### The Diode Model Equation
At room temperature, silicon based diodes have the equation,
$$i_D = I_s^{e^{\frac{V_D}{0.025}} - 1}$$

#### On - Off Model
For the silicone diode, the $V_{D_{on}}$ is 0.6V. This means it only starts emmiting current at 0.6V.

#todo/example Simple diode circuit example

#### LED (Light Emmiting Diodes)
As opposed to dissipating current to heat, LED dissipates curren as light. An LED behaves as a diode and can be used as such in a circuit.

### Operational Amplifiers
