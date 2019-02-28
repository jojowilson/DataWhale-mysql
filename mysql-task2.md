基本的查询语句
===
检索单个列
---
SELECT prod_name
FROM Products;

检索多个列
---
SELECT prod_name, prod_price, prod_id
FROM Products;

检索所有列
---
SELECT * 
FROM Products;<br>
*注意检索出来的记录都是无序排列的*

限制条件 where/group/having
===
SELECT prod_name, prod_price
FROM Products
WHERE prod_price = 3.49;


排序行数 orderby
===
SELECT prod_name <br>
FROM Products
ORDERBY
prod_name;

函数
===


作业
===
task1 查找重复邮箱
---
-- 创建表
CREATE TABLE email (
ID INT NOT NULL PRIMARY KEY,
Email VARCHAR(255)
)

-- 插入数据
INSERT INTO email VALUES('1','a@b.com');
INSERT INTO email VALUES('2','c@d.com');
INSERT INTO email VALUES('3','a@b.com');

---查找重复邮箱
SELECT DISTINCE Email
FROM email;


task2 查找大国
---
-- 创建表
CREATE TABLE World (
name VARCHAR(50) NOT NULL,
continent VARCHAR(50) NOT NULL,
area INT NOT NULL,
population INT NOT NULL,
gdp INT NOT NULL
);


-- 插入数据
INSERT INTO World VALUES( 'Afghanistan', 'Asia',652230,25500100,20343000);
INSERT INTO World VALUES( 'Albania', 'Europe' ,28748,2831741,12960000);
INSERT INTO World VALUES( 'Algeria', 'Africa' ,2381741,37100000,188681000);
INSERT INTO World VALUES( 'Andorra' , 'Europe' ,468,78115,3712000);
INSERT INTO World VALUES( 'Angola' , 'Africa' ,1246700,20609294,100990000);

---查找大国
SELECT name, area, population
FROM World
WHERE area >= 3000000 
OR (population > 25000000 AND gdp > 20000000);
