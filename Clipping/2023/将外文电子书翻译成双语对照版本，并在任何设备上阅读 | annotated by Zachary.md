> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [readwise.io](https://readwise.io/reader/shared/01grpndpbwvmakn7j1cj0kk3ek/)

> 将 EPUB、MOBI 和 AZW3 格式的电子书翻译为双语版本，并在常见格式之间任意转换，无论电脑、手机、iPad 还是 Kindle 均可阅读。

[![](https://cdn.utgd.net/assets/uploads/2023/01/20230128232504397-1140x570.jpg)](https://cdn.utgd.net/assets/uploads/2023/01/20230128232504397-scaled.jpg)

注意：如果你的电子书解压后遇到 XHTML 文件，由于其结构特殊，可能无法使用对照翻译。我极少买到这类电子书，暂时没有头绪。建议搜索 “XHTML 转 HTML” 并尝试转换格式。

翻译外文文献是一个永恒的需求。早已有人意识到，人类绝大部分有价值的文献是用英文写的；而国内谦虚之士也多承认，我们的学术是翻译学术。机器翻译改变了仰赖翻译家的状况——他们的薪酬少得可怜——惟可惜机器产物毕竟错漏较多，仍需与原文对照阅读，遂挖出了对照翻译的需求：翻译只不过是辅助轮，原文就在手边，随时可供查对。

我曾设计了一套[几乎不会失效的对照翻译方案](https://utgd.net/article/4991)，旋又将其用在[电子书翻译](https://utgd.net/article/6901)上，无奈当时急着读书，姑且满足于 PDF 等主流格式，这基本就把阅读活动限定在桌前或者 iPad 上，且能用的阅读软件也有限。

寒假在家拾掇资料，发现这一年读的几乎全是 PDF，原本买来的外文 EPUB 书籍也给硬生生转换成 PDF，未免生硬。于是趁时间宽松，设计了本文方案，以将 EPUB、MOBI 或 AZW3 等格式的电子书转换为**双语版本的原始格式**，在电脑和 Kindle 上均可阅读，不必总被束于案前。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151520.jpg)在 Kindle 上阅读对照翻译后的电子书 图：我自己

第一步：了解不同电子书格式
-------------

常见的电子书基本可以分为两大类，一种是可以——暂不考虑人为限制——相互转换的，包括 EPUB、MOBI 和 AZW3，以及 Amazon 近些年开始采用的 KFX 格式；另一类则不能，一旦转换就会破坏排版并丢失图文信息，典型代表是 PDF。[1](https://utgd.net/article/10001#fn:1)

PDF 本身太难修改，我一直没有找到合适的对照翻译方案，仅仅在[第八期会员栏目](https://utgd.net/article/9583)中尝试了一页原文、一页中文的折中方式，但仍然处于实验阶段。而前一类电子书则比较容易处理。

第一类电子书本质上都是 HTML 文件，相当于一个或一系列网页，只是打包成单个文件而已。其中只有 EPUB（Electronic Publication）是开放标准，而 MOBI、AZW3 和 KFX 均为 Amazon 的封闭格式，需要破解 DRM（Digital rights management，数字版权管理）后才能修改。我无意在道德层面说什么，也不会在这里推荐破解工具，相信各位有办法妥善处理自己掏钱买的东西。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151529.jpeg)流程示意图

本文假设您已有办法处理 MOBI、AZW3 和 KFX 等封闭格式，那么后续思路就统一了：把各种封闭格式转换为开放的 EPUB 格式，将其修改为双语对照翻译的版本，再根据需要直接阅读，或者转换回诸封闭格式。如果你只在电脑上看书，转换流程就比较简单；若是经常使用 Kindle 或者想用 Kindle App，则需要把制作好的电子书转换一下。我建议使用 Calibre 转换电子书格式，它有详尽的参数设置，丰俭自由。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151537.jpeg)用 Calibre 把各种格式的电子书转换为 EPUB

不过，为讨论收束，本文不谨诸格式内部的版本差异，不会涉及 Calibre 的具体使用，因而在格式转换时无法顾及复杂的排版和动态交互。好在只用 EPUB 的读者，应当不受影响。

第二步：制作双语电子书
-----------

之所以直接对 EPUB 下手，盖因出版物的排版往往已经过深思熟虑，我希望尽可能保留它们。通常，EPUB 主要由 HTML 文档、CSS 文件以及图片附件等组成，其中 CSS 负责排版，HTML 存储文字内容，本文仅修改 HTML 而不动 CSS，因此可以最大程度上**保留原文排版风格，也不影响目录跳转**，同时也不耽误显示图片。

对于读过[《用 Safari 翻译外文电子书和文档》](https://utgd.net/article/6901)读者而言，制作双语电子书的方法可以浓缩成一句话：翻译 EPUB 文件内部的 HTML 文档，保存好，结束。可惜，实际上手时仍要翻越道道藩篱。且看下文。

首先要剖开 EPUB 文件，才能修改其中的 HTML 文档。如果你精通 Calibre，则毋须我多言；但对于一般人， 更直观的方法是直接把 `epub` 后缀名修改为 `zip`，然后把它当作压缩包打开。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151545.jpeg)把 EPUB 后缀名改为 ZIP

部分 EPUB 修改而来的 ZIP 文件可能无法用系统自带工具解压 [2](https://utgd.net/article/10001#fn:2)，一般随便挑一个第三方工具就行了，比如免费的 [The Unarchiver](https://apps.apple.com/hk/app/the-unarchiver/id425424353?l=en&mt=12)。喜欢自己折腾的读者，也可以参考我早年的两篇文章：[《Automator 教程：打造 macOS 上最简单的解压工具》](https://blackwinmin.github.io/posts/Automator-%E6%95%99%E7%A8%8B-%E6%89%93%E9%80%A0-macOS-%E4%B8%8A%E6%9C%80%E7%AE%80%E5%8D%95%E7%9A%84%E8%A7%A3%E5%8E%8B%E5%B7%A5%E5%85%B7/)和[《Automator Folder Action：自动解压》](https://blackwinmin.github.io/posts/Automator-Folder-Action-%E8%87%AA%E5%8A%A8%E8%A7%A3%E5%8E%8B/)。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151551.jpeg)部分 EPUB 修改而来的 ZIP 可能无法直接解压

解压后的文件中就能找到 HTML，一般是每一章都有一个单独的 HTML 文件，修改起来确实有一定的工作量，下一节会提供（半）自动化方法。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151600.jpeg)解压后的 EPUB 电子书内部

好在一般来说也没必要修改所有 HTML 文件，只需翻译正文、参考资料和词条索引——如果你看的话——最多再加上序言。商业书往往只有七八章，学术专著十几章（一个学期的课程量），历史类大部头二三十章，掐头去尾之后，翻译下来大概也只要三五分钟，比起用半年乃至或者一辈子等中译本，这笔买卖诸位比我更会算吧。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151605.jpeg)拟翻译的 HTML 文件

[对照翻译](https://utgd.net/article/6901)后，即可得到一段原文、一段中文的文档，此时页面可能很素，没有出版商或制作者的精心排版，毕竟 CSS 尚未加载，迨修改全部完成、恢复到 EPUB 之后则一切如故。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151612.jpeg)对照翻译后的章节

翻译页面并不会修改 HTML 文件中的原始代码，故需手动存之。现在，右键网页空白处并打开网页检查器（Inspector，快捷键是 `‌⌥Option-⌘Command-I`），查看对照翻译后的源码，拷贝其 HTML 格式。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151618.jpeg)在网页检查器中拷贝对照翻译后的 HTML

保存拷贝后的 HTML 代码即可获得离线的对照翻译文档。可以直接用原生文本编辑器 TextEditor 打开 EPUB 中的 HTML 文件，然后替换为新代码并保存。[3](https://utgd.net/article/10001#fn:3) 第一次使用文本编辑器打开 HTML 时，它可能会把 HTML 识别为富文本而非源代码，您需要在其 Open and Save 设置中勾选 “Display HTML files as HTML code instead of formatted text”，此后便能编辑源码。保存好的文档用浏览器、代码编辑器、DEVONthink 等工具都可以浏览，但我们并不止步于此，还需要继续制作完整的 EPUB 电子书。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151623.jpeg)拷贝后的源码就是对照翻译的章节

翻译并保存所有章节后，便可以全选方才解压出来内容，制作一个压缩包。紧接着，把压缩包的后缀名 `zip` 修改为 `epub`，从而得到打包好的 EPUB 电子书。请留心，是选中所有解压出来的文件并重新压缩，而不是压缩它们所在的文件夹。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151629.jpeg)制作压缩包

制作好的电子书可以在 Calibre 或 Apple Books 中阅读，原文的排版风格均得以保留，目录也可以正常使用，仿佛是官方出版的双语版本。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151634.jpeg)制作完成的 EPUB 就是中英对照翻译版的

如需在 Kindle 或其他不支持 EPUB 的设备中阅读 [4](https://utgd.net/article/10001#fn:4)，则需要多走一步，用 Calibre 等工具转换格式。

第三步：加点自动化（可选）
-------------

整个翻译过程，麻烦之处在于逐个修改 HTML 文档。尽管书籍翻译是一本万利的好买卖，但我也想尽可能节省人力，遂编写了下面的 Keyboard Maestro Macro。该 Macro 用于快速保存翻译后的 HTML 到原文件，免去复制 HTML 和编辑原文件的工夫。

![](https://cdn.utgd.net/assets/uploads/2022/00/minja-0128151639.jpeg)Keyboard Maestro 步骤

[Keyboard Maestro 动作下载](https://github.com/BlackwinMin/Keyboard-Maestro-gallery/tree/master/EPUB%20Translate)

如果希望再快人一步，还可以结合之前的[对照翻译](https://utgd.net/article/4991) Macro，把它们拼在一起运行。

小结
--

从[翻译网页](https://utgd.net/article/4991)、[翻译电子书为 PDF](https://utgd.net/article/6901)，到直接翻译电子书，我不断在各种媒介中应用双语对照翻译。各方案也有太多的改进空间，除了更进一步的自动化，翻译引擎也可以考虑更换为 DeepL（但那样就不能分享给诸位读者了，因为 DeepL API 是要钱的）。

各个方案都布满缝缝补补的痕迹，或是用 Keyboard Maestro 简化部分操作，或是来回手动转换文件格式，和产品级的方案相去甚远，但我却不以为意，不仅因为暂时是人无我有，更因为我的目的不是编写工具，而是读懂更多原著。从上个方案到现在的一年多时间里，我或深或浅地涉猎了几百本外书籍，这大概就是 “Don’t Let Perfect Be the Enemy of Good”（莫让完美与优秀为敌）。

停笔至此，打开 Kindle 看书去。

1.  当然，这些格式也有不同版本，较新的排版乃至动画效果自然无法在较低版本上显示。不过，绝大多数的图文并不受影响，而那些罕见的动画则多见于 Apple Books，拜 Apple 的防盗措施所赐，一般来说你也拿不到电子书文件。 [↩](https://utgd.net/article/10001#fnref1:1)
    
2.  系统解压工具的口碑历来很差，已经到了 “不是它自己生成的文件几乎就不能正常解压” 的地步，或者勉强解压出来也尽是乱码。建议所有使用 macOS 的读者都自备一款第三方解压工具，例如免费的 [The Unarchiver](https://apps.apple.com/hk/app/the-unarchiver/id425424353?l=en&mt=12)。 [↩](https://utgd.net/article/10001#fnref1:2)
    
3.  本文默认您并非编程领域的专业人士，故建议使用文本编辑器。对于有更多背景技能的读者而言，[BBEdit](https://www.barebones.com/products/bbedit/) 等代码编辑器更合适。 [↩](https://utgd.net/article/10001#fnref1:3)
    
4.  Kindle 曾宣布 “支持 EPUB”，事实上只是在通过邮件发送文件时帮你自动转换，如果手动将 EPUB 拷贝到 Kindle，则仍然无法显示。 [↩](https://utgd.net/article/10001#fnref1:4)