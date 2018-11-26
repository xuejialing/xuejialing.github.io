---
layout: post
title: vue 学习笔记（十六）上线-接口联调
date: 2018-11-26 12:23:00 +0800
categories: vue update
---
接口联调 ， 修改config/index.js
```
    proxyTable: {
      '/api': {
        	target: 'http://localhost'
      	}
      }
```
+ package.json 开启外部ip访问  ："dev"： --host 0.0.0.0

+ 没有promise的浏览器，安装，支持es6
```
npm install babel-polyfile --save
main.js   import 'babel-polyfill'
```

+ 打包：
```
npm run build
```
-> dist
+ 更换项目目录
把生成的文件放入project中  config/index.js
```
build:{
.........asssetPublicPath: '/project'
```
+ 异步加载：
router/index.js
```
components: () => import('@/pages/city/City')
```
**打包报错：**
ERROR in ./node_modules/_extract-text-webpack-plugin@3.0.2@extract-text-webpack-plugin/dist/loader.js……

解决办法：
cnpm install --save extract-text-webpack-plugin@2.1.2
