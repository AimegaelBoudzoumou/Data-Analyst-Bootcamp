# For Loops

```python
for x in range(7):
    print(x)
```

```python
text = 'Hello World!'

for x in range(len(text)):
    print(x)
```
0

1

2

3

4

5

6

7

8

9

10

11

```python
text = 'Hello World!'

for x in text:
    print(x)
```

H

e

l

l

o
 
W

o

r

l

d

!


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

```python
ice_cream_dict = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

for x in ice_cream_dict.keys():
    print(x)
```

## Nested For Loops

```python
ice_cream_dict = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

for cream in ice_cream_dict.values():
    print(cream)
    
    for key, value in ice_cream_dict.items():
        print(key, '->', value)
```
