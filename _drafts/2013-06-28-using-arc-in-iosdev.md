---
layout: post
title: "在iOS开发中使用ARC"
description: ""
category:
tags: [iOS Dev, ARC]
---
{% include JB/setup %}
#####__strong和__weak
无论实例变量， 属性， 甚至局部变量，
__strong 关键字来表示一个变量是 strong 类型的指针，变量默认就是 strong 的，

weak 类型的变量也能指向一个对象，但是他们不能成为所有者.
@property (strong, nonatomic)
strong 关键字和你想象的一样。 它告诉 ARC 这个属性对应的 synthesize 声明的实例变量，持有一个当前对象的强引用。 换句话说， window 属性包含了一个指向 UIWindow 对象的指针，并且作为这个 UIWindow 对象的所有者。 只要 window 属性还保留着它的值， 那么这个 UIWindow 对象就一直存活。 viewController 属性和 MainViewController 对象也是一样的。
#####__bridge, __bridge_transfer 和 __bridge_retained
一般情况下， iOS 中基于 C 语言的 API 会用到 Core Foundation 对象 (这也是 CF 的意思)， 而基于 Objective-C 的 API 用的是继承自 NSObject 的”真正的”对象。 有时你需要在这两者之间进行转换， 这也是 “可互换的” 对象所代表的意思。

#####@autoreleasepool

“ARC 禁止在 Objective-C 中使用结构体和联合体”
ARC 的一个限制就是你不能在 C 接口体中放入 Objective-C 对象了。

 属性的修饰符是这样：
strong. 这是以前的 “retain” 的一个代号。 strong 属性将会成为它所指对象的所有者。
weak. 这个属性表示弱引用指针。 当它指向的对象被销毁时，它会被自动的设置成 nil。 记住，在 outlet 上使用它
unsafe_unretained. 这和以前的 “assign” 等同。 你只需要在一些例外的情况下会应道它，并且当你在给 iOS 应用时，后面会讲到更多。
copy. 这个和之前是一样的。 它创建一个对象的拷贝，并且创建一个强引用关系。
assign. 你不再允许在对象上用这个修饰符， 但你仍然能在简单类型的值，比如 BOOL,int 和 float 中用到它。