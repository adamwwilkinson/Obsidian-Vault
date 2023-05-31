Created: 30/05/2023 at 11:33

### Cons of Single Ended Amplifier
The disadvantages of a single ended/stage transistor amplifier are:
- bias and gain sensitive
- vulnerable to noise
- may exhibit common mode drift that gets amplified
![[Differential Amplifier-1685428359202.jpeg]]

### Differential Amplifier
It addresses the above concerns by representing the input as a difference between two signals, and amplifying the difference, rejecting the common mode signal.

![[Differential Amplifier-1685428345842.jpeg]]

### Basic Differential Pair
Made by using two transistors, with same parameters. Connecting these two sources together, and biasing with a current source.
![[Differential Amplifier-1685428538079.jpeg]]

Assume $M_1$ and $M_2$ are always in saturation.

#### Qualitative Analysis
![[Differential Amplifier-1685428790256.jpeg]]
Assuming $v_{GS1} = v_{GS2}$, and $v_{DS1} = v_{DS2}$, then $i_{DS1} = i_{DS2}$.

Assuming $V_{in1}$ is more negative than $V_{in2}$, then $M_1$ will be off and $M_2$ will be on. This means $i_{DS1} = 0$ and $i_{DS2} = I_{DS}$.

As $V_{in1}$ increases, $M_1$ gradually turns on, and draws a fraction of $I_{SS}$ lowering $V_{out1}$.

Eventually $M_1$ will be on, and $M_2$ will be off. This means $i_{DS1} = I_{DS}$ and $i_{DS2} = 0$.

The gain is most extreme when $V_{in1} = V_{in2}$.

### Common Mode Gain
We are interested in the common mode gain to be zero, and the differential mode gain to be high.

#### Common Mode Rejection Ratio
The common mode rejection ratio is the ratio of the differential gain to the common mode gain.
$$CMRR = \frac{A_{vD}}{A_{vC}}$$

In single ended it is,
$$CMRR = \frac{A_{DM}}{A_{CM}}$$

And in differential it is,
$$CMRR = \frac{A_{DM}}{A_{CM-DM}}$$

In both cases we want it as large as possible.
