软件安装及服务器配置
===
1.配置好my.ini文件<br>
2.初始化数据库:   mysqld --initialize --console<br>
3.安装并启动数据库: mysqld install<br>                 
                  net start mysql<br>
4.登录并修改数据库密码: 如mysqladmin -uroot -p123 password root<br>

[参考链接](http://www.runoob.com/mysql/mysql-install.html)<br>

安装Navicat时出现的1251错误
===
解决方法
---
ALTER USER 'root'@'localhost' IDENTIFIED BY 'password' PASSWORD EXPIRE NEVER; #修改加密规则 （这行我没有写，不过貌似也可以）<br>

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; #更新一下用户的密码<br> 

FLUSH PRIVILEGES; #刷新权限<br>


数据库的基础知识
===
首先数据库通俗的理解就是一个存放数据的柜子，你可以和它适当的沟通取出你想要的信息。<br>
普通的关系数据库里面的文件呈现出来的是表的形式，但是从数学语言的层面来说，这个表对应的是术语是关系，每一列对应的是属性，每一行对应的是元祖<br>
什么是主键 什么是外键
---
每一行中都应该有一列能够唯一标识表中的每一行，且主键唯一不为空



数据库管理系统
===
DBMS是一个用来管理数据库的系统，属于软件层面，通过这个系统软件我们能够将存储在硬件上的信息合理的管理。<br>

同样在数据库系统体系结构上可以分为内部层、概念层和外部层
