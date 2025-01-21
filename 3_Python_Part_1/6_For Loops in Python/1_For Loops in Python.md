# For Loops

```python
integers = [1,2,3,4,5]

for number in integers:
    print(number)

for number in integers:
    print('yep')
```

```python
integers = [1,2,3,4,5]

for Jelly in integers:
    print(Jelly + Jelly)
```

```python
ice_cream_dict = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

for cream in ice_cream_dict.values():
    print(cream)
```

```python
ice_cream_dict = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

for key, value in ice_cream_dict.items():
    print(key, '->', value)
```

## Nested For Loops

```python
ice_cream_dict = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

for cream in ice_cream_dict.values():
    print(cream)

for key, value in ice_cream_dict.items():
    print(key, '->', value)
```
