参考: [ACID](http://en.wikipedia.org/wiki/ACID)<br />
**DBMS(database management system, 数据库管理系统)**的特点:

- Atomicity(原子性, 或不可分割性）
- Consistency(一致性)
- Isolation(隔离性, 或独立性)
- Durability(持久性)

参考:[SQL](http://en.wikipedia.org/wiki/Category:SQL) | [CURD](http://en.wikipedia.org/wiki/Create,_read,_update_and_delete) | [Types of SQL Statements](http://docs.oracle.com/cd/B28359_01/server.111/b28286/statements_1001.htm)<br />
**SQL(Structured Query Language, 结构化查询语言)**包含下面几部分：

- **DDL(Data Definition Language, 数据定义语言)**<br />
负责数据结构定义与数据库对象定义的语言，由CREATE、ALTER与DROP三个语法所组成
- **DML(Data Manipulation Language, 数据操纵语言)**(<br />
负责对数据库对象运行数据访问工作的指令集，以INSERT、UPDATE、DELETE三种指令为核心，分别代表插入、更新与删除，是开发以数据为中心的应用程序必定会使用到的指令，因此有很多开发人员都把加上SQL的SELECT语句的四大指令以“CRUD”来称呼。 
- **DCL(Data Control Language, 数据控制语言)**<br />
是一种可对数据访问权进行控制的指令，它可以控制特定用户账户对数据表、查看表、预存程序、用户自定义函数等数据库对象的控制权。由 GRANT 和 REVOKE 两个指令组成。

**详细内容待完成,列出常用语法**