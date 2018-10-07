## hugo的 yinwang.org 博客主题

<img style="width:69%" src="https://raw.githubusercontent.com/chinanf-boy/gohugo-theme-yinwang/master/images/tn.png">

<img style="width:80%" src="https://raw.githubusercontent.com/chinanf-boy/gohugo-theme-yinwang/master/images/screenshot.png">


### hugo准备

若你第一次使用hugo, 请参照一下[官方快速教程](https://gohugo.io/getting-started/quick-start/)

> [直到 *添加主题* 那一步往下看](https://gohugo.io/getting-started/quick-start/#step-3-add-a-theme)

### 主题下载

0. 记得初始化

``` bash
git init
```

1. 加入子模块
```
git submodule add https://github.com/chinanf-boy/gohugo-theme-yinwang.git themes/yinwang;
```

2. 主题设置

```
echo 'theme = "yinwang"' >> config.toml
```

2.1 加个文章

```
hugo new post/hello.md
```

> 最好再加个`post/about.md`

3. 服务器启动

```
hugo server -D
```

### config.toml配置

``` toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "我是"
theme = "yinwang"

[params]
    author = "yobrave Lee"
    github = "chinanf-boy"
    # gitlab = "yobrave"
    highlight = "dracula" # default use `github` style
    langs = ["go"] 
    # default load highlight.min.js but some language, Must add by youself
```

### 本主题

是由[basics](https://github.com/arjunkrishnababu96/basics)hugo主题, 拿来改的