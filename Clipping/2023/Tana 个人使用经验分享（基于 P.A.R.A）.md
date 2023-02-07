> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [flowus.cn](https://flowus.cn/share/f442ee82-ad36-45b0-b60f-4f9b3f769421) Tana 个人使用经验分享（基于 P.A.R.A）  
文档加载中

思路说明  
首先先简单的说明下 P.A.R.A 是什么（这个 体系没有经过时间的推敲，我个人也不太相信，但是大概得思想对于目前来说还是很受用）  

Project（项目）：也就是当下进行的重点任务  

Area（领域）：用项目来驱动的一个类别，比如现在重点是学习前端，那么编程就是 Area  

Resource（资源）：跟 Area 相同，但是没有项目驱动（没有任务），一般是一些收藏和记录性的内容，比如工作、住址、收藏等  

Archive（归档）：上面三个的存档（暂时不用的）  
在这个基础上，我个人新添加了 ​​🐷​​ Personal 和 ​​🙌​​ Notes 两个模块，分别对应个人的生活和所有的笔记。后面的模块说明中再详细说明。  

小技巧  
再说说使用 Tana 的一些小 Tip，目前也是个人使用的比较多的  

无限套娃：基于 node 自由、结构化。拥有 supertag 自由而且有序  

工作页面  
用 ​​⭕​​ Workbench 和 Quickeadd（ctrl +e）来构建工作流，而不用 daily note（个人用法，可以根据自己的系统调整，因为默认添加的任何节点基本情况都是在 today 节点下，内容多时容易引起混乱）。目前个人用 daily note 设置 filed 来管理日记和每日打卡  

命令行工具（ctrl+k)：下面是常用的几个命令  

find node：也就是查询，可以通过命令的形式查看到系统一些内置的变量和一些思路  

show view options（view as list、view as table、view as tabs)：将当前的节点转换成视图模式（而不必是查询）。一般用于工作区的排版，当前的各个模块都是使用这种方式。  
![](https://cdn.flowus.cn/oss/57f387c9-c1d3-42ec-96e3-71c83bb0c080/image.png?time=1675784700&token=313827b0df48f9ef0bca6b8c3a90dc0c)

open trash：回收站，目前基于节点的（不是很好用）  

Configure node：配置当前节点，当前的主要功能就是配置 banner  
![](https://cdn.flowus.cn/oss/6d42a919-9d7b-448b-b338-e257ad55ee9d/image.png?time=1675784700&token=fa1dc745af4b5588ff614bd5215d86bb)

set default tag for children：所有的子节点设立 supertag  

add contextual content：添加上下文（根据语境来设置），这个一时也没办法说清楚，目前个人的理解就是两个用法，查询表格中添加上下文 field 用来计算，节点中用来区分反链内容, 可以参考[官网说明](https://help.tana.inc/contextual-content.html)。  

Supertag  

标签的配置：用来模范化工作流。例如：  
![](https://cdn.flowus.cn/oss/2a86490c-67f3-44d7-b983-d1b410ec00a1/image.png?time=1675784700&token=05e2bd3b8a5a23d4f599176aca4c9b76)

设置了每日打卡的内容等等，可以根据自己的需要定制模版  

标签间的继承：用来查询包含性内容时非常好用。例如：  

Media，包含文章、链接（网站）、书籍、音乐等等。我可以将 media 作为这类资源的父类 Supertag，让书籍标签、文章标签等等继承 media 标签。这样，就可以分别查看书籍、音乐等单独的类型，也可以查看 media 包含所有的媒体类型。而且，在【名人】下设置了 live Search，查询的就是【名人】对应的 media（也可以理解为作品）。  
![](https://cdn.flowus.cn/oss/dd7a77be-8f17-4a69-8cca-ff40eb007300/image.png?time=1675784700&token=cf795f6755cac8e08cc24d0cc67104bc)

Live Search：真正的神器，[官网教程](https://help.tana.inc/live-search.html)  

模块说明  
​​👇🏻​​ 是对应的模块说明，请仔细查看图片，都配有基本的说明，都是基于上面使用小 Tip 来实现的  
主页  
![](https://cdn.flowus.cn/oss/a77090e5-498f-4fa8-b822-64850ce470d8/image.png?time=1675784700&token=1ca6f93921a61349c547b595705865f3)​​⭕​​ Workbench  
![](https://cdn.flowus.cn/oss/891865b7-19c6-492c-9b55-1433c0221838/image.png?time=1675784700&token=e46d5239877c04ce85386a465b6c7b3b)​​🔗​​ Quick Capture  
![](https://cdn.flowus.cn/oss/15bfaa77-e4e0-4037-a69b-9d451001a5bc/image.png?time=1675784700&token=c0babd246ff05ca53b5209d14f08c3a7)​​⚔️​​ Area  
![](https://cdn.flowus.cn/oss/1db49cdf-10a8-49a3-bfa6-fc31a0d5ea7f/image.png?time=1675784700&token=69ea696a1de6bfc3b118f3dd6e118ff8)​​📿​​ Resource  
![](https://cdn.flowus.cn/oss/1e55ce16-fdec-44c4-84cb-7cdd923de578/image.png?time=1675784700&token=5978ff497acf0d61f07445c7a986ab77)​​🥊​​ Project  
![](https://cdn.flowus.cn/oss/91f565e8-fdb1-4db6-915b-681b93d5f41a/image.png?time=1675784700&token=da0ab4fbc08006d874d5da7ab9ca5711)​​✅​​ Tasks  
![](https://cdn.flowus.cn/oss/164a4c35-a02a-4bed-b4e0-42f38dd54f06/image.png?time=1675784700&token=b195e1347cf605e9c293d0f82257e6c8)​​🐶​​ Archive  
![](https://cdn.flowus.cn/oss/5502f37e-abcc-443c-9ac9-2e611f92256b/image.png?time=1675784700&token=a46ba1da4a2b1fb54e31f5bc6b85a94b)​​🐷​​ Personal  
![](https://cdn.flowus.cn/oss/6c1b2a66-845e-41df-85a0-312daf10a22c/image.png?time=1675784700&token=9121612c57a64d291322be7753d1187b)​​🙌​​ Notes  
![](https://cdn.flowus.cn/oss/effd6ea4-6fda-4c50-b1fa-375afef8fe25/image.png?time=1675784700&token=4dde4948eba8b99f4a7a1820734a0777)

写在最后  

💡

希望大家都能真正的在做事情，而不是一直折腾效率玩具。自己也深陷其中，祝大家都有锦绣前程。共勉！  

​​  
80%

[](/share/8ce68f53-f24d-4869-8665-57e96bcbdb45)​​  

目录思路说明小技巧模块说明主页⭕ Workbench🔗 Quick Capture⚔️ Area📿 Resource🥊 Project✅ Tasks🐶 Archive🐷 Personal🙌 Notes写在最后