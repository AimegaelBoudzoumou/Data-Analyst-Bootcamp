# Window Functions

```sql
SELECT gender, AVG(salary) AS avg_salary
FROm employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id
GROUP BY gender;
```

```sql
SELECT dem.first_name, dem.last_name, gender, AVG(salary) OVER(PARTITION BY gender)
FROm employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id;
```

```sql
SELECT dem.first_name, dem.last_name, gender, salary,
SUM(salary) OVER(PARTITION BY gender ORDER BY dem.employee_id) AS Rolling_Total
FROm employee_demographics dem
JOIN employee_salary sal
  ON dem.employee_id = sal.employee_id;
```

