---
created: 2023-02-12T16:31:38 (UTC +08:00)
tags: []
source: https://mp.weixin.qq.com/s/KKqWt47wG7EwNwq5xll4-A
author: Vaayne
---

# NotionBoy v1.6.0 更新，全文剪藏，ChatGPT 等多项更新

> NotionBoy v1.6.0 更新，支持剪藏全文TL;DR新年的一大波更新:• 支持保存网页全文的功能•

NotionBoy v1.6.0 更新，支持剪藏全文
==========================

TL;DR
-----

新年的一大波更新:

*   支持保存网页全文的功能
    
*   极大的优化了 ChatGPT 的使用体验
    
*   优化了 Z-Library 的搜索，支持按照文件格式过滤，并且优化了提示信息
    
*   移除保存网页为图片或者 PDF 的功能
    

更新详情
----

### 剪藏文章全文

为了提高开发进度，以前我们采用截图或 PDF 的方式保存网页，但是实际使用效果不佳，而且收藏的网页也不容易搜索，因此我们增加了收藏全文的功能，目前测试结果表明，主流网站均可适配。

**使用方式：**只需在保存 URL 时加上 `#全文` 标签即可，例如`htps://mp.weixin.qq.com/s/SicYTABGjXcJJTqYEbL5dQ #全文`

Notion 中的效果

![](https://mmbiz.qpic.cn/mmbiz_jpg/TDFUU0xqbxKzEsSQUaGW29vM7H85feV1uSOmT6oRQGQ47n67DDgN6HmdVU7G3Cib9pKdokfa7hc1KhaMgj5y3sg/640?wx_fmt=jpeg)

  

**存在的问题：**

1. 如果文章中的图片开启了防盗链，在 Notion 网页端会看不到图片，Notion 客户端可以看到图片，但是图片的尺寸不对，说的就是你「微信公众号」的文章。解决方案也有，就是自建图床，但是这样就需要付费使用，有需要的请联系我，我可以单独为你开通。
    
2. 没有适配所有的网站，如果遇到不能正常获取全文的，请联系我，我会尽快修复
    

另外，提供 Readability 网页用于测试是否可以获取网页全文

`https://readability.theboys.tech/`

### 移除保存网页为截图或者 PDF 的功能

由于其有限的使用和不稳定的功能，我们已经决定移除它。

### 优化 ChatGPT

1.  1. 优化 API 请求的参数，提供默认提示，ChatGPT 返回的结果更加准确。
    
2.  2. 支持保存聊天历史，以便可以持续对话。
    

1.  1. 默认情况下，聊天历史有效期为 10 分钟，这意味着如果 10 分钟内没有交互，聊天将会重置。
    

4.  3. 优化保存聊天记录到 Notion 的方式，会保存整个聊天记录到一个 Notion 页面，而不是一个问题一个页面。开始信息回话，会保存到新的页面
    

下面是一些使用示例

![](https://mmbiz.qpic.cn/mmbiz_png/TDFUU0xqbxKzEsSQUaGW29vM7H85feV15PCSXnyxX4dgsWfpgeRpaUFAHNZTBPWLCCMG62UH6HC4XQD8kQme8w/640?wx_fmt=png)

  

### Z-Library 搜索支持按照文件格式过滤

使用 zlib 进行查询的时候，加上 `#ext` 的标签，例如 `#pdf #mobi #epub` 可以按照文件格式进行过滤

例如： `/zlib 如何阅读一本书 #epub` 就只会查询 `epub` 格式的书籍

这里使用 Telegram 演示，微信功能一样

![](https://mmbiz.qpic.cn/mmbiz_jpg/TDFUU0xqbxKzEsSQUaGW29vM7H85feV1rKdj4MKWDoDjWw53wocM03qYKZUJoc2PBuk0JCbVmEadWK9IslfViag/640?wx_fmt=jpeg)

  

Bounes
------

### NotionAI Chrome

如果你有 NotionAI 的资格，可以使用我开发的这个扩展，可以在任何网页使用 NotionAI 了，而不只是在 Notion 内使用。

💡 这个扩展还在开发，并未上架 Chrome 商店，所以只能先本地导入

1.  1. 扩展安装，进入 GitHub 页面 https://github.com/Vaayne/NotionAI，下载项目，然后进入 Chrome 打开 开发者模式，选择 `notionai-chrome`[1] 目录，就可以加载成功 2. 新打开一个页面，在任意的输入框内选中一段文字，并右键，就会出现各种 NotionAI 支持的功能了
    
2.  ![](https://mmbiz.qpic.cn/mmbiz_png/TDFUU0xqbxKzEsSQUaGW29vM7H85feV1dZbOv6e2AU4S5ZN4eUJQTbs4Yv0GZstnOXElWeBKfib1YMloicvwZfzQ/640?wx_fmt=png)
    
      
    

### Poe From Quora

不知是否了解 Quora？它可以简单地被描述为国外的知乎，有一些底线。

Poe 是 Quora 最近发布的产品，是一款对话应用（目前仅支持 iOS，Android 版本即将推出）。

它的优势在于集成了多种 AI 模型，包括 OpenAI 的 ChatGPT 和 Anthropic 家的 Claude（前几天 Google 投资的，可能未来会被集成到 Google 的 AI 中）。

可以进入 AppStroe 下载，需要梯子和手机号注册！

官网：https://poe.com/ 

发布页面：https://quorablog.quora.com/Poe-1

![](https://mmbiz.qpic.cn/mmbiz_png/TDFUU0xqbxKzEsSQUaGW29vM7H85feV1eHzSDHq1lWibw8lwOg92XSn9VwQr2huaPEAwShGZicySuQf3hfcLsQXw/640?wx_fmt=png)
