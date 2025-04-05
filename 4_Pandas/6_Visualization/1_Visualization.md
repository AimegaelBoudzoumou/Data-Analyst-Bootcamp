# Pandas Visualization

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

```python
df = pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\Pandas_Visualization\Ice Cream Ratings.csv")
df = df.set_index("Date")
df
```
![image](https://github.com/user-attachments/assets/bb3c2047-3f7c-4afc-b023-5b7bcafeeac7)


## Line

```python
df.plot()
```
![image](https://github.com/user-attachments/assets/fadbe42a-66c4-41e9-b210-5d31080a877d)

```python
df.plot(kind = 'line')
```
![image](https://github.com/user-attachments/assets/6b5ee839-87b2-44a5-a236-17dae79e037e)

```python
df.plot(kind = 'line', subplots = True)
```
![image](https://github.com/user-attachments/assets/1099c25e-0a5a-4a14-a0e9-dddfdce13603)


```python
df.plot(kind = 'line', title = "Ice Cream Ratings")
```
![image](https://github.com/user-attachments/assets/5a1e30fa-b4f2-420f-925b-709caf1c691e)


```python
df.plot(kind = 'line', title = "Ice Cream Ratings", xlabel = 'Daily Ratings', ylabel = 'Scores')
```
![image](https://github.com/user-attachments/assets/73710b07-2a18-459c-a5b7-9b1182922e23)


## Bar

```python
df.plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/813b285f-637f-429e-a8a7-2a97c9896e13)


```python
df.plot(kind='bar', stacked = True)
```
![image](https://github.com/user-attachments/assets/c22e3fb2-09c2-47a4-bd54-896a6ee085a0)


```python
df["Flavor Rating"].plot(kind='bar', stacked = True)
```
![image](https://github.com/user-attachments/assets/df41bdb9-1090-4953-8a26-5838ac3ea176)


```python
df.plot.barh(stacked = True)
```
![image](https://github.com/user-attachments/assets/43330209-0264-4a32-9584-d4b875bc098a)


## Scatter

```python
df.plot.scatter(x = 'Texture Rating', y = 'Overall Rating')
```
![image](https://github.com/user-attachments/assets/5aae31af-3561-442e-acd9-be71efb5ca1b)


```python
df.plot.scatter(x = 'Texture Rating', y = 'Overall Rating', s = 200, color = 'Yellow')
```
![image](https://github.com/user-attachments/assets/88acb776-c990-43fd-a241-5a3fe7824b54)


## Hist

```python
df.plot.hist()
```
![image](https://github.com/user-attachments/assets/47f9355a-8da0-4c92-99c7-ae78ffc11174)

```python
df.plot.hist(bins = 20)
```
![image](https://github.com/user-attachments/assets/37d32d50-b474-4425-a2c3-4f86b8aaa425)


```python
df.plot.hist(bins = 5)
```
![image](https://github.com/user-attachments/assets/a551c737-6c40-4843-8c06-44ca789900ee)


```python
df.plot.hist(bins = 100)
```
![image](https://github.com/user-attachments/assets/ed01d6df-b9d8-45f1-824e-7ec059ca583f)


```python
df.plot.hist(bins = 10) # by default
```
![image](https://github.com/user-attachments/assets/1a69a315-c657-4609-83a0-51f6c977b8b7)

## Boxplot

```python
df.boxplot()
```
![image](https://github.com/user-attachments/assets/bcca39a5-4e90-4b97-99bb-828f610089ba)


## Area

```python
df.plot.area()
```
![image](https://github.com/user-attachments/assets/7b7882bb-8d9b-4173-8870-fcfa025069d9)


```python
df.plot.area(figsize = (10,5))
```
![image](https://github.com/user-attachments/assets/ee42e797-6675-45a6-9a97-917a5ef15583)


## Pie

```python
df.plot.pie(y='Flavor Rating', figsize=(10,7))
```
![image](https://github.com/user-attachments/assets/01f47d62-f500-431e-9a25-38076f56d7e5)

### Make some syle 

```python
print(plt.style.available)
```
```
['Solarize_Light2', '_classic_test_patch', '_mpl-gallery', '_mpl-gallery-nogrid', 'bmh', 'classic', 'dark_background', 'fast', 'fivethirtyeight', 'ggplot', 'grayscale', 'seaborn-v0_8', 'seaborn-v0_8-bright', 'seaborn-v0_8-colorblind', 'seaborn-v0_8-dark', 'seaborn-v0_8-dark-palette', 'seaborn-v0_8-darkgrid', 'seaborn-v0_8-deep', 'seaborn-v0_8-muted', 'seaborn-v0_8-notebook', 'seaborn-v0_8-paper', 'seaborn-v0_8-pastel', 'seaborn-v0_8-poster', 'seaborn-v0_8-talk', 'seaborn-v0_8-ticks', 'seaborn-v0_8-white', 'seaborn-v0_8-whitegrid', 'tableau-colorblind10']
```

```python
plt.style.use('fivethirtyeight')
```

```python
df.plot(kind = 'line')
```
![image](https://github.com/user-attachments/assets/5f86829b-13bb-454c-81de-a86fda7d1aa7)

