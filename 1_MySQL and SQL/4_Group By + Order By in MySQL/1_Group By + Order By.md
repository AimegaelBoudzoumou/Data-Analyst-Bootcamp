# Group By + Order By

```sql
SELECT gender
FROM employee_demographics
GROUP BY gender
;
```

-- Error code
```sql
SELECT first_name
FROM employee_demographics
GROUP BY gender
;
```

```sql
SELECT gender, AVG (age)
FROM employee_demographics
GROUP BY gender
;
```

```sql
SELECT occupation
FROM employee_salary
GROUP BY occupation
;
```

```sql
SELECT occupation, salary
FROM employee_salary
GROUP BY occupation, salary
;
```

```sql
SELECT occupation, salary
FROM employee_salary
GROUP BY occupation, salary
;
```

```sql
SELECT gender, AVG (age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUP BY gender
;
```

## ORDER BY  

```sql
SELECT *
FROM employee_demographics
ORDER BY first_name
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY first_name ASC
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY first_name DESC
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY gender
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY gender, age
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY gender, age DESC
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY age, gender
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY 5, 4
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY 5, 4
;
```

```sql
SELECT *
FROM employee_demographics
ORDER BY 5, 4
;
```
