Created: 11/08/2024 at 11:27

In *two-dimensions*, [[Green's Theorem]] relates an integral along a closed curve, to a corresponding integral over the region bounded by that closed curve.

In *three-dimensions*, we have a similar theorem called **Stoke's Theorem** and **Divergence Theorem**.

### Stoke's Theorem
Let $S$ be an oriented piecewise smooth *open* surface.

Let $F$ be a vector field whose components have continuous partial derivatives on an open region containing $S$.

$$\oint_C F \cdot dr = \iint_S \nabla \times F \cdot n dS$$

Where $C$ is the boundary of $S$ and $dS$ is the outwardly oriented surface element.
![[Stoke's Theorem-1723347086317.jpeg]]

*Orientation* of S induces positive orientation of $C$ as follows.
If we walk around $C$ in the positive direction with our head pointing in the direction of $n$, then $S$ will be on our left.

### Divergence Thoerem
Let $V$ be a simply-connected region in $\mathbb{R}^3$ with a positively oriented boundary $S$, hence a *closed surface*.
![[Stoke's Theorem-1723347566057.jpeg]]

Let $F$ be a vector field whose components have continuous partial derivatives in $V$. Then,
$${\huge\unicode{x222F}}_S
 F \cdot n dS = \iiint_V \nabla \cdot F dV$$

Where $n$ is the outwardly oriented unit normal to $S$.

```ad-info
This theorem is a three-dimensional analogue of the normal form of Green's Theorem.
```

#### Example
Evaluate the flux of $F = (x^2, y^2, z^2)$ through the unit cube $[0, 1]^3$. The Divergence theorem gives,
$$\text{Flux} = \iiint_V \nabla \cdot F dV = \int_0^1 \int_0^1 \int_0^1 (2x + 2y + 2z) dxdydz = 3$$
![[Stoke's Theorem-1723348184712.jpeg]]

Evaluate $\iiint_V \nabla \cdot F dV$ where volume $V$ is the *unit ball* $\rho \leq 1$ and $F = (x^2z, y^3z, -x^3, -y^4)$.

The surface $S$ of the ball is $\rho = 1$ and the outward unit normal is $n = r = (x, y, z)$. Hence,
$$F \cdot n = x^3z + y^4z - x^3 - y^4 = 0$$
Hence,
$${\huge\unicode{x222F}}_S F \cdot n dS = 0 \rightarrow \iiint_V \nabla \cdot F dV = 0$$
