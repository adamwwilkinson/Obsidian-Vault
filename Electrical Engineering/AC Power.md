Created: 20/09/2022 at 12:01
Tags: #topic/electrical/powerinaccircuits 
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

## Complex Power
Defined as $S$ with the unit of Volt-Amperes, $VA$.

$$\bar S = \bar V \bar I^\ast \angle \phi$$

$$\bar S = \bar V_{RMS} \bar I_{RMS}^\ast$$
$$\bar S = \vert \bar I_{RMS} \vert ^2 \times \bar Z$$
$$\bar S = \frac {\vert \bar V_{RMS} \vert ^2} {\bar Z^\ast}$$

Where the \* is the conjugate.

$\bar S$ is the *complex* power. $VA$
$P$ is the *real/active/average* power. $W$
$Q$ is the *reactive* power(the imaginary part). $VAR$
$\vert \bar S \vert$ is the *apparent* power. $VA$

$$\bar S = P + jQ$$

```ad-info
$P$ can only be used by resistors and only $P$ does actual work so we want to maximise this for efficiency.

$Q$ can only be used by capacitors and inductors.
```

### Power Factor
$$PF = \frac P {\vert S \vert}$$

![[Power Triangle Drawing]]

#### Power Factor Correction
If the power factor is deemed to low, we can bring it closer to unity by adding capacitors or inductors.

### Maximum Power Transfer
For the dc equivalent look at [[Power in Resistive-only Circuits#Max Power in a Resistive Load Theorem]].

$$P = \frac {V_S^2 R_L} {(R_S +  R_L)^2}$$

Max power is reached when $X_L = -X_S$ and when $R_L = R_S$.

Therfore, max power is achieved when,
$$\bar Z_L = \bar Z_S^\ast$$
and,
$$P_max = \frac {V_S^2} {4R_S}$$

```ad-info
Notice how when the reactive part is zero, it's the same case as the dc equivalent.
```

### Impedance Matching
If we cannot change either the source or the load impedance, how do we maximise power transfer?

A intermediate circuit can be made but in order for it to not lose any power, we must use non-lossy elements only.

```ad-info
A lossy element is one deemed to consume power, such as resistors.
```
