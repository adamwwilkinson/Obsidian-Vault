# Transformers
Created: 2022-10-04 11:50
Tags: #topic/electrical/motorsandtransformers
Related: [[review of some physics laws]]

### What
An AC device to change high voltage low current into low voltage high current without changing the frequency.

It accomplishes this using electromagnetic induction.

### Induction Theory
Based on [[review of some physics laws#faradays law of magnetic induction]].

#todo/excalidraw 12:03 4 oct

### Working Principle of a Transformer
1. When the current in the primary coil changes (AC), a changing magnetic field is produced.
2. The magnetic flux linked with the secondary coil changes.
3. This induces a EMF in the secondary coil.

#todo/excalidraw 12:17

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
