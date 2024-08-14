Created: 02/08/2023 at 09:21

## Types of System
A system is a blackbox input-output network, or system equation relating the input with the output.
There are *single-input single-output* (SISO) systems, *multi-input multi-output* (MIMO) systems, and *multi-input single-output* (MISO) systems.

There are *continuous-time* systems, and *discrete-time* systems.

### Memoryless Systems
A system is *memoryless* if the output at any time depends only on the input at the same time.

### Causal and Noncausal Systems
A system is *causal* if the output at any time depends only on the input at the same time or earlier.
$$y(t) = \frac 1 C \int_{-\infty}^t x(\tau) d\tau$$
or
$$y[n] = x[n] + 3x[n-2]$$

A system is *noncausal* if the output at any time depends on the input at the same time or later.
$$y(t) = \int_{t}^\infty x(\tau) d\tau$$
or
$$y[n] = x[n+1] - 3x[n + 2]$$

In the physical world, all systems are causal.

### Time-variant or Time-Varying and LTI System
It does not matter when the input is applied to a *time-invariant* system, the output will always be the same.

If a system is both *linear*, and *time-invariant*. it is called a **linear time-invariant** (LTI) system.

### Stable and Unstable Systems
If for any bounded input, the output is also bounded, the system is *stable*.

Practical systems whch can be *realised* and *operated* must be causal and stable.
