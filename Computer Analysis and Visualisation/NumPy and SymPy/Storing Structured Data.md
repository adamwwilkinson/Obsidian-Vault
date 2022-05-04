# Storing Structured Data
[[Numerical Python#Arrays|NumPy arrays]] only store simple homogenous data types.
How can we have complex records of different data types in an array?

### Specifying Types
Can specify using 'dtype'
```python 
np.array(a, dtype=float)
```
### Creating NumPy Arrays with Different Types
```python
people = np.array([
	('Alice', 25, 156.2),
	('Cathy', 37, 169.7)],
	dtype = [('name', '<U10'), ('age', '<i8'), ('height', 'f8')])
```
### Accessing Structured Records and Filtering
```python
people[1]['name']
> Alice
 
people[np.where(people['age'] < 30)]
> Alice
```
