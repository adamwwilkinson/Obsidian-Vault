# Interpolation
Trying to predict what other data points might be using *known* data points.

### Linear Interpolation
Assumes data follows a straight line. Uses [[Numerical Python]].
```python
import numpy as np
import matplotlib.pyplot as plt
np.interp(x, xp, fp)

# Example
x_pts = np.linspace(0, 2*np.pi, 10)
y_pts = np.sin(x_pts)
x_vals = np.linspace(0, 2*np.pi, 50)
y_vals = np.interp(x_vals, x_pts. y_points)
ply.ploy(x_pts, y_pts, 'o')
ply.plot(x_vals, y_vals, '-x')
```

### Cubic Spline Interpolation
Use if you know graph should have smooth lines.
```python
from scipy import interpolate
splines = interpolate.splrep(x_pts, y_pts)
y_vals = interpolate.splev(x_vals, splines)
ply.ploy(x_pts, y_pts, 'o')
ply.plot(x_vals, y_vals, '-x')
```
Can also use *interpolate.interpld*.