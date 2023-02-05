---
created: 2023-02-06T04:32:09 (UTC +08:00)
tags: []
source: https://theroamway.com/auto-initialize-random-content/
author: Chris
---

# How to automatically output random block content in Roam - The Roam Way --- Roam中如何自动输出随机方块内容 - The Roam Way

> ## Excerpt
> A step-by-step guide on how to output random block objects from your Roam Research graph onto your daily notes page automatically.

---
December 16, 2022 2022 年 12 月 16 日

In this post, I’ll explain how to pull random blocks instances from your Roam Research graph, and output them automatically every day on your daily notes page (DNP).  
在这篇文章中，我将解释如何从您的 Roam Research 图表中提取随机块实例，并每天在您的每日笔记页面 (DNP) 上自动输出它们。

## **Why we’re building this 我们为什么要建造这个**

I created this blog to highlight some of the cool things I’ve done with Roam and wanted to share with others in the community. I promise it will not _just_ be a Tana feature comparison. That said, when you see something, say something:  
我创建此博客是为了突出我使用 Roam 所做的一些很酷的事情，并希望与社区中的其他人分享。我保证这不仅仅是 Tana 功能比较。也就是说，当您看到某事时，请说：

## **What we’re building: Automatic, random block output in Roam  
我们正在构建的是：Roam 中的自动随机块输出**

Alright, so we have something to aim at. Given we have a collection of _People_ objects in our graph, we want to:  
好吧，所以我们有一些目标。鉴于我们的图中有一组 People 对象，我们希望：

-   Grab just one of those _people_ at random  
    随机抓住其中一个人
-   Output that _person_ \*and\* blocks referencing that person on the daily notes page (DNP)  
    在每日笔记页面 (DNP) 上输出那个人 \* 和 \* 块引用那个人
-   Run this workflow every day automatically, without any additional input once setup  
    每天自动运行此工作流程，设置后无需任何额外输入

## **Prerequisites 先决条件**

Before we dive in and build this thing, you will need to install the [SmartBlocks](https://roamjs.com/extensions/smartblocks) plugin via the Roam Depot plugin manager. A quick diatribe, which you’re free to skip, for those “_this is a hack_” or “_this feature is too important – I need it to be in core to rely on it_” people…  
在我们深入构建这个东西之前，您需要通过 Roam Depot 插件管理器安装 SmartBlocks 插件。一个快速的谩骂，你可以随意跳过，对于那些“这是一个黑客”或“这个功能太重要了——我需要它成为核心来依赖它”的人……

-   **SmartBlocks is one of the ecosystem’s oldest, best-documented, and most well-supported plugins.** At the time of this writing, it has more active users (5,972) than people in the entire Tana slack channel (5,300).  
    SmartBlocks 是生态系统中最古老、文档最齐全、支持最完善的插件之一。在撰写本文时，它的活跃用户 (5,972) 比整个 Tana slack 频道中的用户 (5,300) 还多。
-   **What other system do you hold this “must be included in core” mentality?** Do you only use Apple apps on your iPhone? Microsoft apps in VS Code? I didn’t think so…  
    您持有这种“必须包含在核心”心态的其他系统是什么？您是否只在 iPhone 上使用 Apple 应用程序？ VS Code 中的 Microsoft 应用程序？我不这么认为……
-   **The entire SmartBlock’s repository is open-sourced**. If you wanted, you could fork the entire repo today, make it your own and update it until the end of time.  
    整个 SmartBlock 的存储库都是开源的。如果你愿意，你今天可以 fork 整个 repo，把它变成你自己的并更新它直到时间结束。

## **Get off your soapbox and build, Chris  
放下你的肥皂盒并构建，克里斯**

#### **Visit _The Roam Way_ graph to snag this custom SmartBlock**.  
访问 The Roam Way 图以获取此自定义 SmartBlock。

## Reader Interactions
