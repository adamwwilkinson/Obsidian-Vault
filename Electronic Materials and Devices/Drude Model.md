Created: 06/03/2023 at 10:14
Tags: #topic/conductivity
Related:

###  What
Based on the way gas particles work and interact.
Made before quantum mechanics.
Things that are shiny, generally conduct.
On average the charge across a conductor is 0, sometimes noise may give a small value when measured.

![[Pasted image 20230306102422.png]]

### Ohm Law
We want a version of ohms law which is independent of the geometry of the material.

$$\frac \xi J = \rho = \text{constant}$$

Where $\xi = \frac V L$ is electric field intensity and $J = \frac I A$ as current density.

$\rho$ is called the resistivity and it has a range of 24 orders of magnitude.

#### Conductivity
The inverse of this is conductivity, $\sigma$.
We can then write Ohm's law as 
$$J = \sigma \xi$$

### What Determines the Conductivity
The density of free electrons, which in itself is determined by the valency of the atom. Also, some atoms are bigger than others which means a lower density.

### Assumptions
- Treat valence electrons as gas in a container
- The electrons have an average energy of $\frac {3k_BT} 2$ with Boltzmann constant and $T$ is temperature in kelvin
- There is no memory after the collision
- All electrons move independent of each other
- The conductor is in equilibrium

### Thermal Velocity
The average speed of the electrons.

$$V_{th} = \sqrt{\frac {3k_BT} m}$$

The average length an electron travels before a collision event is called the *mean free path* $\lambda = v_{th} \tau$.

### Drift Velocity
Under an electric field, every electron will have a component of its velocity due to the applied electric field. This is called its *drift velocity* $v_D$.

The current density due to this field will be 
$$J = -eNv_D$$
Where $e$ is the fundamental charge and $N$ is the charge carrier density.

If we assume the drift component averaged over all electrons are 0 then then the average drift velocity is given by
$$v_D = \frac {-e \xi} m \tau$$
where $\tau$ is the average time between collisions.

We assume $N$ is independent of electric field.

$$v_D = -\mu_e \xi$$ where the unknown term is the *mobility constant*.

### Equations
$$\rho = eN\mu_e$$
$$\mu_e = \frac {e \tau} m$$
$$\rho = \frac {Ne^2\tau} m$$

### It Doesn't Fit?
So when lookin at a table, the equations fit the trend, but doesn't give us the exact right numbers.
This is because electrons do affect each other, and we need quantum mechanics to fill the gap.