Created: 11/08/2024 at 20:19

### Fundamentals
Compared to AC machines, DC machines have higher losses, with efficiencies around 70% - 90%. Which makes it discouraged for high power applications.

They also have a greater maintenance cost due to the commutator and brushes.

### Commutators
Rectify the negative torque by ensuring the side the current goes into the coil is always the same and the side it comes out is always the same.

### Stator
Made up of many many windings to ensure the magnetic field is as dominant as possible.
![[DC Electrical Machines-1723379142954.jpeg]]

### Magnetic Analysis
![[DC Electrical Machines-1723379373381.jpeg]]

We can assume all reluctances other than the air gap are negligible. Simplifying to,
![[DC Electrical Machines-1723379705396.jpeg]]
$$\phi = \frac{2F}{2R_g} = \frac{F}{R_g} \quad (\text{simplified})$$
![[DC Electrical Machines-1723379910505.jpeg]]

#### Lookup Tables
![[DC Electrical Machines-1723380020401.jpeg]]
Commonly used in the industry to quicken calculations.

### Armature Reaction
![[DC Electrical Machines-1723380214955.jpeg]]

We can see negative changes to the external flux massively decreases the internal flux, while positive changes barely increase it above this saturation point.

This leads to instability,
$$\tau_{\text{constant}} = K \phi I_A$$
When $\phi$ is reduced, the current must increase, which lowers $\phi$ even more, which increases the current even more, and so on.
![[DC Electrical Machines-1723380425672.jpeg]]

We use compensation widings pictured above to counteract this effect.
