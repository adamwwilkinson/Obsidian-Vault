# AC Power
Created: 20/09/2022 at 12:01
Tags: 
Related: [[Power in Resistive-only Circuits]]

Values for [[Fundamentals of Electrical Engineering#Voltage|voltage]] and [[Fundamentals of Electrical Engineering#Current|current]] is time dependent.

### Instantaneous, Peak, Average Power
#### Instantaneous Power
$$P(t) = v(t)i(t)$$

#### Peak Power
$$P_{pk}(t) = \frac {V^2} {R}$$

#### Root-mean-square
A measure of the average signal.
It is a single value and not a function of time.

$$P_{avg} = \frac {V^2} {2R}$$

$$V_{avg} = \frac {V} {\sqrt{2}}$$

Where $V_{avg}$ is the value that gives $P_{avg}$.

For sin or cos waves, $V_{RMS} = \frac {V} {\sqrt{2}}$.

In general:
$$V_{RMS} = \sqrt {\frac 1 T \int^T_0 v^2(t) \mathrm d t}$$
$$I_{RMS} = \sqrt {\frac 1 T \int^T_0 i^2(t) \mathrm d t}$$

```ad-warning
As the signal spends as much time above 0 as it does below, it gives the illusion that the signal carries zero net power.
$P(t) = \frac {v^2(t)} {R}$; power is proportional to the square of the voltage, which means the power is always above zero.
```
## Power in the AC Steady-State
$V_{rms} = \frac V {\sqrt 2}$
$I_{rms} = \frac I {\sqrt 2}$

$$v(t) = \sqrt 2 V_{rms} \cos(\omega t)$$
$$i(t) = \sqrt 2 I_{rms} \cos(\omega t - \phi)$$

$\phi$ here is the phase difference between the coltage and current signals within a circuit.

### Average Power Dissipated
$P_{avg} = \frac 1 T \int_0^T v(t)i(t) \mathrm d t$

$$ P_{avg} = V_{RMS}I_{RMS} \cos(\phi)$$

```ad-info
By using RMS values for voltage and current, we eliminate the scale factor of 0.5.
```

### Phasor Angle Rotation in Capacitors and Inductors
In a capacitor the phasor current leads the phasor voltage by $90\textdegree$.
In a inductor the phasor voltage leads the phasor current by $90 \textdegree$.

```ad-warning
It is always:

$$\phi = \phi_v - \phi_i$$
```
#todo 11:47 27/sep

## Complex Power
Defined as $S$ with the unit of Volt-Amperes, $VA$.

$$\bar S = \bar V \bar I^\ast \angle \phi$$

Where the \* is the conjugate.

$\bar S$ is the *complex* power. $VA$
$P$ is the *real/active/average* power. $W$
$Q$ is the *reactive* power(the imaginary part). $VAR$
$\vert \bar S \vert$ is the *apparent* power. $VA$

$$\bar S = P + jQ$$

#todo/excalidraw power triangle 12:31

