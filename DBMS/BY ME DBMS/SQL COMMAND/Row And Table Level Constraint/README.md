### Row Level Constraint

// Row level constraint and one primary key
````
CREATE TABLE emp1(
                     employee_id NUMBER(10) CONSTRAINT emp_emp_id_pk_a PRIMARY KEY,
                     first_name VARCHAR2(20) NOT NULL,
                     last_name VARCHAR2(20) NOT NULL,
                     email  VARCHAR2(25) NOT NULL,
                     phone_number VARCHAR2(20),
                     hire_date DATE NOT NULL,
                     job_id Varchar2(10) NOT NULL,
                     salary NUMBER(8,2),
                     commission_pct NUMBER(2,2),
                     manager_id NUMBER(6),
                     department_id NUMBER(4)

)

// check constraint
DESC emp_emp_id_pk_a
````



// Table level constraint and one primary key
````
CREATE TABLE emp2(
                     employee_id NUMBER(10),
                     first_name VARCHAR2(20) NOT NULL,
                     last_name VARCHAR2(20) NOT NULL,
                     email  VARCHAR2(25) NOT NULL,
                     phone_number VARCHAR2(20),
                     hire_date DATE NOT NULL,
                     job_id Varchar2(10) NOT NULL,
                     salary NUMBER(8,2),
                     commission_pct NUMBER(2,2),
                     manager_id NUMBER(6),
                     department_id NUMBER(4),
                     CONSTRAINT emp2_emp2_id_pk_a PRIMARY KEY (employee_id)

)

// check constraint
DESC emp2_emp2_id_pk_a





````
// Table level constraint and multy primary key
````
CREATE TABLE emp3(
                     employee_id NUMBER(10),
                     first_name VARCHAR2(20) NOT NULL,
                     last_name VARCHAR2(20) NOT NULL,
                     email  VARCHAR2(25) NOT NULL,
                     phone_number VARCHAR2(20),
                     hire_date DATE NOT NULL,
                     job_id Varchar2(10) NOT NULL,
                     salary NUMBER(8,2),
                     commission_pct NUMBER(2,2),
                     manager_id NUMBER(6),
                     department_id NUMBER(4),
                     CONSTRAINT emp3_emp3_id_pk_a PRIMARY KEY (employee_id, first_name)

)

// check constraint
DESC emp3_emp3_id_pk_a

````


````
UPDATE employees
SET department_id  = 55
WHERE department_id = 110;
````



````
DELETE FROM departments
WHERE department_id = 60;
````





````
DELETE FROM departments
WHERE department_id = 70;
````

