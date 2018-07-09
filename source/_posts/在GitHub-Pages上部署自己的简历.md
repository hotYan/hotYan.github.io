---
title: 在GitHub Pages上部署自己的简历
date: 2018-06-28 17:11:27
tags: 
- GitHub Pages
- 简历
categories: GitHub 
---
## GitHub Pages <span style="font-size:.5em">[待更新]</span>
>如何将自己的简历上传GitHub？？当我有这个想法的时候，Google了一下,有一篇教程以什么“室友”“实验楼”开头？？知乎有？CSDN有？简书还有？？主要是并没有解决我的问题,看到就有点烦了。还出现什么一篇相同的教程,被不同的人放置在不同的地方？？？

<!--more-->

## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接。
>- [GitHub Pages](https://pages.github.com/)  

看了很多教程,发现官网是说的最简洁明了又清楚的,最终解决了我的问题。建议打开[GitHub Pages](https://pages.github.com/),两边参考着看更简单易懂。

----

## 一、什么是GitHub Pages
1. GitHub Pages是一个静态站点托管服务,旨在直接从GitHub存储库托管我们的个人,组织或项目页面。不支持服务器端代码，例如PHP，Ruby或Python。   

2. 我们可以使用Jekyll Theme Chooser在线创建和发布GitHub Pages网站。我们也可以在本地工作，使用【GitHub Desktop】或【命令行】。  

注意:  
- **[GitHub Desktop](https://desktop.github.com/)**:一个上传项目到github的软件。不想用命令行的不二选择。  
- **[命令行](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)**:指使用git命令上传项目  

【PS:不会命令行没关系，谁敢说自己连一个软件都不会用呀？】  

## 二、GitHub Pages 提供什么  

在官网上有这样一句话:  

    You get one site per GitHub account and organization,and unlimited project sites. 
意思是:
      
    GitHub Pages为每个GitHub帐户/组织提供一个【站点】,以及无限制的【项目站点】。

>注意:  
>1.我们只能有一个【User or organization site】;但是我们可以有很多【Project site】。 
> 
>2.部署简历用【User or organization site】简直是大材小用,用【Project site】就可以了。  
>
>3.【User or organization site】可以拿来部署个人博客,点击[用hexo搭建github博客](https://hotyan.github.io/categories/hotYan-%E5%8D%9A%E5%AE%A2%E4%B9%8B%E8%B7%AF/)了解如何搭建个人博客。


## 三、准备工作  

1、默认已有GitHub账号,并已创建好存储库或会创建存储库。

- 没有GitHub账号？？[点击注册](https://github.com/)   
- 没有存储库？？[了解如何创建](https://help.github.com/articles/creating-a-new-repository/)     

2、默认已有html简历,命名为 index.html   

- 没有简历？？[制作并下载](http://cv.qiaobutang.com/)

## 四、简历部署
>创建新存储库 

1. 点击右上角 **+** 选择 **New repository**

2. 填写 **Repository name** 并勾选 **Initialize this repository with a README**
3. 点击 **Create repository** 完成创建

>上传简历  

1. 在新建的存储库点击 **Upload files**

2. 点击 **choose your files** 上传你的 **index.html** 文件
3. 点击 **Commit changes** 完成上传  

>部署

1. 点击 **Settings** 下滑到 **GitHub Pages** 部分

2. 修改 **Source** 为 **master branch** 并点击 **Save**
3. 再次下滑到 **GitHub Pages** 部分就会看到一个链接
    
>成功  

1. 如果不成功,再次修改 **Source** 为 **master branch** 并点击 **Save**

2. 点击链接就可以看到部署的简历
3. 将简历链接写在你的README.md或者任何地方

## 五、创建【User or organization site】
>跟创建一般存储库流程一样,只是因为我们每个用户只有一个【User or organization site】,所以存储库的名称比较唯一,必须是**username.github.io** 格式,其中username是我们在GitHub上的用户名（或组织名称  

如果不正确则不起作用，因此请确保正确无误。