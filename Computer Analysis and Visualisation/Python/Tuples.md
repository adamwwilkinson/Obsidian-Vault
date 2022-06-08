# Tuples
Similar to [[Computer Analysis and Visualisation/Python/List]] but use a '()'.
Unlike [[Computer Analysis and Visualisation/Python/List]] tuples are immutable, and only have 2 methods: count and index.

### When to use What
List when data is homogenous, tuples when data is inhomogeneous.
Also, tuples are useful if describing a single object.

### Parallel Assignment
```python
person = ("Fred", "Bloggs", 27)
...
(first_name, last_name, age) = person
...
for f, l, a in personlist:
	print(f, l, a)
```

### Sorting Tuples
```python
list_of_tuples.sort(key= lambda x: x[n]) # n is column to sort
```