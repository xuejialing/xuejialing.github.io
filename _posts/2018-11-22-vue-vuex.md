---
layout: post
title: vue 学习笔记（九）兄弟组件传值/better-scroll
date: 2018-11-22 20:43:00 +0800
categories: vue update
---

+ 页面城市列表动态渲染，创建  city-ajax 分支
+ 创建 city.json 文件  放到 static/mock 中
+ import axios from 'axios'
+ 钩子
```
mounted () {
	this.getCityInfo()
}
```
+ 数据父传子
+ 遍历数据
+ 兄弟组件间联动
+ 创建city-components 的分支
+  给字母表绑定点击事件  @click="handleLetterClick"
+ 事件  触发字母数据传递  当前子组件->父组件->兄弟子组件  this.$emit('change',e.target.innerText)
+ 父组件监听 当前子组件事件 @change="handleLetterChange"
+ 父组件利用属性传值给兄弟子组件 letter 传递给city-list
+ watch 监听联动   再利用 better-scroll 滚动到对应字母元素
+ 添加 :ref
```
watch: {
	letter () {
		if(this.letter) {
			const element = this.$refs[this.letter][0]
			this.scroll.scrollToElement(element)
		}
	}
}
```
+ 字母表滚动事件监听
+ 添加三个touch 事件在字母表, touchstart / touchmove / touchend
+ 创建letters 数组存所有的字母
+ 每一个字母都加上ref
+ 计算touch字母是哪个 利用offsetTop/clientY/字母行高
+ 列表切换性能优化
+ 创建 startY  updated 生命周期钩子  减少计算 startY 是A字母距离顶部的距离
+ 函数节流  timer
