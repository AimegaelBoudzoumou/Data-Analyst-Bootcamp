# Where Clause

```sql
SELECT * 
FROM employee_salary
WHERE first_name = 'Leslie'
;
```

```sql
SELECT * 
FROM employee_salary
WHERE salary > 50000
;
```

```sql
SELECT *
FROM employee_salary
WHERE salary >= 50000;
```

```sql
SELECT *
FROM employee_salary
WHERE salary < 50000;
```

```sql
SELECT *
FROM employee_salary
WHERE salary <= 50000;
```

```sql
SELECT *
FROM employee_demographics
WHERE gender = 'Female';
```

```sql
SELECT *
FROM employee_demographics
WHERE gender != 'Female';
```

```sql
SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01';
```

## AND OR NOT -- Logical Operators

```sql
SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01'
AND gender = 'male'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01'
OR gender = 'male'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE birth_date > '1985-01-01'
OR NOT gender = 'male'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE first_name = 'Leslie' AND age = 44
;
```

```sql
SELECT *
FROM employee_demographics
WHERE (first_name = 'Leslie' AND age = 44) OR age > 55
;
```

## LIKE Statement : % and _

```sql
SELECT *
FROM employee_demographics
WHERE first_name = 'Jerry'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE first_name = 'Jer'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'Jer'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'Jer%'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'er%'
;
```


```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE '%er%'
;
```


```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'a%'
;
```


```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'a__'
;
```


```sql
SELECT *
FROM employee_demographics
WHERE first_name LIKE 'a___%'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE birth_date LIKE '1989%'
;
```

```sql
SELECT *
FROM employee_demographics
WHERE birth_date LIKE '1989%'
;
```
