Created: 22/08/2024 at 20:39

### Structure
Transformers are magnetically coupled coils by a common magnetic field. Typically placed on a common magnetic core.

High frequency (kilo to mega cycles), frequency is proportional to volume and weight.

![[Transformers-1724330796363.jpeg]]

#### Shell Type
More complicated with two magnetic parts.
### Applications
Provide electrical isolation between the source and the load, and to change the voltage and current levels.

#### Low Power
Fridge, household electric appliances

#### High Power
Power transmissions
![[Transformers-1724330966629.jpeg]]
Distribution transformers step down thousand of volts, to hundreds.
### Principle
![[Transformers-1724331194412.jpeg]]
Based on Faraday's law:

$e_1 = \frac{d\lambda_1}{dt} = N_1 \frac{d\phi}{dt}$

$e_2 = \frac{d\lambda_2}{dt} = N_2 \frac{d\phi}{dt}$

$\lambda_2 = N_2 \phi$

Kirchhoff's voltage law applied to the two windings gives:

$$v_1 = R_1 i_1 + e_1 = R_1 i_1 + N_1 \frac{d\phi}{dt}$$

$$v_2 = R_2 i_2 + e_2 = R_2 i_2 + N_2 \frac{d\phi}{dt}$$

If the resistances $R_1$ and $R_2$ are negligible, then:

$v_1 = N_1 \frac{d\phi}{dt}$

$v_2 = N_2 \frac{d\phi}{dt}$

$$\frac{v_1}{v_2} \approx \frac{N_1}{N_2} = a = \frac{1}{n}$$

If $a > 1$ then $v_1 > v_2$
Step down transformer

If $a < 1$ then $v_1 < v_2$
Step up transformer

#### Relation of Current
The relationship between the primary and secondary currents can be found by considering the magnetic circuit of the transformer. From the basic magnetic circuit equation, we have:

$\frac{V_1}{V_2} = \frac{N_1}{N_2}$

$$F = N_1 i_1 - N_2 i_2 = \mathcal{R} \phi$$

Note the opposite direction of $i_2$: it opposes the flux created by $i_1$ (net mmf would be zero).

$$\mathcal{R} = \frac{l}{\mu A} = \frac{l}{\mu_0 \mu_r A}$$

If the relative permeability $\mu_r$ is large, $\mathcal{R}$ will be small in comparison with $N_1 i_1 - N_2 i_2$. Thus:

$$N_1 i_1 - N_2 i_2 \approx 0$$

$$\frac{i_1}{i_2} \approx \frac{N_2}{N_1} = \frac{1}{a}$$

$\frac{i_1}{i_2} = \frac{N_2}{N_1} = \frac{v_2}{v_1}$

Thus:

$$v_1 i_1 = v_2 i_2$$

$$v_1 i_1 \cos \theta = v_2 i_2 \cos \theta$$

$$P_1 = P_2$$

Instantaneous power input to the transformer equals the instantaneous power output from the transformer. The same relation applies to apparent and reactive power.

**Ideal Transformer**:
- The winding resistances are negligible.
- All fluxes are confined to the core and link both windings; that means, no leakage fluxes are present. Core losses are assumed to be negligible.
- Permeability of the core is infinite (i.e., $\mu \rightarrow \infty$). Therefore, the exciting current required to establish flux in the core is negligible; that means, the net mmf required to establish a flux in the core is zero.

#### Sinusoidal Operation
Sinusoidal current means you get sinusoidal flux.

There exist a $B_{max}$ which is the maximum flux density of the core. It is normal practice to have $B_{max}$ close to the *saturation* value for the core material when $V_1$ and $f$ have their normal rated values.
![[Transformers-1724331755662.jpeg]]
$$B_{\text{max}} = \frac{V_1}{\sqrt{2\pi f} N_1 A}$$
![[Transformers-1724331851338.jpeg]]

#### Impedance of Transformation
![[Transformers-1724331867568.jpeg]]
$$Z_{in} = \frac {Z_L} {n^2}$$
### Maximum Power Transfer
For maximum power transfer, the resistor in the circuit must be equal to the resistor in the load.
For achieving the maximum power delivered by a power-supplying resistive network to a load, the maximum power would be delivered to the load if the load resistance $R_L$ is equal to the Thevenin supply resistance $R_L = R_{th}$.

In AC circuits, as shown below, for maximum average power transfer, the load impedance $Z_L$ must be equal to the complex conjugate of the Thevenin supply impedance $Z_{Th}$.

$Z_L = R_L + jX_L$

$Z_{th} = R_{th} + jX_{th}$

$P_{max}$ happens when $Z_{th} = Z_L^*$

If the load is purely resistive (i.e., $X_L = 0$), the condition for maximum power transfer is:

$$R_L = \sqrt{R_{th}^2 + X_{th}^2} = |Z_{th}|$$

### Tramsformer Rating
Measured in kVA, not kW. The kVA rating of a transformer is the apparent power it can deliver to the load. The kVA rating of a transformer is the product of the rated voltage and the rated current.

E.g. 10kVA, 1100/110V (primary/secondary) RMS values

Losses should be very low, so we can say the apparant power coming in is equal to the apparant power going out.

### Practical Transformer
- the windings have resistance $R_1$ and $R_2$
- power loss in the core because of hysteresis and eddy currents, $R_c$
- permeability of the core is finite as opposed to infinite, known as magnetic reactance $x_m$
- not all windings link the same flux, reactance $x_1$ and $x_2$ represent the leakage fluxes

![[Transformers-1725422987508.jpeg]]o

#### Simplified Equivalent Circuit
Can be simplified from the 6 components to 4 components.

$R_1$ and $x_1$ are generally much smaller than $R_2$ and $x_m$ so voltage drop is small.

Shunt elements can be moved to input terminals.
![[Transformers-1725423694597.jpeg]]

We can move $R_2$ and $x_2$ to the primary side.
![[Transformers-1725423758700.jpeg]]

### Paramter Determination
#### No Load / Open Circuit Test
Apply rated voltage to one side, other side open circuit. Typically high voltage side is open circuit.
![[Transformers-1725424101464.jpeg]]

#### Full Load / Short Circuit Test
Typically low voltage side is short circuit. Apply 0 voltage in the beggining then gradually increase to a certain value. Once the rated current is reached, measure the voltage.
![[Transformers-1725424265306.jpeg]]

### Transformer Performance
Voltage Regulation: percentage of voltage drop across the parasitic resistance $R_e$ and $x_e$ in transformer primary side.

Voltage Regulation Equation:

$$ \varepsilon = \frac{|V'2| - |V'2{rated}|}{|V'2|} = \frac{\left|\frac{V_2}{n}\right| - \left|\frac{V{2, rated}}{n}\right|}{\left|\frac{V_2}{n}\right|} = \frac{|V{2nl}| - |V_{2fl}|}{|V_{2nl}|} $$

where $|V'_2|$ is the amplitude of no-load secondary side voltage referred to the primary side.

$|V'2{rated}|$ is the amplitude of rated load secondary side voltage referred to the primary side.

$|V_{2nl}| = |V_2|$ is the amplitude of no-load secondary side voltage (subscript 'nl' represents no-load).

$|V_{2fl}| = |V_{rated}|$ is the amplitude of rated load secondary side voltage (subscript 'rated' represents rated load, i.e. full load).

![[Transformers-1725425314259.jpeg]]
#### Tranformer Efficiency
$$\eta = \frac{P_{out}}{P_{in}} = \frac{P_{in} - P_{loss}}{P_{in}}$$
where $P_{loss}$ is $P_{in} - P_{out}$ and consists of core losses and copper losses.


### Types of Transformers
#### Auto-wound Transformer
![[Transformers-1725426229376.jpeg]]
This is a step-down transformer to whatever voltage is required.
This is cheap but you lose the electrical isolation.

#### Three Phase Transformer
![[Transformers-1725426421787.jpeg]]

For star-delat connection, the line voltage is $\sqrt{3}$ times the phase voltage.
$$\frac {V_{AN}} {V_{A'B'}} = \frac {N_1} {N_2}$$
The primary side phase voltage over the secondary side line voltage is equal to the turns ratio.
![[Transformers-1725426844284.jpeg]]

#### Current Transformer (CT)
Basically a small transformer.
![[Transformers-1725427159160.jpeg]]
$$I_M \approx \frac{N_1}{N_2} I_L$$

Suddenly open circuiting the secondary side can cause a very high voltage pulse on the primary side as,
$$N_1 i_1 - N_2 i_2 = 0 \qquad N_1 i_1 = \mathcal{R} \phi$$
Leads to a sudden large change in $\phi$ and induced voltage is given as,
$$e_1 = N_1 \frac{d\phi}{dt}$$

### Transformer Per Unit Values
#### Why do we use per unit values?
When looking at huge systems, it is easier to work with per unit values. It is a way to normalize the values of the system to a common base.

#### Converting
![[Transformers-1725427776695.jpeg]]

![[Transformers-1725428364026.jpeg]]
![[Transformers-1725428467465.jpeg]]

But where is the transformer in the *per unit* system?
The transformer is not in the per unit system, the information is transcribed using the base values.
