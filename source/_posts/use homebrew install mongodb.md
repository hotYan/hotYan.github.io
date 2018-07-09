---
title: Mac Use Homebrew Install Mongodb
date: 2018-05-29 15:38:51
tags: 
    - Homebrew
    - Mongodb 
categories: Install
---

## Mac Use Homebrew Install Mongodb <span style="font-size:.5em">[待完善]</span>
> 课程设计,一开始是打算用Express+ejs+Mongodb,但是后期,使用mongoose出现了问题,尝试解决,没有成功后,就放弃了,转而使用Mysql。将安装过程记录一下。
  
<!--more-->
## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接,以下内容作为我的个人记录,以我的角度去记录,总结。
>- [homebrew官网](https://brew.sh/)
>- [参考链接](https://aaaaaashu.gitbooks.io/mac-dev-setup/content/Homebrew/index.html)  
------
## 一、安装Homebrew
打开Terminal并运行以下命令 

        $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

【注意】 Homebrew将作为安装过程的一部分下载并安装Xcode 8.0的命令行工具。

## 二、安装MongoDB

1.运行以下命令进行安装mongodb  
    
        $ brew install mongodb

2.将mongodb升级，确保版本最新  
    
        $ brew upgrade mongodb

3.创建一个目录，用来保存mongo默认的数据
    
        $ mkdir -p /data/db

4.给目录以可读可写的权限 

        $ chown `id -u` /data/db

5.启动 

        $ brew services start mongodb



## 三、未正常关闭导致数据库突然启动不了
1.删除掉mongod.lock文件，然后重新启动

2.如果还是不可以，先查看一下进程

        $ ps -aef | grep mongo

3.然后根据进程ID杀掉进程

        $ sudo kill 6955

4.重新启动mongodb服务

        $ brew services start mongodb

 