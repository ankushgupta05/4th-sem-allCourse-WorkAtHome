#### create table with creating primary key 
```
CREATE TABLE bhopal1(
          cid INT PRIMARY KEY,
          name VARCHAR(50) NOT NULL
)

```



#### Insert data into 'bhopal1' table
```

insert into bhopal1(cid,name)
VALUES (1,'mumbai');

insert into bhopal1(cid,name)
VALUES (2,'Guna'); 


insert into bhopal1(cid,name)
VALUES (3,'Bhopal');

insert into bhopal1(cid,name)
VALUES (4,'Aron'); 

insert into bhopal1(cid,name)
VALUES (5,'Sehore'); 
```





#### create other table with creating foreign key  

```
create table student4(
        id NUMBER primary key,
        percentage NUMBER,
        name VARCHAR(20) NOT NULL,
        age NUMBER,
        gender VARCHAR(2) NOT NULL,
        city NUMBER NOT NULL,
        FOREIGN KEY (city) references bhopal1(cid)
);
```




#### inserting data into student4 table
```
insert into student4(id,percentage,name,age,gender,city)
VALUES (2001,9,'nikhil',9,'M',1);


insert into student4(id,percentage,name,age,gender,city)
VALUES (1004,98,'nikhlesh',17,'F',2);


insert into student4(id,percentage,name,age,gender,city)
VALUES (1002,95,'shyam',20,'M',3);



insert into student4(id,percentage,name,age,gender,city)
VALUES (1001,96,'Aman',20,'M',4);


insert into student4(id,percentage,name,age,gender,city)
VALUES (1005,99,'monu',19,'M',5);


```



#### Inner joins syntex

```
SELECT column_name
FROM table1  INNER JOIN table2
ON table1.column_name1 = table2.column_name2

Here :- 

column_name1  is a foreign key
column_name2  is a primary key
```



#### code example
```
SELECT * FROM student4 INNER JOIN bhopal1
ON student4.city = bhopal1.cid
```



#### we can also alies of table name 
```
// just aboue code and this code give same output 

SELECT * FROM student4 P INNER JOIN bhopal1 B
ON P.city = B.cid
```



#### this code also same         
```
SELECT  B.CID  ,  P.PERCENTAGE , P.NAME ,  P.AGE , P.GENDER ,  B.NAME
FROM student4 P INNER JOIN bhopal1 B
ON P.city = B.cid
```





#### use where clause  
```

SELECT  B.CID  ,  P.PERCENTAGE , P.NAME ,  P.AGE , P.GENDER ,  B.NAME
FROM student4 P INNER JOIN bhopal1 B
ON P.city = B.cid
WHERE B.name = 'mumbai'

```




####  writting inner word this is a optional
```

SELECT  B.CID  ,  P.PERCENTAGE , P.NAME ,  P.AGE , P.GENDER ,  B.NAME
FROM student4 P  JOIN bhopal1 B
ON P.city = B.cid

```



### Left Joins

```

SELECT *
FROM student4 LEFT JOIN bhopal1
ON student4.city =  bhopal1.cid
```