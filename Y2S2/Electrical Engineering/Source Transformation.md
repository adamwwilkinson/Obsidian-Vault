Created: 12/08/2022 at 11:24
Tags: #topic/electrical/superpositionandequivalentcircuits 
Related: [[Circuit Analysis Techniques]]

### The Issue
The format of power supplies may be different in different circumstances. How can we get *Network A* (a device using the power supply) to look at these different supplies the same?

### The Solution
#### Voltage Source
$V_A = V_S - V_R$
$V_A = V_S - i_AR_S$
Refer to [[Practical Sources#Practical Voltage Sources]]

#### Current Source
$i_A = i_S - i_R$
$i_A = i_s - \frac{V_A}{R_S}$
$V_A = i_SR_S - i_AR_S$
Refer to [[Practical Sources#Practical Current Sources]]

#### Therfore
$$V_S = i_SR_S$$

![[Source Transformation Drawing]]

### Example
![[Source Transformation Example Drawing]]