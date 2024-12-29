# Select Statement

```sql
SELECT *
FROM employee_demographics;
```

```sql
SELECT first_name
FROM employee_demographics 
```

```sql
SELECT first_name,
last_name,
birth_date,
age,
age + 10
FROM employee_demographics 
```

```sql
SELECT first_name,
last_name,
birth_date,
age,
(age + 10) * 10
FROM employee_demographics 
```

```sql
SELECT first_name,
last_name,
birth_date,
age,
(age + 10) * 10 + 10
FROM employee_demographics 
```

## DISTINCT

```sql
SELECT DISTINCT gender
FROM employee_demographics
```

```sql
SELECT DISTINCT first_name, gender
FROM employee_demographics
```
