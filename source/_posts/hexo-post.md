---
title: hexo-post
date: 2019-04-16 08:42:14
tags:
    - 博客
    - hexo
categories:
    - Blog
---

    hexo blog process:
        (1)安装环境：git和node
        (2)安装hexo
            npm install –g hexo-cli
        (3)环境查看：
            git version
            node -v
            hexo version
        (4)新建一个博客md源码的目录，用来存放后续所有的md文章
         D:\myblog
         该目录下可以进行变更目录，此处新增ddrun目录
        (5)初始化
            hexo init ddrun         
        (6)可启动本地服务，查看默认(blog:http://localhost:4000/)
            hexo server  
            
        (7)使用hexo将博客部署到github上，先安装插件
            npm install hexo-deployer-git  --save
            
       （8）修改_config.yaml配置文件
            $ vim _config.yml
            deploy:
              		type: git
              		repo: https://github.com/ddrun/ddrun.github.io.git
              		branch: master
              		message:
              		
       （9）更换主题