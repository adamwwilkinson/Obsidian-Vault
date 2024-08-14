Created: 24/07/2024 at 12:31

Integration in 2 or 3 dimensions.

$$\int_{x=a}^{x=b} \left\{ \int_{y=g(x)}^{y=h(x)} f(x, y) \, dy \right\} \, dx$$

$$\int_{y=c}^{x=d} \left\{ \int_{x=q(y)}^{x=p(y)} f(x, y) \, dx \right\} \, dy$$

##### Example
The integral of $f(x, y) = xy$ over the region bounded by the curves $y = x^3$ and $x = y^2$.
![[Pasted image 20240724124133.png]]

Using vertical strips we have,
$$\int_{x=0}^{x=1} \left\{ \int_{y=x^3}^{y=\sqrt{x}} xy \, dy \right\} \, dx = \int_{x=0}^{x=1} \left[ \frac{xy^2}{2}\right]_{y=x^3}^{y=\sqrt x} \, dx = \int_0^1 \frac {x^2 - x^7} {2} \, dx = \frac 5 {48}$$

Using horizontal strips we have,
$$\int_{y=0}^{y=1} \left\{ \int_{x=y^2}^{x=y^{1/3}} xy \, dx \right\} \, dy = \int_{y=0}^{y=1} \left[ \frac{x^2y}{2} \right]_{x=y^2}^{x=y^{1/3}} \, dy = \int_0^1 \frac {y^{7/3} - y^5} {2} \, dy = \frac 5 {48}$$

### Area
To find the area of a region $R$ we simply integrate the function $f(x, y) = 1$ over the region.
$$ Area = \iint_R 1 \, dxdy $$

#### Example
To find the area bounded by the curves $x = y^2$  and $x = y + 2$. Note the curves intersect where $y^2 = y + 2$ or $y^2 - y - 2 = 0$ which has solutions $y = -1, 2$ and $x = 1,4$
![[Revision-1721797847401.jpeg]]

$$\text {Area} = \int_{y=-1}^{y=2} \left\{ \int_{x=y^2}^{x=y+2} \, dx \right\} \, dy = \int_0^1 \int_{y=-\sqrt x}^{y=\sqrt x} \, dy \, dx + \int_1^4 \int_{y=x-2}^{y=\sqrt x} \, dy \, dx$$
$$ = \frac 9 2 = \frac 4 3 + \frac 19 6$$

### Reversing the Order of Integration
We cannot do the inner integral of this problem:
$$I = \int_{y=0}^{y=1} \int_{x=\sqrt y}^{x=1} e^{x^3}\, dx \, dy$$

Reversing the order of integration solves the problem because the integral in $y$ becomes far easier.
![[Revision-1721798387353.jpeg]]
$$=\int_0^1 x^2 e^{x^3} \, dx = \int_0^1 \frac 1 3 e^u \, du = \frac 1 3 (e - 1)$$
where $u = x^3 \rightarrow du = 3x^2 \, dx$

### Triple Integrals
The integral of a funciton $f(x, y, z)$ over a region $R$ in 3D space is given by:
$$\int_{x=a}^{x=b} \left\{ \int_{y=g(x)}^{y=h(x)} \left\{ \int_{z=p(x, y)}^{z=q(x, y)} f(x, y, z) \, dz \right\} \, dy \right\} \, dx$$
![[Revision-1721798697353.jpeg]]
```ad-note
The outermost integral is always with numbers, the next has one variable, and the innermost has two variables.
```

### Change of Coordinates
A lot of time the cartesian coordinates suck, for things such as spheres. We can evaluate an integral in $xy$ space by changing it to $uv$ space.

$$\iint_R f(x, y) \, dxdy = \iint_S f(g(u, v), h(u, v)) \left| \frac {\partial (x, y)} {\partial (u, v)} \right| \, dudv$$
where $\left| \frac {\partial (x, y)} {\partial (u, v)} \right| = \left| \begin{array}{cc} \frac {\partial x} {\partial u} & \frac {\partial x} {\partial v} \\ \frac {\partial y} {\partial u} & \frac {\partial y} {\partial v} \end{array} \right|$

And $x = g(u, v), y = h(u, v)$

```ad-info
The Jacobian is the determinant of the matrix of partial derivatives. And is a scale factor that accounts for the change in area when changing coordinates.

![[Revision-1721798945584.jpeg]]
```

### Polar Coordinates
We can change to polar coordinates by using the following:
$$x = r \cos \theta, y = r \sin \theta$$
$$\iint_R f(x, y) \, dxdy = \iint_S f(r \cos \theta, r \sin \theta) r \, drd\theta$$

```ad-danger
DO NOT FORGET TO MULTIPLY BY $r$ IN THE POLAR COORDINATES.
```

#### Example
![[Revision-1721799167776.jpeg]]

### Cylindrical Polar Coordinates
We can change to cylindrical polar coordinates by using the following:
$$x = r \cos \theta, y = r \sin \theta, z = z$$

$$\iiint_R f(x, y, z) \, dxdydz = \iiint_S f(r \cos \theta, r \sin \theta, z) r \, drd\theta dz$$

### Spherical Polar Coordinates
We can change to spherical polar coordinates by using the following:
$$x = \rho \sin \phi \cos \theta, y = \rho \sin \phi \sin \theta, z = \rho \cos \phi$$

$$\iiint_R f(x, y, z) \, dxdydz = \iiint_S f(\rho \sin \phi \cos \theta, \rho \sin \phi \sin \theta, \rho \cos \phi) \rho^2 \sin \phi \, d\rho d\phi d\theta$$

```ad-info
$\rho$ is the distance from the origin, $\phi$ is the angle from the $z$-axis, and $\theta$ is the angle from the $x$-axis.
```
