# Solving Equations
Uses [[Symbolic Computation |SymPy]] to solve equations.

### Importing
```python
from sympy import Eq
from sympy.solvers import solve
```

### Methods
```python
x = symbols('x')
solve()
Eq(eqn1, (eqn2)) #equates the two statements
solve(Eq(x ** 3 - 6 * x ** 2, (6 - 11 * x)))
simplify(eqtn) #simplifies complex equations
eqn.subs(x, n) #substitute variable x with number n
Rational(1, 3) #represents 1/3 and will return a rational if used
```

### Systems of Equations
Can be done with the [[Symbolic Computation#Methods|solve()]] method.
In order to solve S.O.E:
$$ \Large z = 4x $$
$$ \LARGE x = y$$
$$ \LARGE z = x^2 + y^2$$

```python
x, y, z = symbols('x y z')
solve([z - 4*x,
	   x - y,
	   z - (x ** 2 + y ** 2)])
> [{x: 0, y: 0, z: 0}, {x: 2, y: 2, z: 8}]
```
[[Symbolic Computation#Methods|solve()]] here returns a list of dictionary objects.