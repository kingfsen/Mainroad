# Mainroad

I forked this theme from [Vimux/Mainroad](https://github.com/Vimux/Mainroad)

[在线预览](https://youendless.com)

![screenshot](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/pc_index.png)

这个主题开发者模板设计的非常规整，整体简洁，特别适合个人博客系统。个人在此基础上修改了部分样式，同时新增了部分功能，目前还在DIY中，作为一个后端开发者，还在努力学习前端技术。

## 主题变化

**新增部分**

+ 增加了中文语言展示
+ 侧边栏增加了友情链接(样式探索中)
+ 增加了多渠道分享按钮，使用的js插件来自[share.js](!https://github.com/overtrue/share.js)，在此基础上调整了一些样式，本主题安装share.js教程        点击[此处](https://youendless.com/post/share_js/)查看，通过参数控制网站顶部以及文章尾部是否显示分享按钮。
+ 文章尾部增加了`相关文章`功能，主要通过tags匹配相关文章。
+ 原主题默认支持Disqus评论系统，考虑到国内无法翻墙，加入了isso评论系统支持，默认不开启，DisqusShortName为空，并且参数isso_open = true才会开启        isso， isso需要自己搭建后端服务，具体教程详见[开源评论系统isso搭建](https://youendless.com/post/isso/)，几分钟就能搞定，相对比较简单，isso支   持匿名评论以及admin管理等特色。
+ Hugo内置支持了Syntax Highlighter代码高亮，同时支持使用Pygments样式，考虑到写Markdown文件时不方便用Hugo的特定渲染语法，我加入了Prims的支持，
  Prims开启了显示行数，同时右上角支持一键copy代码功能，如果不想用prims高亮功能，则在写Markdown文件时代码块标点之后不要加语言名字。
  \```Go 
  这种会自动加了高亮样式。
+ 增加了百度网页自动推送功能，但是经常会被谷歌浏览器截断，通过参数baidu_push控制是否开启推送。
+ 增加了百度统计功能，如果设置了baidu_count_id，则自动开启了百度统计功能，baidu_count_id是你的网站在百度统计分配的。

**修改部分**
+ 修改了内容区的宽度大小，由1080改成了1280，稍微调整了左右两边的占比比例
+ 修改了tags的显示样式(样式正在探索中)
+ 去除了文章内容页面展示的缩略图原图
+ 文章Title下面增加了字数统计(icon待更换)

手机版样式

- 文章列表

  ![mobile_list](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_list.jpg)

- 文章分享

  ![mobile_share](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_share.jpg)

- 文章评论区

  ![mobile_comment](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_comment.jpg)


## Configuration

配置参数解释说明

```toml
baseurl = "/"
title = "Mainroad"
defaultContentLanguage = "zh-cn"
paginate = "10" # Number of posts per page
theme = "mainroad"
disqusShortname = "" # Enable comments by entering your Disqus shortname
googleAnalytics = "" # Enable Google Analytics by entering your tracking id
hasCJKLanguage = true
summaryLength = "145" 

[Author] # Used in authorbox
  name = "John Doe"
  bio = "John Doe's true identity is unknown. Maybe he is a successful blogger or writer. Nobody knows it."
  avatar = "img/avatar.png"

[Params]
  subtitle = "Just another site" # Subtitle of your site. Used in site header
  description = "John Doe's Personal blog about everything" # Site description. Used in meta description
  #copyright = "John Doe" # copyright holder, otherwise will use site title
  opengraph = true # Enable OpenGraph if true
  twitter_cards = true # Enable Twitter Cards if true
  readmore = false # Show "Read more" button in list if true
  authorbox = true # Show authorbox at bottom of pages if true
  toc = true # Enable Table of Contents
  post_navigation = true # Show post navigation at bottom of pages if true
  # post_meta = ["date", "categories", "translations"] # Order of post meta information. Use ["none"] to turn off completely.
  postSections = ["post"] # the section pages to show on home page and the "Recent articles" widget
  #postSections = ["blog", "news"] # alternative that shows more than one section's pages
  #dateformat = "2006-01-02" # change the format of dates
  #mathjax = true # Enable MathJax
  #mathjaxPath = "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js" # Specify MathJax path
  #mathjaxConfig = "TeX-AMS-MML_HTMLorMML" # Specify MathJax config
  customCSS = ["css/custom.css"] # Include custom CSS files
  
  post_related = true #是否开启 相关文章 索引功能
  share_open = true #是否开启文章尾部分享
  baidu_push = true #是否开启百度自动网页推送
  baidu_count_id = "c79473" #百度统计id
  isso_open = true # "是否开启isso评论系统"
  friend_link_open = true #是否显示友情链接
  share_top_show = true #是否展示菜单右上角分享按钮
  
[[Params.friendlink]]   #友情链接
  link = "https://youendless.com"   #链接地址
  title = "君无止境"                 #链接显示文字
  desc = "一个专注于容器技术的博客"    #链接站点描述文字(暂未使用，待开发)
  
[[Params.friendlink]]
  link = "https://youendless.com"
  title = "君无止境"
  desc = "一个专注于容器技术的博客"

[Params.isso] #isso评论插件
  prefix = "isso"  #请求的前缀，默认isso，那么isso服务的请求url则是baseURL/isso/，可以填写一个完整路径https://youendless.com/isso/

[Params.sidebar]
  home = "right" # Configure layout for home page
  list = "left"  # Configure layout for list pages
  single = false # Configure layout for single pages
  # Enable widgets in given order
  widgets = ["search", "recent", "categories", "taglist", "social", "languages", "friendlink"]

[Params.widgets]
  recent_num = 5 # Set the number of articles in the "Recent articles" widget
  tags_counter = false # Enable counter for each tag in "Tags" widget (disabled by default)

[Params.widgets.social]
  # Enable parts of social widget
  facebook = "username"
  twitter = "username"
  instagram = "username"
  linkedin = "username"
  telegram = "username"
  github = "username"
  gitlab = "username"
  bitbucket = "username"
  email = "example@example.com"
  google_plus = "profileid"
```

## Demo完整的配置参数

```toml
LanguageCode = "zh-cn"
title = "君无止境"
hasCJKLanguage = true
theme = "Mainroad"
summaryLength = "145"
defaultContentLanguage = "zh-cn"
    
[Params]
  description = "专注于Java、Go、Kubernetes、Docker、Harbor、Helm等容器相关技术方向开发"
  subtitle = "代码沉淀技术，技术成就梦想!   Hugo、Java、Go、Docker、Harbor、Kubernetes~"
  keywords = "youendless,君无止境Hugo,Java,Go,Kubernetes,Docker,Harbor,Helm,容器技术,博客,静态博客"
  readmore = true
  dateformat = "2006-01-02"
  post_navigation = true
  post_related = true
  share_open = true
  baidu_push = true
  baidu_count_id = "1f38fa809"
  authorbox = true
  isso_open = true
  friend_link_open = true
  toc = true
  share_top_show = true
  
[Author] # Used in authorbox
  name = "文章作者kingfsen"
  bio = "一个不会写Bug的后端开发工程师，擅长Java、Go等编程语言。"
  avatar = "img/avatar.png"
  
[[Params.friendlink]]
  link = "https://youendless.com"
  title = "君无止境"
  desc = "一个专注于容器技术的博客"
  
[[Params.friendlink]]
  link = "https://youendless.com"
  title = "君无止境"
  desc = "一个专注于容器技术的博客"
  
[Params.isso]
  prefix = "isso"

[Params.sidebar]
  home = "right"
  list = "right"
  single = "right"
  widgets = ["search", "languages", "recent", "categories", "taglist", "social", "friendlink"]

[Params.widgets]
  recent_num = 10
  tags_counter = true

[menu]
[[menu.main]]
  identifier = "post"
	name = "博客"
	title = "技术博客文章"
	url = "/post/"

[[menu.main]]
  identifier = "about"
	name = "关于我"
	title = "博客作者的资料信息"
	url = "/about/"
	
[[menu.main]]
  identifier = "timeline"
	name = "时间轴"
	title = "博客创作时间轨迹"
	url = "/timeline/"
	
[Params.widgets.social]
  github = "kingfsen"
  email = "qq.com"
  
[related]
   threshold = 80
   includeNewer = true
   toLower = true
   [[related.indices]]
     name = "tags"
	 weight = 100
```
