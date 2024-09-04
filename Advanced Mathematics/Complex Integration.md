Created: 28/08/2024 at 15:56

In complex analysis we are almost always interested in contrours, or *closed loops*.

How can we do this?

### Example
![[Pasted image 20240828160435.png]]
Integrate around circle $C:∣z−i∣=1$ function

$$f(z) = \frac{z}{z^2 + 3} = \frac{z}{(z + i\sqrt{3})(z - i\sqrt{3})}$$

We can use partial fractions to write this as

$$f(z) = \frac{1}{2}\left(\frac{1}{z + i\sqrt{3}}\right) + \frac{1}{2}\left(\frac{1}{z - i\sqrt{3}}\right)$$

The singularities are $z_1=−i\sqrt3 \quad z_2​=i\sqrt3$.  Observe that $z_2$​ is inside the circle, since $3≈1.732<2$, but $z_1$​ is outside. Note that each term bracket of $f(z)$ is of the form (from ![[Complex Functions#A Useful Result]])

$$\frac{1}{(z - z_0)^1}$$

Hence the integral is

$$\int_C f(z) dz = 0 + \frac{1}{2}(2\pi i) = \pi i$$

### Laurent Series
The general Taylor series expression is given by
$$f(z) = \sum_{n=0}^{\infty} a_n(z - z_0)^n$$

Such a series can be extended to include *negative powers* called Laurent series*.
$$f(z) = \sum_{n=-\infty}^{\infty} a_n(z - z_0)^n$$

#### Poles
A *pole* of $f(z)$ is a point $z_0$ such that $f(z)$ is not analytic at $z_0$ in the form,
$$\frac{1}{(z - z_0)^m}$$
We say that $f(z)$ has a pole of order $m$ at $z_0$. A pole or order 1 is called a *simple pole*. A pole of order 2 is called a *double pole*, and so on.
A **essential singularity** is a point $z_0$ such that $f(z)$ has infinitely many negative powers in its Laurent series expansion.

#### 4 Possibilities
A zero of order $m$,
$$f(z) = \sum_{n=m}^{\infty} a_n(z - z_0)^n$$

Taylor series,
$$f(z) = \sum_{n=0}^{\infty} a_n(z - z_0)^n$$

A pole of order $m$,
$$f(z) = \sum_{n=-m}^{\infty} a_n(z - z_0)^n$$

An essential singularity,
$$f(z) = \sum_{n=-\infty}^{\infty} a_n(z - z_0)^n$$

#### How to Solve
##### Example

$$f(z) = \frac{\cos z - 1}{z^4}$$ around z=0z=0

Recalling that $\cos ⁡z=1− \frac {z^2} 2+ \frac {z^4} {24}−\frac{z^6}{720} = \cdots$ we get

$$f(z) = \frac{1}{z^4} \left[ -1 + \left( 1 - \frac{z^2}{2} + \frac{z^4}{24} - \frac{z^6}{720} + \cdots \right) \right] \Rightarrow f(z) = -\frac{1}{2z^2} + \frac{1}{24} - \frac{z^2}{720} - \cdots$$

and hence f(z)f(z) has a pole of order two at z=0z=0.

Example:

$f(z) = e^{-\frac{1}{z^2}}$ around $z=0$

Recalling that $e^z = 1 + z + \frac{z^2}{2} + \frac{z^3}{6} + \cdots$ we get

$$f(z) = \cdots - \frac{1}{6z^6} + \frac{1}{2z^4} - \frac{1}{z^2} + 1$$

and hence $f(z)$ has an essential singularity at $z=0$.

### Residues
If $f(z)$ has a pole of order $m$ at $z_0$ or essential, then it has a *Laurent series* expansion of the form
$$f(z) = \sum_{n=-m}^{\infty} A_n(z - z_0)^n \qquad \text{or} \qquad f(z) = \sum_{n=-\infty}^{\infty} A_n(z - z_0)^n$$

A coefficient $A_{-1}$ is called the *residue* of $f(z)$ at $z_0$ and is denoted by $\text{Res}(f, z_0)$.

#### Example
$$f(z) = e^{\frac{2}{z}} = 1 + \frac{2}{z} + \frac{2}{z^2} + \frac{4}{3z^3} + \cdots \quad \Rightarrow \quad \text{Res}\left[e^{\frac{2}{z}}, 0\right] = 2$$

#### Example
$$f(z) = \frac{\cos z - 1}{z^4} = -\frac{1}{2z^2} + \frac{0}{z} + \frac{1}{24} + \cdots \quad \Rightarrow \quad \text{Res}\left[f, 0\right] = 0$$

### Why is $A_{-1}$ Important?
Recall the useful result

$$\oint_C \frac{dz}{(z - z_0)^n} = \begin{cases} 2\pi i, & n = 1 \ 0, & n \neq 1 \end{cases}$$

where $n$ is an integer.

The Laurent series now gives us that

$$\oint_C f(z) dz = \sum_{n=-\infty}^{\infty} A_n \oint_C (z - z_0)^n dz = \cdots + 0 + 0 + A_{-1} \oint_C \frac{dz}{z - z_0} + 0 + 0 + \cdots$$

That is,

$$\oint_C f(z) dz = 2\pi i \cdot A_{-1} = 2\pi i \text{Res}[f, z_0]$$

where $z_0$ is the only singularity of $f(z)$ which lies inside $C$. So if we can find the Laurent series for $f(z)$, then we have a very simple way of evaluating contour integrals.

Example:

$$\frac{\sin z}{z^2} = \frac{1}{z} - \frac{z}{6} + \cdots \Rightarrow \oint_C \frac{\sin z}{z^2} dz = 2\pi i \cdot 1 = 2\pi i$$

where $C$ is any curve which encloses the origin.

### Cauchy's Residue Theorem
$$\oint_C f(z) dz = 2\pi i \sum_{n=1}^N \text{Res}[f, z_n]$$

where $z_1, z_2, \cdots, z_N$ are the singularities of $f(z)$ which lie inside $C$.

If $f(z)$ has a *pole of order $k$* at $z_0$, then
$$\text{Res}[f, z_0] = \frac{1}{(k-1)!} \lim_{z \to z_0} \frac{d^{k-1}}{dz^{k-1}} \left[ (z - z_0)^k f(z) \right]$$
![[Pasted image 20240828164454.png]]

#### Proof
Since $f(z)$ has a pole of order k at z_0, we can write
$$f(z) = \frac{A_{-k}}{(z - z_0)^k} + \cdots + A_{-1}(z - z_0)^{-1} + A_0 + A_1(z - z_0) + \cdots$$

Multiplying by $(z - z_0)^k$ and differentiating $k-1$ times gives
$$\lim_{z \to z_0} \frac{d^{k-1}}{dz^{k-1}} \left[ (z - z_0)^k f(z) \right] = A_{-1} \cdot k!$$

### L'Hopital's Rule
If $f(z)$ and $g(z)$ are analytic at $z_0$ and $f(z_0) = g(z_0) = 0$, then
$$\lim_{z \to z_0} \frac{f(z)}{g(z)} = \lim_{z \to z_0} \frac{f'(z_0)}{g'(z_0)}$$

### Leading Order Term
The *leading order term* of a function $f(z)$ at $z_0$ is the term in the Laurent series of $f(z)$ at $z_0$ with the smallest power of $(z - z_0)$.

In order to determine the order of a pole of a function we can replace each term by its leading order term.

$$f(z) = \frac{z^3 e^z + z^2}{\sin z + z \cos z} \longrightarrow \frac{z^3 \cdot 1 + z^2}{z + z \cdot 1} = \frac{1}{2} z^1 + \frac{1}{2} z^2$$

So $f(z)$ has a pole of order 1 at $z=0$.

Sometimes we get a leading order term of 0, in which case we need to use extra terms to determine the order of the pole.

### Steps for Complex Integration
1. Sketch the contour $C$ and identify the singularities of $f(z)$.
2. Determine which poles are inside $C$ and their order
3. Find the residue of $f(z)$ at each pole inside $C$
4. Sum these residues and multiply by $2\pi i$ to get the integral