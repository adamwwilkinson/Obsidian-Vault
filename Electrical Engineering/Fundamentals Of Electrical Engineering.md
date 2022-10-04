# Fundamentals Of Electrical Engineering
Created: 28/07/2022 at 16:19
Tags:  #topic/electrical/introduction
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
![[Transmission Line Structures.png]]

### More Lumped Assumptions
The net charge inside the lumped elements forming a system is always zero.
Electrical components interact solely through wires.

### Models
A model expresses the *relationship* among *voltages* and *currents*. These can be linear or non-linear.

#### Electron Properties
$m_e = 9.11 \times 10 ^ {-31}$kg
$q_e = -1.6 \times 10 ^ {-19}$C

#### Current
the flow of charge in regards to time
$$i(t) = \frac {\mathrm{d}Q(t)}{\mathrm{d}t}$$
The Q has the unit of Coulomb.
Can be inverted to calculate the total charge passed throguh any location:
$$Q(t) = Q(0) + \int_0^t \! i(t) \mathrm{d}t$$

*Conventional Current* - the flow of 'positive charge'


#### Voltage
The voltage (potential difference) between two points is one volt if it requires one joule of energy to move one coloumb of charge between the two points.
$$V = \frac{W}{Q}$$

The negative charge from the electron is already considered in the defiition for voltage.

A $+$ sign in a circuit denotes the point of higher potential, and the $-$ sign denotes the point of lower potential. Even if that lower potential is a postive number.

#### Active vs Passive Components
Active components are ones where current flows *out* the positive terminal.
Passive components are ones where current flows *into* the positive terminal.

#### Reference Points
Always assumed to be zero volts. 
![[Symbols for Earth and Ground]]
Symbols for earth ground and chassis.


#### Ideal Voltage Source
![[DC and AC Drawing]]
1. Pure voltage source, with no lost or storage characteristics. No *Internal resitance, capacitance, or inductance*.
2. Creates the specified voltage across its terminals, regardless of current.

#### Ideal Current Source
![[Ideal Current Drawing|100]]
1. Pure current source, with no loss or storage characteristic. No *Internal resitance, capacitance, or inductance*.
2. Drives the specified current, regardless of voltage.

#### Resistor
![[Resistor Drawing]]
Dissipates energy from the system as heat. Voltage is dropped when current flows through.

#### Capacitor
Stores energy in an *electric field* when a voltage is applied

#### Inductor
Stores energy in a *magnetic field* when a current flows through.

#### Variable Supplies
Provides a voltage or current proportional to another parameter.

### Ohm Law
The linear relationship between current and applied voltage.
$$V = IR$$

#### Resistance
Measured in Ohms($\ohm$ ). Can be evaluated with $R = \frac{V}{I}$

The inverse is called *conductance* ($G$) is also used. $G = \frac{I}{V}$
The SI unit is called *Siemens*($S$)

#### Conductance
Adding $S$ in series:
$$S_T = (\frac 1 S_1 + \frac 1 S_2)^{-1} $$

Adding $S$ in parallel:
$$S_T = S_1 + S_2$$

#### Assumptions
- Material is linear
- Contact of wires produces no effect
- Power supply is ideal

### Power
Power is the *time rate of change of work*. $P = \frac{\mathrm{d}W}{\mathrm{d}t}$,
And, $V = \frac{W}{Q}$.

Therefore, power supplied or dissipated by a circuit element is:
$$P = \frac{\mathrm{d}}{\mathrm{d}t}(QV)$$
For constant voltage, $P = V \frac{\mathrm{d}Q}{\mathrm{d}t} = V \times I$

Measured in joules per second, or *watts*.
```ad-warning
Use the sign of the first symbol the current flows into.
```

Power dissipated by a resistor can be given by,
$$P = I^2R = \frac{V^2}{R}$$

### Energy
The gain or dissipation over a time interval,
$$E = \int^{\Delta t}_0P(t) \mathrm{d}t$$
Energy is the integration of power.

If there is constant voltage and current,
$$E = VI \Delta t$$

Considering dissipation in a resistor,
$$E = I^2 R \Delta t = \frac{V^2}{R} \Delta t$$