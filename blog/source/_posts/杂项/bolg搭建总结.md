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

