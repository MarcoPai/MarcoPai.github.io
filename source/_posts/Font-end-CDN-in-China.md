title: '国内前端CDN服务'
tags:
  - javascript
  - cdn
categories:
  - tools
date: 2014-06-28 22:36:53
updated: 2014-06-28 22:36:53
---

今天在折腾 hexo 中的 Google Fonts 时遇到了无法访问的情况，于是去我之前用的bootcss提供的国内CDN服务列表中招了半天也找到。
只好继续百度，然后找到了360提供的国内CDN服务。下面大体说下这两个国内CDN服务的区别：

#### BootCSS CDN
> Bootstrap中文网联合又拍云存储共同推出了开放CDN服务，我们对广泛的前端开源库提供了稳定的存储和带宽的支持，例如Bootstrap、jQuery等。

##### 地址：[OpenCDN](http://open.bootcss.com/)
##### 特点：提供了几乎涵盖了前端开发大部分的前端库资源

#### 360 CDN

##### 地址：[前端公共库](http://libs.useso.com/)
##### 特点：
- 除了常用的前端库外，还提供了Google公共库和Google字体
- 速度很快


#### 友情提示
鉴于页面中同域最多2个请求的限制，建议页面中如果需要引用多个资源的话，还是分不同的CDN比较好，这样速度会加快不少。当然一定要确保核心资源优先加载哦！