---
layout: post
title: "Xcode 4.2中禁用ARC"
description: "iOS Development"
category: cocoa
tags: [ARC, LLVM, Xcode]
---
{% include JB/setup %}
1.对于整个项目，Xcode 4.2中禁用ARC(Automatic Reference Counting):

Project Info ->Build Settings-> Apple LLVM compiler 3.0 – Language -> Objective-C Automatic Referencing Counting, 设置为NO即可

2.设置部分源文件在编译不进行ARC检查，比如第三方开发源码。。

Target->Build phases->Compile sources 选中不需ARC的文件，双击添加 编译参数 -fno-objc-arc ， 改为手动引用计数方式。
注：打开ARC使用-fobjc-arc强制单个文件使用ARC,对于iOS 4的运行环境，需要在Other Linker Flags选项中加入-fobjc-arc