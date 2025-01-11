# Triggers and Events

```sql
DELIMITER $$
CREATE TRIGGER employee_insert
  AFTER INSERT ON employee_salary
  FOR EACH ROW
BEGIN
  INSERT INTO employee_demographics (employee_id, first_name, last_name)
  VALUES (NEW.employee_id, NEW.first_name, NEW.last_name);
END $$
DELIMITER ;
```

### EVENTS

```sql
DELIMITER $$
CREATE EVENT delete_retirees
ON SCHEDULE EVERY 30 SECOND
DO
BEGIN
  DELETE
  FROM employee_demographics
  WHERE age >= 60;
END $$
DELIMITER ;

SHOW VARIABLES;

SHOW VARIABLES LIKE 'event%';
```
