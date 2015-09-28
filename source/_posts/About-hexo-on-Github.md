title: '在github上建立hexo博客系统'
tags:
  - hexo
  - github
  - markdown
categories:
  - tools
date: 2014-06-28 21:29:39
updated: 2014-06-28 21:29:39
---

[Hexo](//hexo.io) 一个台湾人写的NodeJS下的博客系统

为什么非得是hexo，而不是Wordpress或者其他的PHP的博客系统呢？
其实就是为了能提高点逼格而已，哈哈。
基本上使用hexo作为博客工具的人群，都些码农，尤其是前端码农。为什么这么说呢？接着往下看就知道了。

1. hexo的本地环境是NodeJS
2. 版本当然用的时Git咯
3. 新建、静态化、发布等等工作都是命令行
4. 支持Markdown和Swig语法（当然，后者我没用过）

就以上这几点，是不是很有前端范儿啊！


其实有关hexo的安装与配置也没啥好说的，毕竟网上有关github上搭建hexo博客的文章很多，重点可以参考两篇：
1. 这是我最初看到的：粉丝日志里面的[Hexo在github上构建免费的Web应用](http://blog.fens.me/hexo-blog-github/);
2. 后来又找到了这篇：[hexo系列教程：（二）搭建hexo博客](http://zipperary.com/2013/05/28/hexo-guide-2/)

好了，只说说我在折腾时遇到的问题吧：

1. 我本地环境：Mac OS 10.9 / NodeJS 0.10.29 / npm 1.4.14 / hexo 2.7.1
2. 第一步安装的时候一定要加上sudo，否则会权限报错滴
``` bash
$ sudo npm install hexo -g
```
3. 对于Mac用户来说会有个比较蛋疼的问题，也是我装了N遍都不成功的原因，在[官网](http://hexo.io/docs/)专门针对Mac用户做了下面的提醒：
> You may encounter some problems when compiling. Please install Xcode from App Store first. After Xcode is installed, open Xcode and go to **Preferences -> Download -> Command Line Tools -> Install** to install command line tools.

4. 按照教程把本地都配置完了之后，开始弄github，这里遇到两个问题，一个是域名的解析，一个是github上面cname文件，下面大体说下放到github需要做哪些事情：
    1) github上新建一个和自己名字想同的项目名，比如我的riasky.github.io
    2) ping一下项目地址，拿到ip后在域名解析中增加一条A记录指向这个ip：
    ``` bash
    $ ping riasky.github.io
    ```
    
    > 当然也可以直接CNAME @ 指向 riasky.github.io，好处是如果换IP的话，就不用重新指定了

    3) 在github项目中增加一个CNAME文件，这里需要注意的是，网上的教程都是让你直接在项目中增加一个无后缀名的CNAME文件，里面写上你的域名：
    ``` text
    marcopai.com
    www.marcopai.com
    ```
    
    > 遇到的问题：
    * 但是当执行`hexo deploy`的时候，会将整个项目文件替换为 `hexo generate` 生成的静态文件，也就是说你之前单独建立的CNAME文件会被删除掉（就这个问题折腾了我好几个小时）.
    * 我的办法是在hexo项目文件夹根目录下的source文件夹内新增这个CNAME文件，这样的话，每次deploy的时候就会把这个文件一同带上了
 
    4) 执行hexo的静态化
    ``` bash
    $ hexo generate
    ```
    
    5) 执行同步到github上
    ``` bash
    $ hexo deploy
    ```

5. 都安排妥当了，发了几篇日志后准备在网上看看效果，突然发现页面打开的超级慢，打开firebug的网络工具发现有几个fonts.googleapis.com的请求一直加载中。 没办法只能找替代了，总不能让所有访问的人都翻墙吧：       
    Google Fonts 服务：[Google Open Sans字体无法加载](http://yusi123.com/3062.html) 搜索 `fonts.googleapis.com` 替换为 `fonts.useso.com`

    至于Google无法访问的问题，还是多百度一下吧 [不用翻墙的Google镜像](http://www.admin10000.com/document/4615.html)

    这里推荐几个国内的前端CDN库：
    - [360cdn](http://libs.useso.com/)
    - [bootcss](http://open.bootcss.com/)
     
   更多有关CDN的内容请参考：[国内前端CDN服务](/2014/font-end-CDN-in-China.html) 


###问题：

***2014-7-18***：修改Markdown生成table直接支持bootstrap的表格样式。
文件路径：
```
$ /Users/marco/work/nodejs/hexo/node_modules/hexo-renderer-marked/node_modules/marked/lib/marked.js
```

找到 818 行，修改如下：
```javascript
Renderer.prototype.table = function(header, body) {
  return '<table class="table table-striped table-bordered">\n'
    + '<thead class="active">\n'
    + header
    + '</thead>\n'
    + '<tbody>\n'
    + body
    + '</tbody>\n'
    + '</table>\n';
};
```

---
