---
layout: post
title: "连接设备调试出现Finished running…"
description: ""
category: tech
tags: [armv6, armv7, debug, Xcode]
---
{% include JB/setup %}
[http://stackoverflow.com/questions/7760946/possible-to-target-older-ios-versions-when-using-xcode-4-2-and-ios-5-sdk](http://http://stackoverflow.com/questions/7760946/possible-to-target-older-ios-versions-when-using-xcode-4-2-and-ios-5-sdk)

使用iPod Touch 1代调试程序，Build完成后直接出来”Finished running for iPod”。。
大概原因，Xcode4.2默认不支持armv6，而3G以前的iPhone，第一代和第二代iPod Touch的CPU只支持arm6指令集，iPhone 3GS，iPad以及第三代iPod Touch采用新的处理器，同时支持armv7指令集。
所以在Target->Build Settings->Architectures下的Architectures项添加arm6，Valid Architectures项目同样。。同时支持armv6，armv7。。（[armv7编译的优势](http://stackoverflow.com/questions/3310907/what-are-the-advantages-of-armv7-over-armv6-when-compiling-iphone-apps))