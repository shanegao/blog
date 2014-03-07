---
layout: post
title: "Cocoa声明属性"
description: ""
category: tech
tags:
---

http://stackoverflow.com/questions/9859719/objective-c-declared-property-attributes-nonatomic-copy-strong-weak

http://blog.csdn.net/duxinfeng2010/article/details/8461784
copy与retain：
Copy其实是建立了一个相同的对象，而retain不是：
比如一个NSString对象，地址为0×1111，内容为@”STR”
Copy到另外一个NSString之后，地址为0×2222，内容相同，新的对象retain为1，旧有对象没有变化
retain到另外一个NSString之后，地址相同（建立一个指针，指针拷贝），内容当然相同，这个对象的retain值+1
也就是说，retain是指针拷贝，copy是内容拷贝

assign: 简单赋值，不更改索引计数
对基础数据类型 （例如NSInteger，CGFloat）和C数据类型（int, float, double, char, 等） 适用简单数据类型
此标记说明设置器直接进行赋值，这也是默认值。在使用垃圾收集的应用程序中，如果你要一个属性使用assign，且这个类符合NSCopying协 议，你就要明确指出这个标记，而不是简单地使用默认值，否则的话，你将得到一个编译警告。这再次向编译器说明你确实需要赋值，即使它是 可拷贝的。

