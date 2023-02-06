> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [chichiclub.zhubai.love](https://chichiclub.zhubai.love/posts/2196261672254046208)

这是「搓搓小手」的第一篇文章。「搓搓小手」是一份关于工具的 newsletter，我会在这里分享我对各种工具的探索与使用，包括也不仅限于：效率工具、创作工具、生活方式工具、思考工具、解决问题的工具等等。

这篇文章我会分享我使用 Tana 将近一个月来的感受。我既不是学术研究人员，也不是技术人员，不懂代码与数据，所以我是从一个普通人的角度出发，谈谈我对一个笔记 / 效率工具的体验。如果对一些术语有表述不恰当的地方，还请包容。

关于 Tana
=======

[Tana](https://tana.inc/) 是一个新兴的 Tool for thought 工具，如果你关注这个领域，可能已经看过很多关于它的讨论。有很多人说如果 Roam Research 和 Notion 生了个宝宝就是 Tana。它和 Roam 一样是 block-based 结构，同时又和 Notion 数据库一样可以构建结构化的数据。不得不说，这二者的结合带来的体验真的很奇妙！既可以自下而上地自由记录，又可以有结构地掌握全局。

![](https://imgs.zhubai.love/67d4aa0925ad41a1991c819924014cc6.png)图片加载中

目前 Tana 还在 early access 阶段，我非常幸运地在 10 月初得到了内测机会。用上就停不下来了，并且开始在这里建立我的笔记系统，甚至是 Everything OS。

Tana 有什么不一样？
============

Everything is a node
--------------------

在 Tana 中没有页面的概念，一切都是节点，每个级别的节点都可以独立存在。这让我感到非常放松，以前在使用 Obsidian 的时候总是纠结一段内容到底应该作为一个大标题存在，还是一个单独的页面存在。在 Tana 没有这样的顾虑，只管把一切都写下来就好，反正一切都是节点，随时可以链接，可以引用。

![](https://imgs.zhubai.love/986c95819de845dbbd1a73dbcd24c9b5.png)图片加载中

Supertag
--------

Tana 的标签叫做 Supertag，和其他工具中的 tag 功能也有些不一样。在其他的工具中，我们比较自由地使用标签，有时候作为一种分类，有时候作为一种形容。而 Supertag 只做一件事：它描述一个 node 本质上是什么。

举一个例子：

apple #company 和 apple #fruit 就是两个完全不同的 node。虽然是同一个词，但是 supertag 定义了它的本质。

每个 supertag 都可以有很多自定义的条目 (field)，有点像 Obsidian 中的 YAML，或是 Notion 中的 property，你可以自己去定义每一个 supertag 下应该包含有什么样的数据及类型。

![](https://imgs.zhubai.love/039572776b14440c8a99a8b4dbccb9f4.png)图片加载中

这里的应用就有点像模板，每次你为一个 node 附上标签时，就会自动生成出这些定义好的 field。

Supertag 为什么如此迷人？
=================

Tana 与其他工具最大的不同就是 Supertag，而这听起来很简单的功能为什么能给我带来心流的体验，我试着结合我的使用场景来谈谈我的理解与感受：

Supertag 作为 database
--------------------

Supertag 可以被当做 database 来使用，每个 supertag 下可以设置不同的条目，在 Tana 中被称为 field，支持不同的数据类型（例如数字、日期、列表或是文字等）。

![](https://imgs.zhubai.love/30b59bde44da4b0f81ad1e1974603be9.png)图片加载中

Supertag 定义了一个 node 是什么，而 field 则是描述了一个 node 有什么。这样的结构帮助我从本质去思考一件事物的方方面面。

举一个例子：

在 Tana 中 field 是可以被复用的，如果不同的 supertag 用到了一样的数据内容，可以引用同一个 field。

在我过去的笔记系统里，不同的内容都会用到「状态」这个数据，比如阅读的状态是「未读」「已读」；任务的状态是「待办」「进行中」「已完成」等等。

而在 Tana 中，因为 field 是可以复用的，我开始想，这些不同的事项都有状态，那可以用同一个表达去描述吗？不管是阅读还是任务列表的状态，其实都是表达了一件事在完成过程中所处的阶段，于是我将描述状态的 Status filed 进行了这样的定义：

*   Parked - 是默认初始状态，表明这件事放在系统里了
*   Up Next - 下一个，准备要做的事
*   Now - 正在进行中的事
*   On hold - 因为某种原因搁置了，还会继续
*   Completed - 已经完成
*   Evergreen - 没有明确的结束节点，在系统中常青
*   Archive - 归档，这个状态和删除差不多，但是万一以后需要还是可以找到

目前我所有的数据库都用这同一组状态值去描述，减轻了思考负担，可以用最快的速度理解一件事在我的世界时间轴中所处的位置，无论是要读一本书，完成工作，还是安排日常家务。

![](https://imgs.zhubai.love/a199a1ef328f43ae9d23db24528b85fc.png)图片加载中

/ 上图是浏览我的所有信息源的页面，包含文章、视频、书籍等，红圈中的状态栏表示每一个内容的阅读或观看状态

对我来说设置 supertag 是一件很上瘾的事，这个过程帮助我梳理我自己去定位与丈量万事万物的坐标系和度量衡。它是自由的，又是逻辑的。

Supertag 作为 prompt
------------------

Prompt 是一种给自己的提示。在面对一个空白的页面时，我们总是有点恐慌的。Prompt 可以给一片空白的大脑一点由头，一点启发。在 Supertag 中可以设置条目来提示自己一些相关的可能性。

![](https://imgs.zhubai.love/bfb90b1491ab4ca5abf86529bea5aa95.png)图片加载中

比如：所有的待办事项我都会加上 todo 的 supertag，其中我设置了一个 field 为 “What do you need to start？"。通常一件事最难的就是开始和启动，所以设置这个条目可以提醒我做什么能让我开始。（这一设置受到 [Ev Chapman 的启发](https://twitter.com/evielync/status/1583902811699310592)）

Supertag 作为 workflow
--------------------

在 Supertag 中按步骤或逻辑组合不同的 prompts 就可以形成一个 workflow。每次在处理同一个性质的事时，只需要跟随自己已经设置的流程就好了。可以为我们减少很多重复的思考与能量消耗，更容易达到心流的状态。

![](https://imgs.zhubai.love/d7e4f0bc34db4821a2df28b5401a5172.png)图片加载中

/ 上图展示：当需要做一件事时使用 Focus Mode（专注模式）的标签，自动生成出当需要专注做一件事时经历的步骤

CortexFutuna [有一个视频](https://www.youtube.com/watch?v=jOore8xFkaA)是关于在 Tana 中应用 Interstitial Journaling 的方法，其中介绍了 Focus Mode 的用法，通过 Supertag 设置不同的问题来引导与帮助我们在一段特定的时间内专注完成一件事。我也将这个方法运用到了我自己的系统中。

Supertag 作为思考工具
---------------

workflow 在处理具体事务时是一种工作流程，而在处理信息与笔记时就成为了一种思考框架与工具。当我们面对一条独立的笔记时，这些 prompt 可以提示我们从不同的方向去思考并建立链接。

我在 2 年前接触了 Zettelkasten 卡片笔记法，也尝试过用 Roam Research 和 Obsidian 去实践。因为每个工具的特性不同，所以实践起来的方法各异，Tana 也为此提供了更多可能性。

目前，我的卡片笔记是这样设置的。首先，我有不同类型的 atomic notes，它们从平时各个渠道获取的信息中来，同时也可以脱离语境存在：

*   claim - 其他人的观点
*   scientific study - 科学研究结果
*   spark note - 我自己的想法

每个 Atomic note 都设置有以下的 field：

*   supported by - 支持论点的论据
*   opposed by - 相反的观点
*   lead to - 这个观点可以引出什么其他的观点，或者回答了什么问题

这些 field 就成为了一个思考框架，帮助我去建立链接。

![](https://imgs.zhubai.love/cd9097dc245940a89c137c6cb642760f.png)图片加载中

/ 上图为一条读书笔记示例

一些很主观的感受
========

避免过度过早地建立链接
-----------

Tana 让建立链接变得很方便，我也设置了丰富多样的 prompt 来提示自己建立链接。但是不要让自己迷失在其中，对笔记过早地过度整合。缺乏深思熟虑会导致结构不产生任何意义。

事情往往是这样，过于便利会让我们失去自主意识。主动的、有意义的链接才能产生价值。这里面的平衡需要自己不断调整，也是乐趣所在。

> Let chaos reign, then rein in the chaos. -- Andy Grove

这句话或许可以描述这个过程，首先允许一定程度的混乱存在，没有必要给每一条笔记都找到归属地，不用着急分类与双链，相信意义与结构会慢慢产生，因为这一切是发生在你构建的坐标系里。有意识地构建自己的系统，然后充分信任它。

为什么是英文？
-------

在我的示例中，supertag 和 field 基本上都是英文，而笔记的内容都是中文。这也是在我的使用中逐渐发展成的样子。

最早尝试卡片笔记的时候，原文是什么语言，我就会用什么语言来记录。这个问题困扰了我很久，因为如果不同的笔记不是用一种语言表达，那么在建立链接的时候就难免有些割裂。

于是我决定只用中文一种语言来记笔记。这样，在我阅读英文材料时，必须要翻译成中文，而这个翻译的过程正好符合了卡片笔记法中 “用自己的话来描述” 这个原则，有助于我理解内容。其次，卡片笔记系统实际上是我们的外部大脑，模拟的是思考的过程，我在面对中文的时候可以更快地掌握其中的逻辑与信息。

当然也有例外的情况，如果原文用英文是很精妙的语言表达，具备着英文独有的表达特点时，我会按照原语言来记录。因为此时除了逻辑之外，语法和用词本身也是信息的一部分，需要完整记录。

还分享一个关于语言的小技巧。在我的笔记系统中，遇到名词时也会有用什么语言记录的问题，比如概念、电影名、书名等。这些名词有时候英文是更常用的，有时候中文则是更熟悉的表达。如果我给每个名词都去设置中文名、英文名，也不是很方便使用，并且很僵化，就像街上的双语路牌。

于是我换了个角度来看，将标题设置为我更习惯的语言表达，然后再设置一个 field 为 alternative language title。不按客观的语言种类来分别，而是按照我主观的语言习惯来分别。这么设置让我舒服了很多，也充分证明了建立自己的系统的好处：这就是你的世界，你的坐标。

![](https://imgs.zhubai.love/1e81c6b0c6904786835f9c65b0fd67fd.png)图片加载中

/ 上图为最近看的两部剧，我是按照哪个语言的标题对我来说更熟悉、更易懂来记录的

而为什么 supertag 和 field 我要用英文呢？

因为在这个系统里 supertag 和 field 的作用是符号，是一种指示，在我赋予它含义后，它不需要产生新的逻辑意义了。英文对我来说更容易充当符号的作用。因为我对英文更陌生，我可以通过语言的区隔，将充当指示符号的词语和我真正要去进行逻辑思考的信息内容区隔开，也减轻了大脑的负担，可以更加专注。

工具的力量
-----

大家总是笑谈 “差生文具多”，我也真的是文具上瘾者。从 Notion 到 Rome Research, Obsidian, Heptabase 到 Tana，每一个我都有认真地去尝试和学习。正是因为用了不同的工具，深深感觉到工具对思考方式和 mindset 的影响是极大的。使用 Tana 也有快一个月的时间了，当然有很多” 热恋期“的快乐，我可以明显感受到的心流时刻大大增加了。

![](https://imgs.zhubai.love/79970d20358947b3bc4a06e0f4cdcb39.png)图片加载中

/ 上图为在 Arc 上使用 Tana 做笔记的场景

以前在使用其他工具时，我会极其纠结排版的细节，不管是 Roam 还是 Obsidian 我会花上几天的时间自学 CSS 也要把所有的间距、字号、颜色调整成自己最舒服的状态。可是在 Tana 里我似乎没有这样的偏执（就像谈恋爱，找到了对的人就会发现原来很多事情也没那么重要）。

我认为对于一个 Tool for Thought 工具来说，最重要的还是你是否可以在大脑外建立自己信任的系统，并通过这个系统产生自己的洞察与想法，在信息爆炸的焦虑中获得专注与宁静，拥有思考的安全感。这是完全由我们自己种植的思想花园。

如果看了这篇文章，你对 Tana 也感兴趣，非常推荐加入 Slack community。Tana 的社区氛围特别好，大家都会分享自己搭建的工作流程和各种小技巧。在这里推荐一些我很受启发的内容：

*   Ev Chapman 展示她如何在 Tana 建立从想法捕捉到内容生产的体系的[视频](https://youtu.be/3Jhr_xDPKvI)
*   在 Tana 中应用 Spotify Thoughtful Execution Framework 的[展示视频](https://youtu.be/jyCBPPUpbus)
*   “Rather than product-market fit, we are looking for local memory-storage scheme fit, a system we must build ourselves - essentially the externalization/digital-filization of our passion and curiosity and history and sensitivity - building a second soul” [→](https://twitter.com/gplewis/status/1220045771623395333)
*   Anthony Baker 建立的 All Things Tana [播放列表](https://www.youtube.com/playlist?list=PLsxvf7ga5OJ5dRAypFI3kwz-s08Jp4bZQ)

这是一篇讲述初体验的文章，很多内容没来得及展开，希望以后有机会继续分享关于使用 Tana 的更深入探索。