Created: 04/08/2024 at 11:39

### Amperes Law To Calculate Field Intensity
![[Magnetic FIeld Intensity-1722742836435.jpeg]]

This design on the top right leads to good magnetic symmetry.

### Flux Linkage
![[Magnetic FIeld Intensity-1722743240900.jpeg]]

The magnetic flux in a cross-sectional area of a coil is given by
$$\Phi = B \cdot A \ \ \text{Wb (Weber)}$$
where $B$ is the magnetic flux density and $A$ is the cross-sectional area.

The sum of fluxes of each coil is known as the *flux linkage*.
$$\Lambda = N \Phi \ \ \text{Wt (Weber\  turn)}$$
where $N$ is the number of turns in the coil.

### Inductance
The flux linkage is proportional to current with a linear relationship:
$$\Lambda = L I$$
where $L$ is the inductance of the coil.

$$L = \frac {\Lambda} {I} = \frac {N \Phi} {I} \ \ \text{H(Henry)}$$

For the core we can write,
$$\Phi = B \cdot A = \frac{\mu_0 NiA} {2 \pi r_{AV}}$$
where $\mu$ is the permeability of the core.

Thus,
$$L = \frac {N^2 \mu_0 A} {2 \pi r_{AV}} \ \ \text{H (Henry)}$$

#### Energy Stored
The energy stored in the magnetic field is given by
$$W = \frac {1}{2} L I^2 \ \ \text{J (Joule)}$$
where $W$ is the energy stored in the magnetic field.

With the proof being below
![[Magnetic FIeld Intensity-1722743983987.jpeg]]

### Magnetic Material
#### Relative Permeability
If the toroidal core is wound on a core of magnetic material, the *flux density* and *flux* would increase and consequently the *inductance* will increase
$$L' = \mu_r L$$
where $\mu_r$ is the relative permeability of the material.
$$\mu_r = \frac B {mu_0 H}$$
where $H$ is the magnetic intensity.
![[Magnetic FIeld Intensity-1722744108588.jpeg]]

This happens because the field goes through the path of least resistance which in this case is the high permeability material.

### Magnetisation Curve (B-H Curve)
![[Magnetic FIeld Intensity-1722744221817.jpeg]]

Given a material where they have electrons within it canceliing out each others magnetic field.

Introducing an external magnetic field, strengthens the magnetic field in that direction and weakens in the other.

Increasing the external field, can saturate it which is what the curve shows.

The linear portion is given by,
$$B = \mu_0 \mu_r H$$
where $\mu_r$ is the relative permeability of the material.

![[Magnetic Field Intensity-1722744390229.jpeg]]

Interestingly removing the external field after taking it to a saturation point leaves some residual flux.
![[Magnetic Field Intensity-1722744472680.jpeg]]o

And we need some negative flux intesity in this case $H_C$ to remove the residual flux.

#### Evolution of the Hysteresis Loop
![[Magnetic Field Intensity-1722744584274.jpeg]]

### Magnetic Circuit with Air Gaps
As all electric machines have mechanical rotating parts, the flux is required to path through an *air gap*.
![[Magnetic Field Intensity-1722744854219.jpeg]]

$$l_g << l_s$$

$$\sum i = Ni = \oint H \cdot dl = H_s l_s + H_g l_g$$

Thus,
$$i = \frac {H_s l_s + H_g l_g} {N} \approx \frac {H_g l_g} {N}$$

Assuming $H_s$ is 0 as $\mu_r$ approaches infinity.

As $Ni$ is the driving force in magnetic circuit, it is called the *magnetomotive force* (MMF).
$$F = Ni \ \ At \text{ (Ampere turn)}$$

### Magnetic Circuit Analysis
Voltage in an electric circuit is analogous to magnetic motor force in a magnetic circuit.

$$V \rightarrow \mathcal{F}$$

Current in a electric circuit is analogous to magnetic flux in a magnetic circuit.

$$I \rightarrow \Phi$$

Resistance in an electric circuit is analogous to reluctance in a magnetic circuit.

$$R \rightarrow \mathcal{R}$$

Conductivity is analagous to permeability in an magnetic circuit.

$$\sigma \rightarrow \mu$$

The magneto motive force is given by
$$\mathcal{F} = \frac {Ni} {l} = H_c l_c + H_g l_g$$

Assuming the linear portion of the B-H curve,
$$\mathcal{F} = \frac {Ni} {l} = \frac {B_c l_c} {\mu} + \frac {B_g l_g} {\mu_0}$$

And
$$\mathcal{F} = \ (\frac{l_c}{\mu A_C} + \frac{l_g}{\mu_0 A_g}) = \Phi \mathcal{R}$$

This matches an electric circuit
$$V = IR$$

This term is defind as the *reluctance*
$$\mathcal{R} = \frac {l} {\mu A}$$

$$\mathcal{F} = \Phi (\mathcal{R}_c + \mathcal{R}_g)$$

### Induction
Induction is generation of a voltage in a conductor due to a changing magnetic field.

- *motional induction* is when the conductor moves in a magnetic field
- *transformer induction* is when the magnetic field changes in a stationary conductor

The flux linkage is given by
$$\Lambda = N \Phi = N B A = Li$$

Faradays Law:
$$e = -\frac {d \Lambda} {dt} = -N \frac {d \Phi} {dt}$$

$$e = \frac {d\lambda} {dt} = \frac d {dt} (Li) = L \frac {di} {dt} + i \frac {dL} {dt}$$
![[Magnetic Field Intensity-1722748122677.jpeg]]

If $L$ is constant
$$e = L \frac {di} {dt}$$

if $i$ is constant
$$e = i \frac {dL} {dt}$$

$$L =  \frac{\mu_0 N^2 A} {l}$$

### Mutual Inductance
![[Magnetic Field Intensity-1722748352321.jpeg]]

To simplify analysis we can look at each magnetic circuit separately.

The flux in the second loop is linearly proportional to the current in the first loop.
$$\lambda_{12} = M_{12} i_2$$
And for the first loop,
$$\lambda_{21} = M_{21} i_1$$

$M$ is the mutual inductance between the two loops.

$$M = M_{12} = M_{21}$$
![[Magnetic Field Intensity-1722748664448.jpeg]]
![[Magnetic Field Intensity-1722748698515.jpeg]]