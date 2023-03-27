Created: 27/03/2023 at 18:21

### A 1-D Box
Consider a wire of finite length, large compared to interatomic distances

Let's consider many electrons confined to this well. We have solved this before with the solution, 
![[Density of States-1679912692633.jpeg]]

```ad-note
The larger we make our $l$ in our infinite well, the more continous and closer together different energy levels can be.
```

With this wire, we are assuming if you move an integer multiple of interatomic spacing, the local environment is the same.
$$\psi(0) = \psi(L)$$
This boundary condition is satisfied if 
$$k=2\pi \frac n L$$
That is
$$L = n\lambda$$

![[Density of States-1679913231126.jpeg]]

This means the waves are travelling in both directions, for the case $n = 0$ the wavelength is infinite, a.k.a. constant wave function. This has $k$ value 0 and energy 0. We know from quantum mechanics this $n = 0$ state is not allowed.

The kinetic energy,
![[Density of States-1679913319685.jpeg]]

As our wire $L$ is very large, we will have many levels (about $10^{29}$ per cubic meter and the difference in energy level is roughly $10^{-7} eV$)

Taking temperature to be $T = 0$, we can now fill these levels with electrons taking to account Pauli's exclusion principle, there can only be one electron in each quantum state.

We keep filling up these energy levels with 2 electrons in each level until we have $N$ electrons, have going left and half going right.
![[Density of States-1679913663594.jpeg]]

```ad-info
We can have 2 electrons in each level, because there are two quantum states, *spin up* and *spin down*.
```

In the end we get to level $k_F$ such that 
![[Density of States-1679913732903.jpeg]]

The $F$ stands for *Fermi* and the energy corresponding to this wave number is the Fermi-energy.

![[Density of States-1679913784551.jpeg]]

This is the maximum energy the electron can have at 0 Kelvin.
In the [[Drude Model]] all electrons had zero energy, which isn't possible.

### A 2-D Box
![[Density of States-1679913864007.jpeg]]

We can expand what we've done before to get the allowed energy levels,
![[Density of States-1679914104561.jpeg]]

With the *Fermi* function being,
![[Density of States-1679914148060.jpeg]]

### A 3-D Box
![[Density of States-1679914173624.jpeg]]
Width, height, and depth is $2\frac \pi L$ and that volume is the volume of one state, each state has the same surrounding volume.

![[Density of States-1679914297641.jpeg]]

### Real Life Equation
If we consider a metal in the first column of the periodic table, each atom will have one electron available, and hence $\frac N {L^3}$ is the density of electrons in the metal. We can find the maximum electron energy at T = 0 is around 5 eV with the Fermi velocity of ${10^6 ms^{-1}}$ 