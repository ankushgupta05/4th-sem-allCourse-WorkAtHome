## INSERT values into the table 

````
INSERT INTO departments(department_id, department_name, manager_id, location_id)
VALUES (71,'PUBLICK RELATION', 100, 1700)

````



````

INSERT INTO departments (department_id, department_name, location_id, manager_id)
VALUES (78, 'Public Relations', 1700, 100);


````




````

INSERT INTO departments (department_id,department_name)
VALUES (76, 'purchessing')


````




// this code not work bcz so many values
````
INSERT INTO departments (department_id,department_name)
VALUES (77, 'purchessing',NULL,NULL);

````




// this is not work bcz values not follow domain constriant
````

INSERT INTO employees
VALUES (215, 'Monu', 'Kushwa','monu@gmail.com','626229','6-jun-24','AC_MANAGE',600000,NULL,206,219)
````





// this is right code to insert row  
````
INSERT INTO employees
VALUES (215, 'Monu', 'Kushwa','monu@gmail.com','626229','6-jun-24','AD_PRES',600000,NULL,215,75)

````





// this is right code to insert row  and 'SYSDATE' it give current dates
````

INSERT INTO employees
VALUES (218, 'shyam', 'sahu','shyam@gmail.com','626229',SYSDATE,'AD_PRES',600000,NULL,215,75)

````



// this type gidving data also posible
````

INSERT INTO employees
VALUES (315,'ankush2','gupta2', 'ankushgupta0510@gmail.com','626229',TO_DATE('FEB 3, 1999','MON DD, YYYY'),'AD_PRES',600000,NULL,215,75);

````



// command for check domain constraints of table's columns
````
DESC employees

````


## create table command


// command for check table
````
SELECT *
FROM TABS

````



// create table and insert data
````
CREATE TABLE sales_reps(id NUMBER(4) CONSTRAINT PK_EMP PRIMARY KEY,
                             name VARCHAR2(10),
                              salary NUMBER(7,2),
                              commission_pct NUMBER(7,2)
)



INSERT INTO sales_reps(id, name, salary, commission_pct)
       SELECT employee_id, last_name, salary, commission_pct
       FROM employees
       WHERE job_id LIKE '%REP%'


````



// agai  create  new table and insert all data of employees
````
CREATE TABLE copy_emp(
            employee_id NUMBER(6),
            first_name VARCHAR2(20),
            last_name VARCHAR2(25),
            email VARCHAR2(25),
            phone_number VARCHAR2(20),
            hire_date DATE,
            job_id VARCHAR2(10),
            salary NUMBER(8,2),
            commission_pct NUMBER(2,2),
            manager_id NUMBER(6),
            department_id NUMBER(4)
);


INSERT INTO copy_emp 
SELECT * FROM employees


````



## Update commanad

````
UPDATE employees
SET department_id = 70
WHERE employee_id = 113

````


````
UPDATE employees
SET department_id = 70
WHERE employee_id = 113

````





''''

UPDATE employees
SET job_id = (SELECT job_id 
               FROM employees
               WHERE employee_id = 205
),
salary = (
               SELECT salary
               FROM employees
               WHERE employee_id = 205
)

WHERE employee_id = 114


''''



## delete commands

// this delete only  data of  'temp_emp'  Table
````
// 1)  create table
CREATE TABLE copy_emp(
            employee_id NUMBER(6),
            first_name VARCHAR2(20),
            last_name VARCHAR2(25),
            email VARCHAR2(25),
            phone_number VARCHAR2(20),
            hire_date DATE,
            job_id VARCHAR2(10),
            salary NUMBER(8,2),
            commission_pct NUMBER(2,2),
            manager_id NUMBER(6),
            department_id NUMBER(4)
);

// 2) Insert employees data  into copy_emp
INSERT INTO copy_emp 
SELECT * FROM employees


// 3) Delete copy_emp data but not delete copy_emp Table
DELETE copy_emp

````



#### NOTE :- if our column is primary key than we can not delete that column and it show error 'constraint error'


// this code is wrong and explore it from google
````
DELETE FROM employees 
WHERE department_id = (
       SELECT department_id FROM departments
       WHERE department_name LIKE '%Public%'
)

````

