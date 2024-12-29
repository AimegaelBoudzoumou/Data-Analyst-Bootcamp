# Limit + Aliasing

```sql
SELECT * 
FROM employee_demographics
LIMIT 3
;
```

```sql
SELECT * 
FROM employee_demographics
ORDER BY age DESC
LIMIT 3
;
```

```sql
SELECT * 
FROM employee_demographics
ORDER BY age DESC
LIMIT 2, 1
;
```

```sql
SELECT * 
FROM employee_demographics
ORDER BY age DESC
LIMIT 2, 1
;
```

## Aliasing

```sql
SELECT gender, AVG(age) 
FROM  employee_demographics
GROUP BY gender
;
```

```sql
SELECT gender, AVG(age) AS avg_age
FROM  employee_demographics
GROUP BY gender
HAVING age_age > 40
;
```

```sql
SELECT gender, AVG(age) avg_age
FROM  employee_demographics
GROUP BY gender
HAVING age_age > 40
;
```
