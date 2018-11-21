---
layout: post
title:  About Jekyll & Markdown
date:   2017-11-14 13:40:50 +0800
categories: jekyll update
---

### Jekyll Install

+ 创建gitpages仓库 - github pages repository site expo(your username.github.io)
+ 安装 ruby https://rubyinstaller.org/downloads/
+ 修改 gem 源 (gems.ruby-china.org 无效,改成了com)
```
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
```
+ 安装 jekyll
```
gem install jekyll
jekyll new username.github.io
cd username.github.io
```
+ 启动服务
```
jekyll serve
```
+ 提交到git仓库
```
git init
git clone your repository site
git add .
git commit -m "initial commit"
git push origin master
```
+ 访问blog - your username.github.io

**备注：**
_config.yml 修改jekyll配置,重启本地服务,直接修改_site/index.html 无效，_site 已经被gitignore不上传到创库，是自动生成的。
## Markdown
[https://guides.github.com/features/mastering-markdown/](https://guides.github.com/features/mastering-markdown/)
