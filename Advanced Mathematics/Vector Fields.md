Created: 31/07/2024 at 12:39

### Fields
A function which assigns a quantity to each point in a region of interest.

#### Scalar Fields
A scalar field assigns a point to a *scalar*, density, temperature, pressure, etc.

#### Vector Fields
A function that assigns to each point a *vector*, velocity, electric, etc.

#### Gradient
The *gradient* is an example of a vector field obtained from a scalar field.
$$F = grad \, f = \nabla f = \left( \frac {\partial f}{\partial x}, \frac {\partial f}{\partial y}, \frac {\partial f}{\partial z} \right)$$

### Line Integrals of Vector Fields
The work done by a force field
$$F(x, y, z) =  M(x, y, z) \mathbf{i} + N(x, y, z) \mathbf{j} + P(x, y, z) \mathbf{k}$$ in moving a particle along curve $C$ is
$$\text{work done} = \int_C F \cdot dr = \int_C M \, dx + N \, dy + P \, dz$$

Where $dr = (dx, dy, dz)$

### Flow
If $F(x, y, z)$ is a vector field instead, instead of a *force field*, then the line integral is the *flow* of the field along the curve $C$.

$\text{flow} = \int_C F \cdot dr$

### Closed Curves
A closed curve is one where its inital and end points are the same. And we write $\oint_C$ to denote a closed curve.

### Flux
The flux of a vector field
$$F = M (x, y) \mathbf{i} + N (x, y) \mathbf{j}$$
across a closed curve $C$ in the $x-y$ plane is
$$\text{flux} = \oint_C F \cdot n ds$$
where $n$ is the outwards unit normal vector to the curve.
$$n = \frac {(y'(t), -x'(t))} {\sqrt {x'(t)^2 + y'(t)^2}} = \frac {(\frac {dy}{dt}, -\frac {dx}{dt})} {\frac {ds} {dt}} = \left( \frac {dy}{ds}, -\frac {dx}{ds} \right)$$

hence,

$$F \cdot n = M(x, y) \frac {dy}{ds} - N(x, y) \frac {dx}{ds} \rightarrow \text{flux} = \oint_C M \, dy - N \, dx$$

![[Vector Fields-1722510899366.jpeg]]

### Example 1
Find work done $W$ in moving a particle along a spiral path $r(t) = (\cos t, \sin t, t)$, $0 \leq t \leq 2\pi$ in the force field $F = (x, y + x, yz)$.

$r'(t) = (-\sin t, \cos t, 1)$ and $F = (\cos t, \sin t + \cos t, t \sin t)$

hence,
![[Vector Fields-1722511321514.jpeg]]

### Orientation
A given parametrisation determines an *orientation* of a curve, the *positive* orientation is the one that goes in the direction of increasing $t$.

$-C$ denotes the same curve with the opposite orientation.

$$\int_{-C} f(x, y)dx = -\int_C f(x, y)dx$$

However as $ds$ is always positive,

$$\int_{-C} f(x, y)ds = \int_C f(x, y)ds$$

### Example
The x-axis interval $[0, 1]$ traversed backwards
$$\int_Cdx = \int_1^0dx = -1$$

However, with $x(t) = 1 - t, y(t) = 0$ and $0 \leq t \leq 1$ we have

$$ds = \sqrt {1^2 + 0^2}dt = dt \rightarrow \int_Cds = \int_0^1dt = 1$$

```ad-warning
If it's dx dy interval and you change direction, you add a minus sign while if it's ds, you don't.
```


### Some Geometry
#### Definitions
- a region $D$ is **CONNECTED** if any point in $D$ can be reached from any other point by a *smooth curve*
- a region $D$ is **SIMPLY CONNECTED** if any loop in $D$ can be contracted to a single point in $D$
![[Vector Fields-1722672928396.jpeg]]

First is simply connected while second is not.

- a curve is **SIMPLE** if it does not intersect itself
![[Vector Fields-1722672983250.jpeg]]

The first is simple, the second is not.

- **POSITIVE ORIENTATION** of a simple *closed* curve $C$ refers to a single *anticlockwise* traversal of the curve.

#### Path Independence and Conservative Fields
If the work done by a field $F$ in moving a particle from one point to another is *independent* of the path taken, then we say that the integral $\int_C F \cdot dr$ is *path independent* and the field is *conservative*.
![[Vector Fields-1722673148611.jpeg]]

If the domain has no holes, then for such funtions $F$ there will exist a function $f$ such that $F = \nabla f$.

##### Fundamental Theorem of Line Integrals FTLI

$$F = \left( \frac {\partial f}{\partial x}, \frac {\partial f}{\partial y}, \frac {\partial f}{\partial z} \right)$$

$$ \int_A^B F \cdot dr = f(B) - f(A)$$

```ad-note
$$\oint_C F \cdot dr = 0$$ around any *closed loop* $C$ as $B$ and $A$ coincide and hence $f(B) - f(A) = 0$.
```

### Important Example
![[Vector Fields-1722854677276.jpeg]]

### Component Test for Conservative Fields
$F = (M, N, P)$ is *conservative* if
$$\frac {\partial P}{\partial y} = \frac {\partial N}{\partial z}, \frac {\partial M}{\partial z} = \frac {\partial P}{\partial x}, \frac {\partial N}{\partial x} = \frac {\partial M}{\partial y}$$

If it's not then there is no little $f$ as that only exist if its conservative.

Remember $M = f_x, N = f_y, P = f_z$.

#### In 2 Dimensions
$F = (M, N)$ is conservative if
$$\frac {\partial N}{\partial x} = \frac {\partial M}{\partial y}$$

### Curl and Divergence
The curl is a vector field while the divergence is a scalar field.

#### Curl
A *curl* of a vector field $F = (M, N, P)$ in $\mathbb{R}^3$ is
$$\text{curl} \; F = \nabla \times F = \left( \frac {\partial P}{\partial y} - \frac {\partial N}{\partial z}, \frac {\partial M}{\partial z} - \frac {\partial P}{\partial x}, \frac {\partial N}{\partial x} - \frac {\partial M}{\partial y} \right)$$

A measure of the tendency of the field to **TWIST** particles

#### Divergence
A measure of *expansion/compression* of a field $F = (M, N, P)$ in $\mathbb{R}^3$ is

$$\text{div} \; F = \nabla \cdot F = \frac {\partial M}{\partial x} + \frac {\partial N}{\partial y} + \frac {\partial P}{\partial z}$$

If $\text{div} \; F = 0$ then the field is called *solonoidal* in electrical engineering, or *incompressible* in fluid dynamics.

### Nabla
$$\nabla = \left( \frac {\partial}{\partial x}, \frac {\partial}{\partial y}, \frac {\partial}{\partial z} \right)$$

### Scalar and Vector Potentials
The component test for conservative field using $\nabla$ is
$$\nabla \times F = 0 \rightarrow F = \nabla f$$

If can show $F$ is solenoidal, then there exist a *vector potential* $A$ such that $F = \nabla \times A$.
