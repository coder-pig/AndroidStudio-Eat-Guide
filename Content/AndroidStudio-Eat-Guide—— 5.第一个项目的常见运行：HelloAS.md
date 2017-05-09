# AndroidStudio-Eat-Guide—— 5.第一个项目的常见运行：HelloAS

标签： AndroidStudio-Eat-Guide

Github地址：[https://github.com/coder-pig/AndroidStudio-Eat-Guide][1]


----------

## 1.创建新的工程


如果你刚安装完，或者你把所有的项目close了，会弹出这样的窗口：

![][2]

或者已有项目，你可以直接点顶部菜单栏：**File** -> **New** -> **New Project**

![][3]

接着输入**项目名**，**包名**，**选择项目的存储路径**
 
![][4] 

填写完毕后Next，选择开发的应用类型，支持最低版本的SDK，之类可以点击
蓝字Help me choose查看当前各个系统版本的市场占有率，以供参考
或者查看友盟统计的全域指数：[Android 操作系统统计][5]

![][6]

![][7]

点击Next进入下述页面，提供了多种模板的Activity供你创建，一般直接
Empty Activity就可以了！看自己需要~

![][8]

接着设置**Activity的名字**和**布局文件的名字**

![][9]

 接着就是漫长的Gradle编译了，如果你之前已经下载过Gradle的话，这一步应该
 会很快~如果慢可以参考第一节提供的优化方案进行优化！
 
 


----------


## 2.创建AVD模拟器

在运行我们的Hello AS之前，我们可以创建Android自带的AVD模拟器，
如果是以前的Eclipse，我会建议你直接下个**Genymotion的模拟器**
而现在的AS自带模拟器的性能大大提高了，使用了新的而用户界面，
性能速度也大大提高，点击顶部菜单栏的**AVD Manager**图标

![][10]

![][11]

点击Next选择模拟器搭载的系统版本

![][12]

创建完后，点小箭头启动模拟器

![][13]

![][14]

右侧菜单栏依次是：
**电源**，**增大音量**，**减小音量**，**向左旋转屏幕**，**向右旋转屏幕**
**截屏**，**屏幕放大**，**返回键**，**Home键**，**进程概览**，**更多**
更多里面有：**定位模拟**，**网络信号模拟**，**电磁状态模拟**，**来电信息模拟**
**定向板**，**指纹**，**设置**，**帮助**


----------

## 3.运行程序

点击顶部菜单栏的运行按钮或者按快捷键**Shirt + f10**

![][15]

然后经过漫长的等待，就可以在模拟器看到跑起来的程序了

![][16]


----------





  [1]: http://static.zybuluo.com/coder-pig/xlkzqz0tuxbz3wepe6gsly53/2.png
  [2]: http://static.zybuluo.com/coder-pig/xlkzqz0tuxbz3wepe6gsly53/2.png
  [3]: http://static.zybuluo.com/coder-pig/5u7aafjem5eusy7nktl9t33w/image_1asukdcgatga1aps72168a11ghl.png
  [4]: http://static.zybuluo.com/coder-pig/6pmj5v8gcgk4daf20gsbx9iv/1.png
  [5]: http://www.umindex.com/devices/android_os
  [6]: http://static.zybuluo.com/coder-pig/ij45ctb3npmm3sjvpwlukr6o/3.png
  [7]: http://static.zybuluo.com/coder-pig/3lxmj4vlkua8vnn30eahmt3b/image_1asul2d1f15m91r27o3b1s7qi2v1q.png
  [8]: http://static.zybuluo.com/coder-pig/m66etryc89f3q5phr7pc5iyy/image_1asul82u7b7su5cd5l12r77m227.png
  [9]: http://static.zybuluo.com/coder-pig/i5ctt70m7fw1bl30w2o1k4gz/image_1asuladua8uh15sc1djfbeg1vv2k.png
  [10]: http://static.zybuluo.com/coder-pig/1mgw8fiddis8mps9xbzwziio/image_1asulq5gt16ms1jkl1soev6ofgs31.png
  [11]: http://static.zybuluo.com/coder-pig/6krcrudhj630kmeie6jfo6gf/4.png
  [12]: http://static.zybuluo.com/coder-pig/24ilc42eh342xazafhgia9is/image_1asumegf6138114a1tnf1nslmj347.png
  [13]: http://static.zybuluo.com/coder-pig/g3v1el90v650fyzmeggcey9k/image_1asumfh0nqublq721a5gf15lg4k.png
  [14]: http://static.zybuluo.com/coder-pig/illphr1zw7x2pg7jco5phdcd/image_1asumi139vdic5l1l68se41d6251.png
  [15]: http://static.zybuluo.com/coder-pig/avcr9jw7eofev5ij2fvn303n/image_1asumuggivsi8u5ntvpv8tjl5e.png
  [16]: http://static.zybuluo.com/coder-pig/splzymiasomr6p0sfaqtuwle/image_1asun0ub5ihp1go21cdk3rcmac5r.png