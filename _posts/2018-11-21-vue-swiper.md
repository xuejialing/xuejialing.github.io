---
layout: post
title: vue学习笔记（三）swiper
date:   2018-11-21 12:10:00 +0800
categories: vue update
---
+ 新建index-swiper 分支
+ git pull
+  git checkout index-swiper 切换分支  git status 查看分支
+ github 上搜索  vue-awesome-swiper
+ 安装 npm install vue-awesome-swiper --save   重启服务
+ import VueAwesomeSwiper from 'vue-awesome-swiper'
+ import 'swiper/dist/css/swiper.css'
+ Vue.use(VueAwesomeSwiper)
+ components 下创建组件  Swiper.vue
```
data (){
	return {
		SwiperOption:{}
	}
}
```
+ Home  import Swiper组件  注册   跟 home-header 一起外面需要套个div，否则报错Component template should contain exactly one root element
+ 修改swiper样式
+ swiper 下面内容抖动问题 swiper 外部套个div
+ 添加swiper的白色点 ，颜色修改使用样式穿透 >>>
```
      swiperOption: {
        // 页码点样式标签
        pagination: {
          el: '.swiper-pagination'
        },
        // 循环播放
        loop: true
      }
```
+ 定义swiperList   循环 v-for swiperList  绑定数据
+ loop 循环轮播
+ 合并分支  git checkout master  -   git merge  origin/index-swiper

*备注：*
+ ! important ，可以更改默认的CSS样式优先级规则，使该条样式属性声明具有最高优先级，也就是相当于写在最下
+ chrome Network - Fast 3G  开启chrome 3g模式
+ chrome 插件  vue-devtools  查看components 结构
+ css抖动问题
以下是stylus 语法
```
.wrapper
    overflow: hidden
    width:100%
    height:0
    padding-bottom:31.25%
```




