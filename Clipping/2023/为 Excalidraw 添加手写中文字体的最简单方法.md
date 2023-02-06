---
created: 2023-02-07T03:01:15 (UTC +08:00)
tags: [前端]
source: https://juejin.cn/post/7083788887583096839
author: 前端黑板报
---

# 为 Excalidraw 添加手写中文字体的最简单方法

Excalidraw 是一个漂亮的在线绘图网站，亮点就是其手绘风格的英文：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a2802bcbf6eb477194c95e8806fbe6e3~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp?)

但是没有对中文的手绘风格字体进行兼容处理，所以上图的中文字体有些格格不入。

### 那如何处理呢？

得益于 [Excalidraw](https://link.juejin.cn?target=https%3A%2F%2Fgithub.com%2Fexcalidraw%2Fexcalidraw "https://github.com/excalidraw/excalidraw") 开源大家可以自己部署，两种部署方法：

1.  Nodejs
2.  Docker

第一种方法就方便处理可以直接改源码，也有案例：[segmentfault.com/a/119000004…](https://link.juejin.cn?target=https%3A%2F%2Fsegmentfault.com%2Fa%2F1190000040701795 "https://segmentfault.com/a/1190000040701795")

我这里提供一个稍微简单的方法，使用浏览器的插件重定向字体来实现中文手绘字体的兼容：

步骤：

1.  寻找手绘字体（[猫啃](https://link.juejin.cn?target=https%3A%2F%2Fwww.maoken.com%2F "https://www.maoken.com/")、[100font](https://link.juejin.cn?target=https%3A%2F%2Fwww.100font.com%2F "https://www.100font.com/")）
2.  寻找重定向插件（[XSwitch](https://link.juejin.cn?target=https%3A%2F%2Fchrome.google.com%2Fwebstore%2Fdetail%2Fidkjhjggpffolpidfkikidcokdkdaogg "https://chrome.google.com/webstore/detail/idkjhjggpffolpidfkikidcokdkdaogg")）

### 1. 寻找字体

上面两个网站挑选字体后解压，之后上传到一个存储位置（可以访问的地方）或者本地静态服务器，我这里上传到了腾讯云的 COS 里得到一个可访问链接。

### 2. 配置重定向

找到需要重定向的字体地址：`https://excalidraw.com/Virgil.woff2`

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2fd9116ee4434dfc8a763b8aec28a6b2~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp?)

配置 XSwitch 插件：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f9975eef5bfa4fc2886996a2201dae2f~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp?)

刷新页面（多刷几次，有可能有缓存），效果如下：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bb8ba995001b4c31a516a88759e5990d~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp?) 看着就和谐很多了！
