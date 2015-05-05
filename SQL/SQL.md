参考: [ACID](http://en.wikipedia.org/wiki/ACID)<br />
**DBMS(database management system, 数据库管理系统)**的特点:

- **Atomicity(原子性, 或不可分割性)**
- **Consistency(一致性)**
- **Isolation(隔离性, 或独立性)**
- **Durability(持久性)**

参考:[SQL](http://en.wikipedia.org/wiki/Category:SQL) | [CURD](http://en.wikipedia.org/wiki/Create,_read,_update_and_delete) | [Types of SQL Statements](http://docs.oracle.com/cd/B28359_01/server.111/b28286/statements_1001.htm)<br />
**SQL(Structured Query Language, 结构化查询语言)**主要分为下面两类：

- **DDL(Data Definition Language, 数据定义语言)**<br />
负责数据结构定义与数据库对象定义的语言，由CREATE、ALTER与DROP三个语法所组成
- **DML(Data Manipulation Language, 数据操纵语言)**(<br />
负责对数据库对象运行数据访问工作的指令集，以INSERT、UPDATE、DELETE三种指令为核心，分别代表插入、更新与删除，是开发以数据为中心的应用程序必定会使用到的指令，因此有很多开发人员都把加上SQL的SELECT语句的四大指令以“CRUD”来称呼。 

此外还有**DCL(Data Control Language, 数据控制语言)**和**DQL(Data Query Language, 数据查询语言)**、工具、权限、事务、管理等，概念比较乱。SELECT语句有的归入DML，有的归入DQL。


参考:[SQLite](http://www.sqlite.org/lang.html) | [MySQL](http://dev.mysql.com/doc/refman/5.7/en/sql-syntax.html)<br />
不同的数据库SQL语句差别很大，SQLite和MySQL一般常用形式如下：

<pre>
-- CREATE TABLE
CREATE TABLE [IF NOT EXISTS] table-name (
  column-name type-name [column-constraint],
  column-name type-name [column-constraint],
  ...
)
备注:一个表中可以有多个UNIQUE，但只能有一个PRIMARY KEY。
有的地方认为 PRIMARY KEY (主键) = NOT NULL (非空) + UNIQUE (唯一)

-- ALTER TABLE
ALTER TABLE table-name RENAME TO new-table-name
ALTER TABLE table-name ADD column-name type-name [column-constraint]
备注:SQLite不支持列的改名和删除，但MySQL支持，所以没写上。

-- DROP TABLE
DROP TABLE [IF EXISTS] table-name

column-constraint:[PRIMARY KEY]|[NOT NULL]|[UNIQUE]|[DEFAULT default_value]|[AUTO_INCREMENT]
备注:MySQL中使用AUTO_INCREMENT，而SQLite中使用AUTOINCREMENT
外键约束貌似用得很少，所以没写上。
</pre>
<pre>
-- SELECT
SELECT {* | column-name, column-name, ...} FROM table-name
  [WHERE where_definition]
  [GROUP BY column-name]
  [ORDER BY column-name [ASC | DESC],  column-name [ASC | DESC], ...]
  [LIMIT [offset,] row_count] | [LIMIT row_count OFFSET offset]

where_definition:
  column-name {> | >= | < | <= | = | != | <> | IS | IS NOT} expression
  column-name BETWEEN expression1 AND expression2
  column-name LIKE expression
  column-name IN (expression-list | subquery)
备注:WHERE子句中，上面的column-name也可以是expression
LIKE的expression中"_"匹配单个字符，"%"匹配任意个字符，不区分ASCII字符大小写。
多个WHERE字句还可以再用AND、OR来连接
多表查询JOIN/UNION，查询结果中再查，以后再研究
</pre>
<pre>
-- INSERT
INSERT INTO table-name (column-name, column-name, ...)
  VALUES (expr, expr, ...), (expr, expr, ...), ...

-- DELETE
DELETE FROM table-name
  [WHERE ...] [ORDER BY ...] [LIMIT ...]

-- UPDATE
UPDATE table-name SET {column-name=expr, column-name=expr, ...}
  [WHERE ...] [ORDER BY ...] [LIMIT ...]
</pre>

=====
BEGIN TRANSACTION
COMMIT TRANSACTION
ROLLBACK TRANSACTION
END TRANSACTION