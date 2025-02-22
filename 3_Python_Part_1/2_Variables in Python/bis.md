# Variables in Python

```python
x = 22

print(x)

type(x)

y = 'Mint Chocolate Chip'

print(y)

type(y)

y = 'Chocolate'

Y = 'Mint Chocolate Chip'

print(Y)

x,y,z = 'Chocolate', 'Vanilla', 'Rocky Road'

print(x)
print(y)
print(z)

x = y = z = 'Root Beer Float'

print(x)
print(y)
print(z)

ice_cream = ['Chocolate', 'Vanilla', 'Rocky Road']

x,y,z = ice_cream

print(x)
print(y)
print(z)
```

```python
# Camel Case

# Test Variable Case

testVariableCase = 'Variable Swirl'
```

```python
# Pascal Case

# Test Variable Case

TestVariableCase = 'Variable Swirl'
```

```python
# Snake Case

# Test Variable Case

test_variable_case = 'Variable Swirl'
```

```python
testvar = 'Vanilla Swirl'
test_var = 'Vanilla Swirl'
_test_var = 'Vanilla Swirl'
testVar = 'Vanilla Swirl'
TestVar = 'Vanilla Swirl'
testVar2 = 'Vanilla Swirl'
```

```python
#2testVar = 'Vanilla Swirl' # SyntaxError: invalid decimal literal

test-var2 = 'Vanilla Swirl' # SyntaxError: cannot assign to expression here. Maybe you meant '==' instead of '='?

test Var2 = 'Vanilla Swirl' # SyntaxError: invalid syntax
  
test,Var2 = 'Vanilla Swirl' # ValueError: too many values to unpack (expected 2)

```

```python
x = 'Ice Cream is my favorite' + '.'

print(x)
```

```python
x = 'Ice Cream is my favorite' + 2

print(x) # TypeError: can only concatenate str (not "int") to str

```

```python
y = 3 + 2

print(y)
```

```python
x ='Ice Cream'
y = ' is'
z = ' my favorite.'

print(x+y+z)
```

```python
x = 1
y = 2
z = 3

print(x+y+z)
```

```python
x = 'Ice Cream'
y = 2

print(x+y) # TypeError: can only concatenate str (not "int") to str

```

```python
x = 'Ice Cream'
y = 2

print(x,y)
```
