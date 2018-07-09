---
title: 用hexo搭建github博客二
date: 2018-05-29 15:39:01
tags: 
    - hexo
    - 博客 
categories: hotYan_博客之路
---
## 优化博客 <span style="font-size:.5em">[待完善]</span>
> 搜索了很多Next主题的效果，总结了下常用的效果~  

<!--more-->
## 链接自取
>个人比较喜欢先甩参考链接,可以选择直接去看参考链接。
- [参考链接1](http://shenzekun.cn/hexo%E7%9A%84next%E4%B8%BB%E9%A2%98%E4%B8%AA%E6%80%A7%E5%8C%96%E9%85%8D%E7%BD%AE%E6%95%99%E7%A8%8B.html)
- [参考链接2](https://www.jianshu.com/p/efbeddc5eb19)
- [参考链接3](https://www.jianshu.com/p/f054333ac9e6)
- [参考链接4](https://www.jianshu.com/p/1f8107a8778c)
- [Hexo官网主题](https://hexo.io/themes/)  

------------------

## 一、修改Next主题模式
>修改themes/next/_config.yml文件Schemes属性  

注意不要跟根目录下的_config.yml混淆

        # Schemes
            #scheme: Muse   
            #scheme: Mist
            scheme: Pisces
            #scheme: Gemini


NexT主题默认使用Muse模式,根据自己的喜好选择,我比较喜欢Pisces,但是看了源码做了些样式修改。
>更新Hexo部署  

每次修改后都可以更新部署,也可最后再一次性部署。后面不再赘述。

        $ cd  HotYan_Blog //进入博客文件夹目录

        $ hexo clean    // 清理缓存
        $ hexo generate // 生成文件
        $ hexo deploy   // 线上部署
        
        /*简写如下*/
        $ hexo clean
        $ hexo g
        $ hexo d
## 二、设置首页预览摘要
了解一下[Next官网介绍的三种方法](http://theme-next.iissnan.com/faqs.html#%E9%A6%96%E9%A1%B5%E6%98%BE%E7%A4%BA%E6%96%87%E7%AB%A0%E6%91%98%E5%BD%95)

我使用的是用`<!-- more --> `进行手动截断

## 三、侧边栏显示效果
>修改themes/next/_config.yml文件sidebar属性 


        sidebar:
            # Sidebar Position, available value: left | right (only for Pisces | Gemini).
            position: left
            #position: right //修改侧边栏位置

            # Sidebar Display, available value (only for Muse | Mist):
            #  - post    expand on posts automatically. Default.
            #  - always  expand for all pages automatically
            #  - hide    expand only when click on the sidebar toggle icon.
            #  - remove  Totally remove sidebar including sidebar toggle.
            #display: post      //默认
            display: always     //一直显示
            #display: hide      //初始隐藏
            #display: remove    //移除侧边栏

根据提示,设置自己喜欢的样式,我是Pisces主题,设置侧边栏在左边,且一直显示。
>更新Hexo部署(同上)
##  四、侧边栏社交链接
>修改themes/next/_config.yml文件social属性
    
        /*文字链接*/
        social:
            GitHub: https://github.com/hotYan || github
            E-Mail: mailto:15823566422@163.com || envelope
        /*链接前图标*/
        social_icons:
            enable: true
            GitHub: github 

我只添加了GitHub、E-Mail。
>更新Hexo部署(同上)

## 五、设置RSS
>安装 hexo-generator-feed 插件  

RSS需要有一个Feed链接，而这个链接需要靠hexo-generator-feed插件来生成
    
        $ cd HotYan_Blog
        $ npm install hexo-generator-feed --save
>修改/_config.yml文件  

        #type: RSS的类型(atom/rss2)
        #path: 文件路径,默认是atom.xml/rss2.xml
        #limit:展示文章的数量,使用0或则false代表展示全部
        
        # RSS订阅插件
        feed: 
            type: atom
            path: atom.xml
            limit: 0
        #RSS订阅支持
        plugins: hexo-generate-feed

>修改themes/next/_config.yml文件rss属性   

        rss: /atom.xml 
>更新Hexo部署(同上)
## 六、添加菜单选项
默认情况下，菜单导航栏有首页、归档、关于三个选项，我们可以自行添加

>修改themes/next/_config.yml文件menu属性

        menu:
            home: / || home                //默认有
            about: /about/ || user         // 默认有
            tags: /tags/ || tags            //自行添加
            categories: /categories/ || th  //自行添加
            archives: /archives/ || archive   //默认有
比如我添加了tags、categories
>创建文件夹  

        $ cd  HotYan_Blog //进入博客文件夹目录

        $ hexo new page "tags"
        $ hexo new page "categories"

>修改index.md  

在/source/目录下创建了categories、tags文件夹,在这些文件夹中分别会创建一个index.md文件,对内容type进行修改，使之分别为:

        ---
        title: categories
        date: 2018-05-29 00:02:39
        type: "categories"
        ---
----
        ---
        title: tags
        date: 2018-05-29 00:02:54
        type: "tags"
        ---
>更新Hexo部署(同上)
    
## 七、修改文章底部标签样式
>修改/themes/next/layout/_macro/post.swig文件

        <div class="post-tags">
            {% for tag in post.tags %}
                <a href="{{ url_for(tag.path) }}" rel="tag"><i class="fa fa-tag"></i> {{ tag.name }}</a>
            {% endfor %}
        </div>

搜索 `rel="tag">#`，将 `#` 换成`<i class="fa fa-tag"></i>`
>更新Hexo部署(同上)
    
## 八、文章末尾添加结束标记
>在/themes/next/layout/_macro新建passage-end-tag.swig  

添加以下内容

        <div>
            {% if not is_index %}
                <div style="text-align:center;color: #555;font-size:14px;"> - END - </div>
            {% endif %}
        </div>
>修改/themes/next/layout/_macro/post.swig文件  

在下面相应的位置添加添加相应的代码(觉得自己表达的很清楚了呢)

        {#####################}
        {### END POST BODY ###}
        {#####################}
        ...

        /*插入代码如下*/
        <div>
        {% if not is_index %}
            {% include 'passage-end-tag.swig' %}
        {% endif %}
        </div>
        /*插入到此处结束*/

        <footer class="post-footer">
        {% if post.tags and post.tags.length and not is_index %}
        ...

>修改themes/next/_config.yml文件  

在任意地方添加下面代码

        # 文章末尾添加结束标记
        passage_end_tag:
            enabled: true
>更新Hexo部署(同上)
## 九、访问量统计
>修改themes/next/_config.yml文件busuanzi_count属性  

        busuanzi_count:
            # count values only if the other configs are false
            enable: true 
            # 站点UV配置 总访问人次(一个人访问多篇文章记录一次)
            site_uv: false
            site_uv_header: 总访问量
            site_uv_footer:

            # 站点PV配置 总访问量(一个人访问多篇文章记录多次)
            site_pv: false
            site_pv_header: <i class="fa fa-eye"></i>
            site_pv_footer: 次

            # 文章PV配置 访问量
            page_pv: true
            page_pv_header: <i class="fa fa-eye"></i>
            page_pv_footer: 

我只设置了文章访问量
>更新Hexo部署(同上)
## 十、修改头像
在themes/next/source/images下放置头像
>修改themes/next/_config.yml文件avatar属性  

        avatar: ../images/avata.gif
路径为头像目录
>更新Hexo部署(同上)

## 十一、添加背景图
>修改themes/next/source/css _custom/custom.styl  

添加如下代码:

        body{
            background:url(../images/xx.jpg);
            background-size:cover;
            background-repeat:no-repeat;
            background-attachment:fixed;
            background-position:center;
        }
## 十二、修改各版块透明度
>内容板块    

- 修改在对应主题的对应.yml文件中,ID为【.content-wrap】标签下的background属性
    
         background: rgba(255,255,255,0.7); 
- 以主题Pisces为例,对应内容板块文件路径为:

        themes/next/source/css/_schemes/Pisces/_layout.styl
>菜单栏
- 修改在对应主题的对应.yml文件中,ID为【.header-inner】标签下的background属性。  
- 以主题Pisces为例,对应菜单栏文件路径为: 

        themes/next/source/css/_schemes/Pisces/_layout.styl
>站点概况
- 修改在对应主题的对应.yml文件中,ID为【.sidebar-inner】标签下的background属性
- 以主题Pisces为例,对应站点概况文件路径为: 
        
        themes/next/source/css/_schemes/Pisces/_sidebar.styl
- 修改在对应主题的对应.yml文件中,ID为【.sidebar】标签下的background属性
- 以主题Pisces为例,对应站点概况文件路径为: 
        
        themes/next/source/css/_schemes/Pisces/_layout.styl
>按钮背景  

主题共享的文件,文件位置:

        themes/next/source/css _custom/components/post/post-button.styl

## 十三、点击出现桃心
1. copy[网页](http://7u2ss1.com1.z0.glb.clouddn.com/love.js)代码
2. 在`/themes/next/source/js/src`目录下新建love.js文件,把copy的代码粘贴到此文件。
3. 在\themes\next\layout\_layout.swig 文件引入love.js
        
        在</body>标签前引入love.js
        <script type="text/javascript" src="/js/src/love.js"></script>
