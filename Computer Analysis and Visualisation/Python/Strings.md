# Strings
They are *literals* which means they are constant. Can be indicated with a single, double or triple quote. I.e. ', '', '''
Also uses the [[Object Store]].

### Special Characters
\n - new line
\t - tab
\` - single quote, can be extended to double and triple
\xhh - character with hexadecimal value hh
\\ - backslash

### Operators
'+' - concatenation
'*' - repetition
'%' - formatting

### Objects
Strings are object, everything in python is stored as an object. Objects just contain data.

### Methods
capitalize()
strip([chars])
find(substring, begin, end)
lower()
upper()
startswith(prefix, start, end)
endswith(suffix, start, end)
split(delimeter)
format(value, value, ...)

#### Format
```python
name = "James Bond"
height = 123.4567
template = "Name: {0}, height: {1:.2f}"
print(template.format(name, height))
```
{n:w.pf}
{[argument number]: [field width].[decimal place][type]}