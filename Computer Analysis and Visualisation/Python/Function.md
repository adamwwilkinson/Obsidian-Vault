# Function
*Real functions* return a result from given parameters, *procedures* do not return a value, rather modifies them or prints/displays results.

### Inbuilt
Some inbuilt functions include:
```python
round(x)
abs(x)
int(x)
```

### Local Variables
Variables whose *scope* is in the body of the function variable is used in.

### Default Parameters
A default parameter may be specified only if it's trailing.
```python
def star(var1, var2 = 0):
	block
```

### Keyword Parameters
When calling a function, you may not know the order of parameters, but rather what all parameters are called.
```python
star(var2 = 1, var1 = 3)
```

### Variable Parameters
*args and **kwargs are used to set variable parameters.
kwargs are for key, value pairs, while args are for non key arguments.
```python
def myFun(*args):
	for arg in args:
		print(arg)

def myFun2(**kwargs):
	for key, value in kwargs.items():
		print(key, value)
```
