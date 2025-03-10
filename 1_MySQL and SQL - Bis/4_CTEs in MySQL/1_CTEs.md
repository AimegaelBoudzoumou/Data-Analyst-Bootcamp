# CTEs -- Common Table Expressions

```sql
SELECT gender, AVG(salary), MAX(salary), MIN(salary), COUNT(salary)
FROM employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id
GROUP BY gender;
```

```sql
WITH CTE_Example (Gender, AVG_Sal, MAX_Sal, MIN_Sal, COUNT_Sal) AS
(
SELECT gender, AVG(salary) avg_sal, MAX(salary) max_sal, MIN(salary) min_sal, COUNT(salary) count_sal
FROM employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id
GROUP BY gender
)
SELECT AVG(avg_sal) -- test this : select avg(`AVG(salary)`)
FROM CTE_Example
;
```

The next SQL code is equal to the above : 
```sql
SELECT AVG(avg_sal)
FROM (
SELECT gender, AVG(salary) avg_sal, MAX(salary) max_sal, MIN(salary) min_sal, COUNT(salary) count_sal
FROM employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id
GROUP BY gender
) example_subquery
;
```

This code produce the _Error code 1145 : table CTE_Example doesn't exist_
```sql
SELECT AVG(avg_sal)
FROM CTE_Example
```

```sql
WITH CTE_Example AS
(
SELECT employee_id, gender, birth_date
FROM employee_demographics
WHERE birth_date > '1985-01-01'
),
CTE_Example2 AS
(
SELECT employee_id, salary
FROM employee_salary
WHERE salary > 50000
)
SELECT *
FROM CTE_Example
JOIN CTE_Example2
  ON CTE_Example.employee_id =  CTE_Example2.employee_id
;
```
