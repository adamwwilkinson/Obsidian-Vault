# Circuit Analysis Techniques
Created: 02/08/2022 at 10:58
Tags:  #topic/physics 
Related: [[Fundamentals Of Electrical Engineering]], [[Kirchhoff's Laws]], [[Systematic Approaches]]

### Why?
To evaluate the *current* and *voltages* required for appropriate behaviour.

### Evaluating Unknown Currents or Voltages
We can approach this by examining the circuit and represent it as an *effective resistance* ($R_{in}$).
#todo/excalidraw resistive

### Resistors in [[Kirchhoff's Laws#Parallel or Series|Series]]
For some resistors in series $R_1$ and $R_2$. The respective voltages $V_1$, $V_2$ sum up to the total voltage $V$.
While the **voltage is shared** the **current is constant**, which gives us the source voltage equation,
$$V = IR_1 + IR_2 = I(R_1 + R_2)$$

$$R_{eq} = \sum ^N_{t=1} R_1 + R_2 + R_3 ... R_N$$

#### Voltage Division
Finding the voltage consumed by each part in a resistive series.
$$I = \frac{V}{R_{in}} = \frac{V}{R_{1} + R_2}$$

$$V_1 = \frac{R_1}{R_1 + R_2}V$$
$$V_2 = \frac{R_2}{R_1 + R_2}V$$

### Resistors in [[Kirchhoff's Laws#Parallel or Series|Parallel]]
#todo/excalidraw parralel circuit
$$I = I_1 + I_2$$
$$I_1 = \frac{V}{R_1}, \; \mathrm{and} \; I_2 = \frac{V}{R_2}$$
$$R_{in} = \frac{R_1R_2}{R_1 + R_2}$$

Consequently, the source current is,
$$I = V(\frac{1}{R_1} + \frac{1}{R_2})$$

#### Current Division
$$V = IR_{in} = I\frac{R_1R_2}{R_1 + R_2}$$
$$I_1 = \frac{V}{R_1} = \frac{I\frac{R_1R_2}{R_1 + R_2}}{R_1} = \frac{R_2}{R_1+R_2}I$$
$$I_2 = \frac{V}{R_1} = \frac{I\frac{R_1R_2}{R_1 + R_2}}{R_2} = \frac{R_1}{R_1+R_2}I$$

```ad-info
Notice how finding $I_1$ uses $R_2$ as opposed to $R_1$. The reason for this is if $R_2$ is large, more current will flow through $I_1$ thus leading to a larger $I_1$.
```

$$I_n =  \frac{\Pi^N_{k = 1, k \neq n}R_k}{\sum^N_{m=1}(\Pi^N_{k=1, k\neq m R_k})}I $$

### Analysis of Complicated Circuits
Circuits with a mix of series and parallel components.

If a set of resistors are in series, you can simply add them all together and have it as one resistor.

If a set of resistors are in parallel, you can use the equation $R_C = \frac{R_AR_B}{R_A + R_B}$ all together and have it as one resistor.
```ad-note
The equation above can be said in shorthand $R_C$ = $R_A$ || $R_B$.
```