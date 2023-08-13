Created: 11/08/2023 at 20:45

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

### Transfer Function
Relates the input to the output of a system. It is the ratio of the output to the input in the Laplace domain.
$$H(S) = \frac{Y(s)}{X(s)} = L{h(t)}$$
where $Y(s)$ is the output and $X(s)$ is the input.
