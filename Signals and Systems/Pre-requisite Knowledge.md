Created: 26/07/2023 at 08:58

### Systems
![[Pre-requisite Knowledge-1690333326620.jpeg]]

Here, $x$ and $y$ are the input and output **signals**. For analogue electrical systems that will either be *voltages across* or *currents through* an element (output $y(t)$) and *voltage or curret sources* the excitation source (input $x(t)$) at time $t$.

For digital circuits there are *data samples* (16 bit words) which are presented as the input the system, $x[n]$, or as output $y[n]$ at sample time $n$.

#### Analogue Systems
![[Pre-requisite Knowledge-1690333658777.jpeg]]

#### Digital Systems
![[Pre-requisite Knowledge-1690333676437.jpeg]]

Consist of memory elements (*latches, flip-flops or registers*), numerical multipliers and adders

### Laplace Transform
Used to facilitate the analysis and design of analogue systems, also known as *continious-time systems*.

From the transfer function $H(s)$ we can determine whether the system is causal and stable and from that how to design such systems.

### Z Transform
Used to facilitate the analysis and defisn of digital systems, also known as *discrete-time systems*.

From the transfer function $H(z)$ we can determine whether the system is causal and stable and from that how to design such systems.

### Digital Signal Processing (Fourier Analysis)
The Fourier transform is a mathematical transform which allows almost ubiquitous transform between the time-domain representation of a signal and its spectral profile (*frequency-domain representation*).

There are four types of Fourier transform:
- Fourier Series
- Discrete Fourier Transform (DFT)
- Discrete Time Fourier Series (DTFT)
- Discrete Time Fourier Transform (DTFT)

### Complex Numbers
$$J^2 = -1$$

#### Euler's Formula
$$e^{j\theta} = \cos(\theta) + j\sin(\theta)$$
which leads to,
$$2 \cos(\theta) = e^{j\theta} + e^{-j\theta}$$
$$2j \sin(\theta) = e^{j\theta} - e^{-j\theta}$$

### Periodic Signals
A signal is deemed to be periodic if
$$x(t) = x(t \pm nT_0)$$
where $T$ is the period of the signal.
![[Pre-requisite Knowledge-1690343458621.jpeg]]

If the discrete signal arises from sampling of an analogue signal,
$$F_0 = \frac{f_0}{f_s}$$
$$N_0 = \frac{T_0}{T_s}$$
where $f_0$ is the frequency of the analogue signal, $f_s$ is the sampling frequency, $T_0$ is the period of the analogue signal and $T_s$ is the sampling period.

### Even and Odd Signals
Signals symetric about the $y$-axis are called *even* signals and those symetric about the $x$-axis are called *odd* signals.

### Signal Operations
#### Shifting
Translating the signal left and right is called shifting it.
![[Pre-requisite Knowledge-1690345111184.jpeg]]

#### Scaling
Scaling the signal is called stretching or compressing it.

#### Time Reversal
Flipping the signal about the $y$-axis is called time reversal.
![[Pre-requisite Knowledge-1690345216729.jpeg]]

#### Combinations
When combining signals, the operations are applied in the following order:
- Shifting
- Scaling
- Time Reversal

#### Convolution
![[Pre-requisite Knowledge-1690345457810.jpeg]]

This will be looked at further later.

### Periodic Sampling
For a digital sample to be periodic, typically it will have a $\pi$ in its equation describing it. Formally, for discrete signals the sinusoid is a periodic function of $n$ only for certain values of $\Omega$, where
$$\Omega = 2\pi \frac{m}{N_0} = 2\pi F$$
$N_0$ is the fundamental period. The $m$ says how many sinusoidal periods are required for the signal to repeat.

### Sinc Funtions
Given by either:
$$\text{sinc}(t) = \frac{\sin(\pi t)}{\pi t}$$
This is called normalised, it has zero crossings at $t = 0, \pm 1, \pm 2, \dots$ and a maximum at $t = 0$.
or
$$\text{sinc}(x) = \frac{\sin(t)}{t}$$
unnormalised, it has zero crossings at $t = 0, \pm \pi, \pm 2\pi, \dots$ and a maximum at $t = 0$.

![[Pre-requisite Knowledge-1690345869587.jpeg]]

### Rectangular Pulse and Square Wave
A rectangular pulse of finite-duration.

### Unit Impulse Funtion
At 0 it has a value tending towards infinity, and at all other points it has a value of 0.
![[Pre-requisite Knowledge-1690346129545.jpeg]]

It has an important property called the *sifting property*:
$$\int_{-\infty}^{\infty} \delta(t - t_0) x(t) dt = x(t_0)$$

#### Discrete
For discrete-time signals, the unit impulse function is defined as:
$$\delta[n] = \begin{cases} 1 & n = 0 \\ 0 & n \neq 0 \end{cases}$$

The *sifting property* here is,
$$\sum_{n = -\infty}^{\infty} \delta[n - n_0] x[n] = x[n_0]$$
