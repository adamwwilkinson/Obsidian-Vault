Created: 08/10/2023 at 10:40

### Analog to Digital Conversion
Most applications done automatically. As electrical engineers we need to know what is actually happening.

### Sampling
A signal whose spectrum is bandlimited to $B$ Hz can be reconstructed exactly from its sample taken uniformly at a rate of $f_s = 2B$ samples per second.

#### Proof
The process of sampling is taking a continous time signal, and multipling it by an impulse train.
![[Discrete-Time Fourier Analysis-1697122129004.jpeg]]
![[Discrete-Time Fourier Analysis-1697122183074.jpeg]]
![[Discrete-Time Fourier Analysis-1697122444310.jpeg]]![[Discrete-Time Fourier Analysis-1697122482927.jpeg]]

As $B$ increases the widths increase and eventually overlap. If they overlap we can no longer get back to 1 to 1.

### Example
![[Discrete-Time Fourier Analysis-1697122719058.jpeg]]

#### Why is this obvious?
The left is a sinc squared function. We know a sinc function in one domain gives a rectangle in the other domain, and multiplication in one domain is convolution in the other. This means the product of two sinc functions means 2 rectangles convoluted, whichi gives a triangle.
![[Discrete-Time Fourier Analysis-1697123876912.jpeg]]![[Discrete-Time Fourier Analysis-1697123893867.jpeg]]
![[Discrete-Time Fourier Analysis-1697123944684.jpeg]]

### Output End of a Digital/Analogue Converter
![[Discrete-Time Fourier Analysis-1697256975686.jpeg]]

This anti-imaging filter removes the duplicate images seen in the images above.

How do we take the digital numbers, into an analogue signal?

We need to oversample in order to do this. The more we oversample, the cheaper the lowpass filter and wider the gap, to allow the lowpass to slowly decay.

High sample rate, cheap low pass filter, lower sample rate, expensive low pass filter.

### Input Side
![[Discrete-Time Fourier Analysis-1697257277528.jpeg]]

#### What is the anti aliasing filter?
Aperiodic continous-time signals which are finite duration will usually posses an infinite duration spectrum. We can deal with this by cutting off the tail of the spectrum. However this leads to another issue.
![[Discrete-Time Fourier Analysis-1697257841242.jpeg]]

To fix this we can apply a lowpass filter to the signal before sampling. This is called an *anti-aliasing filter*.

```ad-info
With aliasing the actual analog signal we get upon reconstruction falls within the fundamental band $[-f_s/2,f_s/2]$. This will include any aliased componentes $f > f_s/2$ which get reflected back to the fundamental band from either positive or negative frequencies.
```

### Amplitude Sampling
#### Quantization
![[Discrete-Time Fourier Analysis-1697259282304.jpeg]]
Takes the sample and assign it to the closest horizontal bar on the left.

Lets say our signal oscilates between $-V, V$ and with $m$-bit quantisation we have $2^m$ levels.

Our delta is $2V/L$. Where $L$ is the number of levels.

#### Noise
The more bits used, the smaller the delta and the smaller the quantization error.

### ADC Example
#### Audio
Given a speech audio signal bandwidth of at least 3400 Hz, the filter will haev a sharp but realiable attenuation if $f_s$ is 8000 Hz. So that there is sufficient attenuation by $f_s/2 = 4000 Hz$ to avoid aliasing. For speech an 8bit quantisation is sufficient.

#### Music ADC
High fidelity music audio signals have a bandwidth of 20 kHz. So we need a sampling rate of at least 40 kHz. For CDs the standard sampling rate is 44.1kHz. A higher number of bits is required and a 16bit (l =65536) quantisation is mandated.

### Spectral Sampling
We sample the frequency to get replicas in time.
![[Discrete-Time Fourier Analysis-1697331003408.jpeg]]

Sampling in one domain implies periodicity / replicas in the other domin.

### Discrete Fourier Transform and the FFT
First thing we do is sample the time domain. Then we have replicas in the frequency domain. Sampling this gives us replicas in the time domain.
![[Discrete-Time Fourier Analysis-1697331244271.jpeg]]
$$N_0 = \frac {T_0} {T}$$
$$N'_0 = \frac {f_s} {f_0}$$

$$N_0 = N'_0$$

This means we can increase the frequency resolution $N'_0$ by increasing $T_0$, but the time resolution suffers.

#### Discrete Fourier Transform Pair
$$X[k] = \sum_{n=0}^{N-1} x[n] e^{-j k \Omega_0 n} \leftrightarrow x[n] = \frac {1} {N} \sum_{k=0}^{N-1} X[k] e^{j k \Omega_0 n}$$
where $\Omega_0 = \frac {2 \pi} {N}$

#### Zero Padding
Adding zeros to the end of the signal. This increases the number of samples, but doesn't change the signal. This increases the frequency resolution, but doesn't change the frequency content.

#### Fast Fourier Transform (FFT)
The calculation of DFT requires $O(N^2)$ operations. The FFT algorithm reduces this to $O(N \log N)$ operations.

### Discrete Time Fourier Series
What is a discrete frequency?
$$F = \frac {T} {T_0} = \frac {f} {f_s}$$

The spectral representation of any system must be spectrally between 0 and $f_s/2$.
Digital frequency always goes to zero to a half.

#### Formula
$$x[n] = DTFS^{-1} {X[k]} = \sum_{k=N_0} X[k] e^{j k \Omega_0 n}$$
$$X[k] = DTFS {x[n]} = \frac {1} {N_0} \sum_{n=N_0} x[n] e^{-j k \Omega_0 n}$$
where $\Omega_0 = \frac {2 \pi} {N_0}$
![[Discrete-Time Fourier Analysis-1697383854008.jpeg]]

#### Parseval's Theorem
For the DTFS representation the theorem states the power can be expressed directly from the DTFS.
$$P_x = \frac {1} {N_0} \sum_{n=0}^{N_0 - 1} |x[n]|^2 = \sum_{k=0}^{N_0 - 1} |X[k]|^2$$

### Important Geometric Sum Formula
$$\sum_{n = k}^{l} \beta^n = \quad \frac {\beta^k - \beta^{l+1}} {1 - \beta} \quad \text{for} \quad \beta \neq 1$$

$$\sum_{n = k}^{l} \beta^n = \quad (l - k + 1) \quad \text{for} \quad \beta = 1$$

### Example
![[Discrete-Time Fourier Analysis-1697459191786.jpeg]]

$$N_0 = 32$$
$$\Omega_0 = \frac {2 \pi} {N_0} = \frac {2 \pi} {32} = \frac {\pi} {16}$$
Therefore,
$$x[n] = \sum_{r=32}D_r e^{j \frac {\pi} {16} r n}$$
Where,
$$D_r = \frac {1} {32} \sum_{n=32} x[n] e^{-j \frac {\pi} {16} r n}$$

Choosing the interval of -16 to 15, although any other interval of same width would give the same result.

$$D_r = \frac {1} {32} \sum_{n=-16}^{15} x[n] e^{-j \frac {\pi} {16} r n}$$
As $x[n] = 1$ for -4 to 4, and zero elsewhere.
$$D_r = \frac {1} {32} \sum_{n=-4}^{4} e^{-j \frac {\pi} {16} r n}$$

This is a geometric progression with common ratio $e^{-j \frac {\pi} {16} r}$ and $k = -4$ and $l = 4$.

![[Discrete-Time Fourier Analysis-1697459576067.jpeg]]

### Transform Table
![[Discrete-Time Fourier Analysis-1697459872160.jpeg]]