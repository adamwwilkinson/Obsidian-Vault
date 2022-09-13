# Sinusoidal Sources
Created: 30/08/2022 at 10:59
Tags: #topic/electrical
Related: [[Energy Storage Circuit Elements]]

All the previous work done before were dc-circuits. Sinusoidal steady-state now says the voltage is time dependent, and in the shape of a sinusoidal wave.

### Harmonic Signals
A signal that can be represented as a sinusoid.
Can be mathematically defined as,
$$s(t) = A \sin (\omega t + \phi)$$
$\omega$ is angular frequency, or how fast the wave changes. Measured in radian/s. Given by $2\pi f$.
$f$ is the frequency and is measured in HZ. Given by $\frac 1 T$
$T$ is the period and is measured in seconds.
$\phi$ is the phase shift, how many radians along the wave starts. 
![[Harmonic Signals Drawing]]
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
$z^\ast = x - iy = re^{-i\theta}$

#### $i$?
Typically $i$ is used for imaginary numbers, but in electrical engineering we have $i$ denoting the current. So electrical engineers use $j$ for imaginary numbers.

### Phasor Representation of Circuit Elements
Phasor Analysis (complex form of the polar number) can only apply in the **sinusoidal steady-state**.
This type of analysis is useful because it makes simplifies adding and multiplying sine or cos terms.

Because the voltage and current aren't constant, we cant simply switch off *transients* [[Energy Storage Circuit Elements]].

#### The Phasor
A sinusoidal varying parameter can be given by,
$$v(t) = V_0\cos(\omega t + \phi)$$

Represented by the quantity,
$$V = V_0e^{j(\omega t + \phi)} = V_0 \cos(\omega t + \phi) + jV_0 \sin(\omega t + \phi)$$

With,
$$v(t) = \mathrm {Re} \{V\}$$

The **rotating phasor** is $V_0e^{j(\omega t + \phi)} = V_0e^{j\omega t} e^{j\phi}$

Ignoring the constant $e^{j\omega t}$ we have the **phasor**,
$$\bar V = V_0e^{j\phi}$$

#### Phasor Representation of Sources
As phase angle is relative, it is common practise to define the phase angle of one source to be zero.

The phasor voltge is a small vector.

##### Voltage Sources
$$\bar V = V_0 e^{j\phi}$$

##### Current Sources
$$\bar I = I_0 e^{j\phi}$$

#### Phasor Representation of Resistors
$$\bar V = \bar I R$$

The current-voltage relationship for a resistor remains unchanged.



#### Phasor Representation of Capacitor
$$\bar V = \bar I \frac 1 {j\omega C}$$

The value $\bar Z = \frac 1 {j\omega C}$ is called the impedency of the capacitor.

The current-voltage relationship for a capacitor is now akin to a resistance.

#### Phasor Representation of Inductor
$$\bar V = \bar I j\omega L$$

The value $\bar Z = j\omega L$ is called the impedency of the inductor.

The current-voltage relationship for an inductor is now akin to a resistance.

#### Phasor Representation Summarised
$$R: \bar V = \bar I * R = \bar I * Z_R$$
$$C: \bar V = \bar I * \frac 1 {j \omega C} = \bar I * Z_C$$
$$L: \bar V = \bar I * j \omega L = \bar I * Z_L$$

$Z$: impedance ($\Omega$)

#todo/excalidraw lec 13/sep 11:17 am
We can see the impedency of the resistor is always real.
While the impedency of the capacitor and inductor is always imaginary.

### Admittance
The inverse of the impedance is **admittance**.
Admittance has units of Mho ($\Mho$) or Siemens ($S$) and is given the phasor symbol $\bar Gamma$.

The rules in [[#phasor-representation-summarised]] is simple inverted for admittance.

### Problem Solving
Given an unknown component with an impedance of a real part and an imaginary part. We can split that up as an resistor in series with an inductor or capacitor whether the imaginary part is positive or negatie respectively.

### Phasor back to real
#todo lec 13/sep 11:35 Am

### Combining Impedance
#### Series
#todo like resistors

#### Parallel
#todo like resistors
