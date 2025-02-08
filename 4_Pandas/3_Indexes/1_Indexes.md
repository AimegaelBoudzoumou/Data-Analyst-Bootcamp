# Indexing

```python
import pandas as pd
```

```python
df = pd.read_csv(r"File_To_CSV_File")

df
```

```python
df = pd.read_csv(r"File_To_CSV_File", index_col = 'Country')

df
```

```python
df.reset_index(inplace=True)

df
```

```python
df.set_index('Country')

df
```

```python
df.set_index('Country', inplace = True)

df
```

```python
df.loc['Albania']
```

```python
df.iloc[1]
```

```python
df
```

```python
df.reset_index(inplace = True)

df
```

```python
df.set_index(['Continent','Country'], inplace=True)

df
```

```python
df.sort_index()

pd.set_option('display_max_columns', 235)

df.sort_index(ascending=True)

df.sort_index(ascending=False)

df.sort_index(ascending=[False, True])

df.sort_index()
```

```python
df.loc['Angola'] # Show an error

df.loc['Africa']

df.loc['Africa', 'Angola']
```

```python
df.iloc[1]
```
