---
created: 2023-02-09T12:54:40 (UTC +08:00)
tags: []
source: https://taresky.com/network-setup-2021
author: taresky
---

# 家庭弱电方案分享（2021 年

> 在 2019 年，和软路由说再见 中，我表达过家庭弱电方案稳定的核心：把主路由独立出来，尽可能纯粹，只干路由器该干的活。

Jun 26, 2021

稳定、无聊、又一年
---------

在 [2019 年，和软路由说再见](https://taresky.com/2019byebye) 中，我表达过家庭弱电方案稳定的核心：**把主路由独立出来，尽可能纯粹，只干路由器该干的活**。把脏活累活丢给其他设备，不影响整体的网络稳定。

Table of Contents

*   [简单拓扑图](#toc_1)
*   [详细介绍](#toc_2)
    *   [主路由：ROS RB450Gx4](#toc_3)
    *   [交换机：水星 SG108P](#toc_7)
    *   [AP Mesh：TP-Link XDR5430](#toc_8)
    *   [服务器：M1 Mac Mini](#toc_12)
    *   [存储：J5005 黑群晖](#toc_16)
    *   [摄像头：水星 MIPC351/451](#toc_17)

简单拓扑图
-----

![](https://i.typlog.com/taresky/8375236847_110933.png)

详细介绍
----

### 主路由：ROS RB450Gx4

#### 优点：

1.  稳定。从 18 年使用至今，零故障。
2.  高效。在路由器设置上做了任何更改，**点击 Apply 的那个瞬间，更改就生效了**。没有过渡动画，不必 Loading 或重启。
3.  功能完善。你能想到任何与路由器有关的功能，ROS 几乎都可以实现。比如 **DHCP Option Set**：如果你家里有科学网关，但并不想让全部设备都科学上网。常见做法是默认 DHCP 服务器地址指向主网关，需要科学上网的设备手动配置指向科学网关。而 ROS 的 DHCP Option Set 功能，可以预设多套 DHCP 配置，并且让设备使用指定的配置。这样设备保持自动获取 DHCP（IP / 网关 / DNS） 就好。

#### 缺点：折腾略有门槛，好在资料丰富。

#### 其他推荐：

1.  RB450Gx4 体积非常小，可以适应任何弱电箱。如果你的弱电箱体积稍大一些，可以考虑一步到位购买 RB4011，其实它也仅有一个普通交换机那么大。
2.  除了 ROS 之外，我使用过的、能保持一年以上零故障的主路由（拨号路由）还有 Ubnt USG 和 Velop AC。大胆推测：目前使用高通、博通方案的 Wi-Fi6 路由器，只要固件水平过硬（Linksys、TP-Link），应该都可以达到这个标准。

### 交换机：水星 SG108P

水星是 TP-Link 的廉价子牌，使用两年，零故障。  
对于选择交换机，需要判断：千兆还是万兆；是否需要 POE 供电；是否需要网管功能。家用场景基本不需要考虑背板带宽，越便宜越好。不出意外，目光会锁定在价格屠夫 TP-Link 以及水星。

### AP Mesh：TP-Link XDR5430

#### 优点：

1.  稳定。使用近一年，能算他头上的故障只有一次（最终原因不明，这一次也不能完全确定）。
2.  便宜。三百元出头，可以买到 5G 速率 4804Mbps 的 Wi-Fi6 路由器。让你的苹果设备满速上网（1200Mbps），估计未来十年还是满速。
3.  刀法精湛。为什么是 4804 Mbps？因为再多一点，就要分频了。对于有线回程来说，分频就是浪费（钱）；2.4G 速率 574Mbps 堪堪够用，也只有智能家居才使用 2.4G 频段。
4.  固件实力强。如果任选品牌，从头开始配置三台 Mesh 路由组网，TP-Link 大概是最快完成的，Velop 无疑是最慢的。除了 UI 难看，TP-Link 的固件的性能、稳定性、功能、排版上没什么槽点。很多极其昂贵的品牌，在发布 Mesh 路由器之初，要花一两年时间来更新支持 “有线回程 + AP” 的 Mesh 模式，而 TP-Link 上线即支持。
5.  Mesh 效果出众。Wi-Fi6 以来，我测试过华硕 + 博通、小米 + 高通、Velop + 高通、TP + 博通、TP + 高通。只有 Velop 和 TP 能够做到，大部分时候漫游稳定不丢包。**甚至 TP-Link 在博通 + 高通混搭的情况下，都能稳定漫游不丢包。**

#### 缺点：丑。

#### 其他推荐：无。

在 Wi-Fi6E 的终端设备开始普及之前（特指 Apple），再升级已无必要。

### 服务器：M1 Mac Mini

#### 优点：

1.  举重若轻的安静。在购买 M1 Mac Mini 之前，我用 NUC8 作为家庭服务器，小小的机身发出了惊人的噪音。M1 来了，一切变快了，也安静了。
2.  生态。玩了一段时间 OpenWRT、群晖，最终发现达成相同的目的远不如 macOS 或 Windows 方便。在 macOS 上，Surge 网关 / Plex Server / Roon Server / PT 工具，该有的都有，何不 24 小时开机使用。

#### 缺点：贵

#### 其他推荐：

1.  任何正在闲置的电脑
2.  不定期出现的便宜的洋垃圾
3.  性价比高的 NUC 或 AMD 小主机 只要别搞 All In One 作为主路由，别把对稳定性要求极高的重要服务放在这（例如 DNS），别影响主网络的稳定性，怎么玩都行。

### 存储：J5005 黑群晖

之前沉迷黑群晖的时候组的，18 年买来到现在同样零故障。主要工作是内网数据传输以及 Surveillance Station 摄像头接管。  
还拿来定期备份照片、Time Machine、PT 下载，以及一些重复的备用功能：DDNS、Jellyfin、Adguard。  
说实话 macOS 长期低负载的稳定性超出我的预期，如果没有这台黑群晖，选择 Mac 外接一个 TB3/USB3 硬盘笼也够了。

### 摄像头：水星 MIPC351/451

家里养宠物的人会需要全天候开着摄像头，室内的监控视频毫无疑问是极度隐私。而任何云服务都不可靠，**国内云服务更可以视为已经泄漏**。所以我们需要可以隔离外网，又能方便随时查看监控的解决方案。  
我认为最佳方案是：1. 支持 ONVIF 通用协议的摄像头 + 2. 群晖 Surveillance Station（或监控录像机）+ 3. 能够禁用指定设备的外网权限的主路由 + 4. 家中代理服务器 + 5. 公网 IP 和端口转发 + 6.Surge

1.  水星 MIPC351/451 应该是同规格里最便宜的摄像头，并且还支持 ONVIF 通用协议。联网配置完成之后，立刻禁用它的外网权限，自然无法使用任何云服务，同时在内网可以正常访问。
2.  手头有群晖 Surveillance Station，配置非常简单，添加摄像头的内网 IP 地址即可。可以设置保存监控视频的大小或时间，有 Web 以及手机客户端可以实时查看监控画面，支持加速播放，支持多个摄像头画面同时播放，远胜大部分摄像头的原厂 App。
3.  ROS 当然可以轻松做到，其他的忘了。
4.  不管是 OpenWRT 的 SS-Server 或者 Surge For Mac 的 Snell-Server 都可以，目的是让处于内网的群晖 Surveillance Station 误以为你的设备还在内网，随时随地正常访问监控。
5.  为了减少暴露端口的风险，通常我只开放家中代理服务器这一个端口。
6.  因为 iPhone 和 Mac 的科学上网是永远开启的，使用 Surge 配置规则 `访问 192.168.1.X 时，走家中代理服务器` 即可。这样科学上网和连回家两不耽误，甚至在外移动办公时，Time Machine 仍在毫无察觉地正常工作。

[All rights reserved](https://wikipedia.org/wiki/Copyright)

Except where otherwise noted, content on this page is copyrighted.
