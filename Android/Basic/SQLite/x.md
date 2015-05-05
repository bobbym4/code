参考:
http://developer.android.com/reference/android/database/sqlite/SQLiteDatabase.html
http://developer.android.com/reference/android/database/sqlite/SQLiteOpenHelper.html
http://developer.android.com/reference/android/content/ContentValues.html
http://developer.android.com/reference/android/database/Cursor.html


CREATE TABLE student2 (
  _id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT,
  birth BIGINT
);

ALTER TABLE student ADD height REAL;

INSERT INTO student (name, birth, height) VALUES ('张三', strftime('%s','now'), 160),  ('李四', strftime('%s','1981-01-01 01:01:01'), 170),  ('王五', strftime('%s','1981-01-01 01:01:01'), 170);

UPDATE student SET birth=strftime('%s','1982-02-02 02:02:02'), height=165 WHERE name='李四';

SELECT _id, name, datetime(birth, 'unixepoch'), height FROM student;

/*
DELETE FROM student WHERE _id=1;
DROP TABLE student;
*/