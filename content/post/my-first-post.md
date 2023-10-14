+++
title = 'My First Post'
date = 2023-10-14T08:24:10+08:00
draft = true
+++

## 开始

## 创建网站

<!--more-->

### 命令

```text
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

通过终端中显示的 URL 查看您的站点。按此按钮`Ctrl + C`可停止 Hugo 的开发服务器。

### 命令解释

在目录中为您的项目创建[目录结构](https://gohugo.io/getting-started/directory-structure)`quickstart`。

```text
hugo new site quickstart
```

将当前目录更改为项目的根目录。

```text
cd quickstart
```

在当前目录中初始化一个空的 Git 存储库。

```text
git init
```

[将Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke)主题克隆到该目录中，并将其作为[Git 子模块](https://git-scm.com/book/en/v2/Git-Tools-Submodules)`themes`添加到您的项目中。

```text
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

在站点配置文件中添加一行，指示当前主题。

```text
echo "theme = 'ananke'" >> hugo.toml
```

启动Hugo的开发服务器来查看站点。

```text
hugo server
```

按此按钮`Ctrl + C`可停止 Hugo 的开发服务器。

## 配置站点

使用编辑器打开项目根目录中的[站点配置](https://gohugo.io/getting-started/configuration/)文件 ( )。`hugo.toml`

```text
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme = 'ananke'
```

进行以下更改：

1. 为您的生产站点设置`baseURL`。该值必须以协议开头并以斜杠结尾，如上所示。
2. 设置`languageCode`为您的语言和区域。
3. 为您的生产站点设置`title`。

启动 Hugo 的开发服务器以查看您的更改，请记住包含草稿内容。

```text
hugo server -D
```

这里节选出`new`与`server`这两个比较常用的命令和`-D`,`-E`,`-F`这三个参数的使用方法。更多的hugo命令可以参考[官方文档](https://gohugo.io/getting-started/usage/)。

```
使用方法:
  hugo
  hugo [flags]
  hugo [command]
  hugo [command] [flags]

节选的 command:
  new         为你的站点创建新的内容
  server      一个高性能的web服务器

节选的 flags:
  -D, --buildDrafts                包括被标记为draft的文章
  -E, --buildExpired               包括已过期的文章
  -F, --buildFuture                包括将在未来发布的文章

举几个栗子:
  hugo -D                          生成静态文件并包括draft为true的文章
  hugo new post/new-content.md     新建一篇文章
  hugo new site mysite             新建一个称为mysite的站点
  hugo server --buildExpired       启动服务器并包括已过期的文章
```



## hugo官网

https://gohugo.io/templates/internal/



## 目录结构

```fallback
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```

- **archetypes**: 储存`.md`的模板文件，类似于`hexo`的`scaffolds`，该文件夹的优先级高于主题下的`/archetypes`文件夹
- **config.toml**: 配置文件
- **content**: 储存网站的所有内容，类似于`hexo`的`source`
- **data**: 储存数据文件供模板调用，类似于`hexo`的`source/_data`
- **layouts**: 储存`.html`模板，该文件夹的优先级高于主题下的`/layouts`文件夹
- **static**: 储存图片,css,js等静态文件，该目录下的文件会直接拷贝到`/public`，该文件夹的优先级高于主题下的`/static`文件夹
- **themes**: 储存主题
- **public**: 执行`hugo`命令后，储存生成的静态文件

## 配置 Hugo

编辑你的`config.toml`文件以配置你的站点。以下节选了部分~~有趣的~~参数，完整的配置文件可以参考[官方文档](https://gohugo.io/getting-started/configuration/#toml-configuration)。

```
+++
# 主机名 例如: http://spf13.com/
baseURL =                     ""
# 语言编码(中文: zh-CN)
languageCode =                ""
# 默认的内容语言
defaultContentLanguage =      "zh-CN"

# 自动检测是否包含中文/日文/韩文，该参数会影响摘要和字数统计功能，建议设置为true
hasCJKLanguage =              false

# 若为 false，`Getting Started` 这样的英文标签将会被转换为 `getting-started`
preserveTaxonomyNames =       true

# 设置使用的主题名称 (默认储存在 /themes/THEMENAME/)
theme =        

# 分页
paginate =                    10
paginatePath =                "page"

# 启用 Emoji; see emoji-cheat-sheet.com
enableEmoji =                 false

# 创建robots.txt，建议设置为true
enableRobotsTXT =             false

# 定义文章访问路径，详细见下文"URL管理" See "content-management/urls/"
permalinks =                  ""
+++
```

除了预设的参数外，你也可以通过下面的方式自定义自己的参数。你可以在模板中获取到自定义的参数，通常情况下你使用的主题都会要求你这么做，具体信息可以阅读相关主题的文档。

## 组织content/文件夹

`hugo`会将`content/`目录下的结构反映到生成的静态网站中，如下：



```
.
└── content
    └── about
    |   └── _index.md  // <- https://example.com/about/
    ├── post
    |   ├── _index.md   // <- https://example.com/post/
    |   ├── firstpost.md   // <- https://example.com/post/firstpost/
    |   ├── happy
    |   |   └── ness.md  // <- https://example.com/post/happy/ness/
    |   └── secondpost.md  // <- https://example.com/post/secondpost/
    └── quote
        ├── first.md       // <- https://example.com/quote/first/
        └── second.md      // <- https://example.com/quote/second/
```

需要注意的是`_index.md`是一个比较特殊的文件，如果你只是需要一个about页面，你只需要`hugo new about.md`即可。关于`_index.md`的相关信息可以参阅[官方文档](https://gohugo.io/content-management/organization/#path-breakdown-in-hugo)。



## hugo中的路径分解

```fallback
             section
                    ⊢--^--⊣
                               url
                    ⊢-------------^------------⊣

      baseURL             path        slug
⊢--------^--------⊣ ⊢------^-----⊣⊢----^------⊣
                  permalink
⊢----------------------^-----------------------⊣
https://example.com/events/chicago/lollapalooza/
```

## 分类系统

默认情况下即`tags`与`categories`，通常来说这已经足够我们使用了，但你也可以在`config.toml`文件中添加下面的代码来添加更多的分类。



```
[taxonomies]
  tag = "tags"
  category = "categories"
  series = "series"
```

## Custom Output Formats

`hugo`能够输出多种不同格式的内容，这里简单的举个**如何同时输出markdown文件**的栗子:

在你的`config.toml`文件下添加：

```toml
[mediaTypes]
  [mediaTypes."text/plain"]
    suffix = "md"

[outputFormats.MarkDown]
  mediaType = "text/plain"
  isPlainText = true
  isHTML = false
```

为 MarkDown 新建一个 single.md 模板，写入以下代码，并放置在 /layouts/_default/ 文件夹下

```go-html-template
{{ .RawContent }}
```

针对所有内容，在`config.toml`文件下添加：

```toml
[outputs]
  home = ["HTML", "RSS"]
  page = ["HTML", "MarkDown"]
  section = ["HTML", "RSS"]
  taxonomy = ["HTML", "RSS"]
  taxonomyTerm = ["HTML"]
```
