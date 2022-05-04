# Numerical Python
Is a [[Module|module]] that contains n-dimension array objects, better maths functions and is useful for linear algebra.

### Arrays
Arrays are homogenous, multidimension, fast, and mutable. A 1-d array is a vector and 2-d array's are matrices. Can add arrays together and can use scalers on arrays.

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