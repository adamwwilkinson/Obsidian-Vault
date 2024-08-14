Created: 11/08/2023 at 20:45

### Info
The Laplace transform supercedes what has been learnt in the previous notes. The transfer function can be derived from the differential equations, and the transfer function gives the Laplace transform of the impulse response system.

### Region of Convergence (ROC)
The region of convergence is the set of values of $s$ for which the Laplace transform converges. The ROC is a strip or annulus in the $s$-plane. The ROC is always a right half-plane, a left half-plane, or an annulus. The ROC is always a connected region.

![[Laplace Transform-1691758119835.jpeg]]

$\sigma$ is the real part of $s$. And the region of convergence is the values of s where $Re(s) > -a$.

The region of convergence can determine whether the inverse laplace regards negative time or positive time.

### Poles and Zeroes
In engineering applications $X(s)$ can be expressed in the following polynomial form:
$$X(s) = \frac{\sum_{k=0}^{M} b_k s^k}{\sum_{k=0}^{N} a_k s^k} = \frac{b_0 + b_1 s + b_2 s^2 + \dots + b_M s^M}{a_0 + a_1 s + a_2 s^2 + \dots + a_N s^N}$$
where $M$ and $N$ are the degrees of the numerator and denominator polynomials, respectively. The roots of the denominator polynomial are called the poles of $X(s)$, and the roots of the numerator polynomial are called the zeroes of $X(s)$.

For notation, if there is a zero at the bottom, it is a pole and is marked by a cross, and if there is a zero at the top, it is a zero and is marked by a circle.

### Properties of the ROC
![[Laplace Transform-1691758708601.jpeg]]

### Properties of the Laplace Transform
![[Laplace Transform-1691758967981.jpeg]]

### Common Pairings
![[Laplace Transform-1691759074795.jpeg]]

### Partial Fraction Expansion
For finding the inverse laplace transform, we can use partial fraction expansion. This is where we take the laplace transform and break it up into smaller pieces that we can find in a table.

This can be done using the *method of residues*.

There are three cases for partial fraction expansion:
1. Distinct real poles (most common)
2. Repeated real poles (tedious and not in exams or tests)
3. Complex poles (won't look into)

#### Method of Residues
Take $X(s) = \frac{-6s + 1}{s^2 + 3s + 2}$ as an example.
$$X(s) = \frac{-6s + 1}{s^2 + 3s + 2} = \frac{-6s + 1}{(s+1)(s+2)}$$
where,
$$A_1 = (s + 1)X(s) \Big|_{s = -1} = \frac{-6s + 1}{s + 2} \Big|_{s = -1} = \frac{7}{1} = 7$$
$$A_2 = (s + 2)X(s) \Big|_{s = -2} = \frac{-6s + 1}{s + 1} \Big|_{s = -2} = \frac{13}{-1} = -13$$
Hence,
$$X(s) = \frac{7}{s + 1} + \frac{13}{s + 2}$$

THis can now be used to find the inverse laplace transform.
$$x(t) = (7e^{-t} + 13e^{-2t})u(t)$$

### Zero-State Response
The zero-state response is given by
$$y(t) = x(t) * h(t)$$
where $x(t)$ is the input and $h(t)$ is the impulse response.

### Transfer Function
Relates the input to the output of a system. It is the ratio of the output to the input in the Laplace domain.
$$H(S) = \frac{Y(s)}{X(s)} = L{h(t)}$$
where $Y(s)$ is the output and $X(s)$ is the input.

$$y(t) = H(s)e^{st}$$
![[Laplace Transform-1692239723960.jpeg]]

#### Causality and Stability in LTI Systems from $H(s)$
A system is causal if the ROC of $H(s)$ is the region of the s-plane to the right of all system poles.

A system is stable if the ROC of $H(s)$ includes the $j\omega$-axis.

For all $M \leq N$ all poles of H(s) must lie in the left half of the s-plane. If $M > N$ then the system is BIBO unstable.

### Invertible Systems and Deconvolution
If x(t) is transformed to y(t), if we can apply y(t) to a system to be transformed back to x(t), then the system is invertible.

This is difficult to find and do but is trivial in the s-domain.

$$H(s) H^{\text{inv}} = 1$$
$$H^{\text{inv}} = \frac{1}{H(s)}$$

For the system to be invertible, the zeros have to be in the left hand plane, because they become poles when inverted.

### System Responses
#### Step Response
The step response is the response of a system to a unit step input. It is the inverse laplace transform of the transfer function.
$$s(t) = L^{-1} \{\frac{H(s)}{s}\}$$

#### Frequency  Response
From earlier, $y(t) = H(s)e^{st}$. We can expand this using Euler's formula to get
$$y(t) = H(\pm j\omega)e^{\pm j\omega t}$$
where $\omega$ is the frequency of the input.

![[Laplace Transform-1692241961895.jpeg]]

$$y(t) = |H(j\omega)|\cos(\omega t + \angle H(j\omega))$$
where $|H(j\omega)|$ is the magnitude response and $\angle H(j\omega)$ is the phase response.
![[Laplace Transform-1692243257328.jpeg]]

### Minimum Phase Systems
Systems that have zeros and poles in the left hand plane. This means they are causal, stable and invertible. They also have a minimum or zero phase response, i.e. they respond more quickly.

### Unilateral Laplace Transform
Changing the limits of integration to $0$ to $\infty$, allows us to include the initial conditions in the transform. This is called the unilateral Laplace transform.

#### Example
![[Laplace Transform-1692248199565.jpeg]]
![[Laplace Transform-1692248235044.jpeg]]
![[Laplace Transform-1692248287414.jpeg]]
![[Laplace Transform-1692248380933.jpeg]]