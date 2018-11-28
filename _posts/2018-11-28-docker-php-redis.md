---
layout: post
title: Docker 学习笔记（二）docker 上运行 centos，安装php-redis扩展
date: 2018-11-28 09:52:00 +0800
categories: docker update
---
+ windows 安装redis 扩展
1. https://github.com/MicrosoftArchive/redis/releases
2. 下载redis php扩展（版本、线程安全、php位数）
3. 复制 .pdb  .dll 到 php/ext/
4. 修改php.ini  extension=php_redis.dll
5. 测试  php.exe -m  查看已经开启的扩展

+ CentOS安装redis扩展
1. 修改配置文件redis-6379.conf
bind  ip
2. 重启server
3. centos安装个php
4. 安装依赖：yum -y install gcc gcc-c++ libxml2 libxml2-devel bzip2 bzip2-devel libmcrypt libmcrypt-devel openssl openssl-devel libcurl-devel libjpeg-devel libpng-devel freetype-devel readline readline-devel libxslt-devel perl perl-devel psmisc.x86_64 recode recode-devel libtidy libtidy-devel
5. 查看版本  /opt/app/php7/bin/php -v
6. 扩展地址： https://pecl.php.net/package/redis
7. 官网找扩展地址  wget xxx
8. 解压、cd 、phpize 加载模块
```
/opt/app/php7/bin/phpize
```
9. 编译
```
./configure --with-php-config=/opt/app/php7/bin/php-config
make
make install
```
10. /opt/app/php/lib/php/extensions/no-debug-non-zts-20170718/   会出现redis.so
11. 查看配置文件地址  /opt/app/php7/bin/php --ini
12. 修改配置文件
```
extension=redis.so;
```
13. 执行个命令测试 /opt/app/php7/bin/php -v
14. /opt/app/php7/bin/php -m 查看下加载模块
15. 创建一个php文件测试下

```
<?php
$redis = new Redis();
$redis->connect('localhost',6379);
var_dump($redis);
?>
```


**docker 宿主机与虚拟机文件传输**
docker cp foo.txt mycontainer:/foo.txt
docker cp mycontainer:/foo.txt foo.txt

**问题：**
+ 报错： Cannot find autoconf. Please check your autoconf installation and the
$PHP_AUTOCONF environment variable. Then, rerun this script.

解决：安装下autoconf

+ 查找不到php.ini文件

解决：
/php-7.2.12/php.ini-production
/php-7.2.12/php.ini-development

+ 报错：
systemctl stop firewalld.service
Failed to get D-Bus connection: Operation not permitted

解决： 未解决

**备注：**
centos6关闭防火墙  service iptables stop
ceotos7                  systemctl stop firewalld.service

yum install net-tools
netstat -an | grep 6379
