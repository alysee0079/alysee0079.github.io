---
layout: post
title:  "mongodb 的启动与关闭"
categories: mongodb
tags:  MongoDB 数据库
---


一、启动MongoDB的方式
首先，先安装好MongoDB，并且切换到MongoDB的bin目录下：

然后使用：{% highlight ruby %} net start MongoDB {% endhighlight %} 命令 启动MongoDB

最后使用：{% highlight ruby %} mongo --host ip {% endhighlight %} 地址:端口号（例如127.0.0.1：27017）

或者使用mongo命令

这样就能进入MongoDB了。

二、关闭MongoDB的方式：

（1） 使用 Crtl+C 关闭

直接使用Crtl+C

备注：如果以前台方式启动 MongoDB 服务，使用“Crtl+C” 服务会关闭，这种关闭方式会等待 当前进行中的的操作完成，所以依然是干净的关闭方式。

（2） 使用 db.shutdownServer()命令 关闭

备注：命令 db.shutdownServer()关闭命令只能在admin在使用。不然会出错如下：

（3） 使用 kill命令 关闭

首先使用$ ps -ef | grep mongo查看MongoDB的相关进程

root     17573 14213  0 05:10 pts/1    00:00:00 su - mongo
mongo    17574 17573  0 05:10 pts/1    00:00:00 -bash
mongo    18288     1  0 06:12 ?        00:00:00 mongod -f /database/mongodb/data/mongodb_27017.conf
mongo    18300 17574  6 06:13 pts/1    00:00:00 ps -ef
mongo    18301 17574  0 06:13 pts/1    00:00:00 grep mongo

然后使用 kill mongo命令

例如：kill 18288

备注：可以使用操作系统的 kill 命令，给 mongod 进程发送 SIGINT 或 SIGTERM 信号，即 "kill -2 PID," 或者 “kill -15 PID“
