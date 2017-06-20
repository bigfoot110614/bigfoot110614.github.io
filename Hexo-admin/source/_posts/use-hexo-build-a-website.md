---
title: use hexo build a website
date: 2017-06-16 16:08:37
tags:
---

### use hexo build a website
#### 步骤  

##### 1.在github上创建git仓库
- 创建一个名字为用户名.github.io的远程仓库,默认是master分支
- 在仓库的code标签,switch branch的input框中填写develop分支,然后create(这个分支名称可以自定义)


##### 2.配置git账号
设置Git的用户名和邮件地址（邮箱就是你注册Github时候的邮箱），打开Git Bash,键入

```
$ git config --global user.name "username"
$ git config --global user.email "email@example.com"
```

##### 3.检出并且初始化hexo
将仓库的develop分支检出到本地,我使用 clone with https

``` bash
$ git clone -b develop  https://github.com/bigfoot110614/bigfoot110614.github.io.git
 
$ cd  bigfoot110614.github.io

$ mkdir hexo-blog
```

进入文件夹
```
cd hexo-blog
```

完成安装hexo:
```
$ npm install -g hexo-cli
```

安装 Hexo 完成后，执行下列命令，初始化hexo,并且安装依赖:

```
$ hexo init
$ npm install
```
接下来可以本地预览博客，执行下列命令,然后到浏览器输入localhost:4000看看。
```
$ hexo generate
$ hexo server
```
输入Ctrl+C停止服务。
##### 4.配置文件
打开Hexo-admin根目录的文件_config.yml,这个是整个项目的配置文件,在最末一行
```
deploy:
  type: git
  repository: https://github.com/chaooo/chaooo.github.io.git(填写自己的github仓库地址)
  branch: master
```
##### 5.部署
在本地生成模板  并且发布到github远程仓库
```
$ npm install hexo-deployer-git --save
$ hexo generate
$ hexo deploy
```
访问方式：
 - 访问本地  
 ```
 hexo server
 ```
 在本地浏览器输入localhost:4000或者本地ip:4000
 - 访问github外网发布
 浏览器输入用户名.github.io
 
  每次更改或者新建文章  都要hexo generate重新生成模板，然后hexo deploy 发布文件，成功提示如下
  
  ``` bash
  INFO  Deploying: git
  INFO  Clearing .deploy_git folder...
  INFO  Copying files from public folder...
  INFO  Copying files from extend dirs...
  [master 7c459e5] Site updated: 2017-06-20 22:42:45
   1 file changed, 28 insertions(+), 1 deletion(-)
  To https://github.com/bigfoot110614/bigfoot110614.github.io.git
     f03c288..7c459e5  HEAD -> master
  Branch master set up to track remote branch master from https://github.com/bigfoot110614/bigfoot110614.github.io.git.
  INFO  Deploy done: git
   ```

以上是本地和远程都可以正常访问，以防文件丢失或者换环境开发我们要把本地的工程文件上传到github远程仓库的develop分支

```
git add -A
git commit -m "注释内容"
git pull origin master
git push origin develop
```

##### 6.编写文章
1. 新建页面编写文章，默认是在post方式
```
hexo new [layout] '新页面的名字'
hexo new post 'name'
```
2. 提交 
每次页面完成之后都要重新生成，然后发布

##### 7.主题
我是参考这篇博客来写的，写的很清楚明了

[参考文档1](http://chaoo.oschina.io/2016/05/23/Hexo3-2-github%E6%90%AD%E5%BB%BA%E9%9D%99%E6%80%81%E5%8D%9A%E5%AE%A2.html)

[参考文档2](http://chaoo.oschina.io/2016/12/29/BlueLake%E5%8D%9A%E5%AE%A2%E4%B8%BB%E9%A2%98%E7%9A%84%E8%AF%A6%E7%BB%86%E9%85%8D%E7%BD%AE.html)

##### 8.发布

##### 9.总结
- 命令
```hexo new "postName" #新建文章
   hexo new page "pageName" #新建页面
   hexo generate #生成静态页面至public目录
   hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
   hexo deploy #将.deploy目录部署到GitHub
   hexo help  # 查看帮助
   hexo version  #查看Hexo的版本
   hexo deploy -g  #生成加部署
   hexo server -g  #生成加预览
   #命令的简写
   hexo n == hexo new
   hexo g == hexo generate
   hexo s == hexo server
   hexo d == hexo deploy
```