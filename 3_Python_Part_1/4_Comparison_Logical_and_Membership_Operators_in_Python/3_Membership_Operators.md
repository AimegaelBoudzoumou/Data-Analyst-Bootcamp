# Membership Operators

|   Operator |   Name |
|:-:    |:-:    |
|   in   |   Returns True if a sequence with the specified value is present in the object |
|   not in  |   Returns True if a sequence with the specified value is not present in the object |

```python
ice_cream = 'I love Chocolate ice cream'

print('love' in ice_cream) # True

print('love' in 'I love Chocolate ice cream')

print('love' not in ice_cream) # False

print('Love' in ice_cream) # False

scoops = [1,2,3,4,5]

print(2 in scoops) # True

print(6 not in scoops) # True

wanted_scoop = 8

print(wanted_scoop in scoops) # False

print(wanted_scoop not in scoops) # False
```
