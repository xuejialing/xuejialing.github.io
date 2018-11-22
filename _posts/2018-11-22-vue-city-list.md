---
layout: post
title: vue 学习笔记（八）城市列表
date: 2018-11-22 13:00:00 +0800
categories: vue update
---

+ 创建 city-search 分支
+ 创建Search.vue 组件
+ vue 会给样式自动加浏览器前缀
+ 创建分支  city-list
+ 创建List component
+ 样式
+ github 上搜索  better-scroll  安装  npm install better-scroll --save  重启服务
+ import Bscroll from 'better-scroll'   列表上添加ref 为了获取dom ref='wrapper'
+ 在生命周期函数中 生成scroll实例
```
mounted () {
	this.scroll = new Bscroll(this.$refs.wrapper)
}
```
之后可以实现城市列表的类似原生滚动效果
+ 创建Alphabet.vue   字母表组件
+ 字母表组件样式

**问题**
+ :key="index"  没写：  Elements in iteration expect to have 'v-bind:key'
+ :key="item"   item 是数组  报错：key 的值不是原生的数值（比如string number）[Vue warn]: Avoid using non-primitive value as key, use string/number value instead
