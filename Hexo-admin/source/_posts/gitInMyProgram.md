---
title: gitInMyProgram
date: 2016-10-05 22:47:34
tags:
---
##### 在项目中我的git使用
[大牛git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
学习总是要依靠一些资料,廖雪峰老师的git教科书式的教程是我的引路指南

我使用git的几个地方
1.github
2.工作中用的git

#### github
github是我最早接触git使用的开源托管平台,公司的项目之前并没有采用分布式代码管理的方式,代码管理工具是svn

##### svn和git的区别
   * svn是集中式的,git是分布式的.
        简单讲,集中式是有中央服务器,我们更新代码必须要联网,然后svn update,svn commit.而分布式是本地有完整的版本库,自己可以随时提交到本地,不需要中央服务器来管理,方便时提交到远程服务器的版本库.这样方便我们不受网络的影响.
   * git功能比较强大,git bash使用cygwin模拟了unix的环境,基于cmd丰富了功能,所以在window 的cmd下能运行的命令,在git bash下都可以运行.当然在linux和mac下,命令行是自带git的.
   * Git把内容按元数据方式存储，而SVN是按文件：因为,.git目录是处于你的机器上的一个克隆版的版本库，它拥有中心版本库上所有的东西，例如标签，分支，版本记录等。.git目录的体积大小跟.svn比较差距很大.
   * 关于版本号.svn有唯一的全局版本号,就是在整个版本库中唯一的一个版本号,而git的版本号是全球唯一,就是Git 对于每一次提交，通过对文件的内容或目录的结构计算出一个SHA-1 哈希值，得到一个40位的十六进制字符串，Git将此字符串作为版本号。并且git 不会像svn一样,版本连续可以推算,git的版本号多人提交版本不连续,没有先后,但是有线索.  
   * git 有分支,svn没有.在开发时,多个人同时开发,svn的话,大家提交同一文件,冲突的概率非常大.git可以每个人都拉一个分支,自己独立开发,然后最后合并,大大减少了冲突的可能性.
    
##### 我使用github
   * 因为开源,所以很多高手都会分享自己的工具库,最新的技术和心得.这些丰富的知识对我来说是非常好的资源.
   * blog ,现在使用的hexo 就是在本地安装了hexo,然后在本地预览成功之后,通过hexo deploy,发布到github上,github托管了我发布的静态文件,然后就可以外网直接访问了
    ,这个具体的步骤在另一篇文章[use-hexo-build-website](https://bigfoot110614.github.io/2017/06/16/use-hexo-build-a-website/)
   * 我还有另外一个发布静态博客的方法(我们使用github只能发布静态项目,后台文件是不能运行的)
        步骤：
        1.注册一个gitHub账号（[登录gitHub网站] (https://github.com/bigfoot110614))  
        2.在gitHub中创建一个新的仓库（一个账号可以创建很多的仓库）
        
        ```
         New respository
         name-description-public-initialize this respository-create
        ```
        3.gitHub的基本设置：
        
        ```
        profile（基本信息）-account（个人信息的修改）--Emailes（邮箱修改）--notification（设置邮箱的修改）
        
        ```
        4.在新创建的仓库中发布一个项目，一个仓库只能发布一个项目
        
        ```
        1：settings- GitHub Pages（Launch automatic page generator）
        2：continue to layouts（内容都是自动生成的，我们要发布的内容和他们不一样，所以不用修改，直接发布即可）
        3：publish page（gitHub为我们发布的页面提供了模板，每一个模板风格可以选中，但是一般我们使用自己的页面，例如自己写的移动端简历）
        4：发布完成项目生成一个在线网址 https://zhouxiaotian.github.io/blog/ ，就是别人访问我们的地址， 这个网址全称是https://zhouxiaotian.github.io/blog/index.html 
        ```
        如果我们请求的页面在当前项目根目录下，并且名字是index.html我们可以忽略不写，浏览器也会自己找到，但是在其他目录下或者名字不一致，不能忽略
        以后想要修改项目中的内容，我们需要把最新的文件上传到gh-pages这个分支下，也就是说我们的需要管理的分支是gh-pages这个分支（而不是默认的master）
        
        5.修改本仓库的默认分支
          
        ```
        settings-branches-master/gh-pages--选中后Update
        ```
        一般默认分支都是master，但是我们以后需要管理的是gh-pages，所以为了后期方便操作我们把默认分支切换成这个
        6.上传文件：
        把我们电脑本地需要发布的项目资源文件上传到仓库的gh-pages这个分支下
        1）需要把gitHub仓库gh-pages这个分支下的内容克隆到本地，并且让本地和gitHub的远程仓库进行连接
        2）把默认生成的文件（除了.git）删除掉，然后把自己的项目文件拷贝过来，
        3）把项目文件上传到gitHub的gh-pages分支上 以后文件的修改都是按照这个操作重新的上传即可
        
        ```
        git add -A
        git commit -m"描述信息"
        git push origin gh-pages
        ```
        4）如果在本地仓库想更改分支，从master改到gh-pages，使用命令
        
        ```
        git checkout -b gh-pages origin/gh-pages
        ```
        记住每一次重新提交的时候都要执行 git add  git commit
        
        7.把供别人访问的网址生成二维码 http://cli.im/
    

  
##### 项目中使用git
  后来项目中逐渐开始使用git
  
   1. 基本命令
   - 配置用户名密码
      
      ```
        git config --global user.name "zfpx" 
        git config --global user.email "zfpx@126.com"  
      ```
   - 创建版本库
   
      ```
         $ mkdir learngit
         $ cd learngit
         $ pwd
            /Users/michael/learngit
         $ git init 初始化版本库
            
       ```
   -  本地仓库和远程仓库关联起来
     
   ```
   git remote add origin https://github.com/amgYen/testFactory.git
   ```
   origin 自己可以随便起   https://github.com/amgYen/testFactory.git 是远程仓库的地址
     
   -  查看关联的远程地址
   
   ```
   git remote -v 查看关联
   git remote rm origin 解除关联
  
   ```
   
   -  远程仓库的内容更新到本地仓库
     
     ```
     git pull origin master
     ```
        
   - 把本地的内容提交到远程仓库
    
     ```
      git push -u origin master 
     ```
     -u 把本地的主分支(master)和远程的主分支(master)关联起来 (-u只需要第一次写,下一次就不需要写了)直接 git push origin master就可以了
 
 
##### 我经常用的命令

   - 回滚
    本地代码
    
    ```
    $ Git log
    $ git reset –hard 8ff24a6803173208f3e606e32dfcf82db9ac84d8
    ```
    
    远程代码
    这个是重点要说的内容，过程比本地回滚要复杂
    应用场景：自动部署系统发布后发现问题，需要回滚到某一个commit，再重新发布
    原理：先将本地分支退回到某个commit，删除远程分支，再重新push本地分支
    操作步骤：
    
    ```
    1、git checkout the_branch
    2、git pull  库里所有的分支都pul下来
       git pull origin develop  只更新develop分支
    3、git branch the_branch_backup //备份一下这个分支当前的情况
    4、git reset --hard the_commit_id //把the_branch本地回滚到the_commit_id
    5、git push origin :the_branch //删除远程 the_branch
    6、git push origin the_branch //用回滚后的本地分支重新建立远程分支
    7、git push origin :the_branch_backup //如果前面都成功了，删除这个备份分支
    ```
    
    
    
    对比两次的不同：git diff
    查看现在的状态和更改的文件：git status
    git add -a
    git  commit  -m"comment"
    git  pull  origin branch
    git push origin branch 如果本地有没有提交的东西，是不会提交成功的 
    
    git merge feature/1.6
    给分支重命名
    1.本地分支
    Git branch -m oldbranchname newbranchname
    2. 远程分支重命名 (假设本地分支和远程对应分支名称相同)
    a. 重命名远程分支对应的本地分支
    git branch -m old-local-branch-name new-local-branch-name
    b. 删除远程分支
    git push origin  :old-local-branch-name
    c. 上传新命名的本地分支
    git push origin  new-local-branch-name: new-local-branch-name
    
    
   一般的开发流程:
   先在本地建一个分支(git branch develop)
   更改完之后再develop分支上git add  git commit 
   1.然后提交,领导去合并
   或者
   2.切换到master分支  git checkout

