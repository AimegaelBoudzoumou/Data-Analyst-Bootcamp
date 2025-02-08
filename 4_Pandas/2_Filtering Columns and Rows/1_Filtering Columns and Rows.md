# Filtering Columns and Rows

Assume we are in Jupier Notebook environment.


```python
import pandas as pd

df = pd.read_csv(r"Path_To_CSV_File")

df
```

```python
df[df['Rank'] <= 10]
```

```python
specific_countries = ['Bangladesh', 'Brazil', ]

df[df['Country'].isin(specific_countries)]
```

```python
df[df['Country'].str.contains('United')]
```

```python
df2 = df.set_index('Country')
df2
```

```python
df2.filter(items = ['Continent', 'CCA3'])
```

```python
df2.filter(items = ['Continent', 'CCA3'], axis = 0)
```

```python
df2.filter(items = ['Continent', 'CCA3', axis = 1)]
```

```python
df2.filter(items = ['Zimbabwe', axis = 0])
```

```python
df2.filter(like = 'United', axis = 0)
```

```python
df2.loc['United States']
```

```python
df2.iloc[3]
```

```python
df
```

```python
df[df['Rank'] < 10].sort_values(by='Rank', ascending=True)

df[df['Rank'] < 10].sort_values(by='Rank', ascending=False)
```

```python
df[df['Rank'] < 10].sort_values(by=['Rank', 'Country'], ascending=False)

df[df['Rank'] < 10].sort_values(by=['Country', 'Rank'], ascending=False)
```

```python
df[df['Rank'] < 10].sort_values(by=['Continent', 'Country'], ascending=False)

df[df['Rank'] < 10].sort_values(by=['Continent', 'Country'], ascending=[False, True])
```
