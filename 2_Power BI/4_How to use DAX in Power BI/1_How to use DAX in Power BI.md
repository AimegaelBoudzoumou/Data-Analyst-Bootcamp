# How to use DAX in Power BI

This is the [tutorial](https://www.youtube.com/watch?v=vcijg0gUXSg&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=37&t=23s)


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


### 5. Adding Colum : SUMx (Profit_Column_SUMx)
```dax
Profit_Column_SUMx = SUMX('Apocolypse Sales', ('Apocolypse Store'[Price] - 'Apocolypse Store'[Production Cost]) * 'Apocolypse Sales'[Units Sold])
```
![image](https://github.com/user-attachments/assets/b89cd72a-c568-4b4f-9de9-06d81a03cb93)


### 6. Adding Column : Day of Week
```dax
Day of Week = WEEKDAY('Apocolypse Sales'[Date Purchased], 2)
```
![image](https://github.com/user-attachments/assets/fc2c8772-369a-415e-b3cd-b7c57b7ccb45)


### 7. "Date Purshased" And "Unit Sold"
![image](https://github.com/user-attachments/assets/f0ab9dc8-3fae-4764-9d67-180143926850)

![image](https://github.com/user-attachments/assets/332df684-c00f-4159-8f59-1263ba89effc)

![image](https://github.com/user-attachments/assets/5b7630a0-97e4-469d-a26a-cecc15df3f1a)

![image](https://github.com/user-attachments/assets/e27af106-81fd-42a4-8d86-73ab98edc147)


### 8. IF DAX
```dax
Order_Size = IF('Apocolypse Sales'[Units Sold]>25, "Big Order", "Small Order")
```
![image](https://github.com/user-attachments/assets/8973cb3b-65fb-45c4-898a-931151c66646)
