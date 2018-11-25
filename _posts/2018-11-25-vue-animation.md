---
layout: post
title: vue 学习笔记（十五）动画 transition slot
date: 2018-11-25 21:38:00 +0800
categories: vue update
---

+ detail-list 分支
+ List.vue
+ 数据遍历
+ detail-list 递归遍历
+ detail-ajax 分支
+ 获得动态路由参数 this.$route.params.id
```
axios.get('/api/detail.json', {
	params: {
		id: this.$route.params.id
	}
})
```
+ App  中  keep-alive exclude='Detail'
+ 滚动行为
```
scrollBehavior (to, from, savedPosition) {
	return { x: 0, y: 0 }
}
```
添加到index.js 路由
+ 动画
+ detail-animation 分支
+ common/fade/FadeAnimation.vue
+ Banner 引入FadeAnimation组件
