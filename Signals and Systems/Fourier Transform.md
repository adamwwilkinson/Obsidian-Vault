Created: 21/09/2023 at 13:42

Fourier we have to understand the frequency domain (the electromagnetic spectrum) and the time domain (the time signal).

### From Fourier Series to Fourier Transform
#### Aperiodic Signals
Consider a periodic signal as the period gets larger and larger. As $T_0$ tends to infinity, the frequency $\omega_0$ tends to zero. The Fourier Series becomes a Fourier Transform.

$$x(t) = F^{-1} {X(j \omega)} = \frac {1}{2\pi}\int_{-\infty}^{\infty} X(j \omega) e^{j \omega t} d \omega$$
$$X(j \omega) = F {x(t)} = \int_{-\infty}^{\infty} x(t) e^{-j \omega t} dt$$

```ad-info
It can be noted that the inverse Fourier transform is almost the same as the Fourier transform, except for the sign of the exponent. This means its easy to find the inverse.
```

### Example
![[Fourier Transform-1695276138313.jpeg]]![[Fourier Transform-1695276189201.jpeg]]

```ad-info
For real signals, since the magnitude is an even function of $\omega$ we can state:
$$E_x = \frac 1 \pi \int_{0}^{\infty} |X(j \omega)|^2 d \omega$$

We can only do this if $X(j \omega)$ does not contain an impulse at $\omega = 0$.
```

### Example
![[Fourier Transform-1695276919888.jpeg]]

### Conjugation Property
$$x^\ast(t) \leftrightarrow X^\ast(-j \omega)$$
For practical signals we instead get the *conjugate symmetry* property:
$$X^\ast(j \omega) = X(-j \omega)$$

For this reason, for real signals, the magnitude spectrum is an even function of $\omega$ and the phase spectrum is an odd function of $\omega$.

### Transforms

```ad-info
If a signal is completely real in the time domain, then its Fourier transform is even in the frequency domain.

If a signal is completely imaginary in the time domain, then its Fourier transform is odd in the frequency domain.
```
![[Fourier Transform-1695277696880.jpeg]]

Impulse functions are needed to represent periodic signals with the Fourier transform.

### Properties
![[Fourier Transform-1695278123088.jpeg]]

> [!TIP] Duality
> Notice theres a 'duality' i.e. a time shift as well as a frequency shift. The reason this didn't occur in the Laplace domain was because the s domain didn't really mean anything, it was just a mathematical tool. While the frequency domain is a real thing.

### Exploring the Duality Property
Suppose we have
$$x(t) = \tau sinc (\frac{\tau t}{2})$$
![[Fourier Transform-1695279366239.jpeg]]

Sometimes it is easier to be in the frequency domain, sometimes it is easier to be in the time domain.
> [!info]
> Something spread out in the time domain, is usually narrow in the frequency domain, while something srepad out in the frequency domain, is usually narrow in the time domain.

### FT of the Unit Impulse
$$F[\delta(t)] = \int_{-\infty}^{\infty} \delta(t) e^{-j \omega t} dt = 1$$
![[Fourier Transform-1695279446114.jpeg]]
![[Fourier Transform-1695279466832.jpeg]]

### FT of a Complex Exponential / Sinusoid
Using the sifting property:
$$F^{-1}[\delta(\omega - \omega_0)] = \frac {1} {2\pi} \int_{-\infty}^{\infty} \delta(\omega - \omega_0) e^{j \omega t} d \omega = \frac {1} {2\pi} e^{j \omega_0 t}$$

$$F[e^{j \omega_0 t}] = 2\pi \delta(\omega - \omega_0)$$

Euler's relation tells us that $cos(\omega t) = \frac 1 2 (e^{j \omega t} + e^{-j \omega t})$ and $sin(\omega t) = \frac 1 {2j} (e^{j \omega t} - e^{-j \omega t})$.

$$F[cos(\omega_0 t)] = \pi [\delta(\omega - \omega_0) + \delta(\omega + \omega_0)]$$
![[Fourier Transform-1695279643302.jpeg]]

### FT of a Modulated Signal
In *communications systems* we are interested in the Fourier spectrum of the modulated signal:
$$y(t) = x(t) cos(\omega_c t)$$

where $\omega_c$ is the carrier frequency. By the multiplication property we have:
$$Y(j \omega) = \frac {1} {2\pi} X(j \omega) \ast \pi [\delta(\omega - \omega_c) + \delta(\omega + \omega_c)]$$

hence using the sifting property for convolution,
$$Y(j \omega) = \frac {1} {2} [X(j (\omega - \omega_c)) + X(j (\omega + \omega_c))]$$
![[Fourier Transform-1695280066605.jpeg]]

### Time-Bandwidth Product
Looking at the Fourier transform of a rectangular pulse with parameter $\tau$, it has a time duration of:
$$T_d = \tau$$

Most of the energy in the Fourier spectrum is concentrated over the interval $-2\pi/\tau, 2\pi/\tau$.
The double-sided bandwidth is:
$$B_{ds} = \frac {4\pi} {\tau}$$

The time-bandwidth product is:
$$T_d B_{ds} = 4\pi$$

> [!warning] Uncertainty Principle
> This constant result implies we cannot simultaneously decrease both the time duration and bandwidth of a signal. This is known as the *uncertainty principle* (can't have good time resolution and good frequency resolution).
> A short duration signal, will have a wide bandwidth and vice versa.

> [!info] What is Bandwith $B$?
> It is loosely defined as the major spectral content of a signal. It is the range of frequencies where the signal has most of its energy. It can be manifested as a *baseband bandwidth* (the main spectral content of the signal is around the zero frequency) or a *passband bandwidth* (the main spectral content of the signal is around a non-zero frequency).
> It can be expressed in either Hz (human friendly) or rad/s (math friendly). In EE systems when dealing with low-pass and band-pass systems we usually define the *bandwidth* as the frequency at which the response is 3dB down from the maximum value ($1/\sqrt{2}$).

### Data Truncation
How can we calculate the Fourier transform of a signal that runs for a finite time? We can't use the Fourier transform formula because it is an integral from $-\infty$ to $\infty$.

Instead we take a snapshot of the infinite function, and then we can use the Fourier transform formula.

![[Fourier Transform-1695892012407.jpeg]]

In the bottom right we can see we lose resolution in doing this, but not only that, we generate artifacts in the frequency domain. This is called *spectral leakage*.

Instead it is preferable to sacrfice the width of the main lobe and extending it to get rid of those artifects.

We can remedy this by using tapered window functions.
![[Fourier Transform-1695892145114.jpeg]]

### Example
![[Fourier Transform-1695892387100.jpeg]]![[Fourier Transform-1695892752506.jpeg]]
![[Fourier Transform-1695892800616.jpeg]]

### Filters
![[Fourier Transform-1695892828531.jpeg]]

### Short-time Fourier Transform and Spectrograms
The Fourier Transform provides information of the spectral composition of the signal. We define the energy spectral density (finite signals) and the power spectral density (infinite singals) as:
$$S_x(\omega) = |X(j \omega)|^2$$

A lot of practical signals have time varying spectral characteristics (music, speech) so what we want is to track the signal across time. Not only do we need a window function, but we need to shift the window function across time.

This gives us the *short-time Fourier transform*:
$$X(\tau, \omega) = \int_{-\infty}^{\infty} x(t) w(t - \tau) e^{-j \omega t} dt$$

where $w(t)$ is the window function. The window function is usually a *tapered window*.

And the *spectrogram*:
$$S_x(\tau, \omega) = |X(\tau, \omega)|^2$$
