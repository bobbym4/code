参考:[sqlite](https://www.sqlite.org/datatype3.html)

#数据类型

##基本类型

一般数据库使用静态(static type)或僵化类型(rigid type),而SQLite使用动态类型(dynamic type)

- **NULL** 该值是一个NULL值。
- **INTEGER** 值被一个带符号的整数，存储在1，2，3，4，6，或8个字节根据值的大小。
- **REAL** 该值是一个浮点值，作为一个8字节的IEEE浮点数存储。
- **TEXT** 该值是一个文本字符串，使用数据库编码（UTF-8，UTF-16BE或UTF-16LE）保存。
- **BLOB** 不转换，直接存储，二进制数据

CREATE TABLE 中可以声明很多中类型，系统会自动转换成SQLite支持的基本类型。
Android的一些组件会直接使用"_id"字段名作为ID，如listview的adapter

SQLite中还有一些函数，参考
https://www.sqlite.org/lang_aggfunc.html
https://www.sqlite.org/lang_corefunc.html
https://www.sqlite.org/lang_datefunc.html