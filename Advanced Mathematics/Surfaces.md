Created: 07/08/2024 at 15:40

To *parameterise* a surface $S$ in $\mathbb{R}^3$ we can use two parameters $u$ and $v$:

$$r = r(u, v) = (x(u, v), y(u, v), z(u, v))$$

Where $r$ is the position vector of the point $(x, y, z)$ on the surface.

### Example
The sphere $r=a$ can be parameterised as,
$$r(\phi, \theta) = (a \sin \phi \cos \theta, a \sin \phi \sin \theta, a \cos \phi)$$
where $0 \leq \phi \leq \pi$ and $0 \leq \theta \leq 2\pi$.

$\theta$ is the angle in the $x-y$ plane and $\phi$ is the angle from the $z$ axis.

### Line and Planes
Recall
![[Path Integrals#Example]]

If we consider a parameterisation of a *plane* in $\mathbb{R}^3$ as,
$$r(u, v) = \alpha + u(\beta - \alpha) + v(\gamma - \alpha)$$
where $\alpha, \beta, \gamma$ are points on the plane.

Note that
$$r(0, 0) = \alpha, \ \ \ r(1, 0) = \beta, \ \ \ r(0, 1) = \gamma$$
![[Surfaces-1723017045307.jpeg]]![[Surfaces-1723017057698.jpeg]]

```ad-note
Surfaces have 2 parameters, while curves have 1.
```

### Surface Area
A rectangular element $dudv$ in $D$ will correspond to some curvilinear surface element $dS$ in $S$ and
$$dS = \left | \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right | dudv$$,

where
$$r = r(u, v) = (x(u, v), y(u, v), z(u, v))$$

Therefore the total surface area is
$$A = \int \int_S dS = \int \int_D \left | \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right | dudv$$
![[Surfaces-1723017868424.jpeg]]

### Surface Integrals
#### Scalar Fields
Given a scalar field $f(x, y, z)$, the surface integral of $f$ over $S$ is
$$\int \int_S f \, dS = \int \int_D f(x(u, v), y(u, v), z(u, v)) \left | \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right | dudv$$
##### Example
![[Surfaces-1723263966727.jpeg]]

#### Vector Fields
A surface is called *closed* if it is the boundary of a solid, and *open* otherwise.

The *unit normal* to a surface is
$$\mathbf{n} = \frac {\frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v}} {\left | \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right |}$$
![[Surfaces-1723264062194.jpeg]]

The integral of a vector field $F$ over a surface $S$ is $\int \int_S F \cdot \mathbf{n} \, dS$
and is called the *flux* of $F$ across $S$.

A closed surface is said to have *positive orientation* if the normal points outwards, and *negative orientation* if it points inwards.

As $dS = \left | \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right | dudv$,

Hence, the **flux integral** is,
$$\int \int_S F \cdot \mathbf{n} \, dS = \int \int_D F \cdot \left ( \frac {\partial r}{\partial u} \times \frac {\partial r}{\partial v} \right ) \, dudv$$
