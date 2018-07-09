---
title: Mysql命令小结
date: 2018-06-19 22:04:20
tags: 
    - 图书管理系统
    - Express
    - ejs
    - Mysql

categories: Mysql
---
## Mysql语句 <span style="font-size:.5em">[待更新]</span>
>常用命令小结

<!--more-->

## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接。
>- [参考链接](https://juejin.im/post/5ae55861f265da0ba062ec71)

----


## 一、DATABASE

新建数据库：

        CREATE DATABASE database_name;
删除数据库：

        DROP DATABASE database_name;
查看所有可用的数据库：
    
        SHOW DATABASES;  
选择数据库：

        USE database_name;
显示数据库服务器的状态信息：

        SHOW STATUS;  
获取当前所选的数据库中所有可用的表：

        SHOW TABLES; 
获取表中所有列的信息：
    
        SHOW COLUMNS FROM table_name; 

## 二、TABLE
新建表:

        CREATE TABLE table_name;
删除表,使用DROP TABLE子句:

        DROP TABLE table_name。

清空表中记录:

        delete from table_name;

显示表中的记录:

        select * from table_name;


## 三、导入导出
导入.sql

        source .sql文件路径


备份数据,导出.sql文件

        cd 存放目录
        mysqldump -u root_name -p database_name>file_name.sql
        例如:
        mysqldump -u root -p hotyan>db.sql
退出MYSQL命令:

        exit(回车)
