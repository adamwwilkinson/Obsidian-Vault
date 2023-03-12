Created: 08/03/2023 at 12:48
### Parallel RLC Circuits
![[Pasted image 20230308114351.png]]
Using *KCL* for this circuit wil give us one equation.
![[Pasted image 20230308114845.png]]

$$C \frac{d^2v} {dt^2} + \frac 1 R \frac {dv} {dt} + \frac 1 Lv = 0$$
![[Pasted image 20230308121214.png]]

In general, the solution of $v(t)$ is given by the linear combination.
$$v(t) = A_1 e^{s_1t} + A_2e^{s_2t}$$
This is a natural response of the d.e. as there is no forcing function.
![[Pasted image 20230308122438.png]]
![[Pasted image 20230308122450.png]]

#### Three Distinct Forms of Solution
##### Overdamped
Characterised by $\alpha > \omega_0$ we get two negative real values for $s_1, s_2$

##### Critically Damped
Characterised by $\alpha = \omega_0$. And we only got one root.

##### Underdamped
Characterised by $\alpha < \omega_0$, leads to two complex values for $s_1, s_2$/
![[Pasted image 20230308123055.png]]
![[Pasted image 20230308123241.png]]
![[Pasted image 20230308123959.png]]

#### Damping Ratio Zeta
Given by 
$$\zeta = \frac \alpha {\omega_0}$$
$\zeta > 1$ overdamped 
$\zeta > 1$ critically damped
$\zeta > 1$ underdamped 

### Series RLC Circuits
![[Pasted image 20230308124122.png]]
![[Pasted image 20230308124634.png]]

### RLC Circuits With Sources
We have just covered the *natural* or *homegenous* response of the RLC circuit. Next we consider the case with an independent source which will create a *forces* response of the circuit.

The complete response is a combination of the forced response
$$v_f(t) = V_f$$
and the natural response (from above).
[[RLC Circuits-1678601356492.jpeg]]