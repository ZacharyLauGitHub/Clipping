> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [theroamway.com](https://theroamway.com/auto-initialize-random-content/)

> A step-by-step guide on how to output random block objects from your Roam Research graph onto your da......

December 16, 2022

In this post, I’ll explain how to pull random blocks instances from your Roam Research graph, and output them automatically every day on your daily notes page (DNP).

**Why we’re building this**
---------------------------

I created this blog to highlight some of the cool things I’ve done with Roam and wanted to share with others in the community. I promise it will not _just_ be a Tana feature comparison. That said, when you see something, say something:

> Tana will 100% eat Roam's and Notion's lunch. (Also replaces Readwise and Airtable for me to some extent.)
> 
> Such an incredible product. Truly feels like the tool Roam always should have been. [pic.twitter.com/vOvOD9jzxB](https://t.co/vOvOD9jzxB)
> 
> — Jakob Greenfeld (@jakobgreenfeld) [December 16, 2022](https://twitter.com/jakobgreenfeld/status/1603720566086815746?ref_src=twsrc%5Etfw)

> What the options in the screenshot above do is pull a random person automatically into my daily page.
> 
> Great feature to resurface quotes, notes, and reminders to keep in touch with people.
> 
> — Jakob Greenfeld (@jakobgreenfeld) [December 16, 2022](https://twitter.com/jakobgreenfeld/status/1603721561168568320?ref_src=twsrc%5Etfw)

**What we’re building: Automatic, random block output in Roam**
---------------------------------------------------------------

Alright, so we have something to aim at. Given we have a collection of _People_ objects in our graph, we want to:

*   Grab just one of those _people_ at random
*   Output that _person_ *and* blocks referencing that person on the daily notes page (DNP)
*   Run this workflow every day automatically, without any additional input once setup

**Prerequisites**
-----------------

Before we dive in and build this thing, you will need to install the [SmartBlocks](https://roamjs.com/extensions/smartblocks) plugin via the Roam Depot plugin manager. A quick diatribe, which you’re free to skip, for those “_this is a hack_” or “_this feature is too important – I need it to be in core to rely on it_” people…

*   **SmartBlocks is one of the ecosystem’s oldest, best-documented, and most well-supported plugins.** At the time of this writing, it has more active users (5,972) than people in the entire Tana slack channel (5,300).
*   **What other system do you hold this “must be included in core” mentality?** Do you only use Apple apps on your iPhone? Microsoft apps in VS Code? I didn’t think so…
*   **The entire SmartBlock’s repository is open-sourced**. If you wanted, you could fork the entire repo today, make it your own and update it until the end of time.

**Get off your soapbox and build, Chris**
-----------------------------------------

#### **Visit _The Roam Way_ graph to snag this custom SmartBlock**.