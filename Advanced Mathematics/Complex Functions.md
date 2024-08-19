Created: 16/08/2024 at 17:43

Basically just calculas , with complex functions.
The *exponential* function is
$$e^{z} = e^{x + iy} = e^{x} e^{iy} = e^{x} (\cos y + i \sin y) = e^{x} \cos y + i e^{x} \sin y$$

The *trigonemetric* functions are,
$$\sin z = \frac{e^{iz} - e^{-iz}}{2i} \qquad \cos z = \frac{e^{iz} + e^{-iz}}{2}$$
$$\tan z = \frac{\sin z}{\cos z} \qquad \cot z = \frac{\cos z}{\sin z}$$
$$\csc z = \frac{1}{\sin z} \qquad \sec z = \frac{1}{\cos z}$$
### Differentiable Complex Functions
Conside a complex valued function,
$$w = f(z) = f(x + iy) = u(x,y) + iv(x,y)$$

Rules are completely the same, but as $i^2 = -1$, amazing results arise.

Fumction $f(z) is differentiable at $z=z_0$ if
$$f'(z_0) = \lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0} \text{ exists}$$
The real and imaginary parts have a special property called the *Cauchy-Riemann Equations*.

### Cauchy-Riemann Equations
$$(1)\quad \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \qquad (2) \quad\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$$
Some implications of this,
$$\frac{\partial}{\partial x} (1) + \frac{\partial}{\partial y} (2) \rightarrow u_{xx} + u_{yy} = \cancel{v_{xy}} - \cancel{v_{yx}}$$ 
$$\frac{\partial}{\partial y} (1) - \frac{\partial}{\partial x} (2) \rightarrow \cancel{u_{xy}} - \cancel{u_{yx}} = v_{xx} + v_{yy}$$
Therefore,
$$\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0 \qquad \frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2} = 0$$
### Singularities
The points where a function is not defined. 
$$f(z) = \frac{1}{z^2 + 3} = \frac{1}{(z + i\sqrt{3})(z - i\sqrt{3})}$$
has singularities at $z= -i\sqrt{3}, \ z=i\sqrt{3}$.

### Complex Integration
If $C$ is a curve in the comple plane, then the integral of a complex function $f(z)$ along $C$ is
![[Complex Functions-1723803549775.jpeg]]
$$\int_C f(z) dz = \int_C (u + iv)(dx + idy)$$
$$= \int_C u , dx - v , dy + i \int_C v , dx + u , dy$$

In complex analysis we are always interested in closed loops.
$$\oint_C f(z)dz$$

### Cauchy's Integral Theorem
If $f(z)$ is *differentiable* inside (no singularity) and on a closed path $C$ then,
$$\oint_C f(z)dz = 0$$
### Example
Integrals of $f_1(z) = (z)$ and $f_2(z) = \frac 1 z$ around
$$C: |z| = 1$$
which is the *unit circle* $x^2 + y^2 = 1$, in polar form it is
$$z = e^{i\theta} \rightarrow \frac {dz}{d\theta} = ie^{i\theta} =\rightarrow dz = ie^{i\theta}d\theta$$
Hence,
$$\oint_C f_1(z) dz = \oint_C z dz = \int_{-\pi}^{\pi} e^{i\theta} \cdot i e^{i\theta} d\theta$$
$$= \int_{-\pi}^{\pi} i e^{2i\theta} d\theta = \frac{1}{2} \left[ e^{2i\theta} \right]{-\pi}^{\pi} = \frac{1 - 1}{2} = 0$$
$$\oint_C f_2(z) dz = \oint_C \frac{dz}{z} = \int{-\pi}^{\pi} \frac{i e^{i\theta}}{e^{i\theta}} d\theta = \int_{-\pi}^{\pi} i d\theta = 2\pi i$$

### Example 2
$\oint_{C} \frac{dz}{z^2-1}$ where $C$ is the closed curve
![[Complex Functions-1723863556209.jpeg]]

The function $f(z)= \frac{1} {z^2}$​ is undefined (and hence not analytic) when $z=1, \ -1$.

However, since these two points are not in the interior and not on the boundary of the closed curve, then

$$\oint_{C} \frac{dz}{z^2-1} = 0$$

In complex analysis, a closed curve is called a contour.

### A Useful Result
Suppose contour $C$ encloses point $z_0$. Then
![[Complex Functions-1723864037344.jpeg]]

$$\oint_C \frac{dz}{(z - z_0)^n} = \begin{cases} 
2\pi i, & n = 1 \\
0, & n \neq 1
\end{cases} \quad n \text{ integer}$$

If $n < 1$, the integrand is analytic and hence the result must be true by Cauchy's Integral Theorem.