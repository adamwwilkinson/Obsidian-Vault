Created: 24/03/2023 at 10:10

### Situation
Consider a one dimensional situation where an electron is confined in a potential well such that $U = 0$ inside the well between $z = 0$ and $z = L$ and $U = \inf$ outside the wel.
![[Particle in a Box-1679623908617.jpeg]]

We need to find a function that is 0 just before the boundary, and 0 after as the function has to be continuous.
```ad-note
Cosine functions are 0 every $\pi$, so it can be a solution to this. Sine waves as well can be possible solutions.
```

The wave equation must be in the form:
![[Particle in a Box-1679626598114.jpeg]]
![[Particle in a Box-1679626626465.jpeg]]

Any other energy value for an electron could not have a wave function to describe it, thus leaving its probability 0.
![[Particle in a Box-1679626853073.jpeg]]

### Recap
We have confined the electron to a location between 0 and $L$, i.e. $\Delta z = L$
A standing wave can be considered as the summation of two waves travelling in opposite direction with momentum $p = \bar h k = \pm \frac h {2L}$ hence the uncertainty in momentum is $\Delta p = \frac h L$
$\Delta p \Delta z = h$ as expected from Heinburg's identity.

### Potential Well
![[Particle in a Box-1679627238687.jpeg]]

If there is a particle in this well with energy $E$ less than $U_0$ then we would expect the particle to be trapped. However, we find that it's only possible for certain values of $E$.

Outside the well the particle has the solution,
![[Particle in a Box-1679627491077.jpeg]]

By symmetry, the wave function of the particle must be either symmetric or antisymmetric.

Applying the continuity conditions, solutions only exist for the *even* symmetry case as follows,
![[Particle in a Box-1679627692171.jpeg]]

For the *odd* solutions, we have equations for the symmetric case:
$$\kappa = k\tan(kL)$$
and for the anti symmetric case
$$\kappa = -k\cot(kL)$$

Both $\kappa$ and $k$ depend on $E$ and hence when $E<U_0$ there can only exist solutions for discrete values of $E$.

#### Solutions
![[Particle in a Box-1679628238153.jpeg]]