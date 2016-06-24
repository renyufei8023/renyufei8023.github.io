---
layout: post
title: 使用UIStoryBoard给UITableView添加HeadView
author: 任玉飞
date: 2015.12.03 15:28:32 +0800
categories: Blog
tag: Blog
---

#使用UIStoryBoard给UITableView添加HeadView

###使用UIStoryBoard给UITableView添加HeadView
可以直接拖动一个UITableViewController 上去，默认就会有一个prototype cell. 如果UITableViewController 不能满足你的需要，也可以使用UIViewController + UITableView 的组合。步骤：

1. 在UIViewController 上拖动一个UITableView。看起来像这样
[![alt text](http://img.bbs.csdn.net/upload/201504/14/1428973805_630689.png "title")

2. 再拖一个UITableViewCell 到 UITableView 
[![Alt text](http://upload-images.jianshu.io/upload_images/301240-7e2dffc1c73c29f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 拖一个UIView放到prototype cell的上面，即headerview 
[![Alt text](http://upload-images.jianshu.io/upload_images/301240-dbb05731a98bf952.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)]

