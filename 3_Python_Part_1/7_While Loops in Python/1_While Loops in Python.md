# While Loops

```python
number = 0
while number < 5:
    print(number)
    number = number + 1
```

```python
number = 0
while number < 5:
    print(number)
    if number == 3:
        break
    number = number + 1
```

<!--
```python
number = 0
while number < 5:
    if number == 3:
        break
    print(number)
    number = number + 1
```
-->

```python
number = 0
while number < 5:
    print(number)
    if number == 6:
        break
    number = number + 1
else:
    print('No longer < 5')
```

```python
number = 0
while number < 5:
    print(number)
    if number == 3:
        break
    number = number + 1
else:
    print('No longer < 5')
```

Boucle indéfinie :

```python
number = 0
while number < 5:
    print(number)
    if number == 3:
        continue
    number = number + 1
else:
    print('No longer < 5')
```

La solution à la boucle inféfinie ci-dessus :
```python
number = 0
while number < 5:
    number = number + 1
    if number == 3:
        continue
    print(number)
else:
    print('No longer < 5')
```
