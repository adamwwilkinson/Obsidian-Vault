# Power in Resistive-only Circuits
Created: 20/09/2022 at 11:09
Tags: 
Related:

### Power (Again)
$$P = vi + Q \frac {\mathrm d v} {\mathrm d t}$$
Made up of the electrodynamic term, and the electrostatic term respectively.

Ignoring the static term, which we can only do for [[DC]] circuits and [[Resistors]]:
$$P = vi$$


### Power in a Resistor (dissapation)
$$P = i^2R$$
$$P = \frac {v^2} {R}$$

### Max Power in a Resistive Load Theorem
#todo excalidraw 20 sep 11:26
$$P_L = i^2R_L = \frac {R_L} {(R_S + R_L)^2}v_S^2$$

#### Finding the Max Power
From the first derivitive:
$$R_L = R_S$$

Max power given to the load:
$$P_{\mathrm {max}} = \frac {v_S^2} {4R_S}$$

Also is the power lost in the source resistanc:
$$P_{\mathrm {max}} = \frac {v_S^2} {4R_S}$$

```ad-info
A maximum of half the source power will be delivered to the load.
```

#### Applications
This is a very ineffecient way of delivering power to appliances.
Acceptable for very small power levels, but for larger one, efficiency is prioritised over max power.
