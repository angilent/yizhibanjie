---
pubDatetime: 2023-11-27T21:10:00Z
title: 如何用 astro 搭建个人博客
tags:
  - astro
  - 网站建设
description: 使用 astro 框架和 AstroPaper theme 搭建博客入门
---

Astro 都没太搞懂是什么，但可以很快的用astro 做一个不错的个人blog。

- https://astro.new/

## Table of contents

## 读手册就好

Astro 的文档系统属于超级赞的。基本按照文档一步一步走就可以了。
下面的文档就是一个很好的开始：

- [搭建你的 Astro 博客 🚀 Astro 文档](https://docs.astro.build/zh-cn/tutorial/0-introduction/)

Astro 的手册里甚至有文档阅读的进度跟踪功能。从下图可以看出，我基本学会安装后，就直接去看 astro theme 的说明了。
![教程跟踪](@assets/images/tracing.png)
我用的是 npm 安装 astro 然后在 VS code 中做编程，最后用 Github Action 把 blog 部署到了 Github Pages上了。

Astro 的实时反馈机制挺好的，现在是不是框架都可以做成这样了。用 MicroBlocks 的术语来讲就是 liveness。不过 astro 只能在 dev 环境的实时反馈，应该也够用了。

## 选用 astro theme主题时的注意事项

当选择 astro paper 作为模版构建 blog 时，还需要阅读 astro paper 的配套文档。从使用 astro paper 模版创建项目开始：

- https://astro-paper.pages.dev/posts/how-to-configure-astropaper-theme/

### 路径问题

因为需要部署到gitpage，还不是github 默认的那个。所以需要在URL 里加一个子目录的路径。在 astro 里用了base url 的配置方式，指定子目录到URL中。所以你访问这个 blog 的路径是：https://angilent.github.io/yizhibanjie/
在配置文件中添加以下配置后，还需要对应的修改 astro paper 中的模版页面中的链接。
base: "/yizhibanjie"
![m1](@assets/images/baseurl1.png)![m2](@assets/images/baseurl2.png)
如何部署 Astro 到 Github pages 可以参考 Astro 官方的文档：

- [部署你的 Astro 站点至 GitHub Pages](https://docs.astro.build/zh-cn/guides/deploy/github/)

### 更换默认页面配色

https://astro-paper.pages.dev/posts/how-to-configure-astropaper-theme/
按照上面链接的说明做就好了，在 src/styles/base.css 这个文件中修改配送就好。
最后我放弃了芭比粉，选了蓝绿的配色。（毕竟还是要发给别人去看的呀～）

### 添加 TOC 目录模块

这个很简单只需要安装说明书，在MD 中添加 Table of contents 标题就好了。框架会自动帮你做好目录。

### RSS输入

因为用了base url，RSS 输出也会有影响。RSS 文件中的链接地址是不包含 base url 部分的。所以目前先把rss功能入口的图标给去掉了。我怀疑 sitemap 的链接也会出问题。不过还没去查。

### 上传图片

blog 中上传的图片必须要放到 src/assets/images/ 目录下，最好还是经过压缩的 https://tinypng.com/ 。引用图片时要用到 @assets 的写法，但这样在 vs code 里就不能被直接点链接打开了。

### Markdown 默认模版精简

根据 astro paper 的文档可以把一些用不上的熟悉从 MD 的头信息中去除。比如作者，是否feature，draft 什么的。

## 还有一些没搞定的

- 图片大小调整
- RSS 中的文章链接
- TOC 换成中文描述
- Social 部分还需要添加 B 站部分
- blog 的题图（没有也省的去找图了）

这是一篇在不断尝试和总结中完成的文章。才发现好久不打字，双拼都快忘了。有了新工具，还是对写内容有激励的。

最后说一下为什么不写公众号和竹白？而开始写blog了呢？我想像风一样自由。实践是写不出来总觉得的是坑不好。所以换个坑试试。希望能坚持。至少这里写东西，不需要等审核。或者收到被隐藏通知啥的。但这里写东西很可能就发不出去了，或者人进去了。还是很刺激的。

写完了对 astro 了解的都不能算入门。只是托好文档的福，可以照猫画虎的弄下来。还有之前 Hugo 的经验对这类 blog 框架不陌生。希望对入门的人有所帮助，没帮上请自行查看文档。再表扬一下 astro 的文档，真的是质量超级高。👍
