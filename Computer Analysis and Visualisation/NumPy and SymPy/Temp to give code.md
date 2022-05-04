```python
import numpy as np  
  
  
def larger_sum(npfile1, npfile2):  
    """takes two numpy file names (string) of numpy array types  
    (i.e., type .npy), and prints the filename and the 
    sum difference between the two files"""    
    arr1 = np.load(npfile1)  
    arr2 = np.load(npfile2)  
    if np.sum(arr1) > np.sum(arr2):  
        diff = np.sum(arr1) - np.sum(arr2)  
        filename = npfile1  
    else:  
        diff = np.sum(arr2) - np.sum(arr1)  
        filename = npfile2  
    print(f"{filename}: {diff:.4f}")  
rainfall = [0.2, 0.0, 1.6, 4.8, 0.0, 1.2, 1.4]  
rainfall2 = [3.6, 2.2, 0.0, 0.2, 0.0, 0.3, 1.3]  
np.save("file1.npy", np.array(rainfall))  
np.save("file2.npy", np.array(rainfall2))  
larger_sum("file1.npy", "file2.npy")  
rainfall = [0.2, 0.0]  
rainfall2 = [3.6]  
np.save("file1.npy", np.array(rainfall))  
np.save("file2.npy", np.array(rainfall2))  
larger_sum("file1.npy", "file2.npy")
```