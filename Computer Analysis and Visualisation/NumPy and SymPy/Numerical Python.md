# Numerical Python
Is a [[Module|module]] that contains n-dimension array objects, better maths functions and is useful for linear algebra.

### Arrays
Arrays are *homogenous, multidimension, fast, and mutable*. A 1-d array is a vector and 2-d array's are matrices. Can add arrays together and can use scalers on arrays.

#### Creating Arrays
```python
import numpy
array1 = numpy.array([0, 1, 2, 3])
matrix1 = numpy.array([[0, 1, 2], [3, 4, 5]])
matrix[1][2]
> 5
matrix2 = numpy.array([0, 1, 2, 3, 4, 5])
matrix2[[1, 3, 4]] = 4
> [0, 4, 2, 3, 4, 4]
```

#### Slicing
```python
import numpy as np
array = np.array([[0, 1, 2], [3, 4, 5]])
array[1:]
> [3, 4, 5]
```

#### Aliasing and Prevention
```python
alias = rainfall[:, 2:4] #affects original array
new = rainfall[:. [2, 3]] #does not affect original array
new2 = np.copy(rainfall[:, 2:4]) #also does not affect original array
```

### Functions
#### Creation
```python
np.zeroes([r, c])
np.ones()
np.eyes([r, c]) # leading diagonal of ones
np.arange(start, end, steps)
np.linspace(start, end, points)
np.array(list1)
np.partition(array, n_smallest_values)
```

#### Other Functions
```python
np1.where(x > 0) # gives indexes of where condition
np.count_nonzeros(array1 >= 10) # gives number of elements above
```

#### Reshaping
```python
array.shape # returns rows by columns
np.reshape(array, size) # if -1 flattens to 1 dimension
array.T # returns the transposed array
```

#### Saving and Loading
```python
np.save('ex.txt', array)
np.load('ex.txt')
np.savetxt('ex.csv', array, delimiter= ',')
np.loadtxt('ex.csv', delimiter= ',')
```

#### Sorting
```python
data = np.array([3, 2, 1])
np.sort(data) # sorts from smallest to largest
-np.sort(-data) # sorts from largest to smallest
arrayx.sort(axis= 0) # sorts by columns, if axis= -1 sorts row
```

### Looping
Can be used to find approximate values.
```python
value = np.arrange(0, math.pi, skip)

```