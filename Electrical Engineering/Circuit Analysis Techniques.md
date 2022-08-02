# Circuit Analysis Techniques
Created: 02/08/2022 at 10:58
Tags:  #topic/physics 
Related: [[Fundamentals Of Electrical Engineering]]

### Why?
To evaluate the *current* and *voltages* required for appropriate behaviour.

### Evaluating Unknown Currents or Voltages
We can approach this by examining the circuit and represent it as an *effective resistance* ($R_{in}$).
#todo/excalidraw resistive

### Resistors in Series
For some resistors in series $R_1$ and $R_2$. The respective voltages $V_1$, $V_2$ sum up to the total voltage $V$.
While the **voltage is shared** the **current is constant**, which gives us the source voltage equation,
$$V = IR_1 + IR_2 = I(R_1 + R_2)$$

$$R_{eq} = \sum ^N_{t=1} R_1 + R_2 + R_3 ... R_N$$

#### Voltage Division
Finding the voltage consumed by each part in a resistive series.
$$I = \frac{V}{R_{in}} = \frac{V}{R_{1} + R_2}$$

$$V_1 = \frac{R_1}{R_1 + R_2}V$$
$$V_2 = \frac{R_2}{R_1 + R_2}V$$

### Resistors in Parallel
#todo/excalidraw parralel circuit
$$I = I_1 + I_2$$
$$I_1 = \frac{V}{R_1}, \mathrm{and} I_2 = \frac{V}{R_2}$$

Consequently, the source current is,
$$I = V(\frac{1}{R_1} + \frac{1}{R_2})$$