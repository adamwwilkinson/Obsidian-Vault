Created: 16/10/2023 at 20:48

### Deriviation
Lets take a periodic discrete sequence but push $N_0$ further and further away from the origin.

As $N_0 \to \infty$, $\Omega_0 \to 0$. This implies the kth and the k+1th harmonic get closer and closer, and in the limit $X[k] \to X(e^{j \Omega})$. yielding a continious spectrum.

### Formula
$$x[n] = DTFT^{-1} {X(e^{j \Omega})} = \frac {1} {2 \pi} \int_{-\pi}^{\pi} X(e^{j \Omega}) e^{j \Omega n} d \Omega$$
$$X(e^{j \Omega}) = DTFT {x[n]} = \sum_{n=-\infty}^{\infty} x[n] e^{-j \Omega n}$$

Theres an integral here and thats becaude the spectrum is continious.

### Parseval's Theorem
$$E_x = \sum_{n=-\infty}^{\infty} |x[n]|^2 = \frac {1} {2 \pi} \int_{-\pi}^{\pi} |X(e^{j \Omega})|^2 d \Omega$$

### Properties
- continuous function of digital frequency $\Omega$
- periodic function of $\Omega$ with period $2 \pi$
- for real x[n] there is *conjugate symmetry* which implies:
the magnitude spectrum is an even function of $\Omega$ and the phase spectrum is an odd function of $\Omega$.
- for real the Fourier spectrum is uniquely defined for $0 < \Omega < \pi$

### Relationship with z-transform
$H(e^{j \Omega})$ is the z-transform evaluated on the unit circle and is the frequency response.

It is actually the DTFT of $h[n]$.

Deriving the DTFT from z-transform:
$$X(e^{j \Omega}) = X(z)|_{z = e^{j \Omega}}$$

### LTI System Response
Frequency Response, $X(e^{j \Omega})$
Let the input be $x[n]$, the impulse response be $h[n]$ and the output be $y[n]$.

$$y[n] = x[n] * h[n]$$

$$Y(e^{j \Omega}) = X(e^{j \Omega}) H(e^{j \Omega})$$
and the frequency response is
$$H(e^{j \Omega}) = \frac {Y(e^{j \Omega})} {X(e^{j \Omega})}$$
