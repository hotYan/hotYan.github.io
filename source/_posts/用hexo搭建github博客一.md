---
title: 用hexo搭建github博客一
date: 2018-05-29 15:38:51
tags: 
    - hexo
    - 博客 
categories: hotYan_博客之路
---
## 搭建博客 <span style="font-size:.5em">[待完善]</span>
> 一直想搭个人博客,却无从下手？？
  
  
<!--more-->
## 链接自取
> 个人比较喜欢先甩参考链接,可以选择直接去看参考链接。
>- [参考教程1](http://dmkf.xyz/2017/03/12/6272440/)  
>- [参考教程2](https://sunny73.github.io/2018/02/10/Build-my-first-blog/)  
>- [Hexo官网文档](https://hexo.io/docs/)

【注意】第二个链接也是参考第一个写的,第一个链接加载超级慢,可以选择看第二个


----------
## 一、准备工作
>1.默认已有GitHub账号  

- 没有GitHub账号？？[点击注册](https://github.com/)  

>2.默认已安装Git  

- 没有安装Git？？[了解如何安装](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)


>3.默认已安装 Node.js  

- 没有安装Node.js??[了解如何安装](https://hotyan.github.io/2018/05/30/%E7%94%A8nvm%E8%A3%85node-js/)

>4.Install Hexo    

- 全局下载hexo

        $ npm install -g hexo-cli
- 查看是否成功  

        $ hexo

进入[Hexo官网文档](https://hexo.io/docs/)了解更多
## 二、初始化博客
        $ hexo init HotYan_Bolg //创建一个放在博客项目的文件
        $ cd HotYan_Bolg       //进入该文件
        $ npm install       //安装依赖包

进入HotYan_Bolg,已自动生成以下文件

        .
        ├── _config.yml
        ├── package.json
        ├── scaffolds
        ├── source
        |   ├── _drafts
        |   └── _posts
        └── themes
## 三、本地搭建
>1.修改_config.yml文件  

根据个人情况修改以下部分:

        /*修改前*/
        # Site
        title: # The title of your website
        subtitle: # The subtitle of your website
        description: # The description of your website
        author: # Your name
        language: # The language of your website
        timezone:

        /*修改后*/
        # Site
        title: hotYan's Blog 
        subtitle: 爱美的程序媛
        description: 毒鸡汤Yan
        keywords:
        author: hotYan
        language: zh-CN
        timezone: Asia/Shanghai

【每一项的填写,其 **:** 后面都要保留一个空格,下同。】

>2.本地运行  

        $ cd  HotYan_Blog //进入博客文件夹目录

        $ hexo generate // 生成文件
        $ hexo server   //本地部署
        
        /*简写如下*/
        $ hexo g
        $ hexo s

可在浏览器输入地址 http://host:4000 进行查看

## 四、配置远程环境,线上运行
【不一定要线上运行可跳过此步骤】

>1.github新建一个库

        库名格式为: username.github.io //非常重要！！！

你可能想了解一下[GitHub Pages](https://pages.github.com/)
>2.配置_config.yml文件
- 配置统一资源定位符（个人域名）  

        /*配置前*/
        # URL
        ## If your site is put in a subdirectory, .....
        url: http://yoursite.com/child
        
        /*配置后*/  
        # URL
        ## If your site is put in a subdirectory,......
        url: http://github.com

- 配置部署  

        # Deployment
        ## Docs: https://hexo.io/docs/deployment.html
        deploy:
            type: git 
            /*repo项是之前Github上创建好的仓库地址*/
            repo: https://github.com/hotYan/hotYan.github.io.git
            branch: master

>3.线上运行  

        $ cd  HotYan_Blog //进入博客文件夹目录
        
        $ hexo generate // 生成文件
        $ hexo deploy   // 线上部署
        
        /*简写如下*/
        $ hexo g
        $ hexo d

可在浏览器输入博客地址 https://hotyan.github.io/ 进行查看

## 五、修改主题

1.[下载Next主题](https://github.com/iissnan/hexo-theme-next)  

2.下载后,将压缩包解压缩,复制其中名称为next的文件夹到你博客文件的themes下  

3.修改博客文件根目录下的_config.yml,将主题改为next

        # Extensions
        ## Plugins: https://hexo.io/plugins/
        ## Themes: https://hexo.io/themes/
        # theme: landscape
            theme: next   

## 六、更新Hexo部署
        $ cd  HotYan_Blog //进入博客文件夹目录

        $ hexo clean    // 清理缓存
        $ hexo generate // 生成文件
        $ hexo deploy   // 线上部署
        
        /*简写如下*/
        $ hexo clean
        $ hexo g
        $ hexo d
## 七、创建新文章
>1.创建  

        $ cd  HotYan_Blog   //进入博客文件夹目录
        $ hexo new "用hexo搭建github博客一"  // 新建一篇文章

可在博客文件夹下的source/_post查看你新建的markdown文件  

>2.编写内容

如果不清楚如何编写markdown文件,你可能需要先了解一下。
- [参考链接1](https://github.com/younghz/Markdown)
- [参考链接2](http://xianbai.me/learn-md/article/syntax/blockquotes.html)

>3.更新Hexo部署(同上六)