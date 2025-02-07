# Reading in Files

Assume we are in Jupiter Notebokk environment.

```python
import pandas as pd

df = pd.read_csv(r"Path_To_CSV_File") # put the real file path later

df = pd.read_csv(r"Path_To_CSV_File", header = None)

df = pd.read_csv(r"Path_To_CSV_File", header = None, names = ['Country', 'Region'])

df
```

```python
df = pd.read_csv(r"Path_To_Text_File")

df = pd.read_csv(r"Path_To_Text_File", sep = '\t')
df
```

```python
df = pd.read_table(r"Path_To_Text_File")
df

df = pd.read_table(r"Path_To_Text_File", sep = ',')
df
```

```python
df = pd.read_table(r"Path_To_CSV_File", sep = ',')
df
```

```python
df = pd.read_json(r"Path_To_Json_File")
df
```


```python
df = pd.read_excel(r"Path_To_Excel_File") # xlsx filetype
df

df = pd.read_excel(r"Path_To_Excel_File", sheet_name = 'sheet1')
df
````

```python
pd.set_option('display.max.rows', 235)

pd.set_option('display.max.columns', 40)
````

```python
df2 = pd.read_excel(r"Path_To_Excel_File", sheet_name = 'sheet1')
df2.info()
````


```python
df2.shape
````


```python
df2.head()

df2.head(10)
````


```python
df2.tail(10)
````

```python
df2['Rank']
````


```python
df2.loc[224]
````


```python
df2.iloc[224]
````

```python
df2.loc['Uzbekistan']
````
