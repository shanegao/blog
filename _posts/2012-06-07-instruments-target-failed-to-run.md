---
layout: post
title: "Instruments Target failed to run"
description: ""
category: cocoa
tags: [Instruments, Profile, Xcode]
---
{% include JB/setup %}

在Xcode 4.2中，使用Profile模式运行Instruments检查程序是否有内存泄漏，出现如下错误后直接终止

![image](http://ww4.sinaimg.cn/large/a74e55b4jw1dtxfgy2w9kj.jpg)

Target failed to run: Remote exception encountered: ‘Failed to get task for pid 3404′

在stackoverflow找到一个[解决办法](http://stackoverflow.com/questions/4323369/use-instruments-leaks-with-a-device/5457816#5457816)
Edit Scheme –> Profile … –> Info标签下Build Configuration设为Debug,再运行，一切正常。