# 1_Installing MySQL and  

## Installing MySQL

This is the tutorial of [Installing MySQL and Creating Databases](https://www.youtube.com/watch?v=wgRwITQHszU&list=PLUaB-1hjhk8FE_XZ87vPPSfHqb6OcM0cF&index=4)

## Creating Databases

```sql
DROP TABLE IF EXISTS `Parks_and_Recreation`;

CREATE DATABASE `Parks_and_Recreation`;

USE `Parks_and_Recreation`;

CREATE TABLE employee_demographics (
  employee_id INT NOT NULL,
  first_name VARCHAR2(50),
  last_name VARCHAR2(50),
  age INT,
  gender VARCHAR2(10),
  birth_date DATE,
  PRIMARY KEY (employee_id)
);


```
