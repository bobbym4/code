CREATE TABLE student (
  _id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT,
  birth INTEGER
);

ALTER TABLE student ADD height REAL;

INSERT INTO student (name, birth, height) VALUES ('张三', strftime('%s','now'), 160),  ('李四', strftime('%s','1981-01-01 01:01:01'), 170),  ('王五', strftime('%s','1981-01-01 01:01:01'), 170);

UPDATE student SET birth=strftime('%s','1982-02-02 02:02:02'), height=165 WHERE name='李四';

SELECT _id, name, datetime(birth, 'unixepoch'), height FROM student;

/*
DELETE FROM student WHERE _id=1;
DROP TABLE student;
*/