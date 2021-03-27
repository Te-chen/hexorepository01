---
title: how to create a site
date: 2021-03-20 16:34:42
tags:
 - win10
 - hexo
 - github
 - git
 - markdown
---

<p><b><center>本文僅對 Windows 用戶適用</center></b></p>

<p><i>I prefer to write with the Hexo because it’s more convenient:-)</i>[^6]</p>

#  环境搭建: Hexo & NexT

<p><center>"<i>讓 Hexo 準備就緒僅需幾分鐘</i>[^1]"</center></p>

## 安裝必備軟體

* **[git](https://git-scm.com/download/win)**

![setupgit](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321110145.png)

* **[Node.js](https://nodejs.org/en/download/)**(Node.js 版本需不低於8.10，建議使用 Node.js 10.0 及以上版本)[^1]

![setupnodejs](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321113644.png)

## 部署Hexo博客系统

一旦所有的必備軟體都安裝完畢後，即可透過 npm 安裝 Hexo：<!-- more -->

* 在安裝位置呼出右鍵菜單(Shift+F10)

![gitbushhere](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321113038.png)

* 選中 Git Bush Here, 通过命令行安装：

```
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server
```

建立完成後，專案資料夾會有下列檔案：

![專案資料夾](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321120305.png)

这时候你已经部署好了Hexo博客系统，并且初始化好了博客系统所需的文件，blog就是你的博客根目录。这时候我们需要安装一款名为Next的主题，这个主题也是本博客目前使用的主题。[^2]

## 安装 NexT

### 下载主题

在终端窗口下，定位到 Hexo 站点目录下。使用 `Git` checkout 代码克隆最新版本：[^3]
```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```
安装完成後，主題 (themes) 資料夾會有下列檔案：

![theme/next](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321121625.png)

**在 Hexo 中有两份主要的配置文件，其名称都是` _config.yml`。其中，一份位于站点根目录下，主要包含 Hexo 本身的配置；另一份位于主题目录下，这份配置由主题作者提供，主要用于配置主题相关的选项。 **

<p><b><center>为了描述方便，在以下说明中，将前者称为 ”站点配置文件“，后者称为 “主题配置文件”。 </p></b></center>

### 启用主题

打开 `站点配置文件`，找到 `theme` 字段，并将其值更改为 `next`。 [^3]

![themenext](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321122734.png)

### 验证主题

* 在專案資料夾使用`Git Bush Here`, 輸入`hexo s --debug`, 开启调试模式. 

![hexosdebug](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321123849.png)

当命令行输出中提示出： 

```
INFO  Hexo is running at http://0.0.0.0:4000/. Press Ctrl+C to stop.
```

此时即可使用浏览器访问 `http://localhost:4000`，检查站点是否正确运行。

![localhost4000](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321124259.png)

# 系统部署（GitHub Pages）

上面只是在本地预览，接下来要做的就是就是推送网站，也就是发布网站，让我们的网站可以被更多的人访问。[^4]

> 一旦你注册好了一个GitHub帐号后，在上面建立一个仓库（repository）后，在你计算上设置好SSH Key来打通和GitHub仓库的通道后，你就可以……用人话讲就是，你通过那几条命令把你的网站上传到GitHub的网站上去了。然后你可以访问： `http://username.github.io` ，这网址就是你的博客地址，需要把里面的username替换为你的GitHub账户名。[^2]

## 新建一個名爲`<user>.github.io`的repository

以我個人的爲例：

![repository](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321130813.png)

複製`仓库的完整路径`

![copyrepolink](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321131207.png)

## 一鍵部署私人儲存庫

在`站点配置文件`末尾加入[^5]：

```
deploy:
  type: git
  repo: 仓库的完整路径.git
  branch: gh-pages
```

（以我個人的爲例）

![deployset](https://cdn.jsdelivr.net/gh/Te-chen/figurebed01/20210321125749.png)

## 推送网站

这时，我们分别输入三条命令：

```
hexo clean #清空Hexo数据库和产生的文件
hexo g #生成
hexo d #部署
```

完成后，打开浏览器，在地址栏输入你的放置个人网站的仓库路径，即 `http://<user>.github.io`, 你就会发现你的博客已经上线了，可以在网络上被访问了。



[^1]:https://hexo.io/zh-tw/docs/index.html
[^2]:https://www.bmpi.dev/self/build-write-tool-v1/
[^3]:http://theme-next.iissnan.com/getting-started.html
[^4]:https://zhuanlan.zhihu.com/p/26625249
[^5]:https://hexo.io/zh-tw/docs/github-pages
[^6]:https://chiangtechen.wordpress.com/about/