# 1_Joins

```sql
SELECT * 
FROM  employee_demographics;
```

```sql
SELECT * 
FROM  employee_salary;
```

```sql
SELECT * 
FROM  employee_demographics
INNER JOIN employee_salary
  ON employee_demographics.employee_id = employee_salary.employee_id
;
```

```sql
SELECT * 
FROM  employee_demographics AS dem
INNER JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
;
```

-- Error : Column 'employee_id' in field list is ambiguous
```sql
SELECT employee_id, age, occupation
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
;
```

```sql
SELECT dem.employee_id, age, occupation
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
;
```

## Outer Joins

```sql
SELECT *
FROM employee_demographics AS dem
LEFT JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
;
```

```sql
SELECT *
FROM employee_demographics AS dem
RIGHT JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
;
```

## Selft Join

```sql
SELECT *
FROM employee_salary
;
```

```sql
SELECT *
FROM employee_salary emp1
JOIN employee_salary emp2
  ON emp1.employee_id = emp2.employee_id
;
```

```sql
SELECT *
FROM employee_salary emp1
JOIN employee_salary emp2
  ON emp1.employee_id + 1 = emp2.employee_id
;
```

```sql
SELECT emp1.employee_id AS emp_santa,
emp1.first_name AS first_name_santa,
emp1.first_name AS last_name_santa,
emp2.employee_id AS emp_name,
emp2.first_name AS first_name_emp,
emp2.first_name AS last_name_emp,
FROM employee_salary emp1
JOIN employee_salary emp2
  ON emp1.employee_id + 1 = emp2.employee_id
;
```

## Joining multiple tables together

```sql
SELECT *
FROM employee_demographics AS dem
INNER JOIN employee_salary AS sal
  ON dem.employee_id = sal.employee_id
INNER JOIN parks_departments pd
  ON sal.dept_id = pd.department_id
;
```
