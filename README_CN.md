# xorm

[English](https://github.com/lunny/xorm/blob/master/README.md)

xorm是一个简单而强大的Go语言ORM库. 通过它可以使数据库操作非常简便。

[![Build Status](https://drone.io/github.com/lunny/xorm/status.png)](https://drone.io/github.com/lunny/xorm/latest)

## 讨论
请加入QQ群：280360085 进行讨论。

## 驱动支持

目前支持的Go数据库驱动如下：

* Mysql: [github.com/Go-SQL-Driver/MySQL](https://github.com/Go-SQL-Driver/MySQL)

* MyMysql: [github.com/ziutek/mymysql/godrv](https://github.com/ziutek/mymysql/godrv)

* SQLite: [github.com/mattn/go-sqlite3](https://github.com/mattn/go-sqlite3)

* Postgres: [github.com/bylevel/pq](https://github.com/bylevel/pq)

## 更新日志

* **v0.1.9** : 新增 postgres 和 mymysql 驱动支持; 在Postgres中支持原始SQL语句中使用 ` 和 ? 符号; 新增Cols, StoreEngine, Charset 函数；SQL语句打印支持io.Writer接口，默认打印到控制台；新增更多的字段类型支持，详见 [映射规则](https://github.com/lunny/xorm/blob/master/QuickStart.md#21)；删除废弃的MakeSession和Create函数。
* **v0.1.8** : 新增联合index，联合unique支持，请查看 [映射规则](https://github.com/lunny/xorm/blob/master/QuickStart.md#21)。
* **v0.1.7** : 新增IConnectPool接口以及NoneConnectPool, SysConnectPool, SimpleConnectPool三种实现，可以选择不使用连接池，使用系统连接池和使用自带连接池三种实现，默认为SysConnectPool，即系统自带的连接池。同时支持自定义连接池。Engine新增Close方法，在系统退出时应调用此方法。
* **v0.1.6** : 新增Conversion，支持自定义类型到数据库类型的转换；新增查询结构体自动检测匿名成员支持；新增单向映射支持；
* **v0.1.5** : 新增对多线程的支持；新增Sql()函数；支持任意sql语句的struct查询；Get函数返回值变动；MakeSession和Create函数被NewSession和NewEngine函数替代；
* **v0.1.4** : Get函数和Find函数新增简单的级联载入功能；对更多的数据库类型支持。
* **v0.1.3** : Find函数现在支持传入Slice或者Map，当传入Map时，key为id；新增Table函数以为多表和临时表进行支持。
* **v0.1.2** : Insert函数支持混合struct和slice指针传入，并根据数据库类型自动批量插入，同时自动添加事务
* **v0.1.1** : 添加 Id, In 函数，改善 README 文档
* **v0.1.0** : 初始化工程

## 特性

* 支持Struct和数据库表之间的映射，映射方式支持命名约定和Tag两种方式，映射支持继承

* 事务支持

* 同时支持原始SQL语句和ORM操作的混合执行

* 使用连写来简化调用

* 支持使用Id, In, Where, Limit, Join, Having, Table, Sql, Cols等函数和结构体等方式作为条件

* 支持数据库连接池

* 支持级联加载struct


## 安装

	go get github.com/lunny/xorm

## 快速开始

请访问 [快速开始](https://github.com/lunny/xorm/blob/master/QuickStart.md) 查看详细文档


## 文档

请访问 [GoWalker](http://gowalker.org/github.com/lunny/xorm) 查看详细文档

## FAQ

1.问：xorm的tag和json的tag如何同时起作用？
  
答案：使用空格分开

```Go
type User struct {
    Name string `json:"name" xorm:"name"`
}
```

## LICENSE

BSD License
[http://creativecommons.org/licenses/BSD/](http://creativecommons.org/licenses/BSD/)
