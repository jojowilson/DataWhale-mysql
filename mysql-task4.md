表联结
===
1.给数据库起别名
---
SELECT c.cust_name<br>
FROM Customers AS c;<br>

2.内联结
---
SELECT vend_name, prod_name, prod_price<br>
FROM Vendors INNER JOIN Products<br>
ON Vendors.vend_id = Products.vend_id;<br>

3.外联结
---
SELECT c.cust_id, o.order_num<br>
FROM Customers AS c LEFT OUTER JOIN Orders AS o<br>
ON c.cust_id = o.cust_id;<br>

4.自联结
---
SELECT C.*, O.order_num, O.order_date,<br>
	OI.prod_id, OI.quantity, OI.item_price<br>
FROM Customers AS C, Orders AS O, OrderItems AS OI<br>
WHERE C.cust_id = O.cust_id<br>
AND O.order_num = OI.order_num<br>
AND prod_id = ‘RGAN01’;<br>

5.组合查询---UNION
---
SELECT cust_name, cust_contact, cust_email<br>
FROM Customers<br>
WHERE cust_name = 'Fun4All'<br>
UNION<br>
SELECT cust_name, cust_contact, cust_email<br>
FROM Customers<br>
WHERE cust_state IN ('IL', 'IN', 'MI');<br>

小任务
===
1.组合两张表<br>
CREATE TABLE Person<br>
(<br>
PersonId INT PRIMARY KEY NOT NULL,<br>
FirstName VARCHAR(20) NOT NULL,<br>
LastName VARCHAR(20) NOT NULL<br>
);<br>

---插入数据<br>
INSERT INTO Person VALUES(1, 'rui', 'cun');<br>
INSERT INTO Person VALUES(2, 'zhang', 'cun');<br>
INSERT INTO Person VALUES(3, 'wang', 'cun');<br>
<br>
CREATE TABLE Address<br>
(<br>
PersonId INT PRIMARY KEY NOT NULL,<br>
AddressId INT NOT NULL,<br>
City VARCHAR(20) NOT NULL,<br>
State VARCHAR(20) NOT NULL<br>

---插入数据<br>
INSERT INTO Address VALUES(1, 1002, 'shanghai', 'China');<br>
INSERT INTO Address VALUES(2, 1003, 'beijing', 'China');<br>
INSERT INTO Address VALUES(3, 1004, 'New York', 'America');<br>

---查询<br>
SELECT FirstName, LastName, City, State<br>
FROM Person, Address<br>
WHERE Person.PersonId = Address.PersonId;<br>


项目二
---
----建表<br>
CREATE TABLE email<br>
(<br>
Id INT PRIMARY KEY NOT NULL,<br>
Email VARCHAR(20) NOT NULL<br>
);<br>

---插入数据<br>
INSERT INTO email VALUES(1, 'a@b.com');<br>
INSERT INTO email VALUES(2, 'c@d.com');<br>
INSERT INTO email VALUES(3, 'a@b.com');<br>

---查询<br>
DELETE e1 <br>
FROM email e1, email e2<br>
WHERE e1.Email = e2.Email<br>
AND e1.Id > e2.Id;<br>


