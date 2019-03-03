学习内容
===
数据导入导出 (见附件)

将Excel文件导入MySQL表

MySQL导出表到Excel文件


在Navicat导入文件时，直接点击导入向导选择源文件即可
###遇到的问题
===
导入文件时，无法打开xlsx文件
解决办法:将xlsx用office打开后，在使用navicat导入。

作业
===
项目一
---
-- create table
create table employee(
id int primary key,
name varchar(255) not null,
salary int not null,
departmentId int not NULL
);
 
insert into employee values('1', 'Joe', '70000', '1');
insert into employee values('2', 'Henry', '80000', '2');
insert into employee values('3', 'Sam', '60000', '2');
insert into employee values('4', 'Max', '90000', '1');
 
 
create table department(
id int primary key,
name varchar(255)
 
);
 
insert into department values('1', 'IT');
insert into department values('2', 'Sales');


---查询语句
SELECT D.name as Department, 
	   E.name as Employee, 
	   e.Salary as Salary
From EmplOyeE as E 
     INNER JOIN 
     Department as D
ON E.DepartmentId = D.ID and
   e.SALARY = (SELECT MAX(SALARY)
                FROM EMPLOYEE 
                WHERE DEPARTMENTID = D.ID)
                
                
/*CREATE TABLE SEAT(
ID INT PRIMARY KEY,
STUDENT VARCHAR(255) NOT NULL
);
 
INSERT INTO SEAT VALUES('1','Abbot');
INSERT INTO SEAT VALUES('2','Doris');
INSERT INTO SEAT VALUES('3','Emerson');


项目二
/*CREATE TABLE SEAT(
ID INT PRIMARY KEY,
STUDENT VARCHAR(255) NOT NULL
);
 
INSERT INTO SEAT VALUES('1','Abbot');
INSERT INTO SEAT VALUES('2','Doris');
INSERT INTO SEAT VALUES('3','Emerson');
INSERT INTO SEAT VALUES('4','Green');
INSERT INTO SEAT VALUES('5','Jeames');*/
 
SELECT *
FROM (
       SELECT SEAT.ID -1 AS ID,
              STUDENT 
       FROM SEAT 
       WHERE SEAT.ID % 2 = 0
 
	   UNION
 
	   SELECT SEAT.ID + 1 AS ID, STUDENT 
       FROM SEAT 
       WHERE SEAT.ID % 2 = 1 AND
             SEAT.ID + 1 < (SELECT COUNT(*)
							FROM SEAT)
 
	   UNION
 
       SELECT SEAT.ID AS ID, STUDENT
	   FROM SEAT
       WHERE SEAT.ID % 2 = 1 AND 
             SEAT.ID = (SELECT COUNT(*)
                        FROM SEAT)
) AS T1
ORDER BY T1.ID



项目三
CREATE TABLE SCORE(
ID INT PRIMARY KEY,
SCORE FLOAT NOT NULL
);
 
INSERT INTO SCORE VALUES('1', '3.50');
INSERT INTO SCORE VALUES('2', '3.65');
INSERT INTO SCORE VALUES('3', '4.00');
INSERT INTO SCORE VALUES('4', '3.85');
INSERT INTO SCORE VALUES('5', '4.00');
INSERT INTO SCORE VALUES('6', '3.65');
 
SELECT SCORE, ( SELECT COUNT(DISTINCT S2.SCORE)
                FROM SCORE AS S2
                WHERE S2.SCORE > S1.SCORE) AS 'RANK'
FROM SCORE AS S1
ORDER BY S1.SCORE DSEC;
