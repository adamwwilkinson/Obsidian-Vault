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
In a nonlinear domain,
![[Nonlinear Domain Drawing]]

$$R(i) = \frac{\mathrm d v(i)}{\mathrm d i} = \frac{\Delta v}{\Delta i}$$
Where $R(i)$ is "incremental" resistance.

### Nonlinear Sources
All sources in real life are nonlinear, although we use them in their "linear range". 
![[NonLinear Source Drawing]]
If output power raises over maximum power a voltage source is rated, the voltage will drop to maintain rated power as it approaches a higher current.

## Graphical (Load-Line) Analysis of Non-linear Circuit
![[Load Line  Drawing]]
Assume the nonlinear load has the following i-v characteristic:
$$i = I_0(e^{\alpha v} -1) \qquad v > 0$$ 
$$i = -I_0 \qquad v \leq 0$$

By using KVL, we have:
$$v_T = R_T i_x+v_x \rightarrow i_x = - \frac 1 R_T v_x + \frac {v_t} {R_T}$$

### Diodes
![[Diode Symbol and Graph Drawing]]

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
$$i_{D} = I_{s}^{e^{\frac{V_{D}}{0.025}} - 1}$$

#### On - Off Model
For the silicone diode, the $V_{D_{on}}$ is 0.6V. This means it only starts emmiting current at 0.6V.

#todo/example Simple diode circuit example

#### LED (Light Emmiting Diodes)
As opposed to dissipating current to heat, LED dissipates curren as light. An LED behaves as a diode and can be used as such in a circuit.

### Operational Amplifiers
#todo/excalidraw symbols and model
![[OpAmp Symbols Drawing]]
To amplify the voltage, NOT the current. Has 5 important terminals, the two voltage inputs from the powersupply, the voltage output, the inverting and non inverting inputs.

#### Ideal Op-Amps
We assume the $R_{in} \rightarrow \inf$ and $R_{out} \rightarrow 0$.
This means both the input currents are 0.
$$V_{out} = G \Delta V$$
With $G$ being the amplifier constant.

#### Open-Loop vs Closed-Loop
![[Open and Closed Loop Drawing]]

#### Golden Rules for an Ideal Op-Amp in Negative Feedback
1. The two input voltages are the same, $V_+ = V_-$
2. The inputs draw zero current, $I_+ = I_- = 0$

#### Circuit Gain of an Inverting Configuration
#todo/excalidraw
$$A_v = \frac{v_O}{v_i} = - \frac{R_f}{R_1}$$
This means $A_v$ depends now on resistance which removes the signal distortion.

#### Circuit Gain of a Non-Inverting Configuration
#todo/excalidraw
$$A_v = \frac{v_O}{v_i} = 1 + \frac{R_f}{R_1}$$

#### Saturation
#todo/excalidraw graph
In reality, the power supplies define the upper and lower limits of an amplifier.

#todo/scan examples pg 10 in notebook
