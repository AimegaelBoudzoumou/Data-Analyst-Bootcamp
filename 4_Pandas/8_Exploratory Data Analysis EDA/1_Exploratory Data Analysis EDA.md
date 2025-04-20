# Exploratory Data Analysis in Pandas

## Importing modules
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```

## First Look at data

```python
df = pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\EDA\world_population.csv")

df
```

```python
pd.set_option('display.float_format', lambda x: '%.2f' % x)
```

## info()

```python
df.info()
```

## describe()

```python
df.describe()
```

## Counting all Null Values

```python
df.isnull().sum()
```

## Count of Unique Values

```python
df.nunique()
```

## Sorting on Values

```python
df.sort_values(by="2022 Population").head()
```

```python
df.sort_values(by="2022 Population", ascending=False).head(10)
```

## Correlation between columns

```python
df.corr(numeric_only = True) # Without "numeric_only = True", we get ValueError: could not convert string to float: 'AFG'
```

## Heatmap using Seaborn

```python
sns.heatmap(df.corr(numeric_only = True), annot = True)

plt.rcParams['figure.figsize'] = (20,7)

plt.show
```

## Grouping data

```python
df.groupby('Continent').mean(numeric_only=True)
```

```python
df[df['Continent'].str.contains('Oceania')]
```

```python
df.groupby('Continent').mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)
```

```python
df2 = df.groupby('Continent').mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)
df2
```

```python
df2.transpose()
```

```python
df2.plot()
```

```python
df3 = df2.transpose()
df3.plot()
```

```python
df2 = df.groupby('Continent')[['2022 Population',
       '2020 Population', '2015 Population', '2010 Population',
       '2000 Population', '1990 Population', '1980 Population',
       '1970 Population']].mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)

# or

df2 = df.groupby('Continent')[df.columns[5:13]].mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)

df2
```

```python
df3 = df2.transpose()
df3.plot()
```

## Visualizing Grouped Data

```python
df2 = df.groupby('Continent')[['1970 Population',
       '1980 Population', '1990 Population', '2000 Population',
       '2010 Population', '2015 Population', '2020 Population',
       '2022 Population']].mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)

df2
```

```python
df3 = df2.transpose()
df3
```

```python
df3.plot()
```

## Boxplots for Outliers

```python
df.boxplot(figsize=(20,10))
```

## Data Types of Columns

```python
df.dtypes
```

```python
df.select_dtypes(include='number')
```

```python
df.select_dtypes(include='object')
```

```python
df.select_dtypes(include='float')
```
