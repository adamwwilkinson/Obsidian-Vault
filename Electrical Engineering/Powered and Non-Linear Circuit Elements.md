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
$$v_T = R_Ti_x+v_x \rightarrow i_x = - \frac 1 R_T v_x + \frac v_t R_T$$
### Diodes


### ? Amplifier
