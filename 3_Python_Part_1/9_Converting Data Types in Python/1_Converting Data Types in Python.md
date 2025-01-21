# Converting Data Types

```python
num_int = 7

print(type(num_int)) # int

num_str = '7'

print(type(num_str)) # str
```

```python
num_sum = num_int + num_str # Error
```

```python
num_str_conv = int(num_str)

print(type(num_str_conv))

num_sum = num_int + num_str_conv

print(num_sum)

print(type(num_sum)) # int
```

```python
list_type = [1,2,3]

print(type(list_type)) # list

print(type(tuple(list_type))) # tuple

list_type = [1,2,3,3,2,1,2,3,2,1,5]

print(set(list_type)) # {1, 2, 3, 5}

print(type(set(list_type))) # set
```

```python
dict_type = {'name': 'Alex', 'age': 28, 'hair': 'N/A'}

print(type(dict_type)) # class dict

print(dict_type.items())
print(type(dict_type.items())) # class 'dict_items'

print(dict_type.keys())
print(type(dict_type.keys())) # class 'dict_keys'

print(dict_type.values())
print(type(dict_type.values())) # class 'dict_values'

print(list(dict_type.keys())) # ['name', 'age', 'hair']

print(type(list(dict_type.keys()))) # class list

print(type(list(dict_type.values()))) # class list
```

```python
long_str = "I like to party"

print(list(long_str)) # ['I', ' ', 'l', 'i', 'k', 'e', ' ', 't', 'o', ' ', 'p', 'a', 'r', 't', 'y'] 
```
