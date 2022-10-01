# Interpolation
Trying to predict what other data points might be using *known* data points.

### Linear Interpolation
Assumes data follows a straight line. Uses [[Numerical Python]].
```python
import numpy as np
import matplotlib.pyplot as plt
np.interp(x, xp, fp) # given discrete points xp and fp returns interpolated value at x

# Example
x_pts = np.linspace(0, 2*np.pi, 10) # 10 equidistant x coord
y_pts = np.sin(x_pts)
x_vals = np.linspace(0, 2*np.pi, 50) # 50 desired points
y_vals = np.interp(x_vals, x_pts, y_pts)
plt.plot(x_pts, y_pts, 'o') #plot known
plt.plot(x_vals, y_vals, '-x') # plot interpolated
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

### Interpolating [[Visualisation in Python#3D Plotting|3D Graphs]]
```python
from scipy import interpolate

def interpolate():
	x_pts = np.arrange(-5, 5, 1)
	y_pts = np.arrange(-5, 5, 1)
	x_vals, y_vals = np.meshgrid(x_pts, y_pts)
	# plotting function requires x and y values in a grid format
	z_vals = np.sin(x_vals) + np.cos(y_vals)

	f = interpolate.interp2d(x_pts, y_pts, z_vals, kind='linear') #linear interp
	#for cubic change kind value
	new_x_pts = np.arrange(-5, 5, 0.1)
	new_y_pts = np.arrange(-5, 5, 0.1)
	new_x_vals, new_y_vals = np.meshgrid(new_x_pts, new_y_pts)
	new_z_vals = f(new_x_pts, new_y_pts)
	plot_data(new_x_vals, new_y_vals, new_z_vals)
```
The *plot_data* function is from [[Visualisation in Python#3D Plotting|3D Graphs]].