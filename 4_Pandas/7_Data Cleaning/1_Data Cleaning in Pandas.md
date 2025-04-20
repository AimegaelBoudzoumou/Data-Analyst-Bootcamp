# Data Cleaning in Pandas

## Connect to the datas
```python
import pandas as pd
df = pd.read_excel(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\Data Cleaning\Customer Call List.xlsx")
df
```

## Remove Duplicates Rows
```python
df = df.drop_duplicates()
df
```

## Remove Column
```python
df = df.drop(columns = "Not_Useful_Column")
df
```

## Manage of Last_Name column

Remove unnecessary characters : ..., /, _

```python
#df["Last_Name"] = df["Last_Name"].str.lstrip("...")
#df["Last_Name"] = df["Last_Name"].str.lstrip("/")
#df["Last_Name"] = df["Last_Name"].str.rstrip("_")

df["Last_Name"] = df["Last_Name"].str.strip("123._/")
df
```

## Manage of Phone_Number column
```python
df["Phone_Number"] = df["Phone_Number"].str.replace('[^a-zA-Z0-9]','')
```

```python
df["Phone_Number"] = df["Phone_Number"].str.replace('-','')
```

```python
df["Phone_Number"] = df["Phone_Number"].str.replace('/','')
```

```python
df["Phone_Number"] = df["Phone_Number"].str.replace('|','')
```

```python
df["Phone_Number"] = df["Phone_Number"].apply(lambda x: str(x))
```

```python
df["Phone_Number"] = df["Phone_Number"].apply(lambda x: x[0:3] + '-' + x[3:6] + '-' + x[6:10])
```

```python
df["Phone_Number"] = df["Phone_Number"].str.replace('nan--','')
```

```python
df["Phone_Number"] = df["Phone_Number"].str.replace('Na--','')
df
```

## Manage of Address column

```python
df[["Street_Address", "Street", "Zip_Code"]] = df["Address"].str.split(',', expand=True)
df
```

## Manage of "Paying Customer" column

Replace 'Yes' by 'Y' and 'No' by 'N'

```python
df["Paying Customer"] = df["Paying Customer"].str.replace('Yes','Y')

df["Paying Customer"] = df["Paying Customer"].str.replace('No','N')

df
```

## Manage of "Do_Not_Contact" column

Replace 'Yes' by 'Y' and 'No' by 'N'

```python
df["Do_Not_Contact"] = df["Do_Not_Contact"].str.replace('Yes','Y')

df["Do_Not_Contact"] = df["Do_Not_Contact"].str.replace('No','N')

df
```

## Replace all the 'N/a' by blank, inside the DataFrame :

```python
df = df.replace('N/a', '')
df = df.replace('NaN', '')

df
```

## Replace all the 'NaN' and 'None' by blank, inside the DataFrame :

```python
df = df.fillna('')

df
```

## Remove lines who have 'Do_Not_Contact' at 'Y'

```python
for x in df.index:
    if df.loc[x, "Do_Not_Contact"] == 'Y':
        df.drop(x, inplace=True)

df
```

## Remove all the lines who have not 'Phone_Number'

```sql
for x in df.index:
    if df.loc[x, "Phone_Number"] == '':
        df.drop(x, inplace=True)

df

# Other way to drop null values

df.dropna(subset="Phone_Number", inplace=True) # Remember : dropna, fillna, isna
```

## Reset the indexes

```python
df.reset_index()
```

## Reset the indexes

```python
df = df.reset_index(drop=True)

df
```
