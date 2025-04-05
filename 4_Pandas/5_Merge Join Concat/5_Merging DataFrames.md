# Merge, Join, and Concatenate

```python
df1 = pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\Merge_Join_Concatenate\LOTR.csv")
df1
```

```python
df2 = pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\Merge_Join_Concatenate\LOTR 2.csv")
df2
```

## Merge : inner, outer, left, right, cross

```python
df1.merge(df2)
```

### inner
```python
df1.merge(df2, how = 'inner')
```

```python
df1.merge(df2, how = 'inner', on = 'FellowshipID')
```

```python
df1.merge(df2, how = 'inner', on = ['FellowshipID', 'FirstName'])
```

### outer

```python
df1.merge(df2, how = 'outer')
```

### left

```python
df1.merge(df2, how = 'left')
```

### right

```python
df1.merge(df2, how = 'right')
```

### cross

```python
df1.merge(df2, how = 'cross')
```


## Join

```python
df1.join(df2, on = 'FellowshipID', how = 'outer', lsuffix = '_Left',rsuffix = '_Right')
```

```python
df4 = df1.set_index('FellowshipID').join(df2.set_index('FellowshipID'), lsuffix = '_Left',rsuffix = '_Right')
df4
```

```python
df4 = df1.set_index('FellowshipID').join(df2.set_index('FellowshipID'), lsuffix = '_Left',rsuffix = '_Right', how = 'outer')
df4
```

## Concatenate

```python
pd.concat([df1, df2])
```

```python
pd.concat([df1, df2], join = 'inner')
```

```python
pd.concat([df1, df2], join = 'outer')
```

```python
pd.concat([df1, df2], join = 'outer', axis = 1)
```

```python
df1.append(df2) # AttributeError: 'DataFrame' object has no attribute 'append'
```
