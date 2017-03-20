**目录**

[TOC]

# $sqlite
是数据库服务对象，可以进行数据库增、删、改、查等操作
## $sqlite.openDB()
创建数据库，参数为json类型，db为数据库名字。

**代码演示**
```javascript
var param = {
	"db" : 'qq.db'
}
$sqlite.openDB(param);
```

## $sqlite.execSql()
方法用来执行SQL语句，db为数据库名字，创建表结构。

**代码演示**
```javascript
var sql = "CREATE TABLE person (_id INTEGER PRIMARY KEY AUTOINCREMENT, name VARCHAR, xclass VARCHAR)";
var param = {
	"db" : 'qq.db',
	"sql" : sql
}
$sqlite.execSql(param);
```

## $sqlite.execSql()
方法用来执行SQL语句，db为数据库名字，向表中插入数据。

**代码演示**
```javascript
var sql="INSERT INTO person (name, xclass) VALUES('屈海滨','石化')";
var param = {
	"db" : 'qq.db',
	"sql" : sql
}
for(var i=0;i<6;i++){
	$sqlite.execSql(param);
}
```

## $sqlite.queryByPage()
方法用来查询数据库，返回类型为json数组格式的字符串。

**代码演示**
```javascript
var sql = "select * from person";
var param = {
	"db" : 'qq.db',//数据库名称
	"sql" : sql,//查询条件
	"pageIndex" : 0,//每页的记录数，从1开始
	"pageSize" : 10//页号索引，从0开始
}
var list = $sqlite.queryByPage(param);
```

## $sqlite.query()
用来查询数据库，返回类型为json数组格式的字符串。

**代码演示**
```javascript
var sql = "select * from person";
var param = {
	"db" : 'qq.db'//数据库名称
	"sql" : sql,//查询条件
	"startIndex" : startIndex, //可选参数 起始记录索引号(含)
	"endIndex" : endIndex      //可选参数 结束记录索引号(含)
}
var list = $sqlite.query(param)
```

## $sqlite.exist()
方法用来判断数据库是否已经创建存在,返回值：true|false

**代码演示**
```javascript
var param = {
	db : 'qq.db'
}
var list = $sqlite.exist(param)
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qSqlite">用例github下载地</a>
