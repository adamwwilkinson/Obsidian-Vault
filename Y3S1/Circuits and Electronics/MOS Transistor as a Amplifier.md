Created: 16/05/2023 at 11:28
### Symbols
![[MOS Transistor as a Amplifier-1684207861397.jpeg]]

### Common Source Amplifier
MOS device acts as a voltage controlled current source. (VCCS)
![[MOS Transistor as a Amplifier-1684208088675.jpeg]]
![[MOS Transistor as a Amplifier-1684208369655.jpeg]]

### Load Line
The Load Line is the relationship between $i_D$ and $v_{DS}$.

### Getting Maximum Gain
In order to get the biggest change in $v_{DS}$ for a given change in $v_{in}$ we want to operate in the saturation region.

### Principle of Transistor Amplification
$$i_{DS} = I_{DS} + i_{ds}$$
$$v_{GS} = V_{GS} + v_{gs}$$
$$v_{DS} = V_{DS} + v_{ds}$$
$$i_{DS} = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T} + v_{gs})^2$$
$$I_{DS} + i_{ds} = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})^2 + \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})v_{gs} + \frac{1}{2} \mu_n C_{ox} \frac{W}{L} v_{gs}^2$$
The first term on the right hand sign is $I_{DS}$, the second term is the linear term, and the third term is the distortion.
As $v_{gs} << V_{GS} - V_{T}$, the distortion term is ignored so the linear response is the only thing considered.

$$i_{DS} = I_{DS} + \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})v_{gs}$$
$$V_{DS} = V_{DD} - I_{DS}R_D$$
$$V_{DS} + v_{ds} = V_{DD} - (I_{DS} + i_{ds})R_D$$
$$v_{ds} = -i_{ds}R_D$$
$$v_{ds} = -\mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})v_{gs}R_D$$
$$\frac{v_{ds}}{v_{gs}} = -\mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})R_D$$
This last equation is the small signal gain.

#### Transconductance
A constant that relates the change in the output current to the change in the input voltage and it has the symbol $g_m$.
$$i_{ds} = \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{T})v_{gs}$$
$$g_m = \frac{2I_{DS}}{V_{GS} - V_{T}}$$

Where $V_{GS} - V_{T}$ is the overdrive voltage.

### Small Signal Model
![[MOS Transistor as a Amplifier-1684209722955.jpeg]]

### Seperating DC Analysis and Signal Analysis
Once a stable DC operating point has been established, and all DC qunatities calculated, small signal analysis can be performed.

![[MOS Transistor as a Amplifier-1684210864111.jpeg]]

The operating point is where there is a very high slope in the $i_D$ vs $v_{GS}$ curve.

### Small Signal MOS Model
We don't have to repeat the above analysis for every circuit, we can use a small signal model.
![[MOS Transistor as a Amplifier-1684210958533.jpeg]]

### Drain Conductance
The output resistance is high, but not infinite. The drain current does depen on $v_{DS}$ in a linear manner.
$$r_o \approx \frac{1}{\lambda I_{DS}}$$

### Final Small Signal Model
![[MOS Transistor as a Amplifier-1684211335814.jpeg]]

### Signal Only vs Bias and Signal
![[MOS Transistor as a Amplifier-1684211527093.jpeg]]

### Small Signal Analysis
All DC sources are set to 0, short circuit voltage sources, and open circuit current sources.

Resistors, capacitors, and inductors are left as they are.
Dependent sources remain with control parameters related to signal.
Transistors are replace with their small signal model.

### Example 1
Usually assume capacitors are short circuits for small signal.
![[MOS Transistor as a Amplifier-1684212108528.jpeg]]

### Example 2
![[MOS Transistor as a Amplifier-1684212538860.jpeg]]

### Types of Biasing
![[MOS Transistor as a Amplifier-1684236466562.jpeg]]
![[MOS Transistor as a Amplifier-1684236481839.jpeg]]
![[MOS Transistor as a Amplifier-1684236503444.jpeg]]
Having the resistor $R_S$ tends to stabilise against any variations as,
![[MOS Transistor as a Amplifier-1684236986736.jpeg]]
![[MOS Transistor as a Amplifier-1684237018145.jpeg]]
![[MOS Transistor as a Amplifier-1684237207215.jpeg]]![[MOS Transistor as a Amplifier-1684237233240.jpeg]]
![[MOS Transistor as a Amplifier-1684237307119.jpeg]]
![[MOS Transistor as a Amplifier-1684240661301.jpeg]]

## What Happens at High Frequency
Capacitors are short for low frequency signals when drawing the equivalent circuit.

For DC biasing circuits we see them to be open circuits.

Limited by internal capicatances:
- gate capacitance
- junction capacitance

### Gate Capacitance
![[MOS Transistor as a Amplifier-1685414843091.jpeg]]

### Junction Capacitance
Due to the depletion regions with the drain and source.
![[MOS Transistor as a Amplifier-1685414946846.jpeg]]

### High Frequency Model
![[MOS Transistor as a Amplifier-1685414983057.jpeg]]

#### Simplified Model
![[MOS Transistor as a Amplifier-1685415040873.jpeg]]

### MOSFET Unity Gain Frequency
Current gain,
$$\frac{i_{out}}{i_{in}} = \frac{g_m}{sC_{gs} + sC_{gd}}$$

Unit-gain frequency,
$$f_t = \frac{g_m}{2\pi(C_{gs} + C_{gd})}$$

This is the frequency at which the current gain is 1.

### Frequency Response
#### Low Frequency
![[MOS Transistor as a Amplifier-1685416575626.jpeg]]

This happens if there are no coupling capacitors.
When we do have them,
![[MOS Transistor as a Amplifier-1685416610091.jpeg]]

### Example
![[MOS Transistor as a Amplifier-1685417037996.jpeg]]

#### High Frequency
All the coupling capacitors can be short circuited.
![[MOS Transistor as a Amplifier-1685417148742.jpeg]]![[MOS Transistor as a Amplifier-1685417554809.jpeg]]
