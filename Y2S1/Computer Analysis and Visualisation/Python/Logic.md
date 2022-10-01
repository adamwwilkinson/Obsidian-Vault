# Logic
### Lazy Evaluation
Logic in Python uses lazy evaluation, this means in a case of:
```python
a and b
a or b
```
b is only evaluated if needed.

### deMorgan's Theorem
```python
not(a and b) == (not a) or (not b)
not(a or b) == (not a) and (not b)
```