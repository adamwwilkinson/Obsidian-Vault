Created: 11/03/2023 at 15:43

### The Schrödinger Equation
Electrons are quantum particles. This means we can only describe them with their wave function.
$$\Psi(x,y,z,t)$$
The equation
$$\Psi \times \psi^*dxdydz$$ 
gives the probability the electron would be found at infinitesimal volume $dxdydzdt$ at position $(x, y, z)$ at time $t$.

![[Pasted image 20230311155308.png]]

#### Solving Schrödinger Equation
We assume the particle has to be somewhere in space at a given time:
![[Pasted image 20230311155447.png]]
We also expect the particle to not fully disappear at any time, which implies:
![[Pasted image 20230311155538.png]]
A further requirement is the wave function is continuous and it's first derivative is continuous everywhere.

Assume the total energy $E$ is independent of position, and the potential energy $U$ is independent of time.

Assume $\Psi(x, y, z, t)$ is in the form,
$$\psi(x,y,z)e^{-jE\frac t h}$$
![[Pasted image 20230311160405.png]]
![[Pasted image 20230311160416.png]]

$E - U$ is kinetic energy

The second derivative is a measure of the wave-function and hence the larger the curvature the higher the kinetic energy.

![[Pasted image 20230311160807.png]]

### Unbound Electron Case
This is the simplest case to use the Schrödinger equation.

For a free electron, the potential energy is 0 everywhere.

![[Pasted image 20230311163255.png]]

The electron has momentum $p = \hbar k$ and this value is known.

```ad-info
$$k = \text {wave number} = \frac {2\pi} \lambda$$
```

This is what the wave function looks like in space.
![[Pasted image 20230311163830.png]]
![[Pasted image 20230311164040.png]]

The probability of the particle existing anywhere is $A^2$.

### Useful Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/sPZWtZ8vt1w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### Recap
The electron has given momentum $p=\hbar k$, and this value is known.

The probability density is $P = \Psi(x) \Psi^*(x) = AA^*$ and hence is constant everywhere. This probability is practically zero though as the probability has to be spread through all of space.

### Flux
This is the probability of the electron going through a particular square area. Also known as the probability current.

![[Quantum Mechanics-1678854814753.jpeg]]

The continuity equation for probability $P = \Psi \Psi^*$,
$$\frac \partial {\partial t} \vert\Psi\vert^2 = \frac \partial {\partial x} J$$

The flux is the probability density multiplied by velocity.
For a free particle, $\frac {p^2} {2m} = \frac {\hbar k^2 } {2m}$

The probability flux density is 
$$J = \vert A \vert ^2 \frac {\hbar k} m$$

Where $A$ is the amplitude of the free particle wave-function. The units are $J$ probability per unit area. The second term on the right-hand side is velocity.