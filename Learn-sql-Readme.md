# Learn MySQL

The SQL stands for **S**tructured **Q**uery **L**anguage.

It stores the data as a table modal.

---

## 1. Create a Database

```
CREATE DATABASE employee_db;
```

---

## 2. Select Database

```
USE employee_db;
```

## 3. Delete Database

```
DROP DATABASE employee_db;
```
---

## 3. Create a Table

```

CREATE TABLE employee_table (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    employee_name VARCHAR(100) NOT NULL,
    employee_age INT not null,
    department_name VARCHAR(50) NOT NULL,
    dob DATE NOT NULL
);

 ```

## Describle table 

```
DESCRIBE employee_table;
```
![alter Add  ](/img/2.png);



---

## 4. Insert Data into the Table

```
INSERT INTO employee_table (employee_name, employee_age, department_name, dob)
VALUES 
("dhina", 23, "Developer", "2002-01-10"),
("karan", 22, "HR", "2002-01-10"),
("laran", 25, "Designer", "2002-01-10"),
("deva", 23, "Manager", "2002-01-10"),
("sam", 35, "Senior Developer", "2002-01-10");

```

![alter Add  ](/img/3.png);

---

##### View Record in Table

```
select * from employee_table;


```
 
 --- 

## Alter  to change Column

##### Add Column
```
ALTER TABLE employee_table ADD Experience_in_year INT AFTER dob;

```

##### add data inside a cell
```
UPDATE employee_table
SET Experience_in_year = 3
WHERE name = 'dhina';

UPDATE employee_table
SET Experience_in_year = 1
WHERE name = 'karan';

UPDATE employee_table
SET Experience_in_year = 10
WHERE name = 'sam';
```
![Add cell ](/img/3.png);

##### Rename Column

```
ALTER TABLE student_table RENAME COLUMN dob TO DOB;

```

##### Drop row

```
DELETE FROM employee_table
WHERE employee_id = 3;
```

![alter Add  ](/img/4.png);

##### Drop Column

```
ALTER TABLE student_table DROP COLUMN dept_name;
```

## Drop  Commands

##### Drop table

```
drop table employee_table;
```
##### Drop Database

```
drop database dhina;
```
 ---
## Aggregate function

##### count

```
SELECT COUNT(employee_name) FROM employee_table;
```
![alter Add  ](/img/5.png);
##### sum

```
SELECT SUM(Experience_in_year) FROM employee_table;

```
![alter Add  ](/img/6.png);

##### Avg

```
SELECT AVG(Experience_in_year)FROM employee_table;
```

##### Max

```
SELECT MAX(employee_id) FROM employee_table;

```

##### Min

```
SELECT MIN(employee_id) FROM employee_table;
```

 --- 

## Between

```
SELECT * FROM employee_table WHERE Experience_in_year BETWEEN 3 AND 10;


```

![between](/img/7.png);

 ---
## Less than

```
SELECT * FROM employee_table WHERE Experience_in_year < 3 ;
```

  ---

## As

As is used to give a nickName to a column.

```
SELECT Experience_in_year AS experience FROM employee_table;
```

## like

```
SELECT employee_name FROM employee_table WHERE employee_name LIKE 'd%';

```
![like](/img/8.png);

 ---

## Order

##### Ascending order

```
SELECT * FROM employee_table ORDER BY age ASC;

```

##### Descending Order

```
SELECT * FROM employee_table ORDER BY age DESC;
```

 ---
















