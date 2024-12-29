# Having vs Where

-- Error Code : Invalid use of group function

```sql
SELECT gender, AVG (age)
FROM employee_demographics
WHERE AVG(age) > 40
GROUP BY gender
;
```

```sql
SELECT gender, AVG (age)
FROM employee_demographics
GROUP BY gender
HAVING AVG(age) > 40
;
```

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
GROUP BY occupation
;
```

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation
;
```

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation
HAVING AVG(salary) > 75000
;
```
