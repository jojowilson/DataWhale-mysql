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
FROM Products<br>
ORDERBY<br>
prod_name;<br>

函数
===


作业
===
task1 查找重复邮箱
---
-- 创建表
CREATE TABLE email (<br>
ID INT NOT NULL PRIMARY KEY,<br>
Email VARCHAR(255)<br>
)<br>

-- 插入数据<br>
INSERT INTO email VALUES('1','a@b.com');<br>
INSERT INTO email VALUES('2','c@d.com');<br>
INSERT INTO email VALUES('3','a@b.com');<br>

---查找重复邮箱<br>
SELECT DISTINCE Email<br>
FROM email;<br>


task2 查找大国
---
-- 创建表<br>
CREATE TABLE World (<br>
name VARCHAR(50) NOT NULL,<br>
continent VARCHAR(50) NOT NULL,<br>
area INT NOT NULL,<br>
population INT NOT NULL,<br>
gdp INT NOT NULL<br>
);<br>


-- 插入数据<br>
INSERT INTO World VALUES( 'Afghanistan', 'Asia',652230,25500100,20343000);<br>
INSERT INTO World VALUES( 'Albania', 'Europe' ,28748,2831741,12960000);<br>
INSERT INTO World VALUES( 'Algeria', 'Africa' ,2381741,37100000,188681000);<br>
INSERT INTO World VALUES( 'Andorra' , 'Europe' ,468,78115,3712000);<br>
INSERT INTO World VALUES( 'Angola' , 'Africa' ,1246700,20609294,100990000);<br>

---查找大国<br>
SELECT name, area, population<br>
FROM World<br>
WHERE area >= 3000000 <br>
OR (population > 25000000 AND gdp > 20000000);<br>
