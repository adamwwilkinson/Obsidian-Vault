Created: 26/04/2023 at 17:07

### History
In 1970s new kind of FET called metal-oxide semiconductor field-effect transistor

Extremely popular dde to inherent advantages, can be made smaller, consume less power and have a well controlled manufacturing process.

![[MOSFET Transistors-1682500139777.jpeg]]

### Structure of NMOS Transistor
![[MOSFET Transistors-1682500183631.jpeg]]

### NMOS Terminals
![[MOSFET Transistors-1682500338418.jpeg]]
Purely symmetrical device, source and drain are interchangeable depending on applied voltage.

To differentiate in *NMOS*, the **source terminal is at a lower potential than the drain**.
For *PMOS*, the **source terminal is higher potential than the drain**.

The *BODY* for NMOS is connected to 0V, and the *BODY* for PMOS is connected to the highest potential.

### Symbols
![[MOSFET Transistors-1682500485265.jpeg]]

### Switch Model
Transistor can be modelled as a voltage controlled switch.
$V_T$ is called the threshold voltage of the transistor, positive for NMOS transistors and negative for PMOS. Roughly around 0.1 - 0.5V.
![[MOSFET Transistors-1682500648657.jpeg]]

$$V_{GS} = V_G - V_S, V_{DS} = V_D - V_S$$

### Revision of Silicon and Semiconductors
![[MOSFET Transistors-1682500702987.jpeg]]
![[MOSFET Transistors-1682500722057.jpeg]]
![[MOSFET Transistors-1682500741528.jpeg]]
![[MOSFET Transistors-1682501315766.jpeg]]

#### Doping
![[MOSFET Transistors-1682501406103.jpeg]]

##### Donors (N-type)
![[MOSFET Transistors-1682501425025.jpeg]]

##### Acceptors (P-type)
![[MOSFET Transistors-1682501469330.jpeg]]

### Revision of PN Junctions
![[MOSFET Transistors-1682501517979.jpeg]]
![[MOSFET Transistors-1682501612589.jpeg]]

The charge separation creates an electric field.

#### Forward Bias
![[MOSFET Transistors-1682501779766.jpeg]]

#### Reverse Bias
![[MOSFET Transistors-1682501797055.jpeg]]

### Operation Principle
The region underneath the gate oxide between the source and drain is the channel.
![[MOSFET Transistors-1682500338418.jpeg]]

In MOSFET the Drain/Bulk (body) and Source/Bulk junctions are kept reverse biased.
Current flows between the diffusion terminals if the voltage on the gate terminal is large enough to create a conducting channel.

#### Negative Gate Bias $V_{GS} < 0$
![[MOSFET Transistors-1682502062910.jpeg]]

This is the equivalent to two back to back diodes.

#### Forward Gate Bias $V_{GS} \geq 0$
![[MOSFET Transistors-1682502175198.jpeg]]
This inversion layer is the conductive path.

$$V_{eff} = V_{GS} - V{T}$$

### Linear Mode
![[MOSFET Transistors-1682502412185.jpeg]]
$I_{DS}$ is proportional to $V_{eff}$
NMOS is acting like a resistor, whose resistance is controlled by gate voltage.
```ad-important
The current that enters the drain terminal is equal as the current that leaves the source terminal.
```

### Saturation Mode
![[MOSFET Transistors-1682503442544.jpeg]]

#### Channel Length Modulation
As $V_{DS}$ becomes larger than $V_{GS} - V_{T}$. the depletion region surrounding the drain junction increases in width, this in turns reduces the channel length, a phenomenon called **channel-length modulation**. It can be analytically accounted using the formula,
$$I_{DS} = I_{DSAT}(1 + \lambda V_{DS})$$
Where $\lambda$ is given by technology, typically a range from 0.005 to 0.03 $V^{-1}$.

### Enhancement type P-channel MOS
![[MOSFET Transistors-1682503854128.jpeg]]
$I_{DS} V_{GS} V_{DS}$ are all negative. Slower to NMOS transitors as electron mobility is higher than hole mobility.

### Review
![[MOSFET Transistors-1682503922093.jpeg]]

## Current-Voltage Characteristics
![[MOSFET Transistors-1682505541057.jpeg]]

### I-V Characteristics (NMOS)
![[MOSFET Transistors-1682505604447.jpeg]]
![[MOSFET Transistors-1682505635931.jpeg]]

### I-V Characteristics (PMOS)
![[MOSFET Transistors-1682505704851.jpeg]]

### NMOS and PMOS Handwritten
![[MOSFET Transistors-1682505976740.jpeg]]

### Linear Mode (NMOS)
$V_{DS} \leq V_{GS} - V_T$ is *Linear* mode
$$I_{DS} = k'_n \frac W L[(V_{GS} - V_T) V_{DS} - \frac {V_{DS}^2} 2]$$
For small $V_{DS}$ there is a linear dependence between $V_{DS}$ and $I_D$.

$k'_n = \mu_n C_{ox} = \mu_n \frac {\epsilon_{ox}} {t_{ox}}$ the *transconductance*.
$C_{ox}$ is the gate oxide capacitance, $t_{ox}$ is the thickness of the oxide and $\epsilon_{ox}$ is the oxide permittivity.
$\mu_n$ is the carrier mobility.

### Saturation Mode (NMOS)
$V_{DS} \geq V_{GS} - V_T$ is *Saturation* mode
$$I_{DSAT} = 0.5 k'_n \frac W L[(V_{GS} - V_T)^2]$$
Because of [[#Channel Length Modulation]], the current is not actually contant but exhibits a slight linear dependence on $V_{DS}$.

### Summary
![[MOSFET Transistors-1682506829878.jpeg]]