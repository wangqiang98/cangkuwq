---
title: day2
date: 2020-07-09 22:01:14
tags:
##hexo 应用##
创建博客 hexo new 博客名
会创建一个新的md 文件
该文件在文件夹 source/_posts文件夹内
发布博客
hexo clean 清除缓存
hexo g  生成静态文件
hexo d   把文件部署到博客上
##更改主题##
下载主题文件
next的下载可以在 git clone https://github.com/iissnan/hexo-theme-next thems/next
更改文件配置 theme:landscape改为theme:next 
##Git 分支##
创建分支 git branch dev
切换分支 git checkout dev
合并命令 git checkout -b dev
##行为日志##
  作用     ： 行为日志包括用户的行为，也包括服务器响应是否正常。
 **Nigix**  ：也叫 web server 接收用户在浏览器输入网址后发出的请求
分析用户行为  :1. grep -c '11.176.159.95' cookie_log.log 
              分析从该文件中查找引号内文件出现次数
              1. grep '11.176.159.95' cookie_log.log
              查找关键字所在的行
              1.  GET /renders.test.com/g/agentsales/js/view.js HTTP/1.1        复杂统计出现最多的次数

## shell 脚本##
脚本头  #！/bin/bash
脚本内容  #!/bin/bashif [ -f 'cookie_log.log' ]; then  cat cookie_log.log | awk '{print $8}' | sort | uniq -c | sort -k1r | head -10
保存 top10.sh
运行 sh top10.sh
