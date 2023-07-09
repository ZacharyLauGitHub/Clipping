> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [mp.weixin.qq.com](https://mp.weixin.qq.com/s/K_csi1oWDv5tEaeeKSlvwA)

> 硬核干货：你不知道的一些高级使用技巧！

代码解释器
=====

Code Interpreter (Alpha) 是一个实验性的 ChatGPT 模型，具备以下功能（如何开启，请参考 [ChatGPT 重大更新：代码解释器即将推出，GPT-4 API 全面开放！](http://mp.weixin.qq.com/s?__biz=MzIzNjE2NTI3NQ==&mid=2247487151&idx=1&sn=ae632d47fc0c89dd2d4bf4c4f4129444&chksm=e8dd4f5bdfaac64d1198ccfc06f509078f4ba387a21c09c66d133f89cc905132c0ad89830efb&scene=21#wechat_redirect)）：

*   使用 Python 进行编程：模型内置一个 Python 解释器，可以运行 Python 代码。
    
*   处理上传和下载：支持将文件上传到当前对话工作区，并下载工作结果。
    
*   沙箱化执行环境：解释器插件在一个受保护的执行环境中运行，包括防火墙和临时磁盘空间。
    
*   持久会话：代码由解释器插件在一个持久的会话中进行评估，会话在聊天对话的持续时间内保持活动状态，可通过多次调用构建（超时销毁）。
    
*   使用场景：通过代码解释器，用户可以解决数学问题（定量和定性）、进行数据分析和可视化，以及在不同文件格式之间进行转换。
    
*   新手建议多多尝试，可以挖掘出更多有趣的功能。
    

> 😅 会话超时
> 
> 注意：如果会话超时，会出现以下提示信息。点击下载资源则会提示会话已过期。
> 
> > This code interpreter (beta) chat has timed out. You may continue the conversation, but previous files, links, and code blocks below may not work as expected.
> 
> 此代码解释器（测试版）聊天已超时。您可以继续对话，但之前的文件、链接和下面的代码块可能无法按预期工作。
> 
> > Code interpreter session expired
> 
> 代码解释器会话已过期

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzF9q58spiaWJLmR4picGDhGnsogHgicynRG5yuLtrthUynee4qGZQUjvPQ/640?wx_fmt=png)

可视化
===

代码解释其实就是内置的一个小型 Python 解释器，所以它可以调用诸多 Python 生态库。比如：Matplotlib[1] 可以生成各种图表，qrocde[2] 可以生成二维码，PIL[3] 可以编辑图片，Graphviz[4] 可以生成流程图等。

在数据分析处理方面 Matplotlib 属于老大哥了，它是一个 Python 的 2D 绘图库，它能以高质量的图像生成多种出版物质量级别的图形。它支持各种平台，提供了许多图形库工具。以下是一些常见的 Matplotlib 图形以及它们的适用场景：

*   折线图 (Line Plot): 折线图非常适合展示数据随时间或连续值的变化趋势。例如，股票价格的变化、天气变化等。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzXLXC44gQJ8zAtia9RadTibZkrQqy1m3S0Ijib8eBWrIVCMgcJlMNJPZnQ/640?wx_fmt=png)  
    
*   柱状图 (Bar Chart): 当你需要比较多个类别的数据时，柱状图是一个很好的选择。例如，比较多个城市的人口数量。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzTO2ibuhN66DeNMtNCnO8Rw6XrmaDicA0vV7IGk7nH3z3M4R5mn99x8ibg/640?wx_fmt=png)  
    
*   水平柱状图 (Horizontal Bar Chart): 与普通的柱状图类似，只不过它是水平的。它适用于类别标签过长或者类别数量较多的情况。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzAAxbxIufRkGajWZB7D0Vf1YibTJo8D98XVoxTeCIzUDPHEJcSkdicyTw/640?wx_fmt=png)
    
*   堆积柱状图 (Stacked Bar Chart): 堆积柱状图可以显示每个类别的总量以及每个子类别的比例，例如，公司每季度的总销售额以及各产品销售额的比例。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtzf6EssyiaCGpPRDz6GfiaibG7x7p7LTeUBic7xkznowCf1zzAh7OoBkkFPA/640?wx_fmt=png)  
    
*   饼图 (Pie Chart): 饼图通常用于表示各部分占总体的比例，如公司收入的来源比例。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzrcVZUJSycIpRBIY4DanEjXlb3aS28S43yrZjGBbP3IuJTYLXtrCicxA/640?wx_fmt=png)  
    
*   直方图 (Histogram): 直方图适合显示一组数据的分布情况，如学生成绩的分布。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzrZUXGmAU5Vva19sia5Zx8bNx8UKBic2aEgvQeZDmEGKUwKGiaQhKWhBHA/640?wx_fmt=png)  
    
*   散点图 (Scatter Plot): 散点图常用于显示两个变量之间的关系，如身高与体重的关系。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz7aCrpWps0qDMiaA38XepYXSha5icjhL7siaG4TiabDARicZDU5MGyyAgYhw/640?wx_fmt=png)  
    
*   箱线图 (Box Plot): 箱线图（又名盒髭图）用于展示一组数据的五数概括（最小值、第一四分位数、中位数、第三四分位数和最大值）。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzQF2Kx8O01oB16F5AJmKXOrvLRtFMXib4ia5Yo7T6yqDYS75FxaKJahbg/640?wx_fmt=png)  
    
*   小提琴图 (Violin Plot): 小提琴图是箱线图与核密度估计图的结合，不仅可以展示数据的分布情况，还可以展示数据的概率密度。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz0Gvz7dgASuA5qDmicib2cgDd5hutzcCGRoCiaZRV7GPickwlvYkHAe0gyg/640?wx_fmt=png)  
    
*   等高线图 (Contour Plot): 等高线图通常用于表示三维数据，其中两个维度在平面上，第三个维度由等高线表示。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzmiamrSKfFjOTNp6KQ4seBhSjqnMG099wO9Uk2Yek9A6KNFLMeIsaIXg/640?wx_fmt=png)  
    
*   热图 (Heatmap): 热图通常用于表示数据的相关性或数据的热度分布，如网页的热力图。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzRTtTfpHHlp08q44eiaXyTRRRicibMyoHkwN2BhALWIrnfib5V7rNjRfmvA/640?wx_fmt=png)  
    
*   气泡图 (Bubble Chart): 气泡图是散点图的扩展，每个点的大小和颜色都可以变化，以表示更多维度的数据。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz3zgia8DhAYib3Z13HYsKKD2Evp7S3GZgzh2A2tRgv2CaRKwQMOKArr1w/640?wx_fmt=png)  
    
*   雷达图 (Radar Chart): 雷达图常用于显示多变量的数据，特别是比较几个对象在不同特性上的表现。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz7nZ49yWiasJoYp0XB0LicfGAZZTKAS6gibHJO2MHvQuEfhicMLZTDeRQjg/640?wx_fmt=png)  
    
*   3D 图 (Three-Dimensional Plot): 3D 图可用于显示三个数值变量的关系，例如，x, y, z 三个维度的关系图。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzA3EYbevQTtOCQ2ZXjP50ruhhJxxqZ92bsgWdPvdoHHxxAuSoTmATTA/640?wx_fmt=png)  
    
*   面积图 (Area Plot): 面积图非常适合展示随时间变化的数量和表现出不同类别之间的比较。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtzfic7443tkLWXMnrutSicXjHuevWagzK6kDKBtRC3MiaL95vGU44n5pEjQ/640?wx_fmt=png)  
    
*   误差条图 (Error Bar Plot): 误差条图用于显示数值的不确定性，例如在实验数据中显示标准偏差或标准误差。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzVAn0Rapdc1MWda781SdbrHVPPTIT3NMSBuAmMqsfIVGicGFCofegAtg/640?wx_fmt=png)  
    
*   填充图 (Fill Between Plot): 填充图可以清楚地显示两个数据系列之间的差异，或者表示同一系列中的不确定性。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzqkYOyauDYI9zEQL0XKxerFdyCbWF5eyuxPqiaQiaoSQIvOLQmxmBp7BQ/640?wx_fmt=png)  
    
*   阶梯图 (Step Plot): 阶梯图非常适合表示离散的、不连续的事件，或者表示阈值。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzsE9TOFsNMx1wZZj4JVfVgH4pwWeDaOUrW7HOhTibRm67BHeATrjuq1Q/640?wx_fmt=png)  
    
*   复合图 (Composite Plot): 复合图是多种图形的组合，如在同一个图形上显示折线图和柱状图，适用于需要同时展示多个相关指标的情况。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzovsKspP9VjkeofdKHkeQ50jg1pDKjnAWv1TqicDHXtaHbx7FdoBL6icA/640?wx_fmt=png)  
    
*   蜡烛图 (Candlestick Chart): 蜡烛图在金融分析中非常常见，用于表示股票、期权等的开盘价、收盘价、最高价和最低价。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtznYeib6dPRFYRKrtH8eeMd8g64HiaXUjlI5uzAkpS7PxCCln36KvlhfeA/640?wx_fmt=png)  
    
*   词云图 (Word Cloud): 词云图通常用于文本数据，展示文本数据中词频最高的词。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtzia6IJWWo4BsFjfahz4hpo3SuDsrBko4oovZyOctpib5JbhkyHed5KrkA/640?wx_fmt=png)  
    
*   极坐标图 (Polar Plot): 极坐标图用于表示极坐标系下的数据，如雷达图、风玫瑰图等。
    
    ![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzibLneJfDrZJg3IApqKxMQfqzqAodHALQwaUWuOM9RaiawoDa8zADicSSA/640?wx_fmt=png)  
    

这些图形的选择应根据你的数据特性和你想要表达的信息来决定。在实际使用时，我们可能还需要根据具体需求调整图形的参数，以便更好地表达和解释数据。想要了解更多请查看 Matplotlib 文档 [5]。

使用案例
====

要想体验数据可视化，数据必不可少，大家可以在这个网站（Kaggle[6] 是世界上最大的数据科学社区，拥有强大的工具和资源，可帮助你实现数据科学目标）下载自己喜欢的数据，然后进行分析总结。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzYzt4E2KDjGPWuZY8g8fS9BUxXiapV9ibfPDDhgOBk9aJjUiaHLib5UpibicA/640?wx_fmt=png)

总结并建议
-----

> 📌 Prompt
> 
> *   请你对 prompts.csv 文件进行分析总结，选择一些最佳图表用来展示分析结果，并给出一份编写 prompt 最佳指南。
>     
> *   使用词云统计高频词
>     
> *   ...
>     

从 f/awesome-chatgpt-prompts[7] 下载 `prompts.csv` 文件，上传后依次提问以上 prompt。可以得出以下编写 prompt 的最佳实践：

*   明确指出你需要什么：使用词汇如 `want`、`need`、`help`、`tell` 来明确地指出你需要 ChatGPT 做什么。
    
*   指定角色：像 `act as a ...` 这样的语句可以帮助 ChatGPT 理解你希望它扮演的角色。
    
*   简洁清晰：尽量让你的提示简短而清晰，大部分的提示长度在 200 个字符以下。
    
*   特定的行动：如果可能，使用具体的动词，如 `use`、`create`、`design`、`play` 等，来明确你希望 ChatGPT 执行的具体动作。
    

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzkicVPu7NxS1hUzsYzO5u7jM5ibkqOia4J4f5tJLA5S6LpKmZgwXTKmXSA/640?wx_fmt=png)

视频处理
----

> 📌 Prompt
> 
> *   转换为 mp4 格式，并显示播放（上传视频文件：test.mov）
>     
> *   显示视频总时长，截取第 1/10 秒作为图片显示
>     
> *   显示图片
>     
> *   ...
>     

上传 test.mov 视频文件，依次输入以上 prompt，可以成功将其转换为 .mp4 格式，或者截取视频的某一帧作为图片输出。在转换为 .gif 动图时，因受到临时内存限制，导致任务失败。所以可以得出结论，代码解释器并不适合处理过大内存占用的任务。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzXgYOevd2TicVdLTfkYIMB7iamqfPqxMicfCsDzfic9Uibj0JcYOjJNeNLdQ/640?wx_fmt=png)

图片处理
----

> 📌 Promot
> 
> *   显示原图尺寸，居中裁剪出最大方形，并显示图片
>     
> *   以 576x576 作为原图的滑动窗口，每次移动图片宽度的 1/50，将其制作为循环播放的 gif。
>     
> *   转换为黑白色，并显示
>     
> *   提取原图色系到调色板，并显示颜色值和调色板图片
>     
> *   将原图转换为 JPG 格式提供下载链接，并显示原图
>     
> *   ...
>     

上传图片，依次输入以上 prompt。不但可以获取到图片信息，还可以对图片进行编辑操作（裁剪，制作 gif，颜色处理，格式转换等）。需要注意的是：会话过期需要重新上传图片，转换格式显示图片会受到内存限制。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz9mX2iaUnxr2ia36rcagj4ibzrK2MbEX2j09IR82mYPHBnuGyh1n9nOic7A/640?wx_fmt=png)_原始图像（Stable Diffusion @lencx）_

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtznHXibSVdnfM06Xib4skL200HR4biayUOJS8WwTyUUwzT94hn2p68HxaTg/640?wx_fmt=png)_原始图像灰度处理_

![](https://mmbiz.qpic.cn/mmbiz_gif/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtztc5m5BmmvibhAPoVTdVTicVvhsqDt3JSaKiax3V01n77GicW41U3nibmthg/640?wx_fmt=gif) _Code Interpreter 使用滑动窗口方式将图片输出为 GIF 动图_

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzicX1ANic6zqkOkfP4LncDO7WoNJukceInDzo7RlIicicfI6xXgCUia4qGUg/640?wx_fmt=png)

PDF 处理
------

> 📌 Prompt
> 
> *   文件主要讲了哪些内容
>     
> *   分析全部内容，并尝试提取局部图作为辅助说明
>     
> *   将前 3 页 pdf 文件合并成一张图片显示
>     
> *   ...
>     

上传 PDF 文件，依次输入以上 prompt。GPT 可以帮你分析文本内容，但是当要提取一些局部图片时，却失败了（复杂度偏高）。但是用来处理多页 PDF 合并为一张图片还不错。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzZ18fYrdOTfmic1DkY50icCQZq3DfbLJEbysvxDahl96BlthDt84AWY1g/640?wx_fmt=png)

数据分析
----

> 📌 Prompt
> 
> *   这份数据主要内容是什么
>     
> *   全球人口密度可视化
>     
> *   前 10 个国家人口增长趋势图
>     
> *   ...
>     

下载数据集（World Population by Country[8]），上传 `countries-table.csv` 文件后依次提问以上 prompt，可以从不同维度去分析可视化数据。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz5iccPwbib2vrDPcFz03uCf55JgPaxDzxCGQzpLKvpdOianEHULTRAVJwg/640?wx_fmt=png)

生成二维码
-----

> 📌 Prompt
> 
> *   请将 https://github.com/lencx URL 生成二维码并显示
>     
> *   使用以下代码来修改：
>     
>     ```
>     from qrcode.image.styles.colormasks import RadialGradiantColorMask
>     qr.make_image(image_factory=StyledPilImage, color_mask=RadialGradiantColorMask())
>     
>     
>     ```
>     

依次输入以上 prompt 可以生成二维码，在修改二维码风格时，如果只给方法名并不能很好的处理。这时你需要查看 qrcode 文档 [9]，给出代码示例，来让 GPT 继续工作（代码示例可以在一定程度上修复返回结果）。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzcQvBGSqIyh9RbAB2ax5H0faOK1OVQzSucMAwkOibkSUX3ibGxI2lUYtA/640?wx_fmt=png)

流程图
---

> 📌 Prompt
> 
> *   使用一种合适的可视化方式来介绍一下计算机工作的原理
>     
> *   画个流程图
>     
> *   浏览器工作原理可视化
>     
> *   换一种图表，使其结构更加合理，并补充一些细节（比如：DNS 如何解析，如何建立链接，页面如何渲染等等）
>     
> *   显示 png
>     
> *   你可以尝试使用 Image 来显示图片：
>     
>     ```
>     from PIL import Image
>     img = Image.open('/mnt/data/browser_work_process.png')
>     img.show()
>     
>     
>     ```
>     
> *   ...
>     

你可以尝试依次输入以上提示。在画流程图时，有时它并不能准确返回你想要的结果，需要你不断地给出提示，甚至用代码提示来辅助它更好的完成工作。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzibNwxyTMb7M4mOUkibwYmrbiaCyJug6yBwjlYibkw3eaQXglvcdXSKzK6Q/640?wx_fmt=png)_浏览器工作原理_

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzHIviajLAMTYhvLQYSbWk0ZsoDe6bA0YOrAgNb1AcvwQdHTbGeMVqcLQ/640?wx_fmt=png)

视觉创意
----

> 📌 Prompt
> 
> *   请向我展示一些你可以用 Code Interpreter 做的最具创意，充满未知复杂性，数学艺术之美的东西。它是这个世界上从未见过的，而不仅仅是现有工作的变体。比如：Chaos Game，Cellular automata 或 Fractal，虽然很有创意，但却已存在。
>     
> *   这个并不具有创意，继续探索，比如 3D，透视效果等等。
>     
> *   换个方向，继续探索。
>     
> *   这些都不符合，需要艺术的美感，比如分形那样。
>     
> *   ...
>     

有时候我们并没有固定的方向，也可以借助 Code Interpreter 来帮助我们激发一些灵感。因为它同时兼具算法，可视化，编程等多重能力，所以相比于我们普通人，更具有一些创造力。但是输出的效果不一定很理想，需要你不断地去提示它，或者切换方向进行探索。

![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7Rtz0Aspe9hkyA7Y3Gbj4ic3Q7Wj8CYbP7octFkbWxAWj3rdhOKz1XcAurg/640?wx_fmt=png)_一颗渐变分形树_

_![](https://mmbiz.qpic.cn/mmbiz_png/90Kxd0FAJJd1sb0ReibzyXAyHlJ4K7RtzIcWHvF9MC2AQLonkko10fr07f1wN36UZVc1QACT7774FKPYZlRXdTA/640?wx_fmt=png)_

总结
==

*   代码解释器并不能一次性帮你解决所有问题，向你返回满意的结果。虽然它也会在运行期间会进行自我纠正，但当它失败时，需要你进行一些适当引导提示。
    
*   当它表示因为环境受限不能执行某些操作时，你可以尝试为它提供一些替代方案或者步骤来指导它（需要一定的 Python 编程基础）。
    
*   代码解释器的文件上传功能及图片显示与 ChatGPT 原本的对话能力相结合，进一步放大了 GPT-4 的能力。比如分析数据，文件格式转换，设想验证等等。
    
*   代码解释器的会话是有时效性的，开辟的临时内存在超时后会被销毁。所以它输出的下载资源链接请提前下载到本地进行备份，避免丢失。
    
*   Python 解释器开辟的临时内存空间有限，如果执行复杂耗时任务大概率会失败。它更适合做数据处理和数据分析，文件格式转换这种任务可能会因为源文件过大，爆掉内存导致任务失败。
    

**注意：以上聊天记录长图导出均使用 ChatGPT 桌面应用进行操作，十分方便（了解更多：**[**ChatGPT 桌面应用 v1.0.0 发布啦！**](http://mp.weixin.qq.com/s?__biz=MzIzNjE2NTI3NQ==&mid=2247486680&idx=1&sn=2bc9c16fc59fe9e01492468051554de8&chksm=e8dd4d2cdfaac43a632d1a2fee71e7f74b4f36a927ed70a13135d0ca58e872fc70a29eda6ef5&scene=21#wechat_redirect)**）。**  

> 如果这篇文章对你有帮助，欢迎分享给更多的朋友，公众号发送 `ci` 可以进 Code Interpreter 交流群。

### References

[1]

Matplotlib: _https://matplotlib.org_

[2]

qrocde: _https://github.com/lincolnloop/python-qrcode_

[3]

PIL: _https://pillow.readthedocs.io_

[4]

Graphviz: _https://github.com/xflr6/graphviz_

[5]

Matplotlib 文档: _https://matplotlib.org/stable/plot_types/index.html_

[6]

Kaggle: _https://www.kaggle.com_

[7]

f/awesome-chatgpt-prompts: _https://github.com/f/awesome-chatgpt-prompts/blob/main/prompts.csv_

[8]

World Population by Country: _https://www.kaggle.com/datasets/rajkumarpandey02/2023-world-population-by-country_

[9]

qrcode 文档: _https://github.com/lincolnloop/python-qrcode#styled-image_