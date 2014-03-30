---
layout: post
title: "NSLog 输出控制"
date: 2014-02-28 14:48:17 +0800
comments: true
categories: "iOS开发" 
---
NSLog 在 iOS开发调试时非常方便，但也很耗资源。在APP正式发布时把NSLog一条一条注释掉太过麻烦，而且不利于后续开发维护。使用如下操作可以简化操作:

在 **'PROGJECTNAME'-Prefix.pch** 文件中添加

``` c
#ifdef DEBUG
# define LOG(...) NSLog(__VA_ARGS__)
#else
# define LOG(...) /* */
#endif
```
在 **TARGETS->build Settings->Other C Flags->Debug** 中添加 **”-DDEBUG”**
这样就配置完成了 
![配置示意图](http://ilost.qiniudn.com/imagesdebug_nslog.png)


在需要输出的地方把原来的 **NSLog()** 改为 **LOG()** 就可以了
debug模式下输出，release模式下不输出

