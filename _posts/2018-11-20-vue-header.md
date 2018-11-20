---
layout: post
title: vue学习笔记（二）头部
date:   2018-11-20 20:57:00 +0800
categories: vue update
---

+ npm install stylus --save
+ npm install stylus-loader --save
+ 重启  npm run start
+ 创建header.vue
+ 在Home.vue 下 加入header 组件  import HomeHeader from './components/Header'
+ 声明组件
```
components: {
    HomeHeader
}
```
+ 使用 <home-header></home-header>
+ 写头部组件样式
+ <style lang="stylus" scoped>  加lang scoped  用stylus语法并且scoped只用在当前组件样式
+ stylus语法
```
.header
	height:xxxx rem
```
+ iconfont 图标库-官方图标库 下载到本地
+ 四个字体文件&一个css文件需要用
+ style/创建一个iconfont文件夹 ,再把iconfont.css 放入styles中
+ 修改iconfont.css字体路径
+ main.js 引入iconfont.css
+ 使用 复制icon的字符写入span标签   一定要在span 上加iconfont 样式，否则显示乱码
+ 调整样式
+ 在styles 目录下添加一个varibles.styl   的一个stylus文件，用于放置style公共变量  $bgColor = #00bcd4
+ 使用 style中引入    @import '路相对径'  ，然后替换  #00bcd4  用 $bgColor
+ 使用次数多的路径可以放入  build/webpack.base.conf.js 的alias中
'styles': resolve('src/assets/styles')
使用  ~styles
然后需要重启，npm run start



**备注：**
+ 1rem = html 的 font-size
+ display:flex 弹性盒子
子元素平均分父元素的空间 flex:1

例如：

```
#main
{
	width:220px;
	height:300px;
	border:1px solid black;
	display:flex;
}

#main div
{
	flex:1;
}

```

