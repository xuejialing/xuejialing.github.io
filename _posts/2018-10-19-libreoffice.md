---
layout: post
title: Libreoffice word 转 pdf
date:   2018-10-19 13:20:00 +0800
categories: jekyll update
---
+ 官网:https://www.libreoffice.org/ 软件包最新stable版本：http://download.documentfoundation.org/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm.tar.gz

```
wget http://download.documentfoundation.org/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm.tar.gz
```
```
tar -zxvf LibreOffice_6.0.6_Linux_x86-64_rpm.tar.gz
```
```
cd LibreOffice_6.0.6.2_Linux_x86-64_rpm/RPMS/
```
```
yum localinstall *.rpm
```


+ 中文包语言包&help包：

https://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm_langpack_zh-CN.tar.gz

```
wget  https://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm_langpack_zh-CN.tar.gz
```
```
tar -zxvf LibreOffice_6.0.6_Linux_x86-64_rpm.tar.gz
```
```
cd LibreOffice_6.0.6_Linux_x86-64_rpm_langpack_zh-CN/RPMS/
```
```
yum localinstall *.rpm
```

https://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm_helppack_zh-CN.tar.gz

```
wget  https://mirrors.ustc.edu.cn/tdf/libreoffice/stable/6.0.6/rpm/x86_64/LibreOffice_6.0.6_Linux_x86-64_rpm_helppack_zh-CN.tar.gz
```
```
tar -zxvf LibreOffice_6.0.6_Linux_x86-64_rpm_helppack_zh-CN
```
```
cd LLibreOffice_6.0.6_Linux_x86-64_rpm_helppack_zh-CN/RPMS/
```
```
yum localinstall *.rpm
```


**坑**：
+ error while loading shared libraries: libcairo.so.2: cannot open shared object file: No such file or directory
解决：yum install ibus

+ 忘了复制错误信息，意思就是却jre
解决： 安装 jdk
yum install <yum search 一个版本的jdk，复制版本号>

+ word文档转pdf乱码 ：  C:\Windows\Fonts   所有文件的打包到   L服务器/usr/share/fonts/   下面inux，注意修改权限
1. cd /usr/share/fonts
2. mkdir win 创建一个文件夹，用来保存windows字体，软件会自动找到/usr/share/fonts/win 的字体
3. cd ~  到字体文件目录，我从本地传到了服务器用户家目录
4. unzip Fonts.zip  解压缩
5. mv Fonts/* /usr/share/fonts/win  把字体文件都移动到win
6. cd /usr/share/fonts  到字体目录中
7. chmod -R 755 win  递归修改win及其中的文件权限

**最后生成文件测试**

libreoffice6.0 --headless --convert-to pdf "word文件路径" --outdir "导出pdf存放目录"


