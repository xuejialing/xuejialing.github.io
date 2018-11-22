---
layout: post
title: vue学习笔记（七）城市页面header
date:   2018-11-22 10:56:00 +0800
categories: vue update
---

+ 创建city-router 分支
+ index.js  添加路由  import  City组件
+ 创建pages/City/City.vue

```
import City from '@/pages/city/City'
{
	path: '/city',
	name: 'City',
	compoment: City
}
```

+ 首页城市添加链接  router-link to='/city'
+ 样式
+ 返回链接
+ 公共样式 varibles.styl修改


