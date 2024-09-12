ODE or DE are equations involving an unknown function of one variable and its derivatives.

The order of a differential equation is the order of the highest derivative in the equation.

### Linear and Homogeneous Differential Equations
A linear differential equation is one where its derivatives appear to the first power and are not multiplied by the function itself. For example,
$$\frac{d^2y}{dx^2} + 3\frac{dy}{dx} + 2y = 0$$
As opposed to
$$\frac{d^2y}{dx^2} + 3\frac{dy}{dx} + 2y^2 = 0$$

A homogeneous differential equation is one where the function and its derivatives are the only terms in the equation i.e. a non-zero right-hand side.
$$\frac{d^2y}{dx^2} + 3\frac{dy}{dx} + 2y = 0$$
As opposed to
$$\frac{d^2y}{dx^2} + 3\frac{dy}{dx} + 2y = f(x)$$o

### Separation of Variables for First Order DE
To solve,
$$\frac{df}{dt} = \frac {f} {t^2}$$
First we put all the terms involving $f$ on one side and all the terms involving $t$ on the other side.
$$\frac{df}{f} = \frac {dt} {t^2}$$
Then we integrate both sides.
$$\int \frac{df}{f} = \int \frac {dt} {t^2} \implies \ln |f| = -\frac{1}{t} + C$$

Expotentiate both sides to get the solution.
$$f = e^{-\frac{1}{t} + C} = e^C e^{-\frac{1}{t}} = Ae^{-\frac{1}{t}}$$

### Integrating Factor Method for First Order Linear DE
We can solve a first order linear DE of the form,
$$\frac{df}{dt} + p(t)y = q(t)$$

We can imagine the right hand side as a 'driving force'.

A trick to solve this by the *integrating factor*,
$$\mu(t) = e^{\int p(t) dt}$$

Then multiply both sides by $\mu(t)$,
$$\mu(t) \frac{df}{dt} + p(t)\mu(t)y = \mu(t)q(t)$$

With the chain rule, we can rewrite the left hand side as,
$$\frac{d}{dt}(\mu(t)f) = \mu(t)q(t)$$

Integrating both sides gives,
$$\mu(t)f = \int \mu(t)q(t) dt \implies f(t) = \frac{1}{\mu(t)} \int \mu(t)q(t) dt + C$$

#### Example
$$\frac {df} {dt} + \frac 1 t f = t^2$$
The integrating factor is $\mu(t) = e^{\int \frac 1 t dt} = e^{\ln t} = t$.
$$t \frac {df} {dt} + f = t^3 \implies \frac{d}{dt}(tf) = t^3 \implies tf = \int t^3 dt = \frac{t^4}{4} + C \implies f = \frac{t^3}{4} + \frac{C}{t}$$

	### Constant Coefficient Homogeneous DE
The general form of a second order constant coefficient homogeneous DE is,
$$a\frac{d^2y}{dt^2} + b\frac{dy}{dt} + cy = 0$$
Where $a, b, c$ are constants.

In order to solve these, try solution $y=e^{mx}$ to obtain a quadratic equation for $m$.

E.g. for $y'' - 3y' + 2y = 0$, we get $m^2 - 3m + 2 = 0$ which has roots $m=1, 2$.

#### Roots
Three cases:
1. Two distinct real roots $m_1, m_2$.
$$y = Ae^{m_1x} + Be^{m_2x}$$
2. Repeated real roots $m_1 = m_2$.
$$y = Ae^{m_1x} + Bxe^{m_1x}$$
3. Complex roots $m = \alpha \pm i\beta$.
$$y = e^{\alpha x}(A\cos \beta x + B\sin \beta x)$$

### Euler Differential Equations
The geenral form of a second order Euler DE is,
$$ax^2\frac{d^2y}{dx^2} + bx\frac{dy}{dx} + cy = 0$$
Where $a, b, c$ are constants.
Commonly used in spherical coordinates where x is radius.

In order to solve these, try solution $y=x^m$ to obtain a quadratic equation for $m$.

#### Example
$$x^2y'' - 3xy' + 4y = 0$$
Try $y=x^m$.
$$m(m-1)x^m - 3mx^m + 4x^m = 0 \implies m^2 - 4 = 0 \implies m = \pm 2$$
Hence the solution is,
$$y = Ax^2 + Bx^{-2}$$

#### Roots
Three cases:
1. Two distinct real roots $m_1, m_2$.
$$y = Ax^{m_1} + Bx^{m_2}$$
2. Repeated real roots $m_1 = m_2$.
$$y = Ax^{m_1} + Bx^{m_1}\ln x$$
3. Complex roots $m = \alpha \pm i\beta$.
$$y = x^{\alpha}(A\cos \beta \ln x + B\sin \beta \ln x)$$

### Non-Homogeneous DE
The general form of a second order non-homogeneous DE is,
$$a\frac{d^2y}{dt^2} + b\frac{dy}{dt} + cy = f(t)$$
Where $a, b, c$ are constants and $f(t)$ is a function of $t$.

To solve, first solve the homogeneous equation and then find a particular solution for the non-homogeneous equation.
The solution of the *non-homogeneous* equation is the sum of the *homogeneous* solution and the *particular* solution.
$$y(x) = y_h(x) + y_p(x)$$

Where $y_h(x)$ is the solution to the homogeneous equation and $y_p(x)$ is any solution to the non-homogeneous equation.

#### Method of Undetermined Coefficients
This method is used to find a particular solution to a non-homogeneous DE. Depending on the form of $f(x)$, we can guess a form for $y_p(t)$.

1. $f(x) = Ae^{cx}$
Then guess $y_p(x) = Ce^{cx}$.

2. $f(x) = A\cos(cx)$ or $f(x) = A\sin(cx)$
Then guess $y_p(x) = C_1\cos(cx) + C_2\sin(cx)$.

3. $f(x) = P_n(x)$ where $P_n(x)$ is a polynomial of degree $n$.
Then guess $y_p(x) = C_nx^n + C_{n-1}x^{n-1} + \ldots + C_1x + C_0$.
