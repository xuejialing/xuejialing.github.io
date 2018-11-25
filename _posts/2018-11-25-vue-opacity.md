---
layout: post
title: vue 学习笔记（十四）头部显隐
date: 2018-11-25 18:06:00 +0800
categories: vue update
---
+ detail-header 分支
+ Header.vue
+ 样式
+ 滚动显隐
+ opacity 渐变显示
+ 全局事件解绑
+ 绑定在window的事件会出现问题
+ 解决办法
deactivated () {
	window.removeEventListener
}
