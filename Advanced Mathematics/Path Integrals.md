Created: 24/07/2024 at 13:40

### Curves
We can *parametrise* curves in $\mathbb{R}^2$:

$$x = x(t), y = y(t), a \leq t \leq b$$

where $x(t)$ and $y(t)$ are continuous functions of $t$.
where $t$ is the parameter. The curve is then given by the set of points $(x(t), y(t))$ for all $t$ in the domain of the parametrisation.

![[Path Integrals-1721799697737.jpeg]]

We want to be able to integrate a quantity of interest in $f(x, y), which will be a path density (will have units of *amount per unit length*) along a curve $C$.

#### Radius and Velocity Vectors
![[Path Integrals-1721799916480.jpeg]]

$$r(t) = (x(t), y(t)) \ \ \ \ \ \ \ \ \ \ \ \ \ \ v = (x'(t), y'(t))$$

```ad-note
$v$ is tangent to the curve
```

#### Unit Vectors
The *unit tangent vector* is given by:
$$T = \frac {v} {|v|} = \frac {v} {\sqrt {x'(t)^2 + y'(t)^2}}$$

The *unit normal vector* is perpendicular to $T$.

$$n = \frac {(y'(t), -x'(t))} {\sqrt {x'(t)^2 + y'(t)^2}}$$
![[Path Integrals-1721800227422.jpeg]]

### Example
The line containing the points $a$ and $b$ has the parametrisation:
$$r(t) = a_1 + t(b_1 - a_1)$$
![[Path Integrals-1721800767019.jpeg]]

The *line segment* from $a$ to $b$ is given by $0 \leq t \leq 1$.

Circle: $x^2 + y^2 = 1$ has the parametrisation:
$$x = \cos t, y = \sin t, 0 \leq t \leq 2\pi$$

Ellipse: $\frac {x^2} {a^2} + \frac {y^2} {b^2} = 1$ has the parametrisation:
$$x = a \cos t, y = b \sin t, 0 \leq t \leq 2\pi$$

### Path Integrals
Consider a small element of the curve $ds = \sqrt {dx^2 + dy^2} = \sqrt {x'(t)^2 + y'(t)^2} \, dt = |v(t)| \, dt \rightarrow \frac{ds}{dt} = |v(t)|$
![[Path Integrals-1722160413646.jpeg]]

### Arc Length
The length of the curve $C$ is given by:
$$L = \int_a^b \frac {ds}{dt} \, dt = \int_a^b |v(t)| \, dt$$

#### Example
With the parabola $y = x^2$ below $y = 1$
Parametrise the parabola as $x = t, y = t^2, -1 \leq t \leq 1$.
$$\text {Length} = \int_{-1}^1 \sqrt {1 + 4t^2} \, dt = \frac 1 2 \left[ t \sqrt {1 + 4t^2} + \frac 1 2 \ln |2t + \sqrt {1 + 4t^2}| \right]_{-1}^1 = \sqrt 5 + \frac 1 2 \ln 3$$

```ad-help
When your given a cartesian description. Look for the limits in terms of $t$.
```

### Smoothness
A curve is *smooth* if it has derivitives of all orders

A curve is *piecewise smooth* if it is a collection of smooth curves $C_1, C_2, \ldots, C_n$. For such a curve
$$\int_C f(x, y) \, ds = \sum_{i=1}^n \int_{C_i} f(x, y) \, ds$$

We are often in interested in path integrals with respect to $x$ only or $y$ only.
That is,
$$\int_C f(x, y) \, dx = \int_a^b f(x(t), y(t)) x'(t) \, dt \ \ \ \text { since } dx = x'(t) \, dt$$

Or

$$\int_C f(x, y) \, dy = \int_a^b f(x(t), y(t)) y'(t) \, dt \ \ \ \text { since } dy = y'(t) \, dt$$

Quite often these occure together like,
$$\int_c M(x, y) \, dx + N(x, y) \, dy = \int_C \left[ M(x, y) \, dx + N(x, y) \, dy \right]$$

### Path Integrals in $\mathbb{R}^3$
$$x = x(t), y = y(t), z = z(t), a \leq t \leq b$$
$$\int_C f(x, y, z) \, ds = \int_a^b f(r(t)) |r'(t)| \, dt$$
where $r(t) = (x(t), y(t), z(t))$
![[Path Integrals-1722162271076.jpeg]]

$$\int_C M(x, y, z) \, dx + N(x, y, z) \, dy + P(x, y, z) \, dz
