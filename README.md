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

> 注意 ⚠️:是`post`目录，最好再加个`hugo new about.md`

- **3. 服务器启动**

```
hugo server -D
```

### config.toml 配置

```toml
baseURL = "http://example.org/"
languageCode = "zh-CN"
title = "我是"
theme = "yinwang"
#pygmentsCodeFences = true
#pygmentsCodefencesGuessSyntax = false
#pygmentsStyle = "dracula"
#pygmentsOptions = ['linenos']
# 代码高亮/chroma，hugo默认自带（可选）

[params]
    author = "yobrave Lee"
    github = "chinanf-boy"
    # gitlab = "yobrave"
    googleAnalytics = "UA-128555056-1" # 谷歌统计gtag
    highlight = "atom-one-dark" # 默认样式 `github`
    langs = ["go"]
    # 默认加载 highlight.min.js，但 一些不支持的语言, 你自己添加,
    # 其实也可以使用hugo自带的语法高亮器设置，不过我有点懒
    # single = false # 单页面的Home 按钮去除
    # menus = true # 想加更多目录，具体请看常见问题中的更多配置
    backgroundColor = "#fbf6ec" # 加点黄黄的背景色
    githubRepo = "https://github.com/chinanf-boy/html-css-list"
    editBtn = true # 两个字段一起，才能搞好编辑按钮
    anchorLink = "¶" # 瞄点链接
    copyCode = true # 代码复制按钮
    imageZoom = true # 图片点击 zoom 一下
```

## 小目录

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [功能添加](#%E5%8A%9F%E8%83%BD%E6%B7%BB%E5%8A%A0)
  - [**1.** 可通过`<rawhtml>`短语添加`html`内容](#1-%E5%8F%AF%E9%80%9A%E8%BF%87rawhtml%E7%9F%AD%E8%AF%AD%E6%B7%BB%E5%8A%A0html%E5%86%85%E5%AE%B9)
  - [**2.** 使用`rawcss`，使用 css 内容(主要是修复`< >`符号的转义问题)](#2-%E4%BD%BF%E7%94%A8rawcss%E4%BD%BF%E7%94%A8-css-%E5%86%85%E5%AE%B9%E4%B8%BB%E8%A6%81%E6%98%AF%E4%BF%AE%E5%A4%8D-%E7%AC%A6%E5%8F%B7%E7%9A%84%E8%BD%AC%E4%B9%89%E9%97%AE%E9%A2%98)
  - [**3.** 单文件页面，添加独有的 css 文件](#3-%E5%8D%95%E6%96%87%E4%BB%B6%E9%A1%B5%E9%9D%A2%E6%B7%BB%E5%8A%A0%E7%8B%AC%E6%9C%89%E7%9A%84-css-%E6%96%87%E4%BB%B6)
  - [**4.** `series`系列博文](#4-series%E7%B3%BB%E5%88%97%E5%8D%9A%E6%96%87)
  - [**5.** 编辑按钮](#5-%E7%BC%96%E8%BE%91%E6%8C%89%E9%92%AE)
  - [**6.** 复制代码](#6-%E5%A4%8D%E5%88%B6%E4%BB%A3%E7%A0%81)
  - [**7.** `h*`元素的anchor](#7-h%E5%85%83%E7%B4%A0%E7%9A%84anchor)
- [常见问题](#%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  - [**0. :** 想加其他统计脚本?](#0--%E6%83%B3%E5%8A%A0%E5%85%B6%E4%BB%96%E7%BB%9F%E8%AE%A1%E8%84%9A%E6%9C%AC)
  - [**1. :** 我 想正常添加，更多目录](#1--%E6%88%91-%E6%83%B3%E6%AD%A3%E5%B8%B8%E6%B7%BB%E5%8A%A0%E6%9B%B4%E5%A4%9A%E7%9B%AE%E5%BD%95)
  - [**2. :** 我 想单页面的 Home 按钮去除](#2--%E6%88%91-%E6%83%B3%E5%8D%95%E9%A1%B5%E9%9D%A2%E7%9A%84-home-%E6%8C%89%E9%92%AE%E5%8E%BB%E9%99%A4)
  - [**3. :** 我要最终输出文件的`baseURL`配置，不是根目录，但我又想用开发服务器](#3--%E6%88%91%E8%A6%81%E6%9C%80%E7%BB%88%E8%BE%93%E5%87%BA%E6%96%87%E4%BB%B6%E7%9A%84baseurl%E9%85%8D%E7%BD%AE%E4%B8%8D%E6%98%AF%E6%A0%B9%E7%9B%AE%E5%BD%95%E4%BD%86%E6%88%91%E5%8F%88%E6%83%B3%E7%94%A8%E5%BC%80%E5%8F%91%E6%9C%8D%E5%8A%A1%E5%99%A8)
- [本主题来源](#%E6%9C%AC%E4%B8%BB%E9%A2%98%E6%9D%A5%E6%BA%90)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 功能添加

### **1.** 可通过`<rawhtml>`短语添加`html`内容

<details>

> 注意,只需要一个`<rawhtml>`,同时注意换行不要接-多个空格。(这个 Hugo 功能我也没怎么搞懂，写法不对请指出)

```html
<rawhtml>
  <style>
    div.inner {
      margin: 0 4%;
    }
    tr td:nth-child(2n) {
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
    tr th:not(:first-child) {
      width: 14%;
    }
    th {
      position: static;
    }
  </style></rawhtml
>
```

> 具体例子:[llever.com](http://llever.com/2018/12/11/译搜索工具的功能比较/) \| [源文件](https://github.com/chinanf-boy/yobrave-blog-with-Hugo/blob/master/content/post/译-搜索工具的功能比较.md)

</details>

<br >

### **2.** 使用`rawcss`，使用 css 内容(主要是修复`< >`符号的转义问题)

```
{{% rawcss %}}.blog-post > h2:first-child {display:none}{{% /rawcss %}}
```

> 具体例子: [llever.com](http://llever.com/2018/12/28/rust-官方学习索引译-copy/) \| [源文件](https://github.com/chinanf-boy/yobrave-blog-with-Hugo/blob/master/content/post/Rust-%E5%AE%98%E6%96%B9%E5%AD%A6%E4%B9%A0%E7%B4%A2%E5%BC%95.md)

### **3.** 单文件页面，添加独有的 css 文件

可通过`css`来完成，点击以下例子

<details>

```yaml
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

[网页可看:css 格式添加说明](http://llever.com/2018/12/06/nes.css-任天堂风格css框架-yummy/#yinwang-css-格式添加说明)

> 注意 ⚠️:若你的`baseURL`不是根目录，留心`'/css/main.css'`的前路径。[看看具体操作](<(#3--%E6%88%91%E8%A6%81%E6%9C%80%E7%BB%88%E8%BE%93%E5%87%BA%E6%96%87%E4%BB%B6%E7%9A%84baseurl%E9%85%8D%E7%BD%AE%E4%B8%8D%E6%98%AF%E6%A0%B9%E7%9B%AE%E5%BD%95%E4%BD%86%E6%88%91%E5%8F%88%E6%83%B3%E7%94%A8%E5%BC%80%E5%8F%91%E6%9C%8D%E5%8A%A1%E5%99%A8)>)

### **4.** `series`系列博文

```
series: "我是系列博文哦"
```

> 具体操作可看[llever.com](http://llever.com/2019/01/11/%E7%B3%BB%E5%88%97-%E5%8A%9F%E8%83%BD%E6%B7%BB%E5%8A%A0-hugo-theme/)，与 [js 脚本](./layouts/partials/footer.html#L27)

### **5.** 编辑按钮

```toml
    githubRepo = "https://github.com/chinanf-boy/html-css-list"
    editBtn = true
```

> `githubRepo` 与 `editBtn` 要一起使用，才能发挥作用。

### **6.** 复制代码

```toml
    copyCode = true
```

### **7.** `h*`元素的anchor

```toml
    anchorLink = "¶" # 可以自己改为喜欢的字符
```

## 常见问题

### **0. :** 想加其他统计脚本?

关于百度的统计工具，因为我很少用，若有需要可添加到[footer.html](./layouts/partials/footer.html)，再加个配置**config.toml**可控私人 ID，就好，等你 PR 噢

### **1. :** 我 想正常添加，更多目录

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

### **2. :** 我 想单页面的 Home 按钮去除

```toml
[params]
    single = false
```

### **3. :** 我要最终输出文件的`baseURL`配置，不是根目录，但我又想用开发服务器

答：那么你就有两个命令

- 一是 `hugo -b "/"`，构建静态文件(输入`-b`选项，换网址)命令；
- 二是 `hugo server -D` 开发服务器命令

> 警告⚠️: `baseURL`一定要有`/`结尾。

## 本主题来源

是由[basics](https://github.com/arjunkrishnababu96/basics) hugo 主题, 拿来改的
