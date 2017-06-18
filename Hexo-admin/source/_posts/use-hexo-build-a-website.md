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

##### 5.部署

##### 6.编写文章

##### 7.主题

##### 8.发布

##### 9.总结