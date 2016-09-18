# AndroidStudio-Eat-Guide—— 2.Android Stuido与SDK更新

标签： AndroidStudio-Eat-Guide


----------

## 1.检查更新Android Studio


----------


### 查看当前Android Studio的版本

> 
点击顶部菜单栏：**Help** -> **About**

![][1]


----------

### 检查版本更新

> 
点击顶部菜单栏：**Help** -> **Check for Updates** 选择Update and Restart
然后等他慢慢更新完就好~

![][2]


----------


### 设置更新通道，选择需要更新的版本

> 
依次打开：**Setting** -> **System Settings** -> **Updates**
四个版本分别为：
> 
- **Stable** Channel(稳定版)
- **Canary** Channel(预览版)
- **Beta** Channel(测试版)
- **Dev** Channel(开发版)
>
一般选择稳定版就好，除非你是重度更新强迫症患者~

![][3]

----------

### 设置HTTP代理

> 
关于Android Studio的更新，现在基本都不用代理了，当然你如果想为Android Studio
设置代理也行，依次打开：**Setting** -> **Appearance & Behavior** -> **System Settings**
-> **HTTP Proxy**，自行设置代理即可！

![][4]



----------

## 2.更新Android SDK


----------


### 设置项目依赖的SDK/JDK/NDK

> 
一般默认都已经设置了的，如果你想设置项目默认依赖的SDK和JDK，你可以直接右键项目，
选择：Open Module Settings F4，或者点击顶部工具条的![][5]图标。

![][6]


----------


### 更新SDK

> 
有时我们需要更新Android SDK，依次打开：**Appearance & Behavior** -> **System Settings**
-> **Android SDK**，选中需要下载的Package，然后Accept进行安装即可，如果你想单独打开
SDK安装只需点击底部篮字：**Launch Standalone SDK Manager**即可！

![][7]


----------

### 为Android SDK Manager 设置更新代理(现在不用设代理)

> 
其实现在**已经不用设置SDK代理了**，因为下载流量已经解析到了北京机房~
你可以打开命令行，然后键入：**ping dl.google.com**，你会发现即使你不
挂代理，也能ping得通，如果你有安装dig的话，命令行**dig dl.google.com**
随意拿一个ip来查一下，比如 **203.208.51.33**

![][8]

> 
所以基本不用设置代理了，这里只是知道多一点而已，点击：**Launch Standalone SDK Manager**
单独运行SDK Manager，依次点击：**Tools** -> **Options**，然后填入代理地址与端口，
选中**Force...**的复选框，然后**Close**，然后点击**Packages** -> **Reload**即可！

![][9]

附：几个可用的镜像源，引用自：[Androiddevtools][10]

**Android SDK在线更新镜像服务器**

- 1.中国科学院开源协会镜像站地址:
 - IPV4/IPV6: mirrors.opencas.cn 端口：80
 - IPV4/IPV6: mirrors.opencas.org 端口：80
 - IPV4/IPV6: mirrors.opencas.ac.cn 端口：80
- 2.上海GDG镜像服务器地址:
 - sdk.gdgshanghai.com 端口：8000
- 3.北京化工大学镜像服务器地址:
 - IPv4: ubuntu.buct.edu.cn/ 端口：80
 - IPv4: ubuntu.buct.cn/ 端口：80
 - IPv6: ubuntu.buct6.edu.cn/ 端口：80
- 大连东软信息学院镜像服务器地址:
 - mirrors.neusoft.edu.cn 端口：80
- 腾讯Bugly 镜像:
 - https://dsx.bugly.qq.com/repository/1
 - 腾讯镜像使用方法:https://dsx.bugly.qq.com/repository/1


----------


  [1]: http://static.zybuluo.com/coder-pig/1iysvvlg5mfki8a4znjf5qj1/image_1asjqkteegt71lq51dlf1mmp14c09.png
  [2]: http://static.zybuluo.com/coder-pig/8cj5cdr366h6ngos4rzru9px/image_1asjqrq7g1miajps1bul9u01h6vm.png
  [3]: http://static.zybuluo.com/coder-pig/qgjj7weqr57vcvvibbqzleks/image_1ajokq2gl1r06sf65e31iov3ds7b.png
  [4]: http://static.zybuluo.com/coder-pig/me382wxn31meadkbezr8du4i/image_1ajof7bul1dic14s41sqc1gdaf381t.png
  [5]: http://static.zybuluo.com/coder-pig/pc1qjosctsiyihymon27dchd/image_1astfi5gf5rr1g082j2jvf599.png
  [6]: http://static.zybuluo.com/coder-pig/ouz6b0dbpfxpvqj5wjare2fz/image_1astfj8d1mb1s9k8sagt82vnm.png
  [7]: http://static.zybuluo.com/coder-pig/d0hnw52ug3wzxte97yaxel9h/1.png
  [8]: http://static.zybuluo.com/coder-pig/a7pm5vefgamhgpljwl7jkp8c/image_1asthq43mogfm0i1nll13je114824.png
  [9]: http://static.zybuluo.com/coder-pig/q5reyqae91f87k6f4x1qg80w/image_1asti6pob1qanrq1amqpit1nr42h.png
  [10]: http://www.androiddevtools.cn/