Created: 18/03/2023 at 16:58

In [[The Frequency Domain]], we showed we can represent circuit elements with an impedance which was a *complex number*.

In the *Laplace Domain*, we can represent circuit elements with an impedance which is a *complex function* of the complex variable $s$. We can then use KVL and KCL to generate algebraic equations in *s* describing the circuit. Independent sources are transformed in the Laplace domain as function *s*. We can solve these equations for unkowns and obtain them as functions of *s*.

We can transform the required voltage or current back to the time domain to find the *complete* response (both *natural* and *forced*). By transforming both in and out of the Laplace domain, it prevents us from having to solving complex equations in the time domain

### Benefits
- can include initial conditions
- obtain natural and forced response
- increased range of forcing functions available

### Unilateral Laplace Transform
AKA one-sided Laplace transform. This is where functions are $0$ where $t<0$.
$$F(s) = \mathscr{L}\vert f(t) \vert = \int_0^\inf f(t)e^{-st}dt$$

Where $s = \sigma + j \omega$ and exists if
$$\int_{0^-}^\inf \vert f(t) \vert e^{-\sigma t} dt < \inf$$

![[The Laplace Domain-1679143151608.jpeg]]

### Properties
![[The Laplace Domain-1679143570263.jpeg]]
![[The Laplace Domain-1679143590101.jpeg]]
![[The Laplace Domain-1679143607190.jpeg]]

### Applied
![[The Laplace Domain-1679205441077.jpeg]]

We can do the above method, however, similar to how we used impedance in the *Phasor domain* we can do something similar here in the *Laplace domain*.

### Complex Frequency
![[The Laplace Domain-1679205732854.jpeg]]

### Impedance in the Laplace Domain
#### Resistor
![[The Laplace Domain-1679205828083.jpeg]]

#### Inductor
![[The Laplace Domain-1679206081721.jpeg]]

#### Capacitor
![[The Laplace Domain-1679206161495.jpeg]]

### Applied Again
![[The Laplace Domain-1679206414508.jpeg]]

### Transfering Back Into the Time Domain
Finding $v(t)$ from $V(S)$ is usually performed using partial fraction expansion as well as a table to find the $v(t)$ for each fraction.

![[The Laplace Domain-1679206812378.jpeg]]
The coefficient $c_i$ can be found as,
$$c_i = (s - p_i)F(s)\vert_{s=p_i}$$

#### Example
![[The Laplace Domain-1679207032062.jpeg]]
![[The Laplace Domain-1679207092093.jpeg]]
![[The Laplace Domain-1679207166175.jpeg]]

#### Complex Example
![[The Laplace Domain-1679207536003.jpeg]]
![[The Laplace Domain-1679207580329.jpeg]]
![[The Laplace Domain-1679207622788.jpeg]]

### Driving Point Impedance
A measure of impedance of a circuit at a specific point an input signal is applied.
$$Z_k(s) = \frac {V_k(s)} {I_k(s)}$$

![[Network Functions-1679708083523.jpeg]]

### Properties of Network Functions
Always long polynomials,
![[The Laplace Domain-1679708207941.jpeg]]
- all poles are real or occur in complex conjugate pairs
- the numerator may have negative coefficients
- the poles are natural frequencies of the network
- all network functions of a given network have the same poles provided
- for any network function the total number of zeroes equals the total number of poles

### S-Plane
![[The Laplace Domain-1679708521896.jpeg]]

### Scaling
In practice, we are often interested in real circuits where the impedance and the frequency are much higher than convenient for arithmatic calculation

We can use magnitude and frequency scaling to convert from a circuit with convenient values to one with practical values.

If we have impedance factor $b$, and frequency factor $a$:

$$R^* = bR$$
$$L^* = \frac b a L$$
$$C^* = \frac 1 {ab} C$$

*Driving Point* Impedance Functions:
$$Z^*(s) = bZ(\frac s a)$$

*Voltage Transfer* Network Functions
$$G^*_{jk}(s) = G_{jk}(\frac s a)$$

This means the position of poles and zeroes are scaled by $a$.

### Linear Dependent Sources
![[The Laplace Domain-1679709450824.jpeg]]