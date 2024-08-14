Created: 03/09/2023 at 10:17

### Fourier Representation of Four Classes of Signals
#### Fourier Series
- Periodic analog signals (synthesis, harmonies)

#### Fourier Transform
- Aperiodic analog signals (theory, investigating efficiency...)

#### Discrete-Time Fourier Series
- Periodic digital signals

#### Discrete-Time Fourier Transform
- Aperiodic digital signals

### Transforming from Continuous to Discrete
![[Fourier Analysis-1693707752684.jpeg]]

### The Fourier Series
Any periodic signal $x(t) with period $T_0$ can be represented as a sum of sinusoid of fundamental frequency $f_0 = \frac {1} {T_0}$ and its harmonics $\omega_0 = \frac {2 \pi}{T_0}$.

#### Compact Trigonometric Fourier Series
$$x(t) = C[0] + \sum_{k=1}^{\infty} C[k] \cos (k \omega_0 t) + \theta[k])$$
Here the $C[k]$ repredents the amplitude of the k-th harmonic and $\theta[k]$ the phase shift.

#### Trigonometric Fourier Series
$$x(t) = A[0] + \sum_{k=1}^{\infty} A[k] \cos (k \omega_0 t) + B[k] \sin (k \omega_0 t)$$

$A[0]$ is $\frac {1} {T_0} \int_{t_0} x(t) dt$
$A[k]$ is $\frac {2} {T_0} \int_{t_0} x(t) \cos (k \omega_0 t) dt$
$B[k]$ is $\frac {2} {T_0} \int_{t_0} x(t) \sin (k \omega_0 t) dt$

```ad-info
As we can choose which range, we can decide how difficult the calculations are.
```

##### Example
![[Fourier Analysis-1694913952945.jpeg]]
![[Fourier Analysis-1694913971664.jpeg]]
![[Fourier Analysis-1694913984033.jpeg]]

#### Exponential Fourier Series
$$x(t) = FS^{-1} {X[k]} = \sum_{k=-\infty}^{\infty} X[k] e^{j k \omega_0 t}$$
$$X[k] = FS {x(t)} = \frac {1} {T_0} \int_{t_0} x(t) e^{-j k \omega_0 t} dt$$

##### Conversion between Trigonometric and Exponential Fourier Series
For $k = 0$ (DC component)  we have $A[0] = C[0] = X[0]$ and $B[0] = \theta[0] = 0$.
For $k > 0$:
$$A[k] = X[k] + X[-k]$$
$$B[k] = j (X[k] - X[-k])$$
hence:
$$C[k] = 2 |X[k]|$$
$$\theta[k] = \angle X[k]$$

#### Fourier Series of a Square Wave Periodic Signal
![[Fourier Analysis-1694919570113.jpeg]]

The lower frequencies affects the long-scale behaviour of the signal, while the higher frequencies affects the short-scale behaviour of the signal.

The high frequencies affect the fine structure (discontinuities, sharp edges or fluctuations) of the signal.

### Sharp Signals vs Smooth Signals
Signals with short punchy sharp edges have many frequency components, while a long rectangular signal would have less frequency components.

But short punchy signals use less power rather than smooth signals.

### Gibbs Phenomenon
With increasing $N$ the frequency of oscillation at a discontinuity is $N f_0$ and its width is $0.5 / N f_0$. The oesciallations do not die out with increasing $N$ and instead increase in frequency and become smaller in width.

This can be dealth with by redesigning the wave form such that the discontinuity instead becomes a sharp transition over a small width.

### Even and Odd Signals
#### Even
$x(t) = x(-t)$ then the FS consists of only cosine terms ($B[k] = 0$).

Exponential FS satisfies $X[k] = X[-k]$, for real signals this imples $X[k] = X^*[k]$. which means that the FS consists of only real terms and $\angle K[k] = 0$.

#### Odd
$x(t) = -x(-t)$ then the FS consists of only sine terms ($A[k] = 0$).

Exponential FS satisfies $X[k] = -X[-k]$, for real signals this implies $X[k] = -X^*[k]$. which means that the FS consists of only imaginary terms and $\angle K[k] = \pm \frac {\pi} {2}$.

### Reading From Graph to work out Fourier Series
#### Compact Trigonometric
![[Fourier Analysis-1694920427848.jpeg]]
![[Fourier Analysis-1694920437925.jpeg]]

#### Exponential
 ![[Fourier Analysis-1694920539951.jpeg]]

$$X[k] = |X[k]| e^{j[X[k]]}$$
![[Fourier Analysis-1694920697093.jpeg]]

### LTI Response to Periodic Inputs
For an LTI system we know the reponse to the system for input $x(t) = e^{j \omega_0 t}$ is $y(t) = H(j \omega_0) e^{j \omega_0 t}$.

If the LTI system is excited by a periodic signal with FS representation:
$$x(t) = \sum_{k=-\infty}^{\infty} X[k] e^{j k \omega_0 t}$$

Then from the linearity property and noting $\omega = k \omega_0$:
$$y(t) = \sum_{k=-\infty}^{\infty} X[k] H(j k \omega_0) e^{j k \omega_0 t}$$
