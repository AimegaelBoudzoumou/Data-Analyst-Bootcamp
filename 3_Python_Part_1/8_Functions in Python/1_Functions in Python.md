# Functions

```python
def first_func():
    print('We did it!')

first_func()
```

```python
def number_squared(number):
    print(number**2)

number_squared(5)
```

```python
def number_squared_cust(number,power):
    print(number**power)

number_squared_cust(5,3) # 125
```

```python
def number_args(*number):
    print(number[0]*number[1])

number_args(5,6,1,2,8) # 30
```

```python
args_tuple = (5,6,1,2,8)

def number_args(*number):
    print(number[1]*number[3])

number_args(*args_tuple) # 12
```

```python
def number_squared_cust(number,power):
    print(number**power)

number_squared_cust(power = 5, number = 3) # 243
```

```python
def number_kwarg(**number):
    print('My number is : ' + number['integer'])

number_kwarg(integer = '2309')



def number_kwarg(**number):
    print('My number is : ' + number['integer'] + 'My other number: ' + number['integer2'])

number_kwarg(integer = '2309', integer2 = '349')
```
