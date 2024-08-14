Created: 03/08/2024 at 16:43

### Cross Products vs Dot Products
$$\mathbf{A} \times \mathbf{B} = |\mathbf{A}||\mathbf{B}|\sin(\theta) \mathbf{n}$$
, which is a vector. The direction of the vector is given by the right-hand rule.

$$\mathbf{A} \cdot \mathbf{B} = |\mathbf{A}||\mathbf{B}|\cos(\theta)$$
, and is a scalar




### On Conductors
- the effects are described in terms of a magnetic field
- measured by *Magnetic Flux Density* $B$
- $B$ is a vector and has direction

#### Effect 1
If the conductor is moving with speed $v$ in direction perpendicular to field and current
![[Magnetic Effects-1722675404304.jpeg]]

There will be a voltage generaed in the conductor (Electromagnetic Force) equal to:
$$e = l(v \times B) \ \ \ \ V(volts)$$

where $l$ is the length of the conductor.

**Generator**

#### Effect 2
If a conductor carries a current $i$ in a direction perpendicular to the field.
![[Magnetic Effects-1722675553714.jpeg]]
A force will be exerted on the conductor, with the magnitude being
$$f = i(l\times B) \ \ \ N(Newton)$$

**Motor**

#### Lorentz Force Law
The forces on a moving charge $q$
$$F = q(E + v \times B)$$
where $E$ is the electric field

This force an be divided in two components

##### The Electric Component
$$F_e = qE$$

This force is independent of any particles velocity.

##### The Magnetic Component
$$F_m = q(v \times B)$$
The force is perpendicular to the velocity of the particle and the magnetic field.

### On Iron
![[Magnetic Effects-1722676556282.jpeg]]
![[Magnetic Effects-1722676662196.jpeg]]

The force of a unit of area due to a uniform magnetic field perpendicular to the surface could be expressed as:
$$f_m = \frac{B^2} {2\mu_0}$$

where $\mu_0$ is the permeability of free space.

The structure in the figure has two poles. For each pole:
$$\frac {f_p} {A_p} = \frac {B^2} {2\mu_0}$$

Where $B_g$ is the flux density in the airgap and $\mu_0$ is the primary permeability.

The total force on the armature is:
$$f_t = 2f_p = \frac {B^2 A_p} {\mu_0}$$

### Magnetic Flux and Gauss Law
#### Magnetic Flux
The total flux in a given area is
$$\Phi = \int_s \mathbf{B} \cdot d\mathbf{A}$$

Where $\mathbf{B}$ is the magnetic field and $d\mathbf{A}$ is the area vector.
![[Magnetic Effects-1722677312755.jpeg]]
If $B$ is uniform and at same angle to the area, then
$$\Phi = B A$$

#### Gauss Law
For any closed region in magnetic field the total flux entering the region is equal to the flux leaving.
$$\oint \mathbf{B} \cdot d\mathbf{A} = 0$$

### Permanent Magnet
Instead of using a coil we could use a permanent magnet to create magnetic Flux.
![[Magnetic Effects-1722677752405.jpeg]]
![[Magnetic Effects-1722677771445.jpeg]]

Based on Gauss Law:
$$\Phi = B_sA = B_GA$$

Where $B_s$ is the flux density of the magnet and $B_G$ is the flux density in the airgap.

Important conclusion:
$$B_s = B_G$$

### Magnetic Flux and Gauss Law
![[Magnetic Effects-1722736813293.jpeg]]

Through the airgap:
$$B_g = B_s = \frac {A_m} {A_p} B_m$$


$$f_t = \frac {B_g^2 A_p} {\mu_0} = \frac {B_m^2 A_m^2} {A_p^2} \cdot \frac{A_p} {\mu_0} = \frac {A_m^2} {A_p} \cdot \frac {B_m^2}{\mu_0}$$

### Magnetic Field of a Current Carrying Conductor
Given by the *Bio-Savart* formula (through experiments)
$$dB = \frac {\mu_0 I d\theta} {4\pi r^2}$$

Where $I$ is the current, $r$ is the distance from the conductor and $d\theta$ is the angle between the current and the point.

![[Magnetic Effects-1722737395290.jpeg]]

![[Magnetic Effects-1722737429538.jpeg]]

$$B = \frac{\mu_0I} {2\pi r}$$
![[Magnetic Effects-1722737596419.jpeg]]

### Ampere's Law
#### Magnetic Intensity
$$H = \frac {B} {\mu_0}$$
The magnetic intensity is in units of amperes per meter.

If the magnetic field is flowing through materials, it would be more dense and the magnitude is larger.
$$\mu = \mu_0 \mu_r$$
Where $\mu_r$ is the relative permeability of the material.

Some materials could have as high a relative permeability as $250 000$.

#### Calculating Magnetic Intensity
If $C$ is a contour, the integral of the tangential component of the field intensity over the length of the contour, is equal to the current enclosed by the contour.

$$\oint_C H \cdot dl = \int_s J \cdot dA$$

Where $J$ is the current density and $dA$ is the area vector.

If the current is uniform in the surface then

$$\oint_C H \cdot dl = I_{\text{enclosed}}$$
![[Magnetic Effects-1722738529318.jpeg]]

#### Simplifying Analysis
![[Magnetic Effects-1722738705746.jpeg]]
