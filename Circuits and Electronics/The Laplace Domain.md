Created: 18/03/2023 at 16:58

In [[The Frequency Domain]], we showed we can represent circuit elements with an impedance which was a *complex number*.

In the *Laplace Domain*, we can represent circuit elements with an impedance which is a *complex function* of the complex variable $s$. We can then use KVL and KCL to generate algebraic equations in *s* describing the circuit. Independent sources are transformed in the Laplace domain as function *s*. We can solve these equations for unkowns and obtain them as functions of *s*.

We can transform the required voltage or current back to the time domain to find the *complete* response (both *natural* and *forced*). By transforming both in and out of the Laplace domain, it prevents us from having to solving complex equations in the time domain

### Benefits
- can include initial conditions
- obtain natural and forced response
- increased range of forcing functions available

### Unilateral Laplace Transform
AKA one-sided Laplace transform. This is where functions are $0$ where $t<0$.
$$F(s) = \mathscr{L}\vert f(t) \vert = \int_0^\inf f(t)e^{-st}dt$$

Where $s = \sigma + j \omega$ and exists if
$$\int_{0^-}^\inf \vert f(t) \vert e^{-\sigma t} dt < \inf$$

![[The Laplace Domain-1679143151608.jpeg]]

### Properties
![[The Laplace Domain-1679143570263.jpeg]]
![[The Laplace Domain-1679143590101.jpeg]]
![[The Laplace Domain-1679143607190.jpeg]]