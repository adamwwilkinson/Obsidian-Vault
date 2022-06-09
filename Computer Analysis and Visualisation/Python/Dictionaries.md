# Dictionaries
Made of 2 components, keys and values.
Keys form a [[Sets|set]], and values are mutable.
Defined by {}, e.g. {'banana' : 3, 'apple' : 1}.

### Methods
```python
if key in dictionary:
	block
fruit_counts['mango'] = 42 # add and modify
fruit_counts.pop('mango')
fruit_counts.clear()
fruit_counts.get('key')
fruit_counts.get('key', value if not)
fruit_counts.items() # weird list of key and values
fruit_counts.keys() # list of keys
fruit_counts.values() # list of values
fruit_counts.update(dict) # merges dictionary


keys_list = ["a", "b"]
value_list - [1, 2]
dictionary = dict(zip(keys_list, value_list))

for item in dict:
	print(item, dict[item])
for (key, value) in fruit_counts.item():
	print key, value
```

