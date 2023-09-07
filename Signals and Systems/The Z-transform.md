Created: 19/08/2023 at 09:32

For a general discrete-time signal $x[n]$, the Z-transform is defined as:
$$X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}$$
![[The Z-transform-1692409060986.jpeg]]
```ad-info
Positive powers of $z$ are associated with -ve time, while -ve powers are associated with +ve time.
```

### ROC
The region of convergence is the set of values of $z$ for which the Z-transform converges. The ROC is a ring in the complex plane.
![[The Z-transform-1692409542943.jpeg]]![[The Z-transform-1692409555785.jpeg]]

As digital signals aren't real world, they can be a mix of anti causal and causal signals. The ROC is the region of convergence of the causal part of the signal.
![[The Z-transform-1692409360398.jpeg]]

### Poles and Zeros
When looking at systems, we will have a very well-defined structure, polynomials on both the numerator and denominator but instead of Laplace's $s$ being positive, in the $z$ transform it will have negative exponents
![[The Z-transform-1693653866118.jpeg]]
![[The Z-transform-1693654087333.jpeg]]
In the majority of applications where $N > M$ because of the $z^{N-M}$ term, there will be $N - M$ zeros at the origin. Conversely where $M > N$ we will have $M - N$ poles at the origin.

### Z Transform of Common Signals
![[The Z-transform-1693703071809.jpeg]]
### Properties of the $z$-transform
![[The Z-transform-1693703108628.jpeg]]

#### Time Shift
A *delay* by $k$ applies as a negative exponent, while an *advance* by $k$ is a positive exponent.

### Finding the Inverse
![[The Z-transform-1693703466223.jpeg]]
![[The Z-transform-1693703555832.jpeg]]

#### Power Series Expansion
![[The Z-transform-1693703624756.jpeg]]

### The Transfer Function
$$y[n] = H(z) z^n$$
that is, the ouput is equal to the transfer function times $z^n$.

This is only useful for looking for the frequency response.

The zero-state response is given by,
$$y[n] = x[n] * h[n]$$
applying the convolution property we get,
$$Y(z) = X(z)H(z)$$
where $X(z)$ is the Z-transform of the input signal, and $H(z)$ is the Z-transform of the impulse response.

The transfer function relates the output $Y(z)$ to the input $X(z)$, in the $z$-domain as:
$$H(z) = \frac{Y(z)}{X(z)}$$

#### Example 1
![[The Z-transform-1693704872385.jpeg]]

#### Example 2
![[The Z-transform-1693704992639.jpeg]]
![[The Z-transform-1693705012738.jpeg]]

### Causality and Stability
If the region of convergence of $H(z)$ is the exterior of the circle, it is causal.

If the ROC of $H(z)$ contains the unit circle, it is BIBO stable.

For a system to be both causal and stable all poles of $H(z)$ must lie within the unit circle $|d_k| < 1$.

### Combining Transfer Functions
Similar to resistors, we can combine transfer functions in series and parallel.

Parallel connected transfer functions are added together, while series connected transfer functions are multiplied together.

### Invertible
To be invertible both the poles and zeros must be within the unit circle.

### Frequency Response
From the equation before, $y[n] = H(z) z^n$, if we let $z = e^{j\omega}$, we get $y[n] = H(e^{j\omega}) e^{j\omega n}$.

$e^{j\omega}$ is values on the unit circle. Where in the [[Laplace Transform]] we had the frequency response on the $j \omega$ axis, here we have it on the unit circle.

The **magnitude response** is given by,
$$|H(e^{j\omega})|$$
while the **phase response** is given by,
$$\angle H(e^{j\omega})$$

### Minimum Phase Systems
For a causal and stable system all that is required is for the poles to lie within the unit circle, the zeros can lie anywhere, however it can be shown that zeros within the unit circle and minimise the phase response.
