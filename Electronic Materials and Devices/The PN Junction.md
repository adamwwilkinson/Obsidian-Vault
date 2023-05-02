Created: 24/04/2023 at 17:41
![[The PN Junction-1682329624896.jpeg]]
In the P region a large negative charge is created and in the N region a large positive charge is created which creates an electric field.

There are two forces, the electrons moving due to diffusion, but the electric fields send them back again and in the end there is a balance. 

The movement of majority carriers is due to diffusion, and the movement of minority carriers are due to the electric field.

![[The PN Junction-1682329930949.jpeg]]

### Chemical Potential
Considering a layer of n-type semiconductor with density $N_D$, we also assume the density of free electrons match this.

The potential energy to cause movement due to population is called *chemical potential* $\mu^c$.
The chemical potential of electrons is $\mu^c_e$, and is defined as follows,
$$(\mu_e^c)_N = \mu_i^c + kT ln(\frac {N_D} {n_I})$$
$\mu_i^c$ is the intrinsic Fermi energy $E_i$, and is constant at equilibrium.
$\mu_i^c$ represents the amount of energy required to add an electron to a pure, undoped, crystal of a semiconductor, while $(\mu_e^c)_N$ is the energy required to add an electron to a crystal that has been doped by impurities.
![[The PN Junction-1682330526115.jpeg]]

It takes less energy to put a hole in n-type material than it is to put an electron.

The same maths works for p-type materials.

### PN Junction in Equilibrium
![[The PN Junction-1682330618390.jpeg]]
*Dopant ions*  cannot move because they are covalently bonded in the crystal.

The electric potential barrier will increase in magnitude until eventually it will balance the flow of holes and electrons caused by the chemical-energy difference.

A hole moving from n-type region to a p-type region increases the chemical potential energy, which a hole moving from p-type to n-type decreases it.

### Principle of Detailed Balance
####  Moving from N to P
![[The PN Junction-1682331225978.jpeg]]

#### Moving from P to N
![[The PN Junction-1682331255751.jpeg]]

### Voltage
Combining the equations above,
![[The PN Junction-1682331296330.jpeg]]

Where $\phi$  is out built in voltage.

$$\phi = V_T ln(\frac {N_A N_D} {n_i^2}) $$
$V_T = \frac {kT} {e}$ is the thermal voltage which is 25.9mV at 300K.

Can also be written as,
![[The PN Junction-1682394715952.jpeg]]

### The Electro-chemical Potential
![[The PN Junction-1682394823258.jpeg]]

We can interpret this to mean
$$(\mu_e^c)_P + e\phi = (\mu_e^c)_N$$

### Energy-x Graphs
#### Intrinsic or single type of material
![[The PN Junction-1682395238532.jpeg]]

#### PN Junctions
![[The PN Junction-1682395435668.jpeg]]

The green line is the Electrochemical potential energy, as it is flat and constant, that means the forces are in balance. If we disturb the balance, a current is generated. Using an external voltage, less current will be flowing. Making the voltage lower, less than $\phi_{BI}$, there is less resistance for the electrons moving from the N side to the P side.

```ad-important
![[The PN Junction-1682395674533.jpeg]]
This is how a diode works, where depending on whether the voltage is increased or reduced, determines whether a current flows or not. When the voltage is equal to $\phi_{BI}$, no net current flow. If the barrier height is increased, it reduces the current. Reduce the barrier height and there is a large flow of current.
```

### Maths Explaining the Graphs
Assign electrochemical potential energy for electrons $E_{Fe}$ and $E{Fh}$ for holes, and find the equilibrium where these energies are the same.

The Fermi-energi $E_F$ is the average kinetic energy of free electrons. The electrons that move from the N-region to the P-region increase their electric potential energy by losing kinetic energy. A similar statement can be made for holes.

The Fermi-energy for a *uniform* semiconductor is given by
$$E_F = E_i + kTln(\frac {n} {n_i})$$

As the PN-junction is not uniform, $n$ is a function of $x$ and thus,
$$E_F = E_i + kTln(\frac {n(x)} {n_i})$$

$E_i$ is also a function of x.

$$E_F = E_i(x) + kTln(\frac {n(x)} {n_i}) = \mathrm {constant}$$

On the N-side, $E_i(x) = E_i$
On the P-side, $E_i(x) = E_i + e\phi_{BI}$

In between these two extremes, $E_I(x) = E_i + e\phi(x)$

In the *neutral* N-region, the electrons have zero potential energy and hence the electro-chemical potential is purely the chemical potential, and is equal to the Fermi energy for electrons
$$E_F = E_i + kTln(\frac {N_D} {n_i})$$

A similar argument can be made for the holes in the neutral P=region.

$$E^P_{Fe} = E_{Fe} = E_F = E_{Fp} = E^N_{Fh}$$

#### Graph for Holes
![[The PN Junction-1682397631262.jpeg]]

### Drawing the Band Diagram for a PN-junction in Equilibrium
![[The PN Junction-1682398512505.jpeg]]

### Finding the Chemical Potential Energies
![[The PN Junction-1682738461252.jpeg]]

The reason the intrinsic Fermi energy is higher on the P-side than the N-side is because it is subject to the electric field.
#### Holes
$$E_i - E_F = k_BT ln \frac {N_A} {n_i}$$
$$E_f - E_i = k_BT ln \frac {N_D} {n_i}$$
Adding these two values up, the green side and the blue side, actaully gives *$e\phi_{BI}$*. This shows how the built in voltage can be changed by playing with $N_D$ or $N_A$.

## Drift and Diffusion Currents
![[The PN Junction-1682738985499.jpeg]]
```ad-important
The electrons that go from N-side to P-side is the diffusion current, while the electrons that go from P-side ot N-side is the drift current.
```

Thinking of holes as bubbles will help to imagine its behaviour.
There are 4 types of currents, drift, and diffusion for both electrons and holes.

### Poisson's Equation
$$\nabla (\nabla \phi) = \nabla^2 \phi = -\frac \rho \epsilon $$
Where $\epsilon$ is the electric permittivity, and $\rho$ is the charge density.

As electric potential does not vary except along the x-axis we can simplify it to
$$\frac {d^2 \phi(x)} {dx^2} = - \frac {\rho(x)} {\epsilon}$$
$$\frac {d^2 \phi(x)} {dx^2} = -\frac e \epsilon [p(x) - n(x) + N_D(x) - N_A(x)]$$
##### What charges do we have available
On the right-hand side, we have holes which are positively charged, electrons which are negatively charged, donors which are positively charged, acceptors which are negative charged.

### Simplifying Analysis
We can divide the diode into three regions.
![[The PN Junction-1682739863305.jpeg]]

#### Depletion Approximation
Let's assume that in the space charge regions, there are no free holes or electrons as they have been pushed out. This means in the neutral regions there is no charge, and the charges in the space charge regions are only due to dopants.

This simplifies [[#Poisson's Equation]] to
$$\frac {d^2 \phi(x)} {dx^2} = -\frac e \epsilon [N_D(x) - N_A(x)]$$

### Solving the Equation in two steps:
1. Solving the electric field intensity $\zeta$
2. Solving the electric potential $\phi$
![[The PN Junction-1682740152212.jpeg]]
![[The PN Junction-1682740659813.jpeg]]
![[The PN Junction-1682742796007.jpeg]]
![[The PN Junction-1682742832247.jpeg]]

### Useful Equations
$$N_A x_p = N_D x_n$$
![[The PN Junction-1682742942263.jpeg]]
$$n(x) = n_i\exp(\frac {E_F - E_i(x)} {kT})$$

### Law of the Junction
$$n(x) = N_D \exp \left( -\frac {\phi(x)}{V_T} \right)$$
![[The PN Junction-1683014722007.jpeg]]
