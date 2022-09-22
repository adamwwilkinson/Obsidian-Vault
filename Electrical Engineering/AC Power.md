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

Where $V_{avg} is the value that gives $P_{avg}$.

For sin or cos waves, $V_{RMS} = \frac {V} {\sqrt{2}}$.

In general:
$$V_{RMS} = \sqrt {\frac 1 T \int^T_0 v^2(t) \mathrm d t}$$
$$I_{RMS} = \sqrt {\frac 1 T \int^T_0 i^2(t) \mathrm d t}$$

```ad-warning
As the signal spends as much time above 0 as it does below, it gives the illusion that the signal carries zero net power.
$P(t) = \frac {v^2(t)} {R}$; power is proportional to the square of the voltage, which means the power is always above zero.
```

