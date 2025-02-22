# Data Types

Note : Assume we are  in Jupyter Notebook

<!--Note : use print(type(something)) to see the result of print() method.-->

### int, float, complex

```python
type(12) # int

type(-12) # int

type(-12 + 100) # int

type(-12 + 10.25) # float

type(-12 + 3j) # complex

type(-12 + 3c) # SyntaxError: invalid decimal literal
```

### Boolean

```python
type(True) # bool

type(False) # bool

type (1 > 5) # bool

1 == 1 # True
```

## Strings

```python
'Sigle Quote'

"Double Quote"

multiline = """
The ice cream vanquished
my longing for sweets,
upon this diet I look away,
it no longerexists on this day.

"""

print(multiline)

"I've always wanted to eat a gallon of ice cream."

"""
I've always wanted to eat a gallon of "ice cream."
"""

type(multiline) # str
```

```python
a = 'Hello World!'

print(a[:5]) # Hello

print(a[6]) # W

print(a[-3]) # l

print(a[2:5]) # llo

a*3 # 'Hello World!Hello World!Hello World!'

a + a # 'Hello World!Hello World!'
```

## list

```python
[1,2,3] # [1, 2, 3]

['Cookie Dough', 'Strawberry', 'Chocolate'] # ['Cookie Dough', 'Strawberry', 'Chocolate']

['Vanilla', 3, ['Scoops', 'Spoon'], True] # ['Vanilla', 3, ['Scoops', 'Spoon'], True]

ice_cream = ['Cookie Dough', 'Strawberry', 'Chocolate']

ice_cream # ['Cookie Dough', 'Strawberry', 'Chocolate']

ice_cream.append('Salted Caramel')

ice_cream # ['Cookie Dough', 'Strawberry', 'Chocolate', 'Salted Caramel']

ice_cream[0] = 'Butter Pecan'

['Butter Pecan', 'Strawberry', 'Chocolate', 'Salted Caramel']

nest_list = ['Vanilla', 3, ['Scoops', 'Spoon'], True]

nest_list[0] # 'Vanilla'

nest_list[2] # ['Scoops', 'Spoon']

nest_list[2][1] # 'Spoon'

```

#### List methods
- add to List : append(), inser(), extend(), List Concatenation (using of __+__ operator)
- remove from List : remove(), poop()
- other methods : index(), copy(), reverse(), count(), sort(), clear()

## tuple

```python
tuple_scoops = (1,2,3,2,1)

type(tuple_scoops) # tuple

tuple_scoops[0] # 1

tuple_scoops.append(3) # AttributeError : 'tuple' object has no attribute 'append'
```

## sets

```python
daily_pints = {1,2,3}

type(daily_pints) # set

print(daily_pints) # {1,2,3}

daily_pints_log = {1,2,3,2,3,4,1,2,5,6,3,2}

print(daily_pints_log) # {1,2,3,4,5,6, 31}

wifes_daily_pints_log = {1,3,5,7,3,24,5,7,3,2,0}

print(daily_pints_log | wifes_daily_pints_log) # {0,1,2,3,4,5,6,7, 24, 31}

print(daily_pints_log & wifes_daily_pints_log) # {1, 2, 3, 5}

print(daily_pints - wifes_daily_pints_log) # {4, 6, 31}

print(wifes_daily_pints_log - daily_pints_log) # {0, 24, 7}

print(wifes_daily_pints_log ^ daily_pints_log) # {0, 4, 6, 7, 24, 31}
```

## dictionnaries

```python
# Key/Value Pair

dict_cream = {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC','Chocolate']}

type(dict_cream) # dict

print(dict_cream) # {'name': 'Alex Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC','Chocolate']}

dict_cream.values() # dict_values(['Alex Freberg', 5, ['MCC','Chocolate']])

dict_cream.keys() # dict_keys(['name', 'weekly intake', 'favorite ice creams'])

dict_cream.items() # dict_items([('name', 'Alex Freberg'), ('weekly intake', 5), ('favorite ice creams', ['MCC', 'Chocolate'])])

dict_cream[0] # KeyError: 0

dict_cream['name'] # Alex Freberg

dict_cream['name'] = 'Christine Freberg'

print(dict_cream) # {'name': 'Christine Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate']}

# dict_cream.update({'name': 'Christine Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC','Chocolate']})


dict_cream.update({'name': 'Christine Freberg', 'weekly intake': 5, 'weight': 300})

print(dict_cream) # {'name': 'Christine Freberg', 'weekly intake': 5, 'favorite ice creams': ['MCC', 'Chocolate'], 'weight': 300}

dict_cream.update({'name': 'Christine Freberg', 'weekly intake': 10, 'weight': 300})

print(dict_cream) # {'name': 'Christine Freberg', 'weekly intake': 10, 'favorite ice creams': ['MCC', 'Chocolate'], 'weight': 300}

del dict_cream['weight']

print(dict_cream) # {'name': 'Christine Freberg', 'weekly intake': 10, 'favorite ice creams': ['MCC', 'Chocolate']}
```
