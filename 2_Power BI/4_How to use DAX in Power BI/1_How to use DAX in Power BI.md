# How to use DAX in Power BI

### 1. Count of sales
```dax
Count of Sales = COUNT('Apocolypse Sales'[Order ID])
```
![image](https://github.com/user-attachments/assets/b0413561-8cc7-4a6c-a3ff-9ce35348cbfc)


### 2. Sum of Products Sold
```dax
Sum of Products Sold = SUM('Apocolypse Sales'[Units Sold])
```
![image](https://github.com/user-attachments/assets/6b44328f-049f-409e-a0c8-2aa5a03b340f)


### 3. Profit
```dax
Profit = (SUM('Apocolypse Store'[Price]) - sum('Apocolypse Store'[Production Cost])) * SUM('Apocolypse Sales'[Units Sold])
```
![image](https://github.com/user-attachments/assets/d548a787-4c04-4455-b925-1a1b405c75f0)


### 4. Nouvelle colonne
![image](https://github.com/user-attachments/assets/2085f310-4193-43fc-8d63-f5d7c6e282b1)


### 5. SUMx (Profit_Column_SUMx)
![image](https://github.com/user-attachments/assets/b89cd72a-c568-4b4f-9de9-06d81a03cb93)
