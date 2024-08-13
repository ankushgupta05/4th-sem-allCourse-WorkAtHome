

````
SELECT employee_id , last_name, salary*12 ANNSAL,hire_date
FROM employees
WHERE department_id = 80


// check your created table
DESC dept80
````



## Alter in DBMS


// create a new column
````
ALTER TABLE dept80
ADD (job_id VARCHAR2(9))


// check your created column
SELECT *
FROM dept80

````



// can not reduce size bcz last_name record have many chacractors 
````
ALTER TABLE dept80
MODIFY    (last_name VARCHAR2(9));

````



// this will be run 
````
ALTER TABLE dept80
MODIFY    (last_name VARCHAR2(30));

````



//Drop columns
````

ALTER TABLE dept80
DROP COLUMN job_id

````


#### NOTE : -  DDL mai already commit hota hai means rollback is not posible


// remove columns
````
ALTER TABLE dept80
SET UNUSED (hire_date);

````




// nothing do
````
ALTER TABLE dept80
SET UNUSED columns

````



// drop
````
DROP TABLE dept80
````