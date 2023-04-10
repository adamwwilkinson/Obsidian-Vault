Created: 01/04/2023 at 09:01

### Difference With Metals
The main difference with semiconductors and metals, is that semiconductors have a band gap. This is why as you heat up a metal it's conductivity decreases while if you heat up a semiconductor it's conductivity increases.

### Intrinsic Semiconductor
Has perfect crystal form, no defects nor impurities. At 0K, all states in valence band are full, and all states in conduction band is empty. No conduction under normal electric fields.

When an electron is promoted to the conduction-band, it behaves like a free electron, except its effective mass depends on the lattice. It leaves behind a positive 'hole'. The now free electron will drift under the influence of an electric field in the direction expected for negative charge.

The effective mass of the electrons in the valence band is negative, so they behave positive charge. This means they will drift in the opposite direction. This means these carriers also contribute to current, although with different drift velocities depending on effective mass.

```ad-info
In a intrisic semiconductor, for every electron in the conduction band there is a matching hole in the valence band.
```

In terms of the [[Density of States#Fermi-Dirac Distribution Function]] $E_F$ is halfway between the bottom of the conduction band and the top of the valence band.

![[Semiconductors-1680313841757.jpeg]]

A good semiconductor material has few electrons in the conduction band at room temperature (the band gap energy is large compared to the average thermal energy at room temp). For an intrinsic semiconductor, carriers in the conduction band are generated thermally, and the density of carriers is a random number. This randomness contributes to electrical noise in the device and should be minimised.

### Extrinsic Semiconductors
Adding impurities to a intrinsic semiconductor makes it extrinsic. When doping a intrinsic semiconductor with an element from a group above, there is a free electron left over. This is called n-type materials. P-type is made when doped from an element below.

The impurities make up only a small fraction of the atoms in the crystal.

#### Donors
These are impurities who leave a free electron when covalently bonded to the lattice. This positive charge is *immobile*.

![[Semiconductors-1680314770108.jpeg]]

#### Acceptors
These are impurities that create a positive hole in the lattice, as electrons try to fill up to create covalent bonds.

![[Semiconductors-1680315206054.jpeg]]

#### How to Dope
Grow a crystal of silicon, slice it up with a diamond knife to create silicone wafers.
The impurities can then be shot in.

#### Key Points
- density of holes and electrons are not the same.
- in n-type materials, electrons are majority charge carriers, and density of electrons are far greater than density of holes
- opposite is true for p-type materials

### Variations of Fermi-energy with Temperature
Relates to [[Density of States#Fermi-Dirac Distribution Function]].
![[Semiconductors-1680833126997.jpeg]]

The reason thee is a max temperature for semiconductors, once you reach the temperature where electrons from the valence band jump up to the conduction band, it no longer acts as an n-type material, and instead it acts intrinsic like.

### Doping (for Silicone)
![[Semiconductors-1680833481955.jpeg]]

Electron mobility, and hole mobility, both decrease as doping increases.

### [[Density of States]] Recap
The number of energy levels per unit $\Delta E$ is,
$$N(E) = \frac {8\pi L^3} {3h^3} (2mE)^{3/2}$$
and hence the density of states (number of states per $\Delta E$ in volume $L^3$),
$$\frac {dN(E)}{dE} = \frac {4\pi L^3 (2m)^{3/2}} {h^3} \sqrt E$$

The density of states per unit energy per unit volume $Z(E)$ is,
$$\frac {dN(E)}{L^3 dE} = \frac {4\pi (2m)^{3/2}} {h^3} \sqrt E$$

#### In Conduction Band
$$Z(E)_{CB} = C_e \sqrt {E - E_C}$$
Where $C_e$ is,
$$C_e = \frac {4\pi (2m^*_e)^{3/2}} {h^3}$$
![[Semiconductors-1680834128386.jpeg]]

#### In Valence Band
$$Z(E)_{VB} = C_h \sqrt {E_V - E}$$
Where $C_e$ is,
$$C_h = \frac {4\pi (2m^*_h)^{3/2}} {h^3}$$

### Carrier Densities in a Semiconductor
The number of electrons in a conduction band depends on two things, the density of states, and the Fermi function.
![[Semiconductors-1680834544377.jpeg]]
If the statement at the bottom is satisfied, we can use the Boltzmann approximation
![[Semiconductors-1680834583045.jpeg]]

Integrating this, we get,
$$n = N_C e^{-\frac {E_C - E_F} {kT}}$$

Where $N_C$ is known as the *effective density of states*,
$$N_C = 2(\frac {2\pi m^*_ekT}{h^2}^{3/2})$$

For the density of holes,
$$p = N_V e^{-\frac{E_F - E_V}{kT}}$$

Where $N_V = N_C$ but with $m^*_h$.

### How can we tell what type
If the Fermi energy is in the middle of the band gap, it is intrinsic. If it is closer to the conduction band, it is n-type. And if it is closer to the valence band, it is p-type.

![[Semiconductors-1680835077647.jpeg]]

```ad-note
There is an equation to the side $np = n_i^2$, this says the product of the density of electrons in the conduction-band, and the density of holes in the valence-band, is constant at a given temperature.
```

$n_i$ is the intrinsic electron population in the conduction band, which is equal to $p_i$ the intrinsic hole population in the valence band.

### Where is the Fermi Level
![[Semiconductors-1680835957574.jpeg]]

The intrinsic Fermi level is roughly in the middle of the band gap. The Fermi level is closer to the condunction band in n-types, and closer to the valence band in p-types.

### Equations to find the population of electrons in the conduction band, or to find the Fermi level
![[Semiconductors-1680836146721.jpeg]]