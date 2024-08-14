Created: 17/08/2023 at 13:16

### Applications
Can be used for physical systems, or financial systems.

### Linear Difference Systems
Similiar to differential equations, but with discrete time. The system is linear if it satisfies the superposition principle and homogeneity.

![[Discrete-Time Systems-1692249772260.jpeg]]

### Total Responses
#### Computation Method
We can calculate the total response computationally by using the recursive form in equation 3-2 above.

#### Analytical Method
We can consider the total response in two parts
$$\text{total response} = \text{zero-input response} + \text{zero-state response}$$

where, the zero-input response is the response of the system to the input when the initial conditions are zero, and the zero-state response is the response of the system when it is in zero state (no energy stores)

![[Discrete-Time Systems-1692250358992.jpeg]]
![[Discrete-Time Systems-1692250451982.jpeg]]

### Convolution Sum
The discrete-time equivalent of the convolution integral is the convolution sum. The convolution sum is the sum of the product of the input and impulse response at different times.

$$x_1[n] * x_2[n] = \sum_{k=-\infty}^{\infty} x_1[k]x_2[n-k]$$

Same properties as the convolution integral.

#### Example
Finding the Impulse Response
![[Discrete-Time Systems-1692408238134.jpeg]]

Finding the zero-state response
![[Discrete-Time Systems-1692408420968.jpeg]]

### Properties and Stability
A causal LTI system is:
- asymptotically stable: $|\lambda_k| < 1$ form all $k$
- asympotically unstable: $|\lambda_k| > 1$ for atleast one $k$, or repeated roots when $|\lambda_k| = 1$
- marginally stable: $|\lambda_k| \leq 1$ for all $k$ or unrepeated roots when $|\lambda_k| = 1$
