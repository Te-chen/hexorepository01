---
title: 关于NoteExpress无法引用的问题
tags:
- win10
- ms word
- ms office
date: 2016-03-30 21:12:21
---

<p><center><b>注意: 本文仅针对MS Office 2010及以上版本Word(64x)的引用</b></center></p>

# 现象
点击引用无效
![](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210316212503.png)

<!-- more -->

**(我用的是Office 365, Office 2019可能显示为: *未定义书签*)**
引用成功
![](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210316213645.png)

# 操作方法
## 在NoteExpress主程序中加载插件
在安装NoteExpress的时候，NE会自动在Word中加载插件，用户通过插件可以完成参考文献的插入与格式化等功能，但是，偶尔也会有word插件出现问题的情况，需要重新安装插件.[^1]
1.点击NE工具菜单选择【选项】 
![](http://www.inoteexpress.com/wiki/images/8/89/插件1.jpg)
2.在选项页面中，选中【扩展】，就可以看到Word插件安装的按钮了，必要的时候，可以先卸载一下插件，再重新安装。
![](http://www.inoteexpress.com/wiki/images/1/19/插件2.jpg)
## 在Word加载插件 [^2]
1.在Word的文件菜单中，选择【选项】 
2.在Word选项【加载项】页面中管理加载项，点击【转到】，如图所示 
![](http://www.inoteexpress.com/wiki/images/a/ab/插件3.jpg)
![](http://www.inoteexpress.com/wiki/images/9/9c/插件4.jpg)
3.转到com加载项，添加NE安装目录下 NEWordaddin.dll 文件 
4.添加成功后，点击确定即可。 
![](http://www.inoteexpress.com/wiki/images/a/a0/%E6%8F%92%E4%BB%B65.jpg)
![](http://www.inoteexpress.com/wiki/images/6/66/%E6%8F%92%E4%BB%B66.jpg)

[^1]:www.inoteexpress.com/wiki/index.php/注册及安装Word插件
[^2]:www.inoteexpress.com/wiki/index.php/Word和WPS插件无法安装解决方法集合