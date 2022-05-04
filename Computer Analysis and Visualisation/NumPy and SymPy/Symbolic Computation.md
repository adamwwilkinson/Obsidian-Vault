# Symbolic Computation
A [[Module|module]] for python that allows for more complex maths.
## Importing and Symbols
```python
from sympy import symbols, diff
x, y - symbols ('x y')
y = x ** 2
diff(y)
> 2*x
```
## Init Session
Starts a SymPy console to ease use and display of formulas.
```python
init_session()
```
## Methods
```python
diff(x)
diff(eqtn, x, n) #diff n times, with respect to x
integrate(x)
integrate(eqtn, (x, lower, upper)) #definite integration 
cos(x)
sin(x
solvers.solve(equation) #if not specified solves for 0
```