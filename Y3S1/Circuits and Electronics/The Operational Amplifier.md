Created: 06/05/2023 at 11:22

### History
The name originates from the face this type of amplifier can be used to perform mathematical operations such as scaling, summation, and integration of analog signals.

### Typical 8 Pin Op-Amp
![[The Operational Amplifier-1683343447318.jpeg]]

### Op-Amp Terminals
![[The Operational Amplifier-1683343486569.jpeg]]

The op amp requires dc power to operate. The power supply terminals are labeled V+ and V-.
There are three critical connections:
- Inverting input '-'
- Non-inverting input '+'
- Output

It is designed to amplify the difference between the two inputs. The output is the difference between the two inputs multiplied by the gain of the amplifier $A$.

The gain factor $A$ is referred to as the open-loop gain. It is the gain of the amplifier when no feedback is applied.
It also is the maximum gain of the amplifier.

### Characteristics of an Ideal Op-Amp
An ideal op-amp has the following characteristics:
- Infinite open-loop gain
- Zero gain for the common mode input signal
- Infinite input impedance
- Zero output impedance
- Infinite bandwidth

### Impedances
Why do we care about input and output impedance?

#### Input
![[The Operational Amplifier-1683343835670.jpeg]]
The input impedance of a circuit is the ratio of the voltage applied to the input terminals to the current flowing into the input terminals. It is a measure of how much the circuit impedes the flow of current.

If we want $V_S$ = $V_{in}$ we want $Z_{in}$ to be infinte.

#### Output
![[The Operational Amplifier-1683343909020.jpeg]]

If we want $V_{out}$ = $V_L$ we want $Z_{out}$ to be zero.

### Ideal vs Real Op-Amps
![[The Operational Amplifier-1683343987032.jpeg]]

### Saturation
In practice, the power supply limits the output voltage. When the output voltage reaches the power supply voltage, the output voltage is said to be saturated.

![[The Operational Amplifier-1683344174000.jpeg]]

### Open-Loop vs Closed-Loop
Open loops have no feedback. Closed loops have feedback.
![[The Operational Amplifier-1683344243374.jpeg]]

Closed loops either have negative feedback or positive feedback.
Negative feedback is when the output is fed back to the inverting input, positive to the non-inverting input.

### Comparator
An example of an open loop op-amp.
![[The Operational Amplifier-1683344330950.jpeg]]
![[The Operational Amplifier-1683344574935.jpeg]]

### Distoriton
It is hard to make gain independent of individual devices themselves. Op-amps can be dependent on temperature, power supply voltage, and frequency.

### Negative Feedback Amplifier
![[The Operational Amplifier-1683344750429.jpeg]]

$$A_V = \frac{a}{1+af} \approx \frac 1 f$$

The feedback factor $f$ can be implemented with linear elements, so the closed-loop behaviour is linear even though the amplifier in the block $a$ is not.
![[The Operational Amplifier-1683344987959.jpeg]]

Negative feedback can correct any disturbances in the input signal. It can also reduce the effect of non-linearities in the amplifier.

In an op-amp with no feedback [[#comparator]], there is no corrective mechanism, so the output voltage will go to full saturation with any small amount of input diffrenetial voltage.

### Calculation Rules for Op-Amps
Assumptions:
- The op-amp is ideal
- The op-amp operates in the linear region
- The op-amp is in negative feedback

Calculation Rules:
$$i_+ = i_- = 0$$
$$V_+ = V_-$$
![[The Operational Amplifier-1683345446255.jpeg]]

### Non-Inverting Op-Amp
Amplified with positive gain.
Output connected to inverting input.
Inverting input connected to ground.
Input voltage connected to non-inverting input.
$$V_{out} = V_{in} \left(1 + \frac{R_2}{R_1}\right)$$

### Inverting Op-Amp
Outcpout connected to inverting input.
Non-inverting input connected to ground.
Input voltage connected to inverting input.
Amplified with negative gain.
$$V_{out} = -V_{in} \frac{R_2}{R_1}$$

### Op-Amps for Maths
Closed-loop op amps with negative feedback can be used to perform mathematical operations on analog signals.

![[The Operational Amplifier-1683350174187.jpeg]]

### Inverting Weighted Summer
![[The Operational Amplifier-1683350238627.jpeg]]
$$V_{out} = -R_F \left(\frac{V_1}{R_1} + \frac{V_2}{R_2} + \frac{V_3}{R_3}\right)$$

### Non-Inverting Weighted Summer
![[The Operational Amplifier-1683350418318.jpeg]]
$$V_{out} = \left(1+ \frac{R_2}{R_1}\right)\frac{V_1 + V_2}{2}$$

### Derivitive Op-Amp
![[The Operational Amplifier-1683351043017.jpeg]]

### Integrator Op-Amp
![[The Operational Amplifier-1683351165218.jpeg]]

### Difference Op-Amp
$$V_{out} = \frac{\left(1 + \frac{R_2}{R_1}\right)}{\left(1 + \frac{R_3}{R_4}\right)}V_{I2} - \frac{R_2}{R_1}V_{I1}$$

### Power Supply and Efficiency
$$P_S = V_{AA}I_A + V_{BB}I_B$$
![[The Operational Amplifier-1683434137024.jpeg]]
![[The Operational Amplifier-1683434173563.jpeg]]

The additional power comes from the power supply.
This efficiency is given by
$$\eta = \frac{P_o}{P_S}\times 100$$
