# 如何提升 Clone GitHub 项目的速度


<!--more-->

## 问题

搭建该博客时，需要从 GitHub 克隆一些项目，例如：

`git clone https://github.com/dillonzq/LoveIt.git themes/LoveIt`

然而，下载速度只有 20+KB/s。

## 解决方案

百度了一下，将域名 github.com 改为 github.com.cnpmjs.org 后，下载速度可达 1+MB/s，修改后的命令如下：

`git clone https://github.com.cnpmjs.org/dillonzq/LoveIt.git themes/LoveIt`

## 原理探究

其原理大概是，用 cnpmjs.org 域名做了一个中转。

