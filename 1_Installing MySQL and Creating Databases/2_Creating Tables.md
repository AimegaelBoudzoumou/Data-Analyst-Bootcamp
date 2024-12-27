# Creating Tables

```sql
CREATE TABLE employee_demographics (
  employee_id INT NOT NULL,
  first_name VARCHAR2(50),
  last_name VARCHAR2(50),
  age INT,
  gender VARCHAR2(10),
  birth_date DATE,
  PRIMARY KEY (employee_id)
);

CREATE TABLE employee_salary (
employee_id INT NOT NULL,
first_name VARCHAR2(50) NOT NULL,
last_name VARCHAR2(50) NOT NULL,
occupation VARCHAR2(50),
salary INT,
dept_id INT
);
```
