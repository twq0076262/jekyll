# 快速指南
以下是一个获取最简单 Jekyll 模板并生成静态页面的方法。

```
~ $ gem install jekyll
~ $ jekyll new myblog
~ $ cd myblog
~/myblog $ jekyll serve
# => Now browse to http://localhost:4000
```

就是这么简单。从现在开始，你可以通过创建文章、改变头信息来控制模板和输出、修改 Jekyll 设置来使你的站点变得更有趣～

> 新站点的默认 Markdown 引擎是 Redcarpet,在 Jekyll 1.1 中，我们改变了默认的 Markdown 引擎，对于 `jekyll new` 产生的新站点，引擎将采用 Redcarpet。
安装过程中有问题？请确认是否安装了所有 [依赖的工具](http://jekyll.bootcss.com/docs/installation/) 。