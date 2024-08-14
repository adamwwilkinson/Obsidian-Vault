Created: 10/08/2024 at 12:38

Let $C$ be positively orientated (i.e. anticlockwise), piecewise smooth, simple closed curve in the plane and $D$ is the enclosure of $C$.

If $M(x, y)$ and $N(x, y)$ have continuous partial derivatives in the domain $D$ then
$$\oint_C M \, dx + N \, dy = \iint_D \left( \frac {\partial N}{\partial x} - \frac {\partial M}{\partial y} \right) \, dA$$

### Examples
#### Unit Circle
$\oint_C xy^2dx + x^2ydy$ where $C$ is the unit circle, let $M = xy^2$ and $N = x^2y$. Green's theorem says that
$$\oint_C xy^2dx + x^2ydy = \iint_D \left( \frac {\partial x^2y}{\partial x} - \frac {\partial xy^2}{\partial y} \right) \, dA = \iint_D (2xy - 2xy) \, dA = 0$$

#### Unit Square
![[Green's Theorem-1723265348131.jpeg]]

#### Finding the Area of a Region
$$Area = \iint_D 1 \, dA = \oint_C x \, dy = \oint_C -y \, dx = \frac {1}{2} \oint_C x \, dy - y \, dx$$

We get these cases when,
$$M = 0, \ \ \ N = x \ \ \ \text{or} \ \ \ M = -y, \ \ \ N = 0 \ \ \ \text{or} \ \ \ M = - \frac {y}{2}, \ \ \ N = \frac {x}{2}$$

##### Area of Ellipse
![[Green's Theorem-1723265543891.jpeg]]

##### General Area
![[Green's Theorem-1723265723204.jpeg]]

### Extension of Green's Theorem
To non-simple closed curves, we can make a cut
![[Green's Theorem-1723265765400.jpeg]]
![[Green's Theorem-1723265903422.jpeg]]

The $-C_2$ comes from the fact, we have to traverse it clockwise to complete the loop.

### Encircling The Origin
![[Green's Theorem-1723346660380.jpeg]]![[Green's Theorem-1723346788840.jpeg]]
![[Green's Theorem-1723346848600.jpeg]]