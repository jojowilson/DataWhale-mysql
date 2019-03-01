
任务一：
===
创建如下所示的courses 表：
---
CREATE TABLE courses <br>
(<br>
student VARCHAR(5) NOT NULL,<br>
class VARCHAR(20) NOT NULL<br>
);<br>

插入数据:
---
INSERT INTO courses VALUES('A', 'Math');<br>
INSERT INTO courses VALUES('B', 'English');<br>
INSERT INTO courses VALUES('C', 'Math');<br>
INSERT INTO courses VALUES('D', 'Biology');<br>
INSERT INTO courses VALUES('E', 'Math');<br>
INSERT INTO courses VALUES('F', 'Computer');<br>
INSERT INTO courses VALUES('G', 'Math');<br>
INSERT INTO courses VALUES('H', 'Math');<br>
INSERT INTO courses VALUES('I', 'Math');<br>
INSERT INTO courses VALUES('A', 'Math');<br>

查询语句:
---
SELECT class<br>
FROM courses<br>
GROUP BY class<br>
HAVING COUNT(*) >= 5;<br>


任务二：
===
创建表：
---
CREATE TABLE salary<br>
(<br>
id INT NOT NULL ,<br>
name VARCHAR(20) NOT NULL,<br>
sex VARCHAR(20) NOT NULL,<br>
salary INT NOT NULL<br>
);<br>

插入数据
---
INSERT INTO salary VALUES(1, 'A', 'm', '2500');<br>
INSERT INTO salary VALUES(2, 'B', 'f', '1500');<br>
INSERT INTO salary VALUES(3, 'C', 'm', '5500');<br>
INSERT INTO salary VALUES(4, 'D', 'f', '500');<br>

更新语句
---
UPDATE salary<br>
SET sex =<br>
CASE WHEN sex = 'f'<br>
THEN sex = 'm'<br>
ELSE sex = 'f'<br>
END;<br>
