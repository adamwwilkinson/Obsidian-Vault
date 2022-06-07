# Curve Fitting
Collected data will always have some degree of error, [[Interpolation]] is used with the assumption that all data points are accurate. This is why we use curve fitting  to 'fix' this.

### Linear Regression
Minimises the square of the errors, where the error is the distance each point is from the line.
```python
import numpy as np
import matplotlib.pyplot as plt
x_pts = np.arrange(0, 6, 1) # x values to use later
y_pts = np.array([15, 10, 9, 6, 2, 0])

# linear regression
points = np.polyfit(x_pts, y_pts, 1) # last number is degree
x_vals = np.linspace(0, 6, 100) # x values for linear regression
y_vals = np.polyval(points, x_vals) # linear regression y values

plt.plot(x_pts, y_pts, '.')
plt.plot(x_vals, y_vals, '-')
```