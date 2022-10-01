# Exceptions
"Unexpected happenings". Such as accidentally dividing by zero. If this happens while the code running by default the program will automatically stop. Most of the time, we would prefer the code to continue and finish running if possible.

### How
```python
try: print(1.0 / n)
except: print(n, "not dividable")
```
Pylint will not accept this, as it's a generic error and tells us nothing.

### Specific Exceptions
```python
except TypeError: block
except ZeroDivisionError: block
else: code block
```

### Throw an Exception
```python
if value == 0:
	raise ValueError("Zero")
try: block
except ValueError as e:
	print("caught exception", e)
```