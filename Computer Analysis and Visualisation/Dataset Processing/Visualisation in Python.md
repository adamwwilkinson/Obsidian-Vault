# Visualisation in Python
Uses Matplotlib package.
### Creating Graphs
```python
import matplotlib.pyplot as plt
plt.plot([1,2,3,4], color='red') # (0, 1) , (1, 2), (3, 4)
plt.ylabel('label')
plt.show()
plt.plot([xvalues], [yvalues])
plt.show()
plt.plot(df['Mes'], df['data science']) #many x-values cramp axis
plt.show()
```
The 'df' here is a reference to [[Pandas]].

#### Multiple Graphs
```python
plt.plot(df['Mes'], df['data science'], "g") #can add colour
plt.plot(df['Mes'], df['machine learningn'], "rx") #x indicates marker
plt.show()
```

### Adding Labels
```python
plt.plot(df['Mes'], df['data science'], label='datascience')
plt.xlabel('Date')
plt.ylabel('Popularity')
plt.title('Popularity of AI terms by date')
plt.legend()
```

### Fitting the x-axis
```python
plt.xticks(range(0, len(df['Mes']), len(df['Mes']) // 24), df['Mes'], rotation=90)
plt.tight_layout() #finds boundaries of graph and fits to display
```

### Subplot
Many seperate graphs in one window. Using the method subplot(rows, columns, location). Example uses [[Numerical Python|np]] methods.
```python
x=arramge(0, 10, 0.1)
plt.subplot(2, 1, 1)
plt.plot(x, np.sin(x))
plt.subsplot(2, 1, 2)
plt.plot(x, np.cos(x))
```

### 3D Plotting
```python
from mpl_toolkits.mplot3d import Axes3D
from matplotlib.pyplot as plt
import numpy as np

def plot_data(x, y, z):
	fig = plt.figure()
	ax = fig.add_subplot(111, projection='3d')
	surf = ax.plot_surface(x, y, z)
	plt.show()
```