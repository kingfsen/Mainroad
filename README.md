**推荐一款便宜实惠的国外云服务器，只需验证一个邮箱，支持支付宝付款，搭建网站无需任何备案审核**
<br/>
**按量付费，首次充10刀(70元)然后送50刀，很划算！**

<a href="https://www.vultr.com/?ref=8356490"><img src="https://www.vultr.com/media/banners/banner_728x90.png" width="728" height="90"></a>


# Mainroad

I forked this theme from [Vimux/Mainroad](https://github.com/Vimux/Mainroad)

[在线预览](https://youendless.com)

![screenshot](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/pc_index.png)

这个主题开发者模板设计的非常规整，整体简洁，特别适合个人博客系统。个人在此基础上修改了部分样式，同时新增了部分功能，目前还在DIY中，作为一个后端开发者，还在努力学习前端技术。

## 主题变化

**新增部分**

- 增加了中文语言展示
- 侧边栏增加了友情链接
- 增加了一键分享功能，使用的JS插件是[share.js](!https://github.com/overtrue/share.js)，在此基础上调整了一些样式，Share.js插件安装请查看[此处](https://youendless.com/post/share_js/)
- 文章结尾增加了 `相关文章` 链接功能，通过文章tags匹配相关联文章
- 新增isso评论系统，默认不开启，原主题默认支持Disqus，如果DisqusShortName参数为空并且isso_open设置为true则开启isso功能。isso需要自己搭建后端服务，
	具体搭建教程详见[开源评论系统isso搭建](https://youendless.com/post/isso/)，几分钟就能搞定，相对比较简单，评论数据落地在本地服务器，
	同时支持匿名评论以及admin管理等特色。
+ Hugo内置了Syntax Highlighter代码高亮，同时支持使用Pygments样式，考虑到写Markdown文件时不方便用Hugo的特定渲染语法，加入了Prims的支持。
	Prims能显示代码行数，同时右上角有一键复制代码代码功能按钮，如果不想用prims高亮功能，则在写Markdown文件时代码块标点之后不要加语言名字。
	
	```
	\```Go
		...code
	
	\```
	```
	
	这时code会自动使用Prims代码高亮样式(请忽略展示中的`\`)，下面的则不会使用。
	
	```
	\```
		...code
	\```
	```
+ 增加了百度网页自动推送功能，但是经常会被谷歌浏览器截断，通过参数baidu_push控制是否开启推送。
+ 增加了百度统计功能，如果设置了baidu_count_id，则自动开启了百度统计功能，baidu_count_id是你的网站在百度统计分配的。
+ 增加一键回顶部按钮
+ 自定义显示当前页前后页码数量，最后页、首页数量，通过参数paginate_step设置，不设置默认值5。

![page](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/page.png)

+ 增加google广告，设置google_ads_id即可。


+ 添加了归档页面

博客目录下添加 archives.md, `content/post/archives.md`
内容如下

```cpp
---
title: "文章归档"
layout: archives
hidden: true
type: posts
summary: 历史文章按照年月归档.
url: /archives/
---
```

访问博客主页的 archives 目录即可查看归档页面.

也可以显式添加到 menu 中, 则在配置文件 config.toml 中添加如下内容:

[[menu.main]]
  identifier = "archives"
    name = "归档"
    title = "历史归档页面"
    url = "/archives/"

**修改部分**

+ 修改了内容区的宽度大小，由1080改成了1280，稍微调整了左右两边的占比比例
+ 修改了tags的显示样式(样式正在探索中)
+ 去除了文章内容页面显示缩略图原图
+ 文章Title下面增加了字数统计(icon待更换)



### 手机版预览

| 文章列表   | 文章分享  | 文章评论  |
| :----: | :----: | :----: |
| ![mobile_list](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_list.jpg)  | ![mobile_share](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_share.jpg) | ![mobile_comment](https://raw.githubusercontent.com/kingfsen/blog-images/master/blog/mobile_comment.jpg) |


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
