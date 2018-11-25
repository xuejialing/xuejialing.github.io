---
layout: post
title: vue 学习笔记（十三）画廊
date: 2018-11-23 14:06:00 +0800
categories: vue update
---

+ 新建detail-banner 分支
+ Recommend.vue 文件中，在li标签外套一个router-link标签
+ router-link 加 :to="'/detail/' + item.id"   tag="li"  既有路由的效果还有li的样式，不会改变文字颜色
+ index.js  添加动态路由
+ import Detail from '@/pages/detail/Detail'  添加、引入detail组件
+ 页面布局
+ 创建Banner 局部组件
+ banner样式
+ iconfont
+ 画廊
+ 创建common 全局公用组件 common    common/gallery/gallery.vue
+ 修改 build/webpack.base.conf.js   路径别名   重启
```
alias: {
	'common': resolve('src/common')
}
```
重启服务
+ Banner 中 import  gallery  添加gallery组件
+ gallery 布局、样式
+ swiper
+ swiper 页码
swiperOptions: {
	paginationType: 'fraction'
}
+ 循环数据
+ 点击显示隐藏
+ 画廊宽度问题导致滑动问题  swiper 自我刷新
swiperOptions: {
	observeParents: true,
	observer: true
}
+ 点击关闭画廊
