# AndroidStudio-Eat-Guide—— 1.AS简介，下载安装与配置

标签： AndroidStudio-Eat-Guide

---

## 1.为何提倡使用AS而非使用Eclipse开发Android

答：
> 
- 因为Google在2015年已经停止了Eclipse开发Android的支持，不再做相
关的更新！官网已经不再提供下载链接了(当然有隐藏链接~)；
- Android Studio是Google亲儿子；
- 基于IntelliJ IDEA，功能强大代码编辑器；
- 基于Gradle构建系统等等...
总之就是牛逼哄哄，如果你用熟了AS就不会想着回头摸Eclipse~

附：旧版Eclipse下载的隐藏链接

|系统|位数|下载文件地址|
|:-:|:-:|:-:|
|Window|32位|[https://dl.google.com/android/adt/adt-bundle-windows-x86-20140702.zip][1]|
|Window|64位|[https://dl.google.com/android/adt/adt-bundle-windows-x86_64-20140702.zip][2]|
|Linux|32位|[https://dl.google.com/android/adt/adt-bundle-linux-x86-20140702.zip][3]|
|Linux|64位|[https://dl.google.com/android/adt/adt-bundle-linux-x86_64-20140702.zip][4]|


----------

## 2.AS有哪些优缺点？

**优点**：
> 
- 1.Google亲儿子，官方Android IDE，出问题Google会修复，不断更新；
- 2.AS基于牛叉的Java IDE：**IntelliJ IDEA**，更强大的代码智能提醒，界面更好看，
丰富的插件下载：一键findViewById，代码画词翻译等等，实属开发利器；
- 3.智能重构，智能的代码检测，更丰富的代码搜索功能；
- 4.图片可以直接转.9，并且可以直接编辑.9；
- 5.代码定时自动保存，无需一直ctrl + s；
- 6.强大的Gradle脚本构建工程：一行代码引用开源库，AAR；多渠道打包等等；
- 7.强大的即时运行，不用每次都重新编译运行，直接能看到效果；
- 8.内置性能监测工具，可以事实查看内存，CPU，网络，GPU的情况；
还有其他很多好的地方，自己慢慢发掘~

**缺点**：
> 
用了这么久我觉得AS是非常好用，可能刚接触AS的童鞋会觉得AS有以下几点不好的：
> 
- 1.一个窗口只能打开一个工程，Eclipse可以在一个窗口同时打开多个工程；
- 2.每次Gradle编译运行的时候很卡，要等很久；
卡顿的主要原因是：频繁的IO读写，Gradle默认编译的时候会去查询下载更新库，
然后天朝你懂的，所以很多时候都会很慢；
解决的方向有：
①**升级自己电脑的配置**，SSD固态硬盘是必须得有，120G的也就几百块，普通应用
开发够用了；然后内存上8G，内存多点没什么坏处；
②**设置Gradle离线编译模式**，依次打开：
Setting -> Gradle -> **Use loacl gradle distribution** -> 设置本地gradle路径
然后勾选**offline working**
③**设置编译时分配更多的内存**：到电脑根目录下：![][5]，打开**gradle.properties**，修改
分配内存为2048mb，这里贴下，有需要的自己复制就好；
④项目尽可能模块化；公司搭建本地maven仓库，内网下载比外网快；简化Gradle脚本；

**gradle.properties**
```
org.gradle.daemon=true
org.gradle.jvmargs=-Xmx2048m -XX:MaxPermSize=512m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8 
org.gradle.parallel=true
org.gradle.configureondemand=true
```


----------

## 3.下载安装Android Studio

### Step 1：安装JDK：先装JDK，不然你装好AS也是打不开的


----------


**Window版本**

官网下载地址：[http://www.oracle.com/technetwork/java/javase/downloads/index.html][6]
安装：一直按下一步就好，默认安装在**Program Files\Java**目录下
**配置Java环境变量**：

**新建**：**JAVA_HOME**：jdk的安装路径，比如：C:\Program Files\Java\jdk 
**修改**：**PATH**，光标移到最前面(Home键)，添加：**%JAVA_HOME%\bin;**！！！别删其他东西！！ 
**新建**：**CLASSPATH**，添加：**%JAVA_HOME%\lib\tools.jar;**
后面两个变量配置**别漏掉";"**分号哦！ 

**验证**：打开命令行(cmd)，依次键入：java和javac，出现一堆东西而不是： 
"**java或者javac不是内部或者外部命令**"，就说明环境变量配置成功。


----------

**Ubuntu版本**(基于14.04 LTS)：

**方法一**：直接打开Terminal(终端)，依次键入下述三个命令即可：

```
sudo apt-add-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-set-default
```

这样安装会自动设置好环境变量，可能你想安装的是其他版本的jdk，比如jdk 7的， 
只需把java8改成java7即可，另外还有一点，你可以下载多个jdk，而你不想新下载 
jdk会覆盖你之前的环境变量，可以把安装语句改成：

```
sudo apt-get install oracle-java7-installer
```

默认安装到**/usr/lib/jvm/**目录下！

**方法二**：自己下载jdk压缩包，手动配环境变量

当然，你也可以自己下jdk压缩包，解压后自己手动配Java环境变量，打开Terminal， 
键入:**sudo gedit ~/.bashrc** 然后添加环境变量的配置代码：

```
xport JAVA_HOME=/usr/lib/jvm/jdk1.7.0_55   
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export PATH=${JAVA_HOME}/bin:$PATH
```

保存Terminal键入java，javac看是否生效。


附：**Android系统源码编译时设置局部环境变量**

如题，假如我们开发普通应用是基于jdk 1.8的，而编译源码需要的环境是jdk 1.6或者jdk 1.7 
的，那么我们可以在创建一个设置临时Java环境变量的文件，然后让在当前Terminal中jdk的版 
本变成1.6或者1.7，比如我在源码目录下创建一个jdk.sh的文件，然后写入下述内容：

```
export J2SDKDIR=/usr/lib/jvm/java-7-openjdk-amd64
export J2REDIR=/usr/lib/jvm/java-7-openjdk-amd64/jre
export PATH=/usr/lib/jvm/java-7-openjdk-amd64/bin:/usr/lib/jvm/java-7-openjdk-amd64/db/bin:/usr/lib/jvm/java-7-openjdk-amd64/jre/bin:$PATH
export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64
export DERBY_HOME=/usr/lib/jvm/java-7-openjdk-amd64/db
```
保存，然后在编译源码之前，我只需要键入: **. jdk.sh** 即可让局部环境变量生效， 
那么在这个Terminal里，jdk的版本就变成了1.7了，然后就可以进行源码编译的后续操作了。

----------

### Step 2：下载安装Android Studio

**官网地址**(需要梯子，有些慢)：[https://developer.android.com/studio/index.html ][7]
**AndroidDevTools**(国内站点，资源在百度云)：[http://www.androiddevtools.cn/][8]


----------


**windows版本**：

**安装**：安装路径那里可以自己选下AS和sdk的路径，也可以不选，其他默认下一步，虚的
自己谷歌百度下。

**配置环境变量**：

**新建**：**ANDROID_HOME**：SDK的路径，不如我的：D:\Software\Coding\android-sdk
**修改**：**PATH**：添加

```
%ANDROID_HOME%;%ANDROID_HOME%\tools;%ANDROID_HOME%\build-tools;%ANDROID_HOME%\platform-tools;
```

**验证**：打开命令行(cmd)，键入：adb，出现一堆东西而不是： 
"**adb不是内部或者外部命令**"，说明环境变量配置成功。


----------

**Ubuntu版本**：

**方法一：下载解压(建议)**

解压后，打开Terminal，cd到解压目录的bin目录下，键入： **./studio.sh** 
即可运行Android Studio，接着各种选择，安装，安装完后续打开AS重复这个
步骤即可!

**方法二：键入命令，一键安装**

打开Terminal，依次键入下述命令，不是很简易，因为网络问题可能会失败多次

```
sudo apt-add-repository ppa:paolorotolo/android-studio
sudo apt-get update
sudo apt-get install android-studio
sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1
```

**附**：**Android Studio安装时报错:unable to run mksdcard sdk tool的解决方法**

键入下述命令添加以来，然后重新安装即可

```
sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
```

**附：设置Android Studio快捷启动方式**

每次运行AS都需要敲一波命令显得有些繁琐，我们按照下述操作来设置快捷启动方式
打开Terminal，键入：

```
sudo vim /usr/share/applications/Studio.desktop 
```

接着设置与Android Studio相关的东西：**Exec**代表运作脚本，**Icon**表示图标 
**Terminal**：是否显示shell

```
[Desktop Entry]
Name = Studio
comment= android studio
Exec=/opt/android-studio/bin/studio.sh
Icon=/opt/android-studio/bin/studio.png
Terminal=false
Type=Application
```

保存退出后，来到usr/share/applications目录下，找到Studio图标，拖到左边 
任务栏即可。

**附：Android环境变量的配置：**

打开Terminal，键入：

```
sudo vim /etc/profile
```

复制粘贴，然后把下面的ANDROID_HOME的路径改成你Android Studio的实际路径

```
export ANDROID_HOME="$HOME/Library/Android/sdk"
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/tools
```

修改后保存，wq，接着键入下述指令，可以让环境变量在当前的shell有效：

````
source /etc/profile
```

接着你可以键入:adb，看看是不是出来一大串的东西，来验证环境变量配置是否 
生效，接着重启电脑，接着在其他的shell也会生效了！




  [1]: https://dl.google.com/android/adt/adt-bundle-windows-x86-20140702.zip
  [2]: https://dl.google.com/android/adt/adt-bundle-windows-x86_64-20140702.zip
  [3]: https://dl.google.com/android/adt/adt-bundle-linux-x86-20140702.zip
  [4]: https://dl.google.com/android/adt/adt-bundle-linux-x86_64-20140702.zip
  [5]: http://static.zybuluo.com/coder-pig/jde0jbu0z61iav0rap2a2gqd/image_1asj7jsjp1f711v0uq8nic14vs9.png
  [6]: http://www.oracle.com/technetwork/java/javase/downloads/index.html
  [7]: https://developer.android.com/studio/index.html
  [8]: http://www.androiddevtools.cn/