# MySQL

## 基础

~~~markdown
# 结构化查询语句SQL
# 结构化查询语句分类
	DDL[数据定义语言]:定义和管理数据对象，如数据库，数据表等 [CREATE DROP ALTER] 
	DQL[数据操作语言]:用于操作数据库对象中所包含的的数据[INSERT UPDATE DELETE]
	DML[数据查询语言]:用于查询数据库数据[SELECT]
	DCL[数据控制语言]:用来管理数据库的语言，包含管理权限及数据更改[GRANT COMMIT ROLLBACK]
# 创建数据库
	1、CREATE DATABASE[IF NOT EXISTS] 数据库名 charset=utf8mb4
# 创建数据表
	1、CREATE TABLE [IF NOT EXISTS] 表名(
		列名 类型 参数...，
		列名 类型 参数...
	)
	当前时间 列名 TIMESTAMP DEFAULT CURRENT_TIMESTAMP
# 基本语法
	1、删除数据库
		DROP DATABASE [IF EXISTS] 数据库名
	2、删除数据表
		DROP TABLE [IF EXISTS] 表名
	3、查看表结构
		DESC(表名)
# 表结构修改
	1、更改表名
		ALTER TABLE 表名 RENAME TO 新表名
	2、添加新列
		ALTER TABLE 表名 ADD 列名 类型 /
		ALTER TABLE 表名 ADD(
			列名 类型,
			列名 类型
		)
	3、更改列名
		ALTER TABLE 表名 CHANGE 列名 新列名 类型
	4、更改列类型
		ALTER TABLE 表名 MODIFY 列名 新类型
	5、删除列
		ALTER TABLE 表名 DROP 列名
	6、向表内添加主键
		ALTER TABLE 表名 ADD PRIMARY KEY(列名)
# 添加外键
	建表时创建 FOREIGN KEY(列名) REFERENCES 表名(列名)
	建表之后创建 ALTER TABLE 表名 ADD FOREIGN KEY(列名) REFERENCES 表名(列名)
# 添加主键
	建表时创建 列名 类型 PRIMARY KEY / 复合主键: 列名 类型 PRIMARY KEY(列名,列名...)
	建表之后创建 ALTER TABLE 表名 ADD PRIMARY KEY(列名)
# 属性
	1、自增 AUTO_INCREMENT
	2、主键 PRIMARY KEY
	3、唯一键 UNIQUE
# 总结
	主键[PRIMARY KEY]特点：
		1、不允许重复
		2、一张表只能有一个主键 [可以将多列添加为复合主键]
		3、主键不允许为空
	唯一键[UNIQUE]特点
		1、不允许重复
		2、一张表可以存在多个唯一键
		3、唯一键可以为空
~~~

