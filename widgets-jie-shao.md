# Widgets介绍

`main`函数里面的`runApp()`函数接收`Widget`对象，并将其设为`root widget`，`flutter`还会强制将其铺满屏幕。

写App时候，你一般要创建自己的`Widget`，它需要继承自`StatelessWidget`或`StatefulWidget`，这取决于你的`Widget`是否需要管理状态（`state`）。一个`Widget`的主要功能就是实现`build`函数，它会更具其他更低级的`Widget`来描述构成自己。

`StatelessWidget`从他们的父`Widget`上接收参数，它们被保存在`final`成员变量里面， which it then uses during its build function.

为啥`StatefulWidget`和`State`要分开？

因为两种对象有不同的生命周期。`Widget`是临时对象，用于构造应用程序当前状态的表示。另一方面，`State`对象在`calls`和`build()`之间是持久的，允许它们记住信息。

