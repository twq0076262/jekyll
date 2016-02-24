# 附加功能

Jekyll 提供了诸多 (可任选) 的附加功能，你可以依据你使用 Jekyll 的需求来选择安装它们。

## LaTeX 支持

Maruku 自带了将 LaTeX 渲染成 PNG 的功能可供选择，此功能使用 blahtex (版本 0.6)，必须和 `dvips` 一起被置于你的` $PATH` 中。 如果你需要 Maruku 不调用默认位置的 `dvips`，请查看 [Remi 的 Maruku fork](http://github.com/remi/maruku).

## 可选的 Markdown 处理器

虽然 Jekyll 默认使用 Maruku 来转换 Markdown ，你还可以使用以下三个预定义的 markdown 解析器中的任意一个，或者你也可以自己实现一个。

## RDiscount

如果你更喜欢使用 [RDiscount](http://github.com/rtomayko/rdiscount) 来替代 [Maruku](http://github.com/bhollis/maruku) 解析 Mardown，你只需确认已将其安装：

```
$ [sudo] gem install rdiscount
```

然后在你的 `_config.yml` 文件内选择 RDiscount 作为 Markdown 引擎，使 Jekyl 可以读取该选项来运行。

```
# _config.yml 中
markdown: rdiscount
```

## Kramdown

你还可以选择 Kramdown 来替代 Maruku 解析 Mardown，你只需确认 Kramdown 已被安装：

```
$ [sudo] gem install kramdown
```

然后在你的` _config.yml` 文件内选择 Kramdown 作为 Markdown 引擎。

```
# _config.yml 中
markdown: kramdown
```

Kramdown 提供了各种选项用来自定义其 HTML 的输出。 [配置](http://jekyll.bootcss.com/docs/configuration/)页面列出了 Jekyll 所使用的默认选项。一份完整的选项列表也可见于 [Kramdown 网站](http://kramdown.rubyforge.org/options.html)。

### 自定义

如果你对以上四个内置的 markdown 解析器都不满意，没关系，你还可以自己写个插件：

```
require 'jekyll'
require 'some_renderer'

class Jekyll::Converters::Markdown::MyCustomParser
  def initialize(config)
    @site_config = config
  end

  def convert(content)
    # (this _must_ return the resulting String after the rendering)
    SomeRenderer.new(@site_config).to_html(content)
  end
end
```

一旦你的解析器完成了，就可以在 `_config.yml` 文件中告诉 Jekyll 使用你自己的 markdown 解析器了：

```
markdown: MyCustomParser
```

(注意，这是 大小写敏感的，并且，只需指定 `Jekyll::Converters::Markdown` 后面的部分就可以。) 仅此而已！