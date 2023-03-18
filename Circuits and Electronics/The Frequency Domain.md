Created: 18/03/2023 at 15:31

### Linearity of Differential Operators
Differentiation is a linear operator. Inductors and capacitors are linear elements, and methods based on linearity like superposition can be applied to circuits with them.

These concepts are valid even when voltage and current are based on time varying functions, specifically we will look at the case of sinusoidal functions of time.

### Why Sinusoids
- Derivatives and integrals of sinusoids are sinusoids of the same frequency
- Response of an underdamped second order system is a damped sinusoid 
- Often occurs naturally in power generation

![[The Frequency Domain-1679125093572.jpeg]]

### Forced Response to Sinusoidal Functions
The *forced response* is synonymous with the *steady-state* response. This *steady-state* is now a *sinusoidal steady-state* response which is different to the *DC steady-state*.

![[The Frequency Domain-1679125450400.jpeg]]

![[The Frequency Domain-1679125598067.jpeg]]

#### The Phasor Concept
The result above involves a lot of manipulation, we could take a simpler approach by choosing a complex forcing function.

```ad-note
By changing the instant we call $t=0$, we can adjust the phase of the forcing function.
```

If we chose the forcing function,
$$V_m \cos (\omega t + \theta) + jV_m \sin(\omega t + \theta)$$ 

![[The Frequency Domain-1679126106767.jpeg]]
![[The Frequency Domain-1679126286274.jpeg]]

```ad-info
Even though we only have one equation, as it is a complex equation we can get two unknowns.
```
![[The Frequency Domain-1679126354601.jpeg]]

A sinusoidal current or voltage at frequency $\omega$ is characterised with only two parameters, *amplitude* and *phase angle*.

We can represent the sinusoid by just these two params, typically in polar form.

$$I = I_m \angle \phi = I_m = e^{j\phi}$$

KVL and KCL both hold for phasors.

##### Resistor
![[The Frequency Domain-1679126859323.jpeg]]

##### Inductor
![[The Frequency Domain-1679126981850.jpeg]]

##### Capacitor
![[The Frequency Domain-1679127120807.jpeg]]

### Impedance
![[The Frequency Domain-1679127652923.jpeg]]
Impedance has the same series and parallel rules as resistors. The inverse of this is admittance.

### Sources of Different Frequencies
We can employ superposition to do the analysis.
![[The Frequency Domain-1679127868162.jpeg]]

### Response as a Function of Frequency
![[The Frequency Domain-1679128281318.jpeg]]
![[The Frequency Domain-1679128331725.jpeg]]
![[The Frequency Domain-1679128447969.jpeg]]

### Power
#### Instantaneous
$$p(t) = v(t)i(t)$$

#### Average
$$P_{AVE} = \frac 1 T \int^T_0 p(t) dt$$

#### Maximum Power Transfer
Maximum power is transferred when $Z_L = Z_{Th}^*$

#### Complex Power
![[The Frequency Domain-1679129817859.jpeg]]

For further reading, [[Power and Efficiency]]

### RMS
By letting $P_{AVE} = P_{DC}$ we can find the *root-mean-square* values of current and voltage.

$$V_{eff} = V_{RMS} = \sqrt {\frac 1 T \int_0^Tv^2(t)dt}$$

For sinusoidal sources,
$$I_{RMS} = \frac {I_m} {\sqrt 2}$$


### Further
For further reading. [[Sinusoidal Sources and Phasors]].