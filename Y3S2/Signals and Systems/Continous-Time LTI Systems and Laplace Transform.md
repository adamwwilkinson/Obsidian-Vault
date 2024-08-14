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

### Convolution
The convolution integral occurs frequently in science, engineering, and mathematics. Regarding system analysis it is used to derive the zero-state response of a system from its impulse response and input signal. The convolution of two signals is defined as:
$$y(t) = \int_{-\infty}^{\infty} x(\tau) h(t - \tau) d\tau$$

#### Properties
* Sifting: $\int_{-\infty}^{\infty} x(t) \delta(t - \tau) dt = x(\tau)$
* Commutative: $x(t) * h(t) = h(t) * x(t)$
* Distributive: $x(t) * (h_1(t) + h_2(t)) = x(t) * h_1(t) + x(t) * h_2(t)$
* Associative: $x(t) * (h_1(t) * h_2(t)) = (x(t) * h_1(t)) * h_2(t)$

#### Graphical Explanation
![[Continous-Time LTI Systems and Laplace Transform-1691748844737.jpeg]]

#### Why is it Important
It is important for a zero-state response, it involves a *impulse fuction*.

The *impulse function* allows one to capture the general behavious of a system by applying a single impulse to the system.

```ad-important
Once we have the response of an LTI system to an impulse, we can derive its response to any input signal by convolving the input signal with the impulse response.
```

The input convolved with the impulse response gives the zero-state response.

### Example of Convolution
![[Continous-Time LTI Systems and Laplace Transform-1691749496146.jpeg]]

### Impulse Response
The impulse response has the same terms as the zero-input response because it'll resonate the natural modes.

### Responses
Total response = natural response (zero-input response) + forced response (zero-state response)

### Properties of LTI Systems and Stabiiity
The impulse response function allows us to analyse system properties, specifically:
- memoryless
- causal
- BIBO stable

A system is causal if the impulse response is zero for negative time.

If $M$ > $N$, the system is unstable.

### Asymptotic Stability
Knowing the characteristic modes are going to be of form ${\sum^N_{k=1}c_k e^{\lambda_k t}}$. If every characteristic mode approaches zero then the system is asymptotically stable. If some modes oscillate indefinitely or remain constant, the system is marginally stable. If some modes grow exponentially, the system is asymptomatically unstable.

A causal LTI system  is:
- asymptotically stable: Re($\lambda_k$) < 0 for all $k$
- asymptotically unstable: Re($\lambda_k$) > 0 for at least one $k$, or repeated roots when Re($\lambda_k$) = 0
- marginally stable: Re($\lambda_k$) $\leq 0$ for all $k$, and some unrepeated roots with Re($\lambda_k$) = 0

#### Asymptotic Stability and BIBO Stability
A system which is:
- asymptotically stable is BIBO stable
- asymptotically unstable or marginally stable becomes BIBO unstable when a bounded input applies

### Working out Convolution Intervals
Make the simpler function the one you're shifting. Reverse it and shift it. Because it's reversed, positive t makes it shift right and negative t makes it shift left.