# Membership Operators

|   Operator |   Name |
|:-:    |:-:    |
|   in   |   Returns True if a sequence with the specified value is present in the object |
|   not in  |   Returns True if a sequence with the specified value is not present in the object |

```python
ice_cream = 'I love Chocolate ice cream'

'love' in ice_cream # True

'love' in 'I love Chocolate ice cream' # True

'love' not in ice_cream # False

'Love' not in ice_cream # True

'Love' in ice_cream # False

scoops = [1,2,3,4,5]

2 in scoops # True

6 not in scoops # True

wanted_scoop = 8

wanted_scoop in scoops # False

wanted_scoop not in scoops # True
```
