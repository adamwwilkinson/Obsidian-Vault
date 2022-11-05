Created: 2022-10-04 11:50
Tags: #topic/electrical/motorsandtransformers
Related: [[review of some physics laws]]

### What
An AC device to change high voltage low current into low voltage high current without changing the frequency.

It accomplishes this using electromagnetic induction.

### Induction Theory
Based on [[review of some physics laws#faradays law of magnetic induction]].

![[Screenshot 2022-11-05 at 10.03.04 am.png]]

### Working Principle of a Transformer
1. When the current in the primary coil changes (AC), a changing magnetic field is produced.
2. The magnetic flux linked with the secondary coil changes.
3. This induces a EMF in the secondary coil.

![[Screenshot 2022-11-05 at 10.04.15 am.png]]

### Primary and Secondary Relationship
The *turns ratio (n)* is defined as the ratio of turns in the secondary windings, to the turns in the primary windings.

$$\frac {V_{s}} {V_{p}} = \frac {N_{s}} {N_{p}} = \frac {i_{p}} {i_{s}} = n$$

```ad-note
n > 1, is a step up transformer (increase voltage)
n < 1, is a step down transformer (decrease voltage)
```

```ad-note
Notice how the current is flipped.
```

## Ideal Transformers
The reason the two coils can be magnetically coupled, is because the iron core premits this.

The notation $\phi_{ij}$ explains which flux is targeted to where $i$ and targeted to who, $j$.

### Leakage
A portion of the $\phi_{11}$, which does not link with winding 2 is the primary leakage flux.

Leakage coefficients,
$$k_{21} = \frac {\phi_{21}} {\phi_{11}} \leq 1$$
$$k_{12} = \frac {\phi_{12}} {\phi_{22}} \leq 1$$

Coupling coefficient between windings,
$$k = \sqrt{k_{21}k_{12}} \leq 1$$

If $k$ is around 1, that is the most efficient coupling. Some applications may want a very low $k$ value.

### Self and Mutual Inductance

#### Self Inductance
##### Primary Coil
$$L_1 = \frac {N_1\phi_{11}} {i_1}$$

##### Secondary Coil
$$L_2 = \frac {N_2\phi_{22}} {i_2}$$

#### Mutual Inductance
##### Primary Coil to Secondary Coil
$$M_{21} = \frac {N_2 \phi_{21}} {i_1}$$

##### Secondary Coil to Primary Coil
$$M_{12} = \frac {N_1 \phi_{12}} {i_2}$$

### Leakage Continued
From above,
$$M_{12} = M_{21} = M$$

Therefore,
$$M = k \sqrt{L_1L_2}$$

If $k$ is one then it is a perfect coupling and therefore no leakage.

### Voltage-current Relations for Coupled Coils
Using [[review of some physics laws#faradays law of magnetic induction]],
$$v_1 = \frac {\mathrm d \lambda_1} {\mathrm d t} = L_1 \frac {\mathrm i_1} {\mathrm d t} + M \frac {\mathrm i_2} {\mathrm d t}$$
$$v_2 = \frac {\mathrm d \lambda_2} {\mathrm d t} = L_2 \frac {\mathrm i_2} {\mathrm d t} + M \frac {\mathrm i_1} {\mathrm d t}$$

In the phasor domain, these equations become,
$$\bar V_1 = j\omega L_1 \bar I_1 + j\omega M \bar I_2$$
$$\bar V_2 = j\omega L_2 \bar I_2 + j\omega M \bar I_1$$

#### Direction of Mutual Inductance
If the direction of the flux in either coils are opposite then the flux is additive.
If the direction of the flux in either coils are the same then the flux is negative.

We use the dot convention to denote the direction. If the dots are at the same positions the flux is additive, but if they are opposite sides, the flux is negative.

### Ideal Transformer Rules
- No leakage flux, i.e. $k = 1$, or $\phi_{21} = \phi_{11}$
- No losses in magnetic core or windings
- No energy storage (this needs to be checked)

We can then get the rule,
$$\frac {v_2} {v_1} = \frac {N_2} {N_1} = n$$

#### Checking Energy Storage
$$W = \frac 1 2 Li^2$$
$$Li = N \phi \leftarrow W = \frac {N^2 \phi^2} {2L}$$

For $W \leftarrow 0$, we need $L \leftarrow \inf$. We can get whis with high values of $\mu_M$ which is the magnetic permeability of material in core.

### Impedance Transformation and Matching
Primary side, 
$$P_1 = v_1 i_1$$

Secondary side, 
$$P_2 = v_2 i_2$$

As we want no power supplied to the transformer,
$$P = P_1 + P_2 = v_1 i_1 + v_2 i_2 = 0$$
$$n = \frac {N_2} {N_1}$$

#### Phasor Domain
$$\bar V_2 = n \bar V_1$$
$$\bar I_1 = -n \bar I_2$$

If the dots are on the same side, the voltage on both sides have the same signage. While if they were opposite they would be opposite signage.

If both current both flow into or both flow out of their respective dot terminal, then they have opposite sides.

### Impedance Matching
The load impedance from the secondary winding is reflected back to the primary and scaled by the inverse square of the turns ratio.
$$Z_{in} = \frac {Z_L} {n^2}$$

### Open and Short-circuit Loads
#### Open Circuit
If the load is an open circuit, then the entire circuit is an open circuit. But there is no such thing as an open circuit, just one with very large resistance. If the turn ratio is very large, the value of $R_{in}$ may be small or moderate and must be treated as such.

#### Short-circuit
If the load is a short circuit, then the entire circuit is a short circuit. But there is no such thing as a short circuit, just one with very small resistance. If the turn ratio is very small, the value of $R_{in}$ may be large or moderate and must be treated as such.
