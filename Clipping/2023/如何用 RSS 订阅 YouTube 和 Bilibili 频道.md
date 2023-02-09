> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.instapaper.com](https://www.instapaper.com/read/1577678160)

> A simple tool for saving web pages to read later on your iPhone, iPad, Android, computer, or Kindle.

注意：如果您在使用 macOS 13，请升级到 macOS 13.2 或以上的系统。在更低版本的 macOS 13 中由于 WebKit 的问题，包括 DEVONthink 在内的大量第三方软件可能无法正常播放网页视频。

[@文刀](https://twitter.com/eamesliu)在[第五期会员栏目](https://utgd.net/article/9380)中介绍了视频订阅 RSS 化的思路。我也这么干了好几年，只是担心 hack 之处过多而不适合一般人；直到看见文刀也这么干，同时又有会员提问，才敢放心把整套方案分享出来。本文方案适用于 YouTube、Bilibili 以及其他能够找到 RSS 源的视频站点，但因为我不看 B 站，所以文章中的例子仅限于 YouTube。标题带上 Bilibili 实属无奈，怕 Bilibili 用户错过本文而已。

RSS 后面虽然常常跟着 “阅读器” 三个字，但用它来订阅 YouTube 也很自然，因为关注的主播一多，就容易漏掉节目更新；而 RSS 恰好可以把零碎的更新提醒汇集起来，很适合作为节目更新的提醒工具。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092020.jpeg)用 RSS 阅读器订阅 YouTube 频道更新

我将在后文中介绍两种主要的订阅方法，并提供相应的自动化工具（Keyboard Maestro 版本），以便快速获得订阅链接。

如何用 RSS 订阅 YouTube
------------------

严格来说，用 RSS 订阅 YouTube 频道的理由有**两个**，并且很有趣，它们恰好相反，并且两个理由会引出两种具体的 RSS 订阅方案。

文刀的出发点和我部分相同，我们都关注了一些主播，并且希望不要漏掉视频更新。不过，正如文章一样【引用前文】，我把视频也一刀切成两类，一半是供娱乐的视频，我希望 RSS 里直接带上图文，这样浏览起来就很直观，可以很快确定要不要看一个视频，创意视频和歌手的 MV 的均属此类；另一半则是需要严肃观看的视频，需要挂到专业阅读器里观看，因此我使用 YouTube 官方 RSS 源，以便显示原始页面，这类视频主要是视频教程、访谈节目和纪录片。

### RSSHub：适合娱乐向的频道

第一类，即追求视觉效果的频道，需要使用第三方 RSS 订阅源，比如 [RSSHub](https://docs.rsshub.app/social-media.html#youtube)。RSSHub 提供的订阅源图文兼备，只是有一定概率会挂——实际情况比较乐观，我用了好几年，挂掉的不到个位数，不过还是推荐有能力的读者自己搭建，更加稳定。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092057.jpeg)RSSHub 订阅效果（阅读器为 NetNewsWire）

RSSHub 可以订阅具体某个主播、频道或列表，我主要用于订阅频道，它的 RSS 链接模板是：

```
https://rsshub.app/youtube/channel/频道ID

```

`频道ID` 是重点，能不能正确订阅，就要看能不能正确获取 ID。稍后将介绍的 YouTube 官方方案同样需要获取 ID。YouTube 曾经把 ID 直接放在主播页面的链接中，但目前已经取消了，以至于诞生了一批 ID 抓取工具。其实 ID 仍然写在网页元数据里，检查网页后可以看到 ID——通常是 24 位左右的英文和数字组合，偶尔带有下划线和短横线。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092104.jpeg)网页中其实隐藏了 channel id

把这串 ID 复制出来，和 `https://rsshub.app/youtube/channel/` 拼接在一起就可以订阅了。我在 YouTube 上关注了一批歌手和创意视频博主，他们经常在 YouTube 上首发新作；我把他们的频道订阅到 RSS 工具里（我用的是 NetNewsWire），就可以安心等着视频提醒，而不用再时不时刷一下网页等更新。RSSHub 生成的链接可以直接播放视频，不过我一般还是会下载或观看原始页面，这些内嵌的视频主要用来刮一眼封面，判断内容感不感兴趣——毕竟，看视频封面可比读标题和简介轻松多了。

### YouTube 官方 RSS：适合严肃向的频道

YouTube 自己也提供了 RSS 订阅链接，功能非常基础，只有视频标题和原始链接，并无封面预览，更不会让你占便宜直接播放视频了。但是这个寒酸的链接，却非常适合与 DEVONthink 配合，用于观看需要严肃研究的视频。YouTube 官方源的链接模板如下，同样需要自行填写频道的 ID：

```
https://www.youtube.com/feeds/videos.xml?channel_id=频道ID

```

这当然还是要归功于 DEVONthink 本身。首先，YouTube 上的大量视频都是外文的，我可以用 DEVONthink 把视频标题[批量翻译成中文](https://utgd.net/article/8406)，便于判断哪些值得看，而不需要都点开一遍；其次，用 DEVONthink 观看 YouTube 视频时，它会显示**目录**！原本冗长且絮絮叨叨的视频，瞬间云开雾散，马上可以跳过口水章节，直达有用部分。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092113.jpeg)YouTube 官方 RSS 订阅效果（阅读器为 DEVONthink）

内容严肃的视频，很可能需要边做看边笔记，或许还会涉及字幕检索、截图标注、深度链接等需求。而 DEVONthink 本身是一个强大的信息管理工具，前述功能不在话下，它还提供了一系列后续可能用到的功能：全文检索原始网页，配合第三方工具一键下载视频，生成直达视频任意时间点的 Deep Link，显示不同视频之间的引用关系…… 就算你想拉片看，一帧一帧看，DEVONthink 也不会掉链子。这部分内容绝非一两篇文章能够说完，此处仅仅开个头，方法论将发布在[另一篇文章中](https://utgd.net/article/9896)，对操作细节感兴趣的读者可以与我私下交流。

还有一个很现实的原因，就是官方源毕竟不会随意关停，也不会设置反爬虫限制，因此比较严肃的内容，我更喜欢使用官方源，以免不知不觉漏掉更新。

加点自动化
-----

如上一节所述，RSS 订阅 YouTube 的方案主要有两种，一种是官方源，另一种是八仙过海的第三方源，而无论哪种，都需要先获得频道的 ID。只要解决这了这一环，之后不过就是和链接模板拼接。

我做了一个快速抓取频道 ID 并生成订阅链接的 Keyboard Maestro Macro，使用之前需确保已经给予 Keyboard Maestro 运行 Javascript 的权限：

1.  打开 Safari 浏览器，进入设置页面，在 “Advanced” 菜单中启用开发者菜单——“Show Develop menu in menu bar”（不同版本的 Safari，该选项位置也有差异，找不到的话可转道 “General” 一试）；
2.  在开发者菜单中勾选 “Allow JavaScript from Apple Events”；
3.  选择同意 “Allow”，可能需要输入密码或验证指纹。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092119.jpeg)允许 Safari 运行 Javascript

Macro 的使用方法很简单：

1.  下载安装，注意需要在 Macro 编辑器中手动启动此动作；
2.  在主播的频道页面运行此动作（默认快捷键是 `⌘Command-K`）；
3.  Keyboard Maestro 会把完整的链接拷贝到剪贴板；
4.  转到你所用的 RSS 阅读器，正常订阅。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0117092125.jpeg)用 Keyboard Maestro 一键抓取 RSS 连接

这个动作默认是生成 RSSHub 的 YouTube 频道订阅链接，你可以修改最后两步，将其用于订阅作者或播放列表，也可以切换成 YouTube 官方源或其他源。

[Keyboard Maestro Macro 下载](https://github.com/BlackwinMin/Keyboard-Maestro-gallery/tree/master/Grab%20YouTube%20RSS)