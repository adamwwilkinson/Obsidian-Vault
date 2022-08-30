# The Sinusoidal Steady State
Created: 30/08/2022 at 10:59
Tags: #topic/physics 
Related: [[Energy Storage Circuit Elements]]

All the previous work done before were dc-circuits. Sinusoidal steady-state now says the voltage is time dependent, and in the shape of a sinusoidal wave.
#todo/excalidraw DC and AC

### Sinusoidal Sources #todo make Title? Make current title topic?

### Harmonic Signals
A signal that can be represented as a sinusoid.
Can be mathematically defined as,
$$s(t) = A \sin (\omega t + \phi)$$
$\omega$ is angular frequency, or how fast the wave changes. Measured in radian/s. Given by $2\pi f$.
$f$ is the frequency and is measured in HZ. Given by $\frac 1 T$
$T$ is the period and is measured in seconds.
$\phi$ is the phase shift. #todo 
#todo/excalidraw

### RMS
Root Mean Square, or the effective value of a signal.
$A = \sqrt 2 A_{rms}$
```ad-info
Only true for sinusoidal waves.
```

### Important Relationships
#### Sine-cosine Relationships
$$A \cos(\omega t) = A \sin(\omega t + \frac \pi 2)$$

#### Derivatives
Just know the derivatives bro it aint that hard.

### Phase Lead and Lag
We can say that the phase of the cosine leads the sine by $\frac \pi 2$, or we can say sine lags behind by $\frac \pi 2$.
We usually say the signal that hits it's peak first is the one leading.

### Complex Numbers
The number that solves the equation $i^2 = -1$ is an imaginary number called $i$.
This allows us to solve complex equations with no traditional solution.

#### Argand Plane
A plane where the vertical axis is the imaginary part of the number, and the horizontal axis is the real part of a number.
This gives us a cartesian representation, $z = x + iy$ or $(x, y)$.
We can also represent it with a polar format $(r, \theta)$. With $x = r \cos \theta, \ y = r \sin \theta$.
This is also equivalent to the exponential form $z = r e^{i \theta}$.

$\mathrm {cis} = \angle$

#### Operations
$$z_1 \pm z_2 = (x_1 + iy_1) \pm (x_2 + iy_2) = (x_1 + x_2) \pm i(y_1 + y_2)$$

$$z_1 \times z_2 = (x_1 + iy_1) \times (x_2 + iy_2) = (x_1x_2 - y_1y_2) + i(x_2y_1 + x_1y_2) = r_1r_2e^{i(\theta_1 + \theta_2)}$$

$$\frac {z_1} {z_2} = \frac {r_1} {r_2} e^{i(\theta_1 - \theta_2)}$$

##### Division in Cartesian Form
Multiply the denominator and the numerator by the complex conjugate of the denominator.

#### The Complex Conjugate
$z = x + iy = re^{i\theta}$
$z^* = x - iy = re^{-i\theta}$

#### $i$?
Typically $i$ is used for imaginary numbers, but in electrical engineering we have $i$ denoting the current. So electrical engineers use $j$ for imaginary numbers.
