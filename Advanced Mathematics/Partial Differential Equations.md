Created: 22/09/2024 at 10:47

Shows up when there is a function with more than one variable.

Simple example:
PDE for $u(x, t)$,
$$\frac{\partial u}{\partial t} + \frac{\partial u}{\partial x} = 0$$

### Arbitrary Functions instead of Arbitrary Constants
In ODEs, we have arbitrary constants. In PDEs, we have arbitrary functions.

#### ODE
$$\frac {d^2y}{dx^2} + y = 0 \implies y = A\sin x + B\cos x$$

#### PDE
$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial t^2} = 0 \implies u = f(x + t) + g(x - t)$$

### Special PDEs
#### Wave Equation
$$\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial x^2}$$

#### Heat Equation in 1D
$$\frac{\partial u}{\partial t} = \alpha \frac{\partial^2 u}{\partial x^2}$$

#### Heat Equation in 2D
$$\frac{\partial u}{\partial t} = \alpha \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} \right)$$

#### Laplace's Equation in 2D
$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0$$

#### Laplace's Equation in 3D
$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2} = 0$$

### Initial and Boundary Conditions
An initial condition is a value for when $t$ is given (typically 0), while a boundary condition is a value for when $x$ is given.

If it's $n$-th order in time, we need $n$ initial conditions. If it's $m$-th order in space, we need $m$ boundary conditions.

### Boundary Value Problems
When there is unknown function of *spatial variables* and enough boundary conditions to determine the function.

### Initial-Boundary Value Problems
When there is unknown function of *spatial and time variables* and enough initial and boundary conditions to determine the function.

### Travelling Wave Solutions
These are solutions of the form $u(x, t) = F(\eta) where \eta = x - ct$ and $c$ is the speed of the wave.

#### D'Alembert's Solution
$$\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial x^2}$$
Can be written as,
$$4c^2 \frac{\partial^2 u}{\partial \xi \partial \eta} = 0$$
Integrating both sides with respect to $\xi$,
$$4c^2 \frac{\partial u}{\partial \eta} = g(\eta)$$
Integrating again with respect to $\eta$,
$$u(\xi, \eta) = F(\xi) + G(\eta)$$

$$u(x, t) = F(x + ct) + G(x - ct)$$

Physically this represents two independent waves travelling in opposite directions.

Problem is this solution assumes an infinite domain.

#### Initial Value
We are typically asked to solve the wave equation with initial conditions,
$$u(x, 0) = U(x) \qquad \frac{\partial u}{\partial t}(x, 0) = V(x)$$

$$\frac{\partial u}{\partial t} = cF'(x + ct) - cG'(x - ct)$$

At $t = 0$,
$$F(x) + G(x) = U(x) \qquad F'(x) - G'(x) = \frac{1}{c}V(x)$$

Integrating the second equation,
$$F(x) - G(x) = \frac{1}{c} \int V(x) dx$$

Then we have the solution,
$$F(x) = \frac{U(x) + W(x)}{2} \qquad G(x) = \frac{U(x) - W(x)}{2}$$
where $W(x) = \frac{1}{c} \int V(x) dx$.

Hence,
$$u(x, t) = \frac{U(x + ct) + U(x - ct)}{2} + \frac{1}{2c} \int_{x - ct}^{x + ct} V(s) ds$$