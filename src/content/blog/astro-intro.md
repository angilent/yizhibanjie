---
pubDatetime: 2023-11-27T21:10:00Z
title: 如何用 astro 搭建个人博客
tags:
  - astro
  - 网站建设
description: 使用 astro 框架和 AstroPaper theme 入门
---

astro 都没太搞懂是什么，但可以很快的用astro 做一个不错的个人blog。

## Table of contents

## 读手册就好

Astro 的文档系统属于超级赞的。基本按照文档一步一步走就可以了。
下面的文档就是一个很好的开始：

- [搭建你的 Astro 博客 🚀 Astro 文档](https://docs.astro.build/zh-cn/tutorial/0-introduction/)
  Astro 的手册里甚至有文档阅读的跟踪功能。从下图可以看出，我基本学会安装后，就直接去看 astro theme 的说明了。
  ![教程跟踪](@assets/images/tracing.png)

## 选用 astro theme主题时的注意事项

当选择 astro paper 作为模版构建 blog 时，还需要阅读 astro paper 的配套文档。从使用 astro paper 模版创建项目开始：

- https://astro-paper.pages.dev/posts/how-to-configure-astropaper-theme/

### 路径问题

因为需要部署到gitpage，还不是github 默认的那个。所以需要在URL 里加一个子目录的路径。在 astro 里用了base url 的配置方式，指定子目录到URL中。所以你访问这个 blog 的路径是：https://angilent.github.io/yizhibanjie/
在配置文件中添加以下配置后，还需要对应的修改 astro paper 中的模版页面中的链接。
base: "/yizhibanjie"
![m1](@assets/images/baseurl1.png)
![m2](@assets/images/baseurl2.png)

### 更换默认页面配色

https://astro-paper.pages.dev/posts/how-to-configure-astropaper-theme/
按照上面链接的说明做就好了，在 src/styles/base.css 这个文件中修改配送就好。
最后我放弃了芭比粉，选了蓝绿的配色。（毕竟还是要发给别人去看的呀～）

### RSS输入

因为用了base url，RSS 输出也会有影响。RSS 文件中的链接地址是不包含 base url 部分的。所以目前先把rss功能入口的图标给去掉了。我怀疑 sitemap 的链接也会出问题。不过还没去查。

### 上传图片

blog 中上传的图片必须要放到 src/assets/images/ 目录下，最好还是经过压缩的 https://tinypng.com/ 。引用图片时要用到 @assets 的写法，但这样在 vs code 里就不能被直接点链接打开了。
