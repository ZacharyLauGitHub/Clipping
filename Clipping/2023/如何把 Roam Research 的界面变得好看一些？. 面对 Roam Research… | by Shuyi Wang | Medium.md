---
created: 2023-02-08T02:44:49 (UTC +08:00)
tags: []
source: https://wshuyi.medium.com/%E5%A6%82%E4%BD%95%E6%8A%8A-roam-research-%E7%9A%84%E7%95%8C%E9%9D%A2%E5%8F%98%E5%BE%97%E5%A5%BD%E7%9C%8B%E4%B8%80%E4%BA%9B-b57516f338e
author: Shuyi Wang
---

# 如何把 Roam Research 的界面变得好看一些？

> 面对 Roam Research 的默认主题和字体设定那么久，我觉得在上面码字儿不够愉快。

面对 Roam Research 的默认主题和字体设定那么久，我觉得在上面码字儿不够愉快。
---------------------------------------------

![](https://miro.medium.com/proxy/1*n-RinDIZepe6pQg6AGW0dg.png)

痛点
--

每天，我都要花很多时间使用 Roam Research 。但前一段时间，我几乎把所有的录入和编辑工作都转移到其他应用（例如 Bear 和 Ulysses）上完成。 原因之一可能是审美疲劳吧。面对 Roam Research 的默认主题和字体设定那么久，我觉得在上面码字儿不够愉快。比起 Ulysses 的编辑体验，差很多。

本着「重器轻用」的原则， Roam Research 的作用是明显的。我的工作流需要用 Roam 从卡片梳理出大纲，并且对一些内容进行添加和顺序重新排布。如果我对使用 Roam Research 产生抵触，那么从卡片蹦到输出，有些跳步了。写短文，这事儿还没有什么。但对于长文的构思和迭代，它会给我的工作流带来一些麻烦。

趁着假期，我调整了一下 Roam Research 界面美化相关的设置。这项工作的结果，是我打开 Roam Research 的时候明显感受了到更多的喜悦。当前设置很符合我的口味，使我愿意在 Roam Research 呆上更长的时间 — — 用大纲方式梳理笔记集结文章，还利用链接跳转游览自己的数字花园。

下面我把这几天来美化 Roam Research 界面所做的一些工作步骤介绍给你。希望对于你改造和美化自己的第二大脑工作环境也能有帮助。至少，我踩过的一些坑，你可以直接跳过了。

设置好看的主题
-------

我是从 Twitter 上看到 [Alexander Rink](https://github.com/rcvd) 介绍自己制作的模块化主题系统（Roam CSS Theme）的。

![](https://miro.medium.com/proxy/1*pvuMPgWK9ymmf7nt9WeHvw.png)

他项目托管地址在这个 Github Repo 链接：[rcvd/roam-css-system: Roam CSS System 2.0](https://github.com/rcvd/roam-css-system)

![](https://miro.medium.com/proxy/1*0-B2pOQXEZjSzYtNVd2b_w.png)

在项目里面，Alex 提供了若干套的主题供用户自由选择。包括：

*   iA Quattro
*   Less Wrong
*   Bear
*   Things
*   Craft

这几天，Alex 还进行了大规模更新。使得每一种主题，都分别提供了深色和浅色款。试用下来，我觉得有的主题非常符合自己的审美。

我写作本文的时候，用的就是 Less Wrong 主题的深色款，效果很不错。

![](https://miro.medium.com/proxy/1*MiCS3nc-PPAxkZm4KrY1IA.png)

再比如，这是 iA Quattro 的浅色主题，看着也很舒服：

![](https://miro.medium.com/proxy/1*9OFPrghrUeNL4bUPeHakjw.png)

如果你常用的软件包括 Bear, Craft 和 Things ，那么这几个对应的高仿主题，也都可以试试。

Roam Research 的主题设定方式有很多。第三方开发者早就提供了很多自创主题。但是有的主题安装方式比较麻烦，需要你自己往 roam/css 页面体面粘贴不少内容，甚至还需要你根据自己的需求修改参数。就像这个样子：

![](https://miro.medium.com/proxy/1*Dmv_KIoXadqZl7IO0tWwlg.png)

对非 IT 类用户来说，这些内容带来了很多细节设定上的认知负担，不舒服。好在 Alex 的 Roam CSS system 不需要这些细节的展示。你只需要在 roam/css 页面添加一句话，就能搞定主题安装和运行。

```
@import url('https://rcvd.github.io/roam-css-system/themes/quattro.css');

```

搞定。

更好的消息是， Alex 正在把这个 css 主题系统移植到 Roam Research 的 RoamDepot 上面，这就意味着将来主题安装和选择都变成了一键搞定。

![](https://miro.medium.com/proxy/1*KIVqI8FEpj45GODDMZQ2pg.png)

参考目前 Roam Depot 审核的速度，我估计这个事儿很快就能完成。

不过 Roam Research 里面的界面设置，绝不只是主题那么简单。你看我上面的例子里，字体也不是原本的默认版本，而是自定义设置。

![](https://miro.medium.com/proxy/1*9OFPrghrUeNL4bUPeHakjw.png)

下面咱们来谈谈 Roam Research 里面自定义字体设定方式。

自定义字体
-----

我这人全无艺术细胞，之前本来没有考虑过字体设置的事儿。应用默认提供什么字体，我就用什么。如果遇到默认字体实在难看的（例如外文应用，而且没有考虑中文字体问题），我会考虑用苹果提供的「苹方」或者微软的雅黑字体来替换。

但是前几天，听了贾行家老师在《文化参考》节目里面偶然的推荐，我突然明白自己天天看的「得到电子书」用的是一种叫做「得到今楷」的字体。

> 书写之道连着武术之道，这并不牵强，因为它同样都是有关动作和韵律的艺术，物理规律一样，审美修养也一样。日常的例子也有：印在书上、海报上或者贴在墙上的字，本身就有文字信息之外的直观感觉，否则我们也不会为得到今楷投入这么大的精力了。

一下子，我来了兴趣。既然这种字体平时看着习惯舒服，那迁移到笔记工具里，也是一种不错的选择吧？可是「得到今楷」是得到 App 的专属字体，网上无从下载。普通用户是不是只能望洋兴叹了呢？

我上网搜了一下，发现[知乎上有人写了答案](https://www.zhihu.com/question/320418581)，说所谓的「得到今楷」，其实就是「仓耳今楷 01」。作者是严永亮。这样一来就好办了。因为「仓耳今楷 01」的下载地址到处都是。

我从[这个地址下载了全套字体](https://www.jb51.net/fonts/639767.html#downintro2)，解压之后，是一系列的 otf 文件。

![](https://miro.medium.com/proxy/1*NLrYDtCoy1eAIrg-wTTizA.png)

需要用到哪个 otf 文件，直接双击安装就可以了。

![](https://miro.medium.com/proxy/1*wI0aHfPorg7nSVyFdpUrwg.png)

我把「仓耳今楷 01」字体压缩包里面的 5 个 otf 文件，一股脑全都安装上。现在 macOS 里面就有了 5 种笔画粗细不同的字体版本。

然后，你需要在 Roam Research 里面进行字体设定。还是 roam/css 里面，开启一个代码段，然后这样写：

```
body, html, a, div, textarea {
  font-family: "Iowan Old Style", serif, "TsangerJinKai01-9128 W03", -apple-system, "SF UI Text", "Lucida Grande", STheiti, "Microsoft YaHei", sans-serif !important;
}

```

其中的 `TsangerJinKai01-9128 W03` 把字体设定成了第 3 阶的粗细。这是我尝试过来，比较符合自己习惯的设定。你可以根据自己的偏好修改。

![](https://miro.medium.com/proxy/1*7uxFVV-8XFO85Pp4iRbIgA.png)

你看，现在界面字体好看多了吧？

只不过，字号大小依然是个问题。当右侧主编辑区字号符合我的要求时（你知道的，我喜欢大字），左边栏的字号就显得太大了，有些傻。

![](https://miro.medium.com/proxy/1*11TJP8WrC0hrfLH67QOT6A.png)

咱们来调整一下。

调整字号
----

我需要保持右侧字号不变的情况下，把左侧边栏的字号改小。这一部分，实话实说，因为对 css 不大熟悉，我自己没有搞定。

但是这不是问题，因为我有个朋友叫立青 (@JimmyLv) 啊。

立青和我进行了 3 个来回的迭代（他提供代码，我负责实测和反馈），处理了一些细节上的问题，完成了修改工作。

你可以在 roam/css 页面新建一个代码段，把下面这段贴上就好。

```
body, textarea, html, blockquote  {
  font-size: 24px;
}
.starred-pages a .page {
    font-size: 16px !important;
}
.roam-body .roam-app .roam-sidebar-container .roam-sidebar-content div.log-button {
    font-size: 16px;
}

.roam-body .roam-app .roam-sidebar-container .roam-sidebar-content .starred-pages-wrapper .title {
    font-size: 16px;
}
.roam-body .roam-app .roam-sidebar-container .roam-sidebar-content .rm-left-sidebar__roam-depot.log-button div {
    font-size: 16px;
}

.roam-body .roam-app .roam-sidebar-container .roam-sidebar-content .rm-db-title {
    font-size: 16px;
}

```

立竿见影，原本傻大黑粗的左侧边栏，变成了这个样子：

![](https://miro.medium.com/proxy/1*y2yEZxQZ-lz7vtQYSDOBrw.png)

怎么样？顺眼多了吧？

小结
--

本文我给你介绍了自己对 Roam Research 界面调整的 3 项工作：

*   Roam CSS System 主题安装
*   自定义字体设定
*   左侧边栏的字号调整

顺便说一句， Roam CSS System 主题不止支持 Roam Research ，也有对应的 Logseq 版本，[地址在这里](https://github.com/rcvd/logseq-css-system)。

![](https://miro.medium.com/proxy/1*3EaSeObC00ki5DlS8wmzFw.png)

如果你使用 Logseq ，也不妨尝试一下。

你有没有优化笔记工具界面的经验？在优化过程中，有没有什么独特的心得或者教训可以分享？欢迎留言，我们一起交流讨论。
