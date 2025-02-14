# Group By and Aggregate Functions

This is the Tutorial's weblink : 

```python
import pandas as pd

df = pd.read_csv(r"Paath_To_File\Flavors.csv")

df
```

```python
group_by_frame = df.groupby('Base Flavor')

group_by_frame.mean()
```

ou en une seule ligne : 

```python
df.groupby('Base Flavor').mean()
```

```python
df.groupby('Base Flavor').count()
```

```python
df.groupby('Base Flavor').min()
```

```python
df.groupby('Base Flavor').max()
```

```python
df.groupby('Base Flavor').sum()
```

```python
df.groupby('Base Flavor').agg({'Flavor Rating': ['mean', 'max', 'count', 'sum']})
```

```python
df.groupby('Base Flavor').agg({'Flavor Rating': ['mean', 'max', 'count', 'sum'], 'Texture Rating': ['mean', 'max', 'count', 'sum']})
```

```python
df
```

```python
df.groupby(['Base Flavor', 'Liked']).mean()
```

```python
df.groupby(['Base Flavor', 'Liked']).agg({'Flavor Rating': ['mean', 'max', 'count', 'sum']})
```

```python
df.groupby('Base Flavor').describe()
```
