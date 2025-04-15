# Data Cleaning in Pandas

```python
# Connect to the datas
import pandas as pd
df = pd.read_excel(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\Data Cleaning\Customer Call List.xlsx")
df
```

```python
# Remove Duplicates Rows
df = df.drop_duplicates()
df
```

```python
# Remove Column
df = df.drop(columns = "Not_Useful_Column")
df
```

```python
# Manage of Last_Name column

#df["Last_Name"] = df["Last_Name"].str.lstrip("...")
#df["Last_Name"] = df["Last_Name"].str.lstrip("/")
#df["Last_Name"] = df["Last_Name"].str.rstrip("_")

df["Last_Name"] = df["Last_Name"].str.strip("123._/")
df
```

```python
# manage of Phone_Number column -- 13:25

```
