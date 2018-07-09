---
title: 用nvm装node.js
date: 2018-05-30 22:23:44
tags: 
- nvm 
- node.js
- npm 
categories: Install
---

## 关于node安装  <span style="font-size:.5em">[持续完善]</span> 
> 本地安装？全局安装？nvm安装？傻傻分不清楚？
使用 nvm 管理不同版本的 node 与 npm

<!--more-->
## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接。 
>- 了解[NVM](https://github.com/creationix/nvm)  
>- 了解[Node.js](https://nodejs.org/en/)  
>- 了解[通过包管理器安装Node.js](https://nodejs.org/en/download/package-manager/)NVM部分  
>- 了解[NPM](https://www.npmjs.com/get-npm)  
>- [本文参考链接](https://www.runoob.com/w3cnote/nvm-manager-node-versions.html) 
-----
## 一、卸载全局安装的 node
在官网下载的 node 安装包,运行后会自动安装在全局目录,使用过程中经常会遇到一些权限问题,用以下方法卸载全局安装的 node。(不需要卸载则跳过此步骤)

>删除 node 和 node_modules 相关的文件和文件夹  

打开Finder,按 shift+command+G 来打开前往文件夹的窗口,分别进入下列目录,删除 node 和 node_modules 相关的文件和文件夹

        /usr/local/lib
        /usr/local/include

>如果你是使用的 brew install node 安装的,还需要在终端中执行以下命令来卸载
    
        $ brew uninstall node 
    
>检查 node 和 node_modules 相关文件/文件夹是否删除成功    

检查个人主文件夹下面的所有的 local、lib 以及 include 文件夹，并且删除所有与 node 和 node_modules 相关的文件以及文件夹

>进入 /usr/local/bin 并删除 node 可执行文件  


>你可能还需要在终端中输入一些额外的指令  


        $ sudo rm /usr/local/bin/npm
        $ sudo rm /usr/local/share/man/man1/node.1
        $ sudo rm /usr/local/lib/dtrace/node.d
        $ sudo rm -rf ~/.npm
        $ sudo rm -rf ~/.node-gyp
        $ sudo rm /opt/local/bin/node
        $ sudo rm /opt/local/include/node
        $ sudo rm -rf /opt/local/lib/node_modules

## 二、OSX 安装 NVM
>用 X-Code 的命令行工具  

运行以下命令

        $ xcode-select --install
        
        $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
    

## 三、安装多版本 node
查看远程服务器上所有的可用版本  


        $ nvm ls-remote

安装最新版 Node    


        $ nvm install node 

安装某一版本(4.2.2)   


        $ nvm install 4.2.2

安装4.2 系列的最新的一个版本   


        $ nvm install 4.2
nvm 遵守语义化版本命名规则,nvm 会寻找 4.2.x 中最高的版本来安装。



## 四、在不同版本间切换
每当安装了一个新版本 Node 后,全局环境会自动把这个新版本设置为默认。

>nvm 提供 nvm use 命令用于版本切换  


切换到最新版：

        $ nvm use node

切换到 4.2.2：

        $ nvm use 4.2.2
切换到最新的 4.2.x：

        $ nvm use 4.2


每次执行切换的时候，系统都会把 node 的可执行文件链接放到特定版本的文件上。

## 五、用 nvm 给不同的版本号设置别名
给4.2.2 版本号起个别名hotyan-version  

        $ nvm alias hotyan-version 4.2.2

运行:

        $ nvm use hotyan-version
取消别名：

        $ nvm unalias hotyan-version  

## 六、列出已安装实例
        $ nvm ls

## 七、确认某个版本Node的路径  

        $ nvm which 4.2.2

## 八、检查是否成功安装node和npm
当成功下载Node.js时,会自动安装npm。
检查Node

        $ node -v
确认npm

        $ npm -v
