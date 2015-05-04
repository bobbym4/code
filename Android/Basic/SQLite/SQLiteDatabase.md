参考: [SQLiteDatabase](http://developer.android.com/reference/android/database/sqlite/SQLiteDatabase.html)
[Cursor](http://developer.android.com/reference/android/database/Cursor.html)

	void execSQL(String sql)
	void execSQL(String sql, Object[] bindArgs)
执行一条没有返回值的SQL语句(SELECT/INSERT/UPDATE/DELETE是有返回值的)<br />
**详细内容待完成，还涉及后面的很多方法**

	long insert(String table, String nullColumnHack, ContentValues values)
便捷方法，插入一行到数据库中。<br />
参数：**table** 要插入到的表。**nullColumnHack** 可以为null的可选参数。底层数据库不允许插入一个空行，当values参数为空或者里面没有内容的时候会失败。为了防止这种情况，在这里指定一个列名，如果发现将要插入的行为空行时，就会将你指定的这个列名的值设为null，然后再向数据库中插入。**values** ，类似map的ContentValues对象，通过键值对的形式存储值。 this map contains the initial column values for the row. The keys should be the column names and the values the column values
返回：新插入的行的行号，如果发生错误返回-1

	Cursor query(String table, String[] columns, String selection, String[] selectionArgs, String groupBy, String having, String orderBy, String limit)
	Cursor query(boolean distinct, String table, String[] columns, String selection, String[] selectionArgs, String groupBy, String having, String orderBy, String limit, CancellationSignal cancellationSignal)
	Cursor query(String table, String[] columns, String selection, String[] selectionArgs, String groupBy, String having, String orderBy)
	Cursor query(boolean distinct, String table, String[] columns, String selection, String[] selectionArgs, String groupBy, String having, String orderBy, String limit)
查询指定表/URL，返回结果集的游标。

	int update(String table, ContentValues values, String whereClause, String[] whereArgs)
便捷方法，在数据库中更新行。<br />
参数：**table** 要更新的表。**values** 列和值，null是有效的，将被转换成NULL。**whereClause** 可选的WHERE子句，null会更新所有行。
**whereArgs** 绑定到WHERE子句值，值会绑定为字符串
返回：受影响的行数

	int delete(String table, String whereClause, String[] whereArgs)
便捷方法，删除行到数据库中。<br />
参数：
**table**
the table to delete from
**whereClause**
the optional WHERE clause to apply when deleting. Passing null will delete all rows.
**whereArgs**
You may include ?s in the where clause, which will be replaced by the values from whereArgs. The values will be bound as Strings.
返回：
the number of rows affected if a whereClause is passed in, 0 otherwise. To remove all rows and get a count pass "1" as the whereClause. 


---
	void beginTransaction()
Begins a transaction in EXCLUSIVE mode. 

	static SQLiteDatabase create(SQLiteDatabase.CursorFactory factory)
Create a memory backed SQLite database. 

 

	static boolean deleteDatabase(File file)
Deletes a database including its journal file and other auxiliary files that may have been created by the database engine. 

	SQLiteStatement compileStatement(String sql)


	Cursor rawQuery(String sql, String[] selectionArgs, CancellationSignal cancellationSignal)
Runs the provided SQL and returns a Cursor over the result set.

	Cursor rawQuery(String sql, String[] selectionArgs)
	Cursor rawQueryWithFactory(SQLiteDatabase.CursorFactory cursorFactory, String sql, String[] selectionArgs, String editTable)
	Cursor rawQueryWithFactory(SQLiteDatabase.CursorFactory cursorFactory, String sql, String[] selectionArgs, String editTable, CancellationSignal cancellationSignal)
Runs the provided SQL and returns a Cursor over the result set.