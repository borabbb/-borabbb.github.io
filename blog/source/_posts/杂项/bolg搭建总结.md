---
title: hexo+github next博客搭建
date: 2014-12-22 16:39:04
tags: 杂项
categories: hexo
---

## 环境准备

1. node.js安装 ![node版本](/images/nodejs版本.jpg)
2. 安装git
3. 建立创库

    ![仓库命名](/images/1641378617(1).jpg)

4. 安装hexo


```java
npm install hexo-cli -g
hexo init blog
cd blog
hexo g  生成静态文件
hexo d  发布git
```

5. 主配置文件_config.yml 添加

~~~yml
deploy:
  type: 'git'
  repository: https://github.com/borabbb/borabbb.github.io
  branch: main
~~~



## next主题配置



安装搜索插件

	1. 在博客根目录 https://github.com/flashlab/hexo-generator-search

```shell
npm install hexo-generator-searchdb --save  --安装插件，用于生成博客索引数据
```

2. 修改博客配置文件（根目录/_config.yml）添加

```yml
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
  content: true
```

3. 把false 改为true

```yml
# Local search
# Dependencies: https://github.com/flashlab/hexo-generator-search
local_search:
  enable: false
  # if auto, trigger search by changing input
  # if manual, trigger search by pressing enter key or search button
  trigger: auto
  # show top n results per article, show all results by setting to -1
  top_n_per_article: 1
```



### 目录

```css
//文章目录默认展开
.post-toc .nav .nav-child { display: block; }
```

### 链接生成

```shell
npm install hexo-abbrlink --save
```

配置文件(_config.yml)里改为

```yml
permalink: post/:abbrlink.html
abbrlink:
  alg: crc32  # 算法：crc16(default) and crc32
  rep: hex    # 进制：dec(default) and hex
```



### 添加文件相关推荐

