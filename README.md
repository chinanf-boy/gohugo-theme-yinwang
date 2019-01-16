## hugo 的 yinwang.org 博客主题

<p>
<img width="49%" src="https://raw.githubusercontent.com/chinanf-boy/gohugo-theme-yinwang/master/images/tn.png">

<img width="49%" src="https://raw.githubusercontent.com/chinanf-boy/gohugo-theme-yinwang/master/images/screenshot.png">
</p>

### hugo 准备

若你第一次使用 hugo, 请参照一下[官方快速教程](https://gohugo.io/getting-started/quick-start/)

> [直到 _添加主题_ 那一步往下看](https://gohugo.io/getting-started/quick-start/#step-3-add-a-theme)

### 主题下载

- **0. 记得初始化**

```bash
git init
```

- **1. 加入子模块**

```
git submodule add https://github.com/chinanf-boy/gohugo-theme-yinwang.git themes/yinwang;
```

- **2. 主题设置**

```
echo 'theme = "yinwang"' >> config.toml
```

- **2.1 加个文章**

```
hugo new post/hello.md
```

> 最好再加个`about.md`

- **3. 服务器启动**

```
hugo server -D
```

### config.toml 配置

```toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "我是"
theme = "yinwang"
#pygmentsCodeFences = true
#pygmentsCodefencesGuessSyntax = false
#pygmentsStyle = "dracula"
#pygmentsOptions = ['linenos']
# 代码高亮/chroma，hugo默认自带

[params]
    author = "yobrave Lee"
    github = "chinanf-boy"
    # gitlab = "yobrave"
    #googleAnalytics = "****"
    # 谷歌统计gtag
    highlight = "dracula" # 默认样式 `github`
    langs = ["go"]
    # 默认加载 highlight.min.js，但 一些不支持的语言, 你自己添加,
    # 其实也可以使用hugo自带的语法高亮器设置，不过我有点懒
    # single = false
    # 单页面的Home 按钮去除
    # menus = true
    # 我 想加更多目录
    # backgroundColor = "#fbf6ec"
    # 加点黄黄的背景色
```

### 功能添加

- **1.** 可通过`<rawhtml>`短语添加`html`内容

<details>

> 注意,只需要一个`<rawhtml>`,同时注意换行不要接-多个空格。(这个Hugo功能我也没怎么搞懂，写法不对请指出)

``` html
<rawhtml>
<style> 
div.inner {
margin: 0 4%; 
}
tr td:nth-child(2n){
background-color: #ffdfac;
}
tr td:not(:first-child) code {
background-color: #ffdfac;
font-size: 14px;
margin: 1px;
display: block;
padding: 5px;
text-align: center;
}
tr th:not(:first-child)  {
width:14%;
}
th {
    position: static;
}
</style>
```

> 具体例子:[llever.com](http://llever.com/2018/12/11/译搜索工具的功能比较/) \| [源文件](https://github.com/chinanf-boy/yobrave-blog-with-Hugo/blob/master/content/post/译-搜索工具的功能比较.md)

</details>

<br >

- **2.** 使用`rawcss`，使用css内容(主要是修复`< >`符号的转义问题)

```
{{% rawcss %}}.blog-post > h2:first-child {display:none}{{% /rawcss %}}
```

> 具体例子: [llever.com](http://llever.com/2018/12/28/rust-官方学习索引译-copy/) \| [源文件](https://github.com/chinanf-boy/yobrave-blog-with-Hugo/blob/master/content/post/Rust-%E5%AE%98%E6%96%B9%E5%AD%A6%E4%B9%A0%E7%B4%A2%E5%BC%95.md)

- **3.** 单文件页面，添加独有的 css 文件

可通过`css`来完成，点击以下例子

<details>

```  yaml
title: 'NES.css 任天堂风格css框架 Yummy'
date: 2018-12-06T12:23:36+08:00
categories: ['css']
tags: ['NES']
description: 'NES.css 任天堂风格css框架'
css: # 当你输入这个字段，会覆盖掉默认css文件
  [
    '/css/main.css', # 这个就是默认，只在博文页面 css文件
    '/css/stylesheet.css'  # 这个用来存有主页与博文，相同的css格式的文件
    'https://unpkg.com/nes.css@0.0.2/css/nes.min.css',
  ]
```

</details>

<br />

[网页可看:css格式添加说明](http://llever.com/2018/12/06/nes.css-任天堂风格css框架-yummy/#yinwang-css-格式添加说明)

- **4.** `series`系列博文

```
series: "我是系列博文哦"
```

> 具体操作可看[llever.com](http://llever.com/2019/01/11/%E7%B3%BB%E5%88%97-%E5%8A%9F%E8%83%BD%E6%B7%BB%E5%8A%A0-hugo-theme/)，与 [js脚本](./layouts/partials/footer.html#L27)

## 常见问题

- **0. :** 想加其他统计脚本?

关于百度的统计工具，因为我很少用，若有需要可添加到[footer.html](./layouts/partials/footer.html)，再加个配置**config.toml**可控私人 ID，就好，等你 PR 噢

- **1. :** 我 想正常添加，更多目录

```toml
[params]
    menus = true

[[menu.main]]
name = "分类"
url = "/categories/"

[[menu.main]]
name = "标签"
url = "/tags"

[[menu.main]]
  name = "Home"
  url = "/"
  # weight = 10
# 这个权重，是衡量顺序的
```

> 提示：main 的 html 顺序是相反的, 若想自定义顺序，添加 **权重值**

- **2. :** 我 想单页面的 Home 按钮去除

```toml
[params]
    single = false
```

### 本主题

是由[basics](https://github.com/arjunkrishnababu96/basics) hugo 主题, 拿来改的
