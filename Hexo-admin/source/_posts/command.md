---
title: command
date: 2017-07-06 18:27:48
tags:
---

#### linux  command
#### 1.curl  and wget
    关于curl和wget的相同不同点整理(个人理解):
- 双向通信:
 curl提供了上传功能,而wget只支持http post,curl比较优于模拟请求,在控制台中复制了请求,copy as curl,可以在命令行中模拟请求
- curl支持的平台更多
- curl多协议支持 curl 支持的协议有： FTP, FTPS, HTTP, HTTPS, SCP, SFTP, TFTP, TELNET, DICT, LDAP, LDAPS, FILE, POP3, IMAP, SMTP 和 RTSP 在写这篇文章时，Wget仅仅支持 HTTP, HTTPS 和 FTP.
- 支持压缩: curl 支持GZIP和 inflate Content-Encoding 并且自动进行解压缩操作
- wget的好处是支持递归下载


#### 2.chmod和chown的区别
chmod 修改某个目录或者文件的访问权限
chown 是用来修改用户组

#### 3. root用户和普通用户的区别
root用户 有独一无二的管理权限 路径在root下
普通用户的文件目录在home下

#### 4.文件目录操作方法
    cd 进入用户主目录； 
    cd ~ 进入用户主目录； 
    cd - 返回进入此目录之前所在的目录； 
    cd .. 返回上级目录（若当前目录为“/“，则执行完后还在“/"；".."为上级目录的意思）； 
    cd ../.. 返回上两级目录； 
    cd !$ 把上个命令的参数作为cd参数使用。
    
#### 5.linux文件目录的挂载
    
