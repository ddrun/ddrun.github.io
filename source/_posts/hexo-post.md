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
              		
       （9）更换主题并发布
            发布：
                hexo clean
                hexo g
                hexo d
            按照上述命令即可将静态文章资源发布到ddrun的master分支下，github
            pages就可以根据master下的内容生成博客文章。
        (10)多设备源码同步
            将源码托管到github，源码和文章静态文件由分支控制
            主设备操作：
                在文章所在根目录下键入如下命令：
                // git初始化，生成.git文件，在.gitignore文件中添加不将上传的目录或文件
                git init
                // 添加仓库地址
                git remote add origin https://github.com/ddrun/ddrun.github.io.git
                // 新建分支并切换到新建的分支
                git checkout -b hexo
                // 添加所有当前根目录下本地文件到git
                git add .
                // git提交
                git commit -m "first commit to hexo "
                // 文件推送到hexo分支
                git push origin hexo
            
            后续发布编译文章还是按照正常流程
                hexo clean
                hexo g
                hexo d
            在设备上编辑或新增了md后，将源码提交到hexo分支即可保证源码的同步性
                
            其他设备操作：
                //安装git node
                
                //新建目录，存放文章源码，clone分支hexo项目内容
                git clone -b hexo  https://github.com/ddrun/ddrun.github.io.git
                //安装hexo
                npm install -g hexo-cli
                //安装hexo后不要做初始化init操作，否则会重置hexo配置
                //安装依赖包
                npm install
                //安装hexo发布插件
                npm install hexo-deployer-git
            
            
            参考：https://vitan.me/2018/01/30/Hexo%E6%BA%90%E7%A0%81%E5%A4%9A%E8%AE%BE%E5%A4%87%E5%90%8C%E6%AD%A5/