# Converting Data Types

```python
num_int = 7

type(num_int) # int

num_str = '7'

type(num_str) # str
```

```python
num_sum = num_int + num_str # TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

```python
num_str_conv = int(num_str)

type(num_str_conv) # int

num_sum = num_int + num_str_conv

print(num_sum) # 14

type(num_sum) # int
```

```python
list_type = [1,2,3]

type(list_type) # list

type(tuple(list_type)) # tuple

list_type = [1,2,3,3,2,1,2,3,2,1,5]

set(list_type) # {1, 2, 3, 5}

type(set(list_type)) # set
```

```python
dict_type = {'name': 'Alex', 'age': 28, 'hair': 'N/A'}

type(dict_type) # dict

dict_type.items() # dict_items([('name', 'Alex'), ('age', 28), ('hair', 'N/A')])

type(dict_type.items()) # dict_items

```

```python
dict_type.keys() # dict_keys(['name', 'age', 'hair'])

type(dict_type.keys()) # dict_keys

dict_type.values() # dict_values(['Alex', 28, 'N/A'])

type(dict_type.values()) # dict_values
```

```python
print(list(dict_type.keys())) # ['name', 'age', 'hair']

type(list(dict_type.keys())) # list

type(list(dict_type.values())) # list
```

```python
long_str = 'I like to party'

print(list(long_str)) # ['I', ' ', 'l', 'i', 'k', 'e', ' ', 't', 'o', ' ', 'p', 'a', 'r', 't', 'y']
```
