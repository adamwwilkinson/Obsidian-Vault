Created: 05/08/2023 at 11:05

### Linear Differential Systems
A system is *linear* if it satisfies the *superposition principle*.
$$a_N \frac{d^N y(t)}{dt^N} + a_{N-1} \frac{d^{N-1} y(t)}{dt^{N-1}} + ... + a_1 \frac{dy(t)}{dt} + a_0 y(t) = b_M \frac{d^M x(t)}{dt^M} + b_{M-1} \frac{d^{M-1} x(t)}{dt^{M-1}} + ... + b_1 \frac{dx(t)}{dt} + b_0 x(t)$$

Using the operational notation $D = \frac d {dt}$, the equation can be written as:
$$Q(D)y(t) = P(D)x(t)$$

To ensure the system remains stable, the powers $M$ and $N$ must satisfy $M \leq N$.


### Roots
case roots
when 'real, distinct'
	$y_0(t) = c_1 e^{\lambda_1 t} + c_2 e^{\lambda_2 t}$
 ![[Continous-Time LTI Systems and Laplace Transform-1691205631495.jpeg]]
when 'real, repeated'
  $y_0(t) = c_1 e^{\lambda t} + c_2 t e^{\lambda t}$
  ![[Continous-Time LTI Systems and Laplace Transform-1691205640113.jpeg]]
when 'complex'
  $y_0(t) = e^{\alpha t} (c_1 cos(\beta t) + c_2 sin(\beta t))$
  ![[Continous-Time LTI Systems and Laplace Transform-1691205651057.jpeg]]
end

### Example
![[Continous-Time LTI Systems and Laplace Transform-1691205421762.jpeg]]