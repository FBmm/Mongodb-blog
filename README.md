# Mongodb-blog

MongoDB 学习博客

## 什么是 MongoDB

- MongoDB 是 c++ 编写的基于分布式文件存储开源数据库。
- 在高负载的情况下，添加更多的节点，可以保证服务器性能。 
- MongoDB 旨在为WEB应用提供可扩展的高性能数据存储解决方案。
- MongoDB 将数据存储为一个文档，数据结构由键值(key=>value)对组成。
- MongoDB 文档类似于 JSON 对象。字段值可以包含其他文档，数组及文档数组。

> 分布式文件存储：[参考博客](https://blog.csdn.net/weixin_42064002/article/details/82355929)

## mongoDB 概念

| SQL术语/概念 | MongoDB术语/概念 | 解释/说明 |
| ------      | ------           | ------ |
| database    | database         | 数据库 |
| table	      | collection	     | 数据库表/集合 |
| row	      | document	     | 数据记录行/文档 |
| column	  | field	         | 数据字段/域 |
| index	      | index	         | 索引 |
| table       | joins	         | 表连接,MongoDB不支持 |
| primary key | primary key	     | 主键,MongoDB自动将_id字段设置为主键 |

### 数据库 database

- show dbs 显示所有数据库
- db <db_name> 显示名称为 db_name 的数据库
- use <db_name> 链接到指定数据库

### 集合 collection

- 集合是 mongoDB 的文档组，类似 mysql 数据库中的表格。
- 当插入第一条数据，集合就会被创建。

### 文档 document

- 文档是一个键值(key-value)对(即BSON)。
- MongoDB 的文档不需要设置相同的字段，并且相同的字段不需要相同的数据类型，这与关系型数据库有很大的区别，也是 MongoDB 非常突出的特点。

| RDBMS  | MongoDB |
| ------ | ------ |     
| 数据库  | 数据库 |
| 表格    | 集合 |
| 行      | 文档 |
| 列	  | 字段 |
| 表联合  | 嵌入文档 |
| 主键    | 主键 (MongoDB 提供了 key 为 _id ) |

注意:
1. 文档中的键/值对是有序的。
2. 文档中的值不仅可以是在双引号里面的字符串，还可以是其他几种数据类型（甚至可以是整个嵌入的文档)。
3. MongoDB区分类型和大小写。
4. MongoDB的文档不能有重复的键。
5. 文档的键是字符串。除了少数例外情况，键可以使用任意UTF-8字符。

### MongoDB 数据类型

| 数据类型   | 描述 |
| ------      | ------ | 
| String      | 字符串。存储数据常用的数据类型。在 MongoDB 中，UTF-8 编码的字符串才是合法的。|
| Integer	  | 整型数值。用于存储数值。根据你所采用的服务器，可分为 32 位或 64 位。|
| Boolean	  | 布尔值。用于存储布尔值（真/假）。|
| Double	  | 双精度浮点值。用于存储浮点值。|
| Min/Max keys|	将一个值与 BSON（二进制的 JSON）元素的最低值和最高值相对比。|
| Arrays	  | 用于将数组或列表或多个值存储为一个键。|
| Timestamp	  | 时间戳。记录文档修改或添加的具体时间。|
| Object	  | 用于内嵌文档。|
| Null	      | 用于创建空值。|
| Symbol	  | 符号。该数据类型基本上等同于字符串类型，但不同的是，它一般用于采用特殊符号类型的语言。|
| Date	      | 日期时间。用 UNIX 时间格式来存储当前日期或时间。你可以指定自己的日期时间：创建 Date 对象，传入年月日信息。|
| Object ID	  | 对象 ID。用于创建文档的 ID。|
| Binary Data |	二进制数据。用于存储二进制数据。|
| Code	      | 代码类型。用于在文档中存储 JavaScript 代码。|
| Regular expression | 正则表达式类型。用于存储正则表达式。|