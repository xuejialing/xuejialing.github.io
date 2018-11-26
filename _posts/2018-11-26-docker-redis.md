---
layout: post
title: Docker 学习笔记（一）docker 上运行centos 安装redis
date: 2018-11-26 12:15:00 +0800
categories: docker update
---
+ 修改镜像源 Settings - Daemon  - Registry mirrors
+ 拉取一个image docker pull
+ 运行一个docker 容器
```
docker run -it centos /bin/bash
```
+ 生成一个image
```
docker commit container_id image
```
+ 安装gcc   yum install gcc
```
wget wget http://download.redis.io/releases/redis-5.0.2.tar.gz
tar zxf redis-5.0.2.tar.gz
cd redis-5.0.2.tar.gz
```
+ 安装redis
+ make PREFIX=/USR/.....  设置安装目录
```
make PREFIX=/opt/app/redis install
```
+ 复制解压缩文件中的配置模板到etc 下  ，
```
cp redis.conf /etc/redis-6379.conf
```
+ 如何以守护进程模式启动redis
+ redis-6379.conf 修改这个配置文件 daemonize no -> daemonize yes
+ 守护进程启动redis  /opt/app/redis/bin/redis-server /etc/redis-6379.conf
+ 启动redis客户端  /opt/app/redis/bin/redis-cli -p 6379
+ 修改服务端监听端口
```
port 6380
daemonize yes
pidfile /var/run/redis_6380.pid
```
+ 启动服务  /opt/app/redis/bin/redis-server /etc/redis-6380.conf
+ 启动客户端 /opt/app/redis/bin/redis-cli -p 6380
+ 守护进程模式启动后退出服务  /opt/app/redis/bin/redis-cli -p 6879 shutdown

**问题：**
报错 Newer version of jemalloc required
解决 make PREFIX=/opt/app/redis MALLOC=libc install
