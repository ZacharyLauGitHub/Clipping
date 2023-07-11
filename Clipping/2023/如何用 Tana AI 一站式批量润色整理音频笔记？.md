---
created: 2023-07-11T18:07:04 (UTC +08:00)
tags: []
source: https://xiaobot.net/post/458970a7-ff81-44b9-bd91-885d0ed7125d?timestamp=1689063524296
author: 
---

# 如何用 Tana AI 一站式批量润色整理音频笔记？

用好 Tana AI Builder ，充分体验和发挥 AI 工作流的强大性能。

![](https://static.xiaobot.net/file/2023-07-11/502/cf91a37e15725e5380f7d4626b0fc88b.png!post)

痛点
--

作为一个足够懒惰的写作者，我对音频转文本这事儿，有**强烈的刚需**。之前我给你介绍过[用 Tana 处理音频笔记](https://xiaobot.net/post/0d38e93a-d613-4be3-b93f-3ad745e89b0a)的方式。有了移动端的 Tana Capture App，语音输入非常方便。

![](https://static.xiaobot.net/file/2023-07-11/502/b1c0e9df815dcbaa510243147b27b125.png!post)

在 Tana 的 Inbox 里面，你可以批量进行 Transcribe All 操作，把语音转换成文本。

![](https://static.xiaobot.net/file/2023-07-11/502/701f427d59d896907e97dbb4ffd75911.png!post)

不过 Tana 里面转写成文本后，无法直接使用。你看，标点符号不全，有些识别错误与啰唆的成分。有个必不可少的步骤，是**风格化润色改写**。

可惜，在我之前的 Tana 处理流程中，这个「改写」就不那么直观方便了。我先将全部需要润色的语音识别文本都选中，给它添加一个标签 napkin-note ，打开 napkin-note 动态搜索表格视图，过滤掉已经处理过的临时笔记，再用表格列上的 AI 功能对笔记进行批量润色。

![](https://static.xiaobot.net/file/2023-07-11/502/559d0ab95b79fe5b44c4ae0ff0e17f4e.png!post)

设置的时候，你需要填写自己的提示词，这样 Tana AI 才知道你润色的目标和方向。

![](https://static.xiaobot.net/file/2023-07-11/502/a341d1f60b69cdc350cd8ca0696f3e2d.png!post)

我们回过头来，看看现在 Tana 里润色音频笔记的操作步骤：

你需要打开 Inbox，按下按钮批量处理（Transcribe All）音频转换文本，之后给每一个要处理的转换后文本条目打标签，打开对应的视图，然后点击相应的 AI 栏操作。别高兴太早，至此这些笔记依然存在 Inbox 里面，为了不影响将来新笔记加入批量操作，你还需要手动把它们挪到某个指定页面。有时候，一旦几天没有整理 Inbox ，那就会有一系列的操作在等着你…… 唉，太麻烦了。

前些日子，[我开始重度使用 AudioPen 这个工具来把语音转成文本](https://www.bilibili.com/video/BV1UP411i7cp/)。不同于 Tana ，AudioPen 不需要你进行任何复杂的手动操作与设置，打开、录音，然后等润色后文本返回即可。你甚至连 OpenAI API key 都不需要设定。

可惜对我来说，AudioPen 也有两个大问题。

首先所有资料都只存在这款 App 中，你需要将它们分别地复制出来到自己的「第二大脑」。AudioPen 提供了到 Zapier 的连接，所以它支持把新生成的内容同步到 Notion 和 Google Docs 。但是…… 我不用这俩工具当第二大脑啊。况且，不知道是不是因为我 Zapier 操作有误，每次同步，都不会同步最新的笔记，都是从上一条或者上两条开始。好吧，咱干脆手动复制到 Tana 或者 Heptabase。虽然麻烦些，这个我忍了。

另一个问题，我就**很难忍受**了——每次使用 AudioPen ，处理过程都是**串行**的。你输入语音后，它会自动执行转写（Transcribe）与风格化改写 (Rewrite) 操作。这个时候，你**什么也做不了**，甚至不敢退出界面，否则可能导致资料损失——别问我怎么知道的。等 AudioPen 改写好，你终于可以继续录入下一段语音了…… 哎，我刚才想说啥来着？😂

本着「两害相权取其轻」的原则，我这段时间一直凑合着用 AudioPen。痛点一直在，灵感经常在等待风格改写时随风消逝。我只好骗自己说，写每一张卡片之前，停顿并且认真思考一下，有好处。

这无疑就叫做「**自欺欺人**」。

启发
--

这种语音笔记录入的苦恼，一直持续到上周六。那天我参加了在氪空间举办的 Tana 用户线下见面会。主角是 Tana AI 负责人，挪威人侯爽 (Stian Haklev)。

![](https://static.xiaobot.net/file/2023-07-11/502/e0d33d09fcb31821964e1a35d5fcffde.png!post)

我作为嘉宾，也进行了分享。

![](https://static.xiaobot.net/file/2023-07-11/502/1642cee61709283149ed06abafc9be18.png!post)

线下讲座开始之前，我就问侯爽有没有用过 AudioPen？他说**当然没有**，因为自己的工具 Tana 更好用。可我说，要做到完整的从语音到润色，还是需要用户去做一些手动工作的。他说对，现在还不够简便，估计到了秋天，情况能有改观。

![](https://static.xiaobot.net/file/2023-07-11/502/2cdde6c8ceafa09eeeeca8c4436cd391.png!post)

侯爽正式展示的过程中，我突然看到了他的 Inbox 批处理命令，大吃一惊。原来 AI 命令之间早已能这样灵活组合，这不相当于在 Tana 内部嵌套了一个 Keyboard Maestro 吗？！

![](https://static.xiaobot.net/file/2023-07-11/502/975d5cd059599b7ea81102384500d085.png!post)

后来我翻找 Slack ，才发现这个对 Inbox 全方位处理的功能，他一个多月以前就公开分享了。

![](https://static.xiaobot.net/file/2023-07-11/502/13f3c01cd86a7ea25fb8b4ba70d0160a.png!post)

在这个处理流程中，侯爽对三类不同类别的信息进行处理。

首先，是**音频**批量转写。这个主要调用预置命令，只不过他这里用了一个过滤器，把 Inbox 里的全部音频输入找出来。咱们后面的流程会借鉴。

![](https://static.xiaobot.net/file/2023-07-11/502/7feefae6447478e0659babf16ff9a49a.png!post)

其次，对于 **Twitter 条目**，获取内容全文并且加上标题和摘要，还打上标签。

![](https://static.xiaobot.net/file/2023-07-11/502/e3eddee171489b050f6744795717e362.png!post)

最后，对于**网址链接**，读取内容并且进行摘要。

![](https://static.xiaobot.net/file/2023-07-11/502/3f268c747a01c68d707ff630b92f2f60.png!post)

那他是怎么实现 Inbox 全部内容批量处理的呢？

其实也非常简单，就是加了个 Run commands on all children。

![](https://static.xiaobot.net/file/2023-07-11/502/b9bb8bba08338f2f20ebbcc9b93b9d8f.png!post)

我看后感觉醍醐灌顶，立刻明白了我想要达到的一站式批量完成音频转写、润色、标签与归类的功能，该如何利用 Tana AI 来实现。回来后立即加以实践并且顺利完成了这个工作流设置。你或许对音频笔记的录入整理并没有那么强烈的执念，但如能**举一反三**，那你会发现 Tana AI 可以帮助你完成的工作还有很多。

下面我就把这个过程，给你详细演示和讲解一下。

基础
--

我们先来讲讲最基础的操作，就是怎么把一个 Tana 里的普通节点转换成命令节点（command node）。

方法就是用 Cmd + k，调用 convert to command node 功能。

![](https://static.xiaobot.net/file/2023-07-11/502/09c61edd5cb862f71b790c03220914c7.png!post)

之后这里就是填空了。如果你希望填入命令，用 @ 开头，会有一堆已经定义好的 AI 命令（包括你自定义的）出现在列表中，你可以自行选择。

![](https://static.xiaobot.net/file/2023-07-11/502/e32d3f04c02bfb6363f141625ddf3139.png!post)

如果你需要填入参数 (parameter)，那么就用 > 来开头。例如这里如果需要进行节点过滤，就可以选择其中的 Node filter。

![](https://static.xiaobot.net/file/2023-07-11/502/54c5aa2a918267ba53a2d7447742ff29.png!post)

掌握了这个基础操作以后，你就有了乐高基本模块，下面无非就是拼装组合，来自建 Tana AI command 了。

初步
--

咱们先来建立第一个 AI command ，叫做 polish audio input ，用来把已经初步转写的内容，进行润色和风格化处理。下面咱们逐步查看这个命令的设置。

![](https://static.xiaobot.net/file/2023-07-11/502/bdabfa7c46814f35b7cd02f4f2fd7efd.png!post)

首先设置 Temperature，如果你希望 AI 的输出更「老实」一点儿，这个值就尽量小；如果你希望 AI 更活跃有创造力，就设置更高的取值。我在这个例子里设定 0.2 ，希望润色尽量保持原意，不要过度即兴发挥。你在润色过程中，可以根据自己的偏好来修改。

然后这里 Prompt （提示词）是关键点。

![](https://static.xiaobot.net/file/2023-07-11/502/60895e7a50cbb4813de4f9942217ed72.png!post)

你看，我对文本的润色提出了具体要求，不仅包括了处理音频转文字常见的错误、标点符号使用中文版本等明确指令，也给出了我自己语言风格的样例。这里参考的是王佩老师打磨出来的提示词，在此向王佩兄表示感谢。你可以在此基础上，把提示词中的样例替换成自己之前论文或博客文章几处段落，让 AI 熟悉并使用你自己独特的风格。

之后，尤其注意，要使用 ${sys:content} 作为你要转换的输入内容。${sys:content} 是什么东西呢？在 Tana 里面，每一行都是一个「节点」。既然是节点，它本身的内容就可以直接作为转换文本的输入。可是，Tana 里自动转写之后的文本，往往是这样的组织结构：

![](https://static.xiaobot.net/file/2023-07-11/502/43a58f078c9e3363d210d59d0335e048.png!post)

第一行（也就是你当前操作的节点）只是标题，你并不希望润色标题，而是希望润色下面转写文本对应的子节点，也就是下图中标红的部分。

![](https://static.xiaobot.net/file/2023-07-11/502/6685b0d91c2a9208c15a76d0bd43adc9.png!post)

在 Tana 里指定「**当前节点的子节点**内容」，就可以用 ${sys:content} 来指代。

下一个参数，是你调用的模型。

![](https://static.xiaobot.net/file/2023-07-11/502/ccc8f264cf711912853b4b77def96ea2.png!post)

这个不用多解释了，要想实现最好的结果，请选择使用 GPT-4，不过它**慢而且贵**； gpt-3.5-turbo-16k 则比较均衡——价格可以接受，速度快，还能接收更长的输入文本长度（token length）。咱们就先用它吧。

最后的一个选项，是输出位置。你可以选择将润色后的内容输出到当前节点的子节点、兄弟节点或者干脆替换原始内容。

![](https://static.xiaobot.net/file/2023-07-11/502/741246ab97a07b6d2fe748775eade456.png!post)

这里咱们选择当前节点的子节点作为输出位置，也就是和原本的转写文本并列。

![](https://static.xiaobot.net/file/2023-07-11/502/161f0e1b33758a1030f857ccc86ed6fd.png!post)

这样一来，单独的 polish audio input 命令就算是建构（build）完毕了。它将会成为我们整体 Inbox 整理工作流中的一个组成单元。

下面我们来尝试新建一个命令，对语音笔记转写、润色、打标签和挪动到合适位置，都**一站式完成**。

组合
--

我们把这个命令，叫做 polish inbox audio ，它的设置如下。

![](https://static.xiaobot.net/file/2023-07-11/502/4439f05bdf3150488baf3470c3cc9517.png!post)

下面咱们**一步步解释**。

首先是做一个**节点过滤器**，也就是什么样特征的节点会被当成语音节点进行处理。在 Tana 的 Inbox 里面，这些语音录入节点都是这样的：

![](https://static.xiaobot.net/file/2023-07-11/502/a0333ba18d679cbda29cd0905202fb0a.png!post)

所以，这里你只需要填写 Audio captured 作为过滤条件就好。你的 Inbox 里，还有很多的其他内容，例如链接和图片等，你不希望 Tana 对它们做同样的处理流程。

![](https://static.xiaobot.net/file/2023-07-11/502/b35f57a625daa577cdb4a2580f66d7e2.png!post)

第二步比较直接，调用 Tana AI 里面的预置命令（叫做 Transcribe audio）把**音频转写文本**。咱们照单全收，不需要对它的设置做任何修改。

![](https://static.xiaobot.net/file/2023-07-11/502/15802bc05c1f94b9fdd2847434d1306f.png!post)

第三步，**润色**。因为刚才建立了 polish audio input ，你只需要在这里引用它。

![](https://static.xiaobot.net/file/2023-07-11/502/ba1e4490b0b80d6d549082a491301f74.png!post)

从语音到润色后文字的转换完成了。下面该**打标签**了。我定义所有的语音输入笔记为一个「临时笔记」（fleeting-note），都需要给它打上这个标签。

![](https://static.xiaobot.net/file/2023-07-11/502/1225dacc73417fea0919015ec418a225.png!post)

标签打好，咱们还要求把它**挪动到语音录入的日期**。

![](https://static.xiaobot.net/file/2023-07-11/502/0d96c1a1a5955db67eb5424d8d4e5a6a.png!post)

你可以看到这里还有其他挪动位置的可选项，例如移动到今天（Current day page），移动到当前工作区的 Library ，或者移动到 Inbox 等。

![](https://static.xiaobot.net/file/2023-07-11/502/ae46182bec89e8fb700dac675be12dc3.png!post)

我比较喜欢移动到创建日期，这样一些语音录入的日记就可以方便按照时间顺序查看了。

不过，现在你只能在某个节点上单独执行这个 polish inbox audio 命令。如果你有很多的音频输入，这种手动单独操作依然很麻烦。所以，下面咱们需要再定义一个 AI Command ，批量执行该操作。

批处理
---

这个 AI command 叫做 Arrange Inbox ，内容非常简单。你只需要指定，它在当前节点的**每一个子节点上**执行 polish inbox audio 命令，就完事儿了。

![](https://static.xiaobot.net/file/2023-07-11/502/7f842a01570a1dbbb4789de8000ca225.png!post)

更妙的是，如果你不想每次都用 Cmd + k 呼叫 Arrange Inbox 命令，则可以让它变成一个按钮出现在 Inbox 页面上。为了达成这一点，你需要在 Inbox 里面进行一下设定。Cmd + K ，然后找到并且执行 Configure node。

![](https://static.xiaobot.net/file/2023-07-11/502/0a94f3c5276c2bda216423458bc58f16.png!post)

然后你只需要把刚刚定义好的命令 Arrange Inbox 填写到 Commands 栏目下面即可。

![](https://static.xiaobot.net/file/2023-07-11/502/60fae3f7678f99d97e45927cd4cf58a7.png!post)

看到这里，你可能会很疑惑 —— 既然定义了 3 个函数，之间都是嵌套关系，那咱们只在 Inbox 页面上呼叫一个函数，然后把上面所有内容都写在这一个函数里，岂不是更直观和方便？干嘛调用来调用去的？

这里的原因，跟咱们一直介绍的《卡片笔记写作法》一样，关键在于**拼装和复用**。今天你在 Inbox 处理上需要润色功能，确实写成一个整体命令更加直观。但明天可能你拿到了之前什么地方语音转换后的文本，也需要润色。到那时，如果你有单独的 polish audio input，就可以直接拿来用，而不必再重新拆分或者定义了。再说了，把所有功能都写在一起，不利于发生问题的时候进行查错。所以还是「高内聚、低耦合」单独定义命令功能，然后组装起来发挥威力更为合适。

效果
--

下面咱们来尝试执行。

可以看到，Arrange Inbox 作为一个按钮，出现在了 Inbox 上面。一旦点击，所有的音频就会开始执行预先定义的一系列操作。

![](https://static.xiaobot.net/file/2023-07-11/502/9c14aed20b936ad80968e23492bc30cb.png!post)

下图是执行后的效果。为了保护隐私，我做了一些模糊化处理。不过你可以清楚看到所有的条目都打上了咱们设置的标签 fleeting-note，并且挪动到了创建时间对应的日期页面下面。

![](https://static.xiaobot.net/file/2023-07-11/502/2d9e11b06f46bc671bb0ba5cab3bed65.png!post)

点开查看其中第二条笔记，你可以看到音频前后分别进行了转写和风格化润色。你可以对比一下单纯语音转文字版和最终整理出的风格化文本之间的区别。中文标点符号正确添加，而且转折词的使用等细节也都经过了调整处理。

![](https://static.xiaobot.net/file/2023-07-11/502/ef73b5e6e2c96c6ecac179c0b2ed7394.png!post)

这下，你再也不用面对内容庞杂的 Tana 收件箱五味杂陈，甚至是烦恼不堪了。你感觉如何呢？

小结
--

这篇文章里咱们用了 3 个 AI command，完成了一键批量音频转写、润色、打标签和归类操作。不管你的 Inbox 里面只有一条语音笔记还是有 100 条，都只需要按一下按钮就可以去歇着等结果。对于懒人来说，这显著降低了咱们处理临时笔记输入和整理的成本。我的感触是，它带来的绝不仅仅是时间的节省，而是输入量的爆发。

这件事更给我一个启示 —— 见识真的非常重要。如果没有看到侯爽演示出来的设置，我根本就不可能想到 Tana 可以像 Keyboard Maestro 一样轻易组织一系列的 AI command，在指定页面批量运行并完成复杂的操作流程。从这点来说，线下活动确实比线上会议更加高效，不仅因为交流密度更高，而且可以快速消除很多细碎的理解障碍。看来，以后咱们还要多参加一些线下活动和会议。虽然路途辛苦，但是值得。

![](https://static.xiaobot.net/file/2023-07-11/502/027727bf9d4b1b653fee2628dcc38d66.png!post)

侯爽特意给我解释了 Tana AI builder 的命名初衷。最终的目标，是 Tana 里面的 AI 将变得非常好用，普通用户无需和这些需要一定门槛的设定打交道，也能完成高效的工作和研究。但是目前 Tana 还做不到那么简易，却可以释放这些能力，让营造者 (builder) 充分体验和发挥 AI 的强大性能。

希望你能够举一反三，把今天讲解展示的内容用在自己的笔记系统里，营造 (build) 出更多的个性化应用，解决自己的实际需求，甚至分享出来帮助其他用户获得更多的收益。

祝 AI 笔记愉快！

如果你觉得本文有用，请点击**有启发**按钮。

本专栏已经开通合伙人计划，**邀请朋友订阅有 30% 收益**。欢迎你分享知识，一起成长。

延伸阅读
----

*   [GPT-3 加持的语音输入文字新流程](https://xiaobot.net/post/14a80c28-d0b6-4428-98a6-a592c49f4cd4)
    
*   [如何用语音记临时笔记？](https://mp.weixin.qq.com/s/KoAEGvvLrIX5mEpFsPZbcQ)
    
*   [如何用 AI 练英语口语？](https://mp.weixin.qq.com/s/ggubaZk2HPHOd21UDS94kg)
    
*   [如何用人工智能帮你剪视频？](https://mp.weixin.qq.com/s/JvwkkSBYHAw7PdLc_qELCA)
    
*   [如何用人工智能免费帮你改英文？](https://mp.weixin.qq.com/s/Eam1C8SdoMgB7VNt8YnmuQ)
