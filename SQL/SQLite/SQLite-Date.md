##时间和日期

SQLite不能存储日期或时间,但可以通过内置函数存储为TEXT、REAL或INTEGER。

- TEXT: ISO8601字符串("YYYY-MM-DD HH:MM:SS.SSS").
- REAL: 以Julian日期格式存储.
- INTEGER: Unix时间戳. 

感觉BIGINT名字存时间戳舒服点,下面是利用SQLite的内置函数装换
<pre>
CREATE TABLE student2 (
  _id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT,
  birth BIGINT
);

INSERT INTO student (name, birth, height) VALUES
  ('张三', strftime('%s','now'), 160), 
  ('李四', strftime('%s','1981-01-01 01:01:01'), 170),
  ('王五', strftime('%s','1981-01-01 01:01:01'), 170);

UPDATE student SET birth=strftime('%s','1982-02-02 02:02:02'), height=165 WHERE name='李四';

SELECT _id, name, datetime(birth, 'unixepoch'), height FROM student;
</pre>