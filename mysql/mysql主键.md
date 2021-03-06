


# 主键 Primary Key

主键是为了标识数据库记录唯一性，不允许记录重复，且键值不能为空，主键也是一个特殊索引。 


## 什么是主键

表中的每一行都应该具有可以唯一标识自己的一列(或一组列)。而这个承担标识作用的列称为主键。

如果没有主键，数据的管理将会十分混乱。比如会存在多条一模一样的记录，删除和修改特定行十分困难。


## 那些列可以作为主键：

任何列都可以作为主键，只要它满足以下条件：

• 任何两行都不具有相同的主键值。就是说这列的值都是互不相同的。
• 每个行都必须具有一个主键值。主键列不允许设置为NULL。
• 主键列的值不建议进行修改和更新。


## 声明主键的方法

```
CREATE TABLE t1(
   id int not null primary key,
   name char(20)
);
```
## 复合主键：
```
CREATE TABLE t1(
   id int not null,
   name char(20),
   primary key (id,name)
);
```


# MySQL主键与索引的区别和联系

1. 主键一定是唯一性索引，唯一性索引并不一定就是主键
2. 一个表中可以有多个唯一性索引，但只能有一个主键
3. 主键列不允许空值，而唯一性索引列允许空值
4. 索引可以提高查询的速度


# Mysql中主键 primary 与唯一约束 unique 的区别分析

1.UNIQUE约束的字段中不能包含重复值，可以为一个或多个字段定义UNIQUE约束,

2.PRIMARY KEY不可空不可重复，在一个表里可以定义联合主键；
简单的说, primary key = unique + not null

