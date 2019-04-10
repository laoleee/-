# Flutter工程卡死在Initializing gradle的解决办法

首先说解决办法：在`flutter`的安装目录下找到`flutter.gradle`文件：

![](.gitbook/assets/image.png)

然后编辑该文件：

![](.gitbook/assets/image%20%281%29.png)

注释掉两行，加上`maven`开头的三行：

```text
  maven { url 'https://maven.aliyun.com/repository/google' }
  maven { url 'https://maven.aliyun.com/repository/jcenter' }
  maven { url 'http://maven.aliyun.com/nexus/content/groups/public' }
```

然后在工程里面再次运行`flutter run`，等待即可。

为什么呢？

首先要知道`Andorid`应用是使用`Gradle`进行构建的，不了解`Gradle`，看这篇文章：

> [https://www.cnblogs.com/Bonker/p/5619458.html](https://www.cnblogs.com/Bonker/p/5619458.html)

在构建过程会下载一些依赖包，但由于天朝网络原因，你懂的。

所以把下载依赖包的仓库地址换为国内阿里云的镜像就好了。

