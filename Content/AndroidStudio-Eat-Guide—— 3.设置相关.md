# AndroidStudio-Eat-Guide—— 3.设置相关

标签： AndroidStudio-Eat-Guide

Github地址：[https://github.com/coder-pig/AndroidStudio-Eat-Guide][1]


----------

## 1.必须记住的快捷键：Ctrl+Shift+A

> 
To find any action inside the IDE use(找到IDE里使用的所有Action) 
当我们想快速定位某一个设置或者操作在哪可以直接用这个快捷键，比如：

![][2]

**Ctrl+Shift+A**，后面都简称为："**CSA**"


----------

## 2.设置Http代理

> 
按CSA，输入：**Http Proxy**

![][3]

> 然后点进去，自己设置代理相关的东西即可。

![][4]


----------

## 3.设置SDK路径

> 
按CSA，输入：**SDK Manager**

![][5]

![][6]


----------

## 4.设置项目依赖的SDK，JDK，NDK

> 
按CSA，输入：**Project Structure**

![][7]

![][8]


----------

## 5.配置Git

> 
依次打开：**Setting** -> **Version Control** -> **Git**

![][9]


----------

## 6.设置默认编码方式

> 
依次打开：**Setting** -> **Editor** -> **File Encodings**

![][10]


----------

## 7.修改IDE字体与字体大小

> 
**代码编辑部分**，依次打开：**Settings** -> **Editor** -> **Colors & Fonts** -> **Font**

![][11]

如果想修改**Console控制台字体**，选择线面的**Console Font**，也是同样的设置~


----------

## 8.设置自动导包

> 
按CSA，输入：**auto import**，都勾选上，然后点击Settings那一项

![][12]

![][13]



----------

## 9.设置鼠标停留在方法里显示方法说明

> 
依次点击：**Setting** -> **Editor** -> **General** 找到下面这个，勾选

![][14]

----------

## 10.自定义需要折叠的代码种类

> 
可以自定义可以折叠的代码，依次点击：**Setting** -> **Editor** -> **Code Folding**，
自己勾选需要折叠的代码种类即可！

![][15]

----------

## 11.自定义代码折叠区域

> 当我们想折叠某个区域，可以用<**editor-fold**><**/editor-fold**>标签包住折叠区域

```
//<editor-fold desc=”折叠后显示的文字”> 
折叠的区域 
//</editor-fold>
```

比如把变量包裹起来，直接折叠代码，还是蛮嗨的。

![][16]


----------

## 12.让某个区域禁止自动对齐

> 
有时我们写的代码，不想按ctrl + alt + L的时候自动对齐，把我们自己写
的代码格式破坏掉，比如这样写：

![][17]

> 
如果按自动对齐这个排版就完了，我们可以给这个区域加个前后标记，
把这个区域锁住，不自动对齐。

![][18]

> 
勾选后，用//@formatter:off 和//@formatter:on 包裹住。Ctrl + Alt + L就不会对齐了。

  [1]: http://static.zybuluo.com/coder-pig/2dw2goibg75erplcnfzjz6sw/image_1ajodq8151vlu1qad1mco15fdtdim.png
  [2]: http://static.zybuluo.com/coder-pig/2dw2goibg75erplcnfzjz6sw/image_1ajodq8151vlu1qad1mco15fdtdim.png
  [3]: http://static.zybuluo.com/coder-pig/bkr3stpink9b9tgb32vmlkc6/image_1ajoevurg12015itkcejmg1kuf1g.png
  [4]: http://static.zybuluo.com/coder-pig/me382wxn31meadkbezr8du4i/image_1ajof7bul1dic14s41sqc1gdaf381t.png
  [5]: http://static.zybuluo.com/coder-pig/iqg7uhf8gkw2u57f5pb7g7rd/image_1ajoggr3c19v5h78ef1tt32fm34.png
  [6]: http://static.zybuluo.com/coder-pig/306adm3g8walz32gz2gm6jrt/3.png
  [7]: http://static.zybuluo.com/coder-pig/7q4heue0gzgejd180xrgce08/image_1ajofv08namer2iv31bjn1n3f2a.png
  [8]: http://static.zybuluo.com/coder-pig/ouz6b0dbpfxpvqj5wjare2fz/image_1astfj8d1mb1s9k8sagt82vnm.png
  [9]: http://static.zybuluo.com/coder-pig/dpz2y3xy3af5obatjp4udwab/image_1ajoijo4vug11q3li231p9b156944.png
  [10]: http://static.zybuluo.com/coder-pig/dn2czn6qqminpc64nsr1i48d/image_1ajoisf0ecmebkclh2mrampt4u.png
  [11]: http://static.zybuluo.com/coder-pig/q4fk1aipn1tq9932zqkr13lc/1.png
  [12]: http://static.zybuluo.com/coder-pig/aldfm3sgbz2zema4i1q199di/image_1asuhl3jo1v99v35loc1kb015d0l.png
  [13]: http://static.zybuluo.com/coder-pig/as0mxfpk3pufi1eux2ksogwh/image_1asuho5ahopc81n1v7a1tulhs812.png
  [14]: http://static.zybuluo.com/coder-pig/1gupxz1jfls2whqyhzybo4zx/image_1asuhvlrp1q561pcbah914m41uhu1f.png
  [15]: http://static.zybuluo.com/coder-pig/qcp8l2y5zqf5zerx09ipx5qh/image_1asuiucaiqadtq5108b1mvnu0f1s.png
  [16]: http://static.zybuluo.com/coder-pig/582r5k74p2djnuljym44bh75/image_1ajon0cgqgpn9te1cq17a61qb49p.png
  [17]: http://static.zybuluo.com/coder-pig/laeqq8yflwpwxxbpfu7pxaqw/image_1asujen5a2hu17bs1n461lqk9h2g.png
  [18]: http://static.zybuluo.com/coder-pig/d4l6bczmyvbc1d8icezijqg9/image_1ajom9njtneq1jl1ngnmike8i.png