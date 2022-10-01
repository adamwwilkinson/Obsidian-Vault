# Loops
### Iteration
```python
for variable in list:
	block
```

### List Comprehension
```python
newlist = []
for x in list:
	if "a" in x:
		newlist.append(x)
```
instead can do this instead:
```python
newlist = [x for x in list is "a" in x]
```

### Counting Loop
```python
for i in range(0, 7):
	block
```
range(inclusive, exclusive, incrementer)

### Enumerate
Takes a sequence and returns a sequence of tuples of (index, value)
```python
for (i, num) in enumerate(nums):
	nums[i] - num * scalefactor
```

### While Loops
Useful when you don't know how long a sequence is.
```python
while condition:
	block
```

#### Continue and Break
*Break* is used in a loop to escape the loop, *continue* is used in a loop to return to the top of the loop.