---
layout: post
title: "Objective-C 语言中的类类型"
date: 2014-03-05 11:07:38 +0800
comments: true
categories: "iOS开发"
---

小菜鸟在学习使用UICollectionView的时候发现个函数：

```objective-c
- (void)registerClass:(Class)cellClass forCellWithReuseIdentifier:(NSString *)identifier;
```
这个函数允许用户为不同的标示设置对应的类型，生成UICollectionCell组建UICollectionView时，会根据 identifier的不同创建不同类型的Cell。

其中这个 `Class` 就是Obj-c中的`类类型`。

从UICllection的使用可以看出类类型在自定义类的使用中非常方便。

下面是类类型的使用：

# 得到类类型
每个类都有类类型生成方法：
```
+ (Class)class;
```
接受类类型
```
Class CLString = [NSString class];
```

# 使用类类型
使用类类型也非常简单
```
id aString = [CLString new];  
```
或者
```
id aString = [[CLString alloc] init];  
```
这时 aString就是NSString的一个实例了。