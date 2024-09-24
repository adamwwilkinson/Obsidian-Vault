Created: 17/09/2024 at 20:29

A function $f(t)$ is called periodic with period $P$ is $f(t + P) = f(t)$ for all $t$. The smallest such $P$ is called the fundamental period. The function is called periodic if it has a fundamental period.

Instead of represeting these with the Taylor series, i.e. an infinite sum of polynoimials, we can represent them with a Fourier series, i.e. an infinite sum of sines and cosines.

$$a_0 + \sum_{n=1}^{\infty} a_n cos(nt) + b_n sin(nt)$$

where $a_0, a_n, b_n$ are the Fourier coefficients.

We call this the *Fourier series* of $f(t)$.

Calculating $a_0$ is very easy, utilising the fact the integral of a sine or cosine over a period is 0.

$$a_0 = \frac{1}{2\pi} \int_{-\pi}^{\pi} f(t) dt$$

And this is the average value of the function.

For the other coeffecients is slightly more involved,
$$a_k = \frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \cos(kt) dt$$

And similarly for $b_k$,
$$b_k = \frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \sin(kt) dt$$

### Periodic Extension
Simply represent the function as a periodic function, i.e. $f(t) = f(t + P)$, where $P$ is the period of the function. And putting a dot as a midpoint between potential jumps.

$$f(t) = e^{\frac t 5} \qquad \text{for} \qquad -\pi < t < \pi$$
![[Fourier Series-1726726254040.jpeg]]

### Even and Odd Functions
A function is called *even* if $f(t) = f(-t)$ and *odd* if $f(t) = -f(-t)$.

Eveness and oddness are refered as *parity*.

Multiplcation and addition:
$$EE = E \qquad EO = O \qquad OO = E \qquad OE = O$$

Differentiation and integration:
$$\text{Even} \rightarrow \text{Odd} \qquad \text{Odd} \rightarrow \text{Even}$$

### Half-Range Expansion
We can force a *parity* on the function by using the half-range expansion. If we have $(0, L)$, we an extend it to $(-L, 0)$ in two ways.

Even: $f(-t) = f(t)$, which leads to a *cosine* series.
Odd: $f(-t) = -f(t)$, which leads to a *sine* series.

If $f(t)$ is even, its Fourier series will have even terms only:

$$b_n = 0$$

Also: $a_0 = \frac{1}{L} \int_0^L f(t) dt$, $a_n = \frac{2}{L} \int_0^L f(t) \cos \left( \frac{n \pi t}{L} \right) dt$

Example: $f(t) = t^2$, $0 < t < 1$ with $f(-t) = f(t)$

$a_0 = \int_0^1 t^2 dt = \frac{1}{3}$, $a_n = 2 \int_0^1 t^2 \cos(n \pi t) dt = \cdots = \frac{4 (-1)^n}{\pi^2 n^2}$

If $f(t)$ is odd, its Fourier series will have odd terms only:
$$a_0 = 0 \qquad q_n = 0$$
