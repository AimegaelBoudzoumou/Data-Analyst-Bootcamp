# Subqueries

```sql
SELECT *
FROM employee_demographics
WHERE employee_id IN
                ( SELECT employee_id
                  FROM employee_id
                  WHERE dept_id = 1)
;
```

```sql
SELECT first_name, salary,
(SELECT AVG(salary)
FROM employee_salary)
FROM employee_salary;
```

```sql
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender;
```

```sql
SELECT *
FROM
(
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender
) AS Agg_table
;
```

Without the above alias _Agg_table_, we obtain the _Error Code 1248. Every derivated table must have its own alias_

The next SQL code produce the _Error Code : 1054. Unknown column 'age' in field list_

```sql
SELECT gender, AVG(MAX(age))
FROM
(
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender
) AS Agg_table
;
```

This SQL code also is false. I get the _Error Code : 1140. In aggregated query without GROUP BY, expression of SELECT list contains nonaggregated column_

```sql
SELECT gender, AVG(`MAX(age)`)
FROM
(
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender
) AS Agg_table
;
```

The solution consist to add _GROUP BY gender_

```sql
SELECT gender, AVG(`MAX(age)`)
FROM
(
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender ) AS Agg_table
GROUP BY gender
;
```

```sql
SELECT AVG(`MAX(age)`)
FROM
(
SELECT gender, AVG(age), MAX(age), MIN(age), COUNT(age)
FROM employee_demographics
GROUB BY gender ) AS Agg_table
;
```
The advantage of using aliases : 

```sql
SELECT AVG(max_age)
FROM
(
SELECT gender,
AVG(age) AS avg_age,
MAX(age) AS max_age,
MIN(age) AS min_age,
COUNT(age)
FROM employee_demographics
GROUB BY gender ) AS Agg_table
;
```
