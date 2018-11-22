---
layout: post
title: vue 学习笔记（十）城市搜索列表
date: 2018-11-22 21:28:00 +0800
categories: vue update
---

+ 创建搜索逻辑分支  city-search-logic
+ 添加搜索列表区块 search-content
+ 创建keyword   v-model="keyword" 数据双向绑定
+ 接收父组件传过来的cities
+ 监听keyword  并且做查询节流
```
watch: {
	keyword () {
		节流
		遍历匹配城市跟keyword
	}
}
```
+ 遍历城市
+ 样式
+ 添加mounted 钩子  引入better-scroll 并且实例  加滚动效果
+ 如果搜索关键词没有，清空list
+ 没有搜索结果  添加一个提示 v-show="!list.length"
+ v-show="keyword" 判断是否显示列表
+ computed  hasNoData替换  list.length
