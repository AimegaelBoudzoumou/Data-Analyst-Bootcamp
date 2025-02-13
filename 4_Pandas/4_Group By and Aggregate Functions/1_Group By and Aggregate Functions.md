# Group By and Aggregate Functions

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
df.group_by_frame.mean().mean()
```

```python
df.group_by_frame.mean().count()
```

```python
df.group_by_frame.mean().min()
```

```python
df.group_by_frame.mean().max()
```

```python
df.group_by_frame.mean().sum()
```

```python
df.group_by_frame.mean().agg({'Flavor Rating': ['mean', 'max', 'count', 'sum']})
```

```python
df.group_by_frame.mean().agg({'Flavor Rating': ['mean', 'max', 'count', 'sum'], 'Texture Rating': ['mean', 'max', 'count', 'sum']})
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
