# AndroidStudio-Eat-Guide—— 2.Gradle编译优化

标签： AndroidStudio-Eat-Guide

Github地址：[https://github.com/coder-pig/AndroidStudio-Eat-Guide][1]

----------

[TOC]

**问题描述**

上一节中我们了解了Android Studio的优缺点，下载与安装。可能你已经摩拳擦掌
想试试AS这个强大的Android IDE了。然后，你新建了一个项目，接着你视线中会
出现：![][2] 这个东西，他会一直在转个不停，而且可能很卡，
可能N多分钟过去了，你还没进入到新建的项目中，然后你就开始
疯狂吐槽了，什么垃圾编译器，新建个项目都要跑这么久，还不如用回Eclipse...

然而AS中的Gradle构建工具表示很无奈，卡顿的主要原因如下：

- 1.**电脑硬件问题**：编译时会有较大的CPU暂用，内存占用，频繁的IO读写
- 2.Gradle编译时候会去查询下载项目依赖的库，然后仓库是jcenter，国外，你懂得；
- 3.项目模块较多，Gradle默认挨个按顺序处理
- 4.等等...

既然知道了问题，那么接下来从各个方面来优化Gradle构建的速度。


----------

## 1.硬件优化

标准配置：**CPU** **i5**以上，**内存** 至少**8G**，**硬盘** **必须固态SSD**
附：相同配置的电脑Ubuntu系统上使用AS比Windows流畅一些，亲测~


----------

## 2.使用国内Maven仓库或自己搭建

上面也说了，Gradle默认会到jcenter下载项目依赖的库，国外下载速度会很慢，
或者根本没网速，如果你没代理的话，这里的话可以公司搭建本地maven仓库，
库都下到这个Maven仓库，项目在添加上这个仓库的地址，当然配置是比较繁琐的。
如果就那么几个人开发的话，没什么太大的必要去搞，可以直接使用阿里提供的
Maven仓库，在项目根目录下的build.gradle中添加仓库地址即可：

```
maven{ url 'http://maven.aliyun.com/nexus/content/groups/public/'}
```

![][3]


----------

## 3.使用SS代理

相信经常Google查学习资料的童鞋都有SS这样的代理工具，既然jcenter是国外
的，自然可以通过配置SS来加快下载速度咯。打开AS的Setting，勾选输入下述
内容：

![][4]

SS开启PAC模式代理即可。


----------

## 4.开启Gradle离线编译模式

假如你通过上述的套路**已经**把相应的库**下载到**了**本地**，你就可以开启离线编译模式了，
如果某个依赖在本地不存在的话，是会编译出错的！直接打开Setting，勾选Offline，
选择本地的.gradle文件夹即可。

![][5]

也可以命令行走一波：

```
./gradlew --offline build
```

----------

## 5.调整gradle.properties中的各种配置

前面的话是下载库优化的，接着是gradle配置优化，打开项目根目录的
gradle.properties文件，按需添加下述配置项：

```
# 分配更大的内存
org.gradle.jvmargs=-Xmx3062m -XX:MaxPermSize=512m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8

# 开启守护进程
org.gradle.daemon=true

# 开启并行编译
org.gradle.parallel=true

# 开启缓存
android.enableBuildCache=true

# 开启孵化模式
org.gradle.configureondemand=true
```


----------

## 6.Android Studio配置优化

同样，也可以为AS分配更多的内存，打开AS的安装目录下的bin目录，找到 ![][6]
文件，打开修改下这两个：

![][7]

比如改成：-Xms512m -Xmx2048m ，然后重启下AS即可。


----------

## 7.写死依赖库版本

有些小伙伴在build.gradle添加依赖库的时候喜欢写成下面这种版本号，

```
compile "com.github.bumptech.glide:glide:3.+"
```

初衷是好的：每次都从仓库中获取最新的库，自动升级，但是也意味着
如果新版接口改了会导致编译失败的问题，而且Gradle回去仓库中试图
拉取最新版本，网络不好时，也会拖慢Gradle的构建速度，所以还是建
议写死依赖库的版本号。例如：

```
compile "com.github.bumptech.glide:glide:3.7.0"
```


----------

## 8.直接在git bash命令行编译项目

这点不算优化，只是个人偏好的一种方式，比如你在gayhub上clone了
一个Demo，如果你直接用AS打开的话，那么你有N多分钟不用做事了，
就卡在编译界面那里，我们可以直接在命令行进行编译，进入项目
目录右键，git bash，键入下述指令进行编译：

```
./gradlew build
```

Gradle在干什么，一目了然~


----------

暂时想到的就这些，如果后面get了什么新姿势再来补充吧，如果你知道
更多Gradle优化的技巧欢迎告知，万分感激~

----------

**参考文献**：

- [一些关于加速Gradle构建的个人经验][8]


  [1]: https://github.com/coder-pig/AndroidStudio-Eat-Guide
  [2]: http://static.zybuluo.com/coder-pig/kq5gxog8l3bymyc6j29w1qlp/image_1bfm2fesia4erv0nb81cbn1p6j9.png
  [3]: http://static.zybuluo.com/coder-pig/eou6vurfcp1zcok02zbrld5c/image_1bfm4vnuab7vf3uvk51iua1rspm.png
  [4]: http://static.zybuluo.com/coder-pig/l9yb6vzkzb1phn3afpeairk8/image_1bfm5djcv105d1ebd1p591s0evqq13.png
  [5]: http://static.zybuluo.com/coder-pig/b9ozofzctytaqavsb6k5l3tg/image_1bfm6l20nauu42k21aka1lca20.png
  [6]: http://static.zybuluo.com/coder-pig/d6jp8p4wpi6avc1by8l4xwlx/image_1bfm85sdacvq1s3a17i5q1ogsr2d.png
  [7]: http://static.zybuluo.com/coder-pig/m7jzqowt253vpfxqvjtclvuc/image_1bfm873di153l1qat8pr11cdg5l2q.png
  [8]: http://droidyue.com/blog/2017/04/16/speedup-gradle-building/