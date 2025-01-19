# Logical Operators

|   Operator |   Name |
|:-:    |:-:    |
|   and   |   Returns True if both statements are true |
|   or  |   Returns True if noe of the statement is true |
|   not   |   Reverse the result, results False if the result is true |

```python
(10 > 50) and (50 > 50) # False

print((70 > 50) and (50 > 10)) # True

print((10 > 50) or (50 > 10)) # True

print(('Vanilla' > 'Chocolate') or (50 > 10)) # True

print('Chocolate' > 'Vanilla') # False

print('Vanilla' > 'Chocolate') # True

print('W' < 'z') # True

print(('Vanilla' > 'Chocolate') and (50 > 10)) # True

print(not(50 > 10)) # False
```
