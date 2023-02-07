> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.instapaper.com](https://www.instapaper.com/read/1559131500)

> A simple tool for saving web pages to read later on your iPhone, iPad, Android, computer, or Kindle.

December 5, 2022

In this post, I’ll explain exactly what supertags are, how they work in Tana, and how you can easily replicate most of the functionality in Roam Research.  
在本文中，我将准确解释超级标签是什么、它们在 Tana 中的工作原理，以及如何轻松复制 Roam Research 中的大部分功能。

**TLDR;**
---------

*   The features most associated with supertags are fields with forced structure and default content  
    与超级标签最相关的功能是具有强制结构和默认内容的字段
*   We can recreate the functionality of _supertags_ in Roam using the Smartblocks + Query Builder plugins  
    我们可以使用 Smartblocks + Query Builder 插件在 Roam 中重新创建超级标签的功能
*   Tana’s implementation is ahead in some areas, most noticeably the highly polished views  
    Tana 的实施在某些领域领先，最引人注目的是高度抛光的视图

### **Sneak peak of what we’re building  
抢先了解我们正在构建的内容**

By the end of this post, you’ll know exactly how to build a _supertag-like_ SmartBlock in Roam Research.  
到本文结尾，您将确切了解如何在 Roam Research 中构建类似超级标签的 SmartBlock。

Our custom SmartBlock will have features like structured fields and instances – things you probably thought were _only_ available in Tana or other database-centric tools like Notion (spoiler alert, they’re not). I’ll provide you with the complete SmartBlock workflow and the custom CSS, so your graph can look just like the videos in this tutorial.  
我们的自定义 SmartBlock 将具有结构化字段和实例等功能——您可能认为这些功能仅在 Tana 或其他以数据库为中心的工具（如 Notion）中可用（剧透警报，它们不是）。我将为您提供完整的 SmartBlock 工作流程和自定义 CSS，因此您的图形看起来就像本教程中的视频一样。

![](https://theroamway.com/wp-content/uploads/2022/12/Workflow.gif)

### **What the heck are _supertags_ anyway?  
到底什么是超级标签？**

_[Jump to the section where you build this in Roam  
跳转到您在 Roam 中构建它的部分](https://theroamway.com/build-a-supertag-in-roam-research#build-roam)_

Supertags in Tana cover a lot, but for this article, we’re going to focus on fields, forced structure, and default content.  
Tana 中的超级标签涵盖了很多内容，但对于本文，我们将重点关注字段、强制结构和默认内容。

**Fields**

Fields allow us to add additional structure and information to a supertag object. An example is helpful to illustrate:  
字段允许我们向超级标签对象添加额外的结构和信息。举个例子有助于说明：

Let’s say that we’re building a supertag to manage our projects. Each time we create a new project, we also want to set some additional fields to help keep our projects organized. Those additional fields might look something like this:  
假设我们正在构建一个超级标签来管理我们的项目。每次我们创建一个新项目时，我们还想设置一些额外的字段来帮助保持我们的项目井井有条。这些额外的字段可能看起来像这样：

*   Project name
*   Client
*   Status
*   Assignee
*   Created date
*   Due date

**Forced structure**

Forced structure is just a way of saying: when we populate this field, it _must_ be a particular type or format. Building on our project setup above that would look something like this:  
强制结构只是一种说法：当我们填充这个字段时，它必须是特定的类型或格式。基于我们上面的项目设置，看起来像这样：

*   Project name: **Free text – Input field**  
    项目名称：自由文本 - 输入域
*   Client: **Dynamic options – Only items I’ve already marked _client_**  
    客户端：动态选项——只有我已经标记为客户端的项目
*   Status: **Fixed options – One of: Not Started, In Progress, Complete**  
    状态：固定选项 - 其中之一：未开始、进行中、完成
*   Assignee: **Graph users – Auto-initialize to user that’s triggering**  
    受让人：图形用户——自动初始化为触发的用户
*   Created date: **Date format – Auto-initialize to _today’s_ date**  
    创建日期：日期格式——自动初始化为今天的日期
*   Due date: **Date format – User selected**  
    截止日期：日期格式 - 用户选择

**Default content**

Default content is the ability to automatically populate additional content each time we create a new supertag instance. The content could be simple static text, or a complex dynamic query (live search). Regardless of complexity, the point here is that we only need to define the format and structure of the content once, but we get it (by default) each time.  
默认内容是每次我们创建新的超级标签实例时自动填充额外内容的能力。内容可以是简单的静态文本，也可以是复杂的动态查询（实时搜索）。不管复杂性如何，这里的重点是我们只需要定义一次内容的格式和结构，但我们每次都会（默认情况下）获取它。

Building on our example above, each time we create a new _project_, we also want to create a corresponding tasks table that automatically outputs all to-do’s assigned to _this_ project.  
基于我们上面的示例，每次我们创建一个新项目时，我们还想创建一个相应的任务表，自动输出分配给该项目的所有待办事项。

_I originally planned on building this supertag in Tana (yes, I have access), but that would make the post even longer, and it’s already too long. I’ll let you search the interwebs for others who have built supertags in Tana to get an idea of what that’s like.  
我最初计划在 Tana 中构建这个超级标签（是的，我可以访问），但这会使帖子变得更长，而且已经太长了。我会让您在互联网上搜索其他在 Tana 中构建超级标签的人，以了解那是什么样的。_

### ****Building a supertag in Roam Research  
在 Roam Research 中构建超级标签****

Using the project outline above as our guide, let’s see if we can create that _exact_ supertag in Roam Research. This means we’ll need to accomplish the following:  
使用上面的项目大纲作为我们的指南，让我们看看我们是否可以在 Roam Research 中创建完全相同的超级标签。这意味着我们需要完成以下任务：

1.  Set additional fields (client, status, due date, etc…) every time a new project is created  
    每次创建新项目时设置附加字段（客户、状态、截止日期等）
2.  Ensure the additional fields are of the exact type and format we specified in the outline  
    确保附加字段的类型和格式与我们在大纲中指定的完全一致
3.  Automatically create and output a _tasks table_ capturing all todo’s referencing the project  
    自动创建和输出任务表，捕获所有引用项目的待办事项

Ready? Let’s jump in. To replicate supertags in Roam, we’re going to be using two plugins from the Roam Depot:  
准备好？让我们开始吧。要在 Roam 中复制超级标签，我们将使用 Roam Depot 中的两个插件：

*   [SmartBlocks](https://roamjs.com/extensions/smartblocks) – API for fetching and manipulating your Roam data + build custom commands and workflows  
    SmartBlocks – 用于获取和操作漫游数据的 API + 构建自定义命令和工作流
*   [Query Builder](https://roamjs.com/extensions/query-builder) – Interface for querying and viewing your Roam data  
    Query Builder – 用于查询和查看漫游数据的界面

That’s it. With just those two plugins, we have everything we need to build our project _SmartBlock_. Here’s how we do it:  
就是这样。仅使用这两个插件，我们就拥有了构建项目 SmartBlock 所需的一切。我们是这样做的：

**Step 1: Build a clients table with Query Builder  
第 1 步：使用查询生成器构建客户表**

How do we enforce that our client field is _only_ populated with clients? Simple; we create a query that retrieves all clients, and then we limit the input options to the results.  
我们如何强制我们的客户字段只填充客户？简单的; 我们创建一个检索所有客户端的查询，然后我们将输入选项限制为结果。

[![](https://theroamway.com/wp-content/uploads/2022/11/Clients-1-1024x516.png)](https://theroamway.com/wp-content/uploads/2022/11/Clients-1.png)Our simple list of clients 我们简单的客户名单

A simple structure to denote what a _client_ is in our graph. You might use a tag system `#Client`, attributes, or another method. If you have questions or need help regarding your specific setup, I recommend you jump into the Roam Slack.  
一个简单的结构来表示我们图中的客户端。您可以使用标记系统 `#Client` 、属性或其他方法。如果您对特定设置有疑问或需要帮助，我建议您跳转到 Roam Slack。

[![](https://theroamway.com/wp-content/uploads/2022/11/Query-1024x516.png)](https://theroamway.com/wp-content/uploads/2022/11/Query.png)Query params to fetch our clients  
查询参数以获取我们的客户

To make a new query, go to _any_ block and type `{{query block}}`. Here we’re using two conditions: _has parent_, which takes a variable (_clientParent_), and _references title_, which auto-fills your graph’s links as you type.  
要进行新查询，请转到任何块并键入 `{{query block}}` 。这里我们使用了两个条件：有父级，它接受一个变量 (clientParent)，和引用标题，它在您键入时自动填充图表的链接。

[![](https://theroamway.com/wp-content/uploads/2022/11/Query-Results-1024x516.png)](https://theroamway.com/wp-content/uploads/2022/11/Query-Results.png)Final “clients table” output 最终的 “客户表” 输出

A simple table with all of our clients is the final output of our query block. Where you decide to put your query block does not matter. What does matter for our next step is recording the table’s _block reference_ `((lLZQSXA5W))`.  
一个包含我们所有客户的简单表格是我们查询块的最终输出。您决定将查询块放在哪里并不重要。对我们下一步来说重要的是记录表的块引用 `((lLZQSXA5W))` 。

**Step 2: Build a workflow to set our project fields  
第 2 步：构建工作流程以设置我们的项目字段**

Here we’re building the workflow that will prompt us to enter values for the additional fields we want to set each time a new project is created. If you’re brand new to SmartBlocks, the [RoamJS site](https://roamjs.com/extensions/smartblocks/understanding_commands) has a nice primer on syntax and command structure.  
在这里，我们正在构建工作流，该工作流将提示我们为每次创建新项目时要设置的附加字段输入值。如果您是 SmartBlocks 的新手，RoamJS 站点有一个很好的语法和命令结构入门。

#SmartBlock Project #SmartBlock 项目

<%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>  
<%SET: 名称,<%INPUT: 项目名称 %>%> <%NOBLOCKOUTPUT%>

<%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>  
<%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>

<%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>  
<%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>

<%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>

<%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>

<%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>

#SmartBlock Project <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%> <%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%> <%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%> <%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%> <%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%> <%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>

```
#SmartBlock Project
    <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>
    <%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>
    <%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>
    <%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>
    <%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>
    <%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>


```

_Don’t copy/paste this into Roam! It’s a block-based tool; the workflow above is not in blocks. [Click here](https://theroamway.com/build-a-supertag-in-roam-research#cta) to get the working SmartBlock.  
不要将其复制 / 粘贴到漫游中！这是一个基于块的工具；上面的工作流程不是块状的。单击此处获取可用的 SmartBlock。_

Line-by-line code explanation 逐行代码解释

*   `#SmartBlock Project`
    *   **Register** a new **SmartBlock** called _Project_
*   `<%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>`
    *   Set variable **name** (Project Name) from a **free-text input**
*   `<%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%>`
    *   Set variable **client** from a **dropdown** populated by the **clients tables** (sUWHCHyYp)
*   `<%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%>`
    *   Set variable **status** from a **dropdown** populated by **fixed options**
*   `<%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>`
    *   Set variable **assignee** from native **SmartBlock** command
*   `<%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>`
    *   Set variable **created** from native **SmartBlock** date command
*   `<%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>`
    *   Set variable **due** from a **free text input**
    *   _** We’ll turn that number into a date in the next step_

**Step 3: Create a new project page with the values  
第 3 步：使用值创建一个新的项目页面**

Here we’re taking the field values set in the previous step and using them to populate a new project page. We’re utilizing Roam’s _attributes_ to define the project, but this workflow can easily be modified to use tags or links.  
在这里，我们采用上一步中设置的字段值，并使用它们来填充新的项目页面。我们利用 Roam 的属性来定义项目，但可以轻松修改此工作流程以使用标签或链接。

#SmartBlock Generate Project <%HIDE%>  
#SmartBlock 生成项目 <%HIDE%>

<%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%>

For Client:: <%GET:client%>

Owner:: <%HASHTAG:<%GET:assignee%>%>

Status:: <%HASHTAG:<%GET:status%>%>

Due Date:: <%DATE:in <%GET:days%> days%>

#SmartBlock Project #SmartBlock 项目

<%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>  
<%SET: 名称,<%INPUT: 项目名称 %>%> <%NOBLOCKOUTPUT%>

<%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>  
<%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>

<%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>  
<%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>

<%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>

<%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>

<%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>

<%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>  
<%SMARTBLOCK: 生成项目,<%GET:name%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>  
<%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>

#SmartBlock Generate Project <%HIDE%> <%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%> For Client:: <%GET:client%> Owner:: <%HASHTAG:<%GET:assignee%>%> Status:: <%HASHTAG:<%GET:status%>%> Due Date:: <%DATE:in <%GET:days%> days%> #SmartBlock Project <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%> <%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%> <%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%> <%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%> <%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%> <%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%> <%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%> <%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>

```
#SmartBlock Generate Project <%HIDE%>
    <%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%>
    For Client:: <%GET:client%>
    Owner:: <%HASHTAG:<%GET:assignee%>%>
    Status:: <%HASHTAG:<%GET:status%>%>
    Due Date:: <%DATE:in <%GET:days%> days%>
#SmartBlock Project
    <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>
    <%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>
    <%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>
    <%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>
    <%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>
    <%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>
    <%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>



```

_Don’t copy/paste this into Roam! It’s a block-based tool; the workflow above is not in blocks. [Click here](https://theroamway.com/build-a-supertag-in-roam-research#cta) to get the working SmartBlock.  
不要将其复制 / 粘贴到漫游中！这是一个基于块的工具；上面的工作流程不是块状的。单击此处获取可用的 SmartBlock。_

Line-by-line code explanation 逐行代码解释

_Covering only the newly added code from step 1_ _(starting at line 14 and working down, then back up from line 1 to line 6_)

*   `<%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>`
    *   **Run** the SmartBlock **“Generate Project”** and output on a page with a title that equals the **name** variable
    *   _* If there is no page with that title, SmartBlocks will create one for us_
*   `<%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>`
    *   If variable **projectPage** was set on **Generate Project** SmartBlock, open it in the **right sidebar**
*   `#SmartBlock Generate Project <%HIDE%>`
    *   **Register** a new custom **SmartBlock** called **Generate Project**
*   `<%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%>`
    *   Set variable **projectPage** from native SmartBlock command **<%CURRENTPAGENAME%>**
*   `For Client:: <%GET:client%>`
    *   **Output** “For Client” **attribute** with value **client**
*   `Owner:: <%HASHTAG:<%GET:assignee%>%>`
    *   **Output** “Owner” **attribute** with value **assignee**
*   `Status:: <%HASHTAG:<%GET:status%>%>`
    *   **Output** “Status” **attribute** with value **status**
*   `Due Date:: <%DATE:in <%GET:days%> days%>`
    *   **Output** “Due Date” **attribute** with value **days**
    *   _* Days is wrapped in a built-in SmartBlock command <%DATE:%> that runs natural language processing_

**Bonus 1 – Improving the UX / UI of our dialog prompt  
奖励 1 – 改进对话提示的用户体验 / 用户界面**

Customizing the look and feel of our graph is trivially easy in Roam, so let’s take advantage of that. The custom CSS below improves the stock design and adds carefully selected _focus_ styles so you can quickly whip through the entire workflow without ever having to touch your mouse.  
在 Roam 中自定义图形的外观和感觉非常容易，所以让我们利用它。下面的自定义 CSS 改进了库存设计并添加了精心选择的焦点样式，因此您无需触摸鼠标即可快速完成整个工作流程。

**Standard dialog design 标准对话框设计**

**Custom dialog design 自定义对话框设计**

CSS for custom dialog prompt 用于自定义对话框提示的 CSS

.roamjs-query-builder-parent {

0 1px 1px hsl(0deg 0% 50% / 0.075),

0 2px 2px hsl(0deg 0% 50% / 0.075),

0 4px 4px hsl(0deg 0% 50% / 0.075),

0 8px 8px hsl(0deg 0% 50% / 0.075),

0 16px 16px hsl(0deg 0% 50% / 0.075);

.roamjs-query-results-view > span.absolute > p {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog h3.bp3-heading {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-contents,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-label

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div {

background-color: #F3F7FF;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button {

justify-content: space-between;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button > span {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button .bp3-icon {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button > span {

-webkit-font-smoothing: antialiased;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer {

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content {

min-width: 16rem !important;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-overlay-backdrop {

background: rgba(0,0,0,.65);

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog {

background-color: transparent !important;

border: 1px solid #d6d7db;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body {

background-color: #fff !important;

border-top-left-radius: 0.5rem;

border-top-right-radius: 0.5rem;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer {

padding: .85rem 1.5rem !important;

background-color: rgb(249,250,251) !important;

margin-top: 0 !important;

border-bottom-left-radius: 0.5rem;

border-bottom-right-radius: 0.5rem;

border-top: 1px solid #eee;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-label {

color: rgb(17,24,39) !important;

-webkit-font-smoothing: antialiased;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]{

background-color: #F3F7FF;

-webkit-font-smoothing: initial;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]::placeholder {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]:focus,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div:focus-within

outline: 1px solid #0050F0 !important;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button {

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:focus,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:hover

outline-width: 1px !important;

outline-style: solid !important;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type {

background-color: #85adff;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:focus,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:hover

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type {

outline-color: rgb(209,213,219) !important;

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:focus,

#smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:hover

background-color: transparent;

outline-color: #8d97a5 !important;

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content,

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu {

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li:not(:last-of-type) {

border-bottom: 1px solid #eee;

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a,

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a div {

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a.bp3-active,

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a.bp3-active div {

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li > .bp3-menu-item.bp3-intent-primary.bp3-active {

background-color: rgb(241,245,249);

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li:hover > a,

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li > a:hover {

background-color: #dbe6f0;

.roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a div {

.roamjs-query-builder-parent { margin-top: .5rem; box-shadow: 0 1px 1px hsl(0deg 0% 50% / 0.075), 0 2px 2px hsl(0deg 0% 50% / 0.075), 0 4px 4px hsl(0deg 0% 50% / 0.075), 0 8px 8px hsl(0deg 0% 50% / 0.075), 0 16px 16px hsl(0deg 0% 50% / 0.075); } .roamjs-query-results-view > span.absolute > p { padding-left: 1rem; font-size: .9rem; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog { background: #222326; width: 750px; min-width: 750px; padding: 2.5rem; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog h3.bp3-heading { display: none; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-contents, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-label { width: 100%; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div { border-radius: 6px; display: inline-block; background-color: #F3F7FF; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button { background: transparent; min-width: 16rem; display: flex; justify-content: space-between; border-radius: 6px; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button > span { font-size: 1rem; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div > button .bp3-icon { color: #18191b; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button > span { font-weight: bold; -webkit-font-smoothing: antialiased; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer { margin-top: 1rem; } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content { min-width: 16rem !important; } /* (Light) */ #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-overlay-backdrop { background: rgba(0,0,0,.65); } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog { padding: 0 !important; background-color: transparent !important; border-radius: 0.5rem; border: 1px solid #d6d7db; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body { padding: 1.25rem; background-color: #fff !important; border-top-left-radius: 0.5rem; border-top-right-radius: 0.5rem; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer { padding: .85rem 1.5rem !important; background-color: rgb(249,250,251) !important; margin-top: 0 !important; border-bottom-left-radius: 0.5rem; border-bottom-right-radius: 0.5rem; border-top: 1px solid #eee; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-label { color: rgb(17,24,39) !important; white-space: pre-wrap; font-size: 1rem; font-weight: bolder; -webkit-font-smoothing: antialiased; margin-bottom: 0; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]{ margin-top: 0; min-width: 16rem; font-size: 1rem; color: #18191b; font-weight: 500; height: 40px; line-height: 40px; background-color: #F3F7FF; -webkit-font-smoothing: initial; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]::placeholder { font-weight: normal; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type="text"]:focus, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper > .bp3-popover-target > div:focus-within { background-color: #fff; outline: 1px solid #0050F0 !important; outline-offset: 0; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body > .bp3-label > .bp3-popover-wrapper, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group { margin-top: .75rem; } /* Footer */ #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button { padding: 8px 16px; font-weight: 500; line-height: 20px; border-radius: 0.375rem; outline-style: solid; outline-width: 1px; outline-offset: 0; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:focus, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:hover { outline-width: 1px !important; outline-style: solid !important; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type { background-color: #85adff; outline-color: #528bff; color: #fafafa; margin-left: 12px; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:focus, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:hover { background: #3A7BFF; outline-color: #226BFF; color: #fff; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type { background-color: #fff; outline-color: rgb(209,213,219) !important; color: #57667f; } #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:focus, #smartblocks-prompt + .bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:hover { background-color: transparent; outline-color: #8d97a5 !important; color: #29313d; } /* Dropdowns */ .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content, .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu { background-color: #fff; } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li:not(:last-of-type) { border-bottom: 1px solid #eee; } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a, .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a div { color: rgb(15,23,42); } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a.bp3-active, .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a.bp3-active div { color: #030303; } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li > .bp3-menu-item.bp3-intent-primary.bp3-active { background-color: rgb(241,245,249); } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li:hover > a, .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li > a:hover { background-color: #dbe6f0; } .roamjs-prompt-dropdown > .bp3-transition-container > .bp3-popover > .bp3-popover-content > div > ul.bp3-menu li a div { font-size: 1rem; padding-top: 4px; padding-bottom: 4px; }

Minified CSS

.roamjs-query-builder-parent{margin-top:.5rem;box-shadow:0 1px 1px hsl(0deg 0% 50% / .075),0 2px 2px hsl(0deg 0% 50% / .075),0 4px 4px hsl(0deg 0% 50% / .075),0 8px 8px hsl(0deg 0% 50% / .075),0 16px 16px hsl(0deg 0% 50% / .075)}.roamjs-query-results-view>span.absolute>p{padding-left:1rem;font-size:.9rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog{background:#222326;width:750px;min-width:750px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog h3.bp3-heading{display:none}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-contents,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-label{width:100%}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div{border-radius:6px;display:inline-block;background-color:#f3f7ff}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button{background:0 0;min-width:16rem;display:flex;justify-content:space-between;border-radius:6px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button>span{font-size:1rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button .bp3-icon{color:#18191b}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button>span{font-weight:700;-webkit-font-smoothing:antialiased}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content{min-width:16rem!important}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-overlay-backdrop{background:rgba(0,0,0,.65)}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog{padding:0!important;background-color:transparent!important;border-radius:.5rem;border:1px solid #d6d7db}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body{padding:1.25rem;background-color:#fff!important;border-top-left-radius:.5rem;border-top-right-radius:.5rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer{padding:.85rem 1.5rem!important;background-color:#f9fafb!important;margin-top:0!important;border-bottom-left-radius:.5rem;border-bottom-right-radius:.5rem;border-top:1px solid #eee}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-label{color:#111827!important;white-space:pre-wrap;font-size:1rem;font-weight:bolder;-webkit-font-smoothing:antialiased;margin-bottom:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]{margin-top:0;min-width:16rem;font-size:1rem;color:#18191b;font-weight:500;height:40px;line-height:40px;background-color:#f3f7ff;-webkit-font-smoothing:initial}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]::placeholder{font-weight:400}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div:focus-within,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]:focus{background-color:#fff;outline:#0050F0 solid 1px!important;outline-offset:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group{margin-top:.75rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button{padding:8px 16px;font-weight:500;line-height:20px;border-radius:.375rem;outline-style:solid;outline-width:1px;outline-offset:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:hover{outline-width:1px!important;outline-style:solid!important}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type{background-color:#85adff;outline-color:#528bff;color:#fafafa;margin-left:12px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:hover{background:#3a7bff;outline-color:#226bff;color:#fff}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type{background-color:#fff;outline-color:#d1d5db!important;color:#57667f}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:hover{background-color:transparent;outline-color:#8d97a5!important;color:#29313d}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu{background-color:#fff}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li:not(:last-of-type){border-bottom:1px solid #eee}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a div{color:#0f172a}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a.bp3-active,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a.bp3-active div{color:#030303}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li>.bp3-menu-item.bp3-intent-primary.bp3-active{background-color:#f1f5f9}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li:hover>a,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li>a:hover{background-color:#dbe6f0}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a div{font-size:1rem;padding-top:4px;padding-bottom:4px}

.roamjs-query-builder-parent{margin-top:.5rem;box-shadow:0 1px 1px hsl(0deg 0% 50% / .075),0 2px 2px hsl(0deg 0% 50% / .075),0 4px 4px hsl(0deg 0% 50% / .075),0 8px 8px hsl(0deg 0% 50% / .075),0 16px 16px hsl(0deg 0% 50% / .075)}.roamjs-query-results-view>span.absolute>p{padding-left:1rem;font-size:.9rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog{background:#222326;width:750px;min-width:750px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog h3.bp3-heading{display:none}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-contents,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-label{width:100%}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div{border-radius:6px;display:inline-block;background-color:#f3f7ff}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button{background:0 0;min-width:16rem;display:flex;justify-content:space-between;border-radius:6px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button>span{font-size:1rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div>button .bp3-icon{color:#18191b}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button>span{font-weight:700;-webkit-font-smoothing:antialiased}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content{min-width:16rem!important}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-overlay-backdrop{background:rgba(0,0,0,.65)}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog{padding:0!important;background-color:transparent!important;border-radius:.5rem;border:1px solid #d6d7db}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body{padding:1.25rem;background-color:#fff!important;border-top-left-radius:.5rem;border-top-right-radius:.5rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer{padding:.85rem 1.5rem!important;background-color:#f9fafb!important;margin-top:0!important;border-bottom-left-radius:.5rem;border-bottom-right-radius:.5rem;border-top:1px solid #eee}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-label{color:#111827!important;white-space:pre-wrap;font-size:1rem;font-weight:bolder;-webkit-font-smoothing:antialiased;margin-bottom:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]{margin-top:0;min-width:16rem;font-size:1rem;color:#18191b;font-weight:500;height:40px;line-height:40px;background-color:#f3f7ff;-webkit-font-smoothing:initial}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]::placeholder{font-weight:400}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper>.bp3-popover-target>div:focus-within,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group input[type=text]:focus{background-color:#fff;outline:#0050F0 solid 1px!important;outline-offset:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-body>.bp3-label>.bp3-popover-wrapper,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-input-group{margin-top:.75rem}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button{padding:8px 16px;font-weight:500;line-height:20px;border-radius:.375rem;outline-style:solid;outline-width:1px;outline-offset:0}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:hover{outline-width:1px!important;outline-style:solid!important}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type{background-color:#85adff;outline-color:#528bff;color:#fafafa;margin-left:12px}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:first-of-type:hover{background:#3a7bff;outline-color:#226bff;color:#fff}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type{background-color:#fff;outline-color:#d1d5db!important;color:#57667f}#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:focus,#smartblocks-prompt+.bp3-portal .bp3-overlay .bp3-dialog .bp3-alert-footer button:last-of-type:hover{background-color:transparent;outline-color:#8d97a5!important;color:#29313d}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu{background-color:#fff}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li:not(:last-of-type){border-bottom:1px solid #eee}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a div{color:#0f172a}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a.bp3-active,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a.bp3-active div{color:#030303}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li>.bp3-menu-item.bp3-intent-primary.bp3-active{background-color:#f1f5f9}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li:hover>a,.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li>a:hover{background-color:#dbe6f0}.roamjs-prompt-dropdown>.bp3-transition-container>.bp3-popover>.bp3-popover-content>div>ul.bp3-menu li a div{font-size:1rem;padding-top:4px;padding-bottom:4px}

**Bonus 2 – Setup conditionals to control the output of our workflow  
奖励 2 – 设置条件来控制我们工作流程的输出**

This step is optional, but quite helpful. By default, SmartBlocks will run every command we define (which is good), but what if we triggered it by accident or need to back out halfway through for whatever reason?  
此步骤是可选的，但很有帮助。默认情况下，SmartBlocks 将运行我们定义的每个命令（这很好），但是如果我们意外触发它或出于某种原因需要中途退出怎么办？

With conditionals, we can ensure that we’ve captured a value from the previous prompt _before_ the workflow moves on to the next.  
有了条件，我们可以确保在工作流进入下一个提示之前，我们已经从上一个提示中捕获了一个值。

**Workflow with conditionals 带条件的工作流**

#SmartBlock Generate Project <%HIDE%>  
#SmartBlock 生成项目 <%HIDE%>

<%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%>

For Client:: <%GET:client%>

Owner:: <%HASHTAG:<%GET:assignee%>%>

Status:: <%HASHTAG:<%GET:status%>%>

Due Date:: <%DATE:in <%GET:due%> days%>

#SmartBlock Project #SmartBlock 项目

<%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>  
<%SET: 名称,<%INPUT: 项目名称 %>%> <%NOBLOCKOUTPUT%>

<%IFVAR:name,/.+/%><%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:name,/.+/%><%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:client,/.+/%><%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:client,/.+/%><%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:status,/.+/%><%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:status,/.+/%><%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:assignee,/.+/%><%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:assignee,/.+/%><%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:created,/.+/%><%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:created,/.+/%><%SET:due,<%INPUT: 多少天到期？%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:due,/.+/%><%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>  
<%IFVAR:due,/.+/%><%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>

<%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>  
<%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>

#SmartBlock Generate Project <%HIDE%> <%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%> For Client:: <%GET:client%> Owner:: <%HASHTAG:<%GET:assignee%>%> Status:: <%HASHTAG:<%GET:status%>%> Due Date:: <%DATE:in <%GET:due%> days%> #SmartBlock Project <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%> <%IFVAR:name,/.+/%><%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%> <%IFVAR:client,/.+/%><%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%> <%IFVAR:status,/.+/%><%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%> <%IFVAR:assignee,/.+/%><%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%> <%IFVAR:created,/.+/%><%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%> <%IFVAR:due,/.+/%><%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%> <%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>

```
#SmartBlock Generate Project <%HIDE%>
    <%SET:projectPage,<%CURRENTPAGENAME%>%> <%NOBLOCKOUTPUT%>
    For Client:: <%GET:client%>
    Owner:: <%HASHTAG:<%GET:assignee%>%>
    Status:: <%HASHTAG:<%GET:status%>%>
    Due Date:: <%DATE:in <%GET:due%> days%>
#SmartBlock Project
    <%SET:name,<%INPUT:Project name%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:name,/.+/%><%SET:client,<%INPUT:Client,<%QUERYBUILDER:sUWHCHyYp,{text}%>%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:client,/.+/%><%SET:status,<%INPUT:Status%%Not Started%%In-Progress%%Complete%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:status,/.+/%><%SET:assignee,<%CURRENTUSER%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:assignee,/.+/%><%SET:created,<%DATE:today%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:created,/.+/%><%SET:due,<%INPUT:Due in how many days?%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:due,/.+/%><%SMARTBLOCK:Generate Project,<%GET:name%>%> <%NOBLOCKOUTPUT%>
    <%IFVAR:projectPage,/.+/%> <%SIDEBARWINDOWOPEN:<%GET:projectPage%>%><%TAG:<%GET:projectPage%>%>


```

_Don’t copy/paste this into Roam! It’s a block-based tool; the workflow above is not in blocks. [Click here](https://theroamway.com/build-a-supertag-in-roam-research#cta) to get the working SmartBlock.  
不要将其复制 / 粘贴到漫游中！这是一个基于块的工具；上面的工作流程不是块状的。单击此处获取可用的 SmartBlock。_

Code explanation

*   9-14: `<%IFVAR:name,/.+/%>`
    *   The _IFVAR_ commands that proceed each workflow prompt ensure that a variable (“name” in the case above) is not empty. If it is empty, stop running that block.

**Step 4: Create our dynamic tasks table (default content**)  
第 4 步：创建我们的动态任务表（默认内容）

As we defined in the outline, a tasks table should be created each time we create a new project. The table needs to capture all todo’s assigned to _this_ specific project and output automatically each time a new one is created.  
正如我们在大纲中定义的，每次我们创建一个新项目时都应该创建一个任务表。该表需要捕获分配给该特定项目的所有待办事项，并在每次创建新项目时自动输出。

Below is a quick overview of how we accomplish that in Roam using Query Builder. In short, we define the table logic, replace hard-coded references with variables, and finally take our table code and incorporate it into our custom SmartBlock.  
下面是我们如何使用查询生成器在 Roam 中实现这一点的快速概述。简而言之，我们定义表逻辑，用变量替换硬编码引用，最后获取我们的表代码并将其合并到我们的自定义 SmartBlock 中。

Confused? Don’t be, it’s actually quite easy. Let’s walk through each step:  
使困惑？不要，这实际上很容易。让我们来看看每个步骤：

[![](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Query-Builder-1024x300.png)](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Query-Builder.png)1. Define the base logic for our tasks table  
1. 定义任务表的基本逻辑

In this simple example, we are querying for all nodes that reference `TODO` and have a parent (represented by the variable `parentNode`) that references the _Example Acme project._ We input the logic for this query using Query Builder’s graphical interface, which auto-displays whenever we enter {{query block}} into a block in Roam.  
在这个简单的示例中，我们正在查询引用 `TODO` 并具有引用示例 Acme 项目的父节点（由变量 `parentNode` 表示）的所有节点。我们使用 Query Builder 的图形界面输入此查询的逻辑，每当我们将 {{query block}} 输入到 Roam 中的块时，该界面就会自动显示。

[![](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Query-Instructions-1024x300.png)](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Query-Instructions.png)2. Get the query instructions 2. 获取查询说明

The logic for our tasks table query from step 1 ends up as block-level instructions that output directly below the table (nested under “Results” and “Scratch”). These plain-text, block-level instructions define and process the query in Roam. Everything is contained within, from the query parameters, output style, view type, and even default filters/sorts.  
我们从步骤 1 开始的任务表查询逻辑最终作为块级指令输出，直接在表下方（嵌套在 “Results” 和“Scratch”下）。这些纯文本、块级指令在 Roam 中定义和处理查询。一切都包含在其中，从查询参数、输出样式、视图类型，甚至默认过滤器 / 排序。

[![](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Static-Instructions-1024x300.png)](https://theroamway.com/wp-content/uploads/2022/12/Tasks-Table-Static-Instructions.png)3. Replace static instructions with variables  
3. 用变量替换静态指令

Now that we have our plain-text query instructions, we can use them to generate our default content. Notice the value for parentNode in step 1 is hard-coded “Example Acme project”? If we identify where that condition lives in the instructions and replace it with the (built-in) SmartBlock command `<%CURRENTPAGENAME%>`, we’ve now turned our _static_ table into a _dynamic_ table.  
现在我们有了纯文本查询指令，我们可以使用它们来生成我们的默认内容。请注意第 1 步中 parentNode 的值是硬编码的 “Example Acme project”？如果我们确定该条件在指令中的位置并将其替换为（内置）SmartBlock 命令 `<%CURRENTPAGENAME%>` ，那么我们现在已经将静态表变成了动态表。

### **The final result: Supertag functionality in Roam Research  
最终结果：Roam Research 中的 Supertag 功能**

If it feels like it took _a lot_ to get here, keep in the mind the following:  
如果感觉花了很多时间才到达这里，请记住以下几点：

*   This was written for users with little-to-no experience with SmartBlocks or Query Builder.  
    这是为几乎没有 SmartBlocks 或查询生成器经验的用户编写的。
*   As you get more comfortable using SmartBlocks and Query Builder, you can whip up custom workflows crazy fast. Building this workflow only took 10 minutes!  
    随着您越来越习惯使用 SmartBlocks 和查询生成器，您可以疯狂地快速启动自定义工作流程。构建此工作流程仅需 10 分钟！
*   **The final result is a _blazing-fast_ workflow that outputs a new project page with additional fields _and_ a dynamic tasks table in under 30 seconds 🤯  
    最终结果是一个超快的工作流程，可以在 30 秒内输出一个带有附加字段的新项目页面和一个动态任务表🤯**

#### **Visit _The Roam Way_ graph to snag the Project SmartBlock and custom CSS from this article**.  
访问 The Roam Way 图以获取本文中的 Project SmartBlock 和自定义 CSS。

### **Our Project SmartBlock in Action 我们的项目 SmartBlock 在行动**

### **Roam’s SmartBlocks vs Tana Supertags – Which system is best?  
Roam 的 SmartBlocks 与 Tana Supertags——哪个系统最好？**

I use Roam (you’re on a site called theroamway.com), but I’m going to be fair and as objective as possible about how the two platforms compare for this use case.  
我使用 Roam（你在一个名为 theroamway.com 的网站上），但我将尽可能公正客观地比较这两个平台在这个用例中的表现。

**Setup**: **How easy is it to build and configure the supertag functionality?**  
设置：构建和配置超级标签功能有多容易？

Admittedly, the SmartBlock syntax in Roam looks daunting at first. That said, you don’t need to be a high-level programmer to implement SmartBlocks any more than you need to implement _live searches_ in Tana. Both systems allow for the following:  
诚然，Roam 中的 SmartBlock 语法乍一看令人望而生畏。也就是说，您无需成为高级程序员即可实施 SmartBlocks，就像您无需在 Tana 中实施实时搜索一样。两个系统都允许执行以下操作：

*   Mandatory fields
*   Default content
*   Static and dynamic inputs 静态和动态输入

I’m giving Tana the slight edge in this match-up for two reasons: the _supertag_ functionality is built-in to core and doesn’t require plugins. Tana’s interface is likely more approachable for the everyday user.  
我认为 Tana 在这场比赛中略占优势，原因有二：超级标签功能是核心内置的，不需要插件。 Tana 的界面可能更适合日常用户。

Winner: **Tana**

**Features: Which system has the most complete feature-set?  
特性：哪个系统具有最完整的特性集？**

Both systems can handle this _project_ supertag and _tasks-table_ use-case easily, but there are two feature sets unique to Tana that give them a leg-up:  
这两个系统都可以轻松处理这个项目超级标签和任务表用例，但是 Tana 有两个独特的功能集可以帮助他们：

*   Views
    *   The ability and robustness of data querying are similar between the two systems. Tana stands out, however, in how well it handles the output of the data with its built-in views. They’re easy to use, have a highly polished design, and allow for functionality like _post-query grouping_ that you don’t currently get in Roam.  
        两个系统的数据查询能力和健壮性相似。然而，Tana 以其内置视图处理数据输出的能力而脱颖而出。它们易于使用，具有高度完善的设计，并允许您目前在 Roam 中没有的查询后分组等功能。
    *   You can make your Roam tables, lists, and kanbans pretty and highly functional, but it takes some tweaking and custom CSS to get there. Don’t believe me? Here’s a little sneak peek into my next post on [building custom dashboards in Roam](https://theroamway.com/wp-content/uploads/2022/12/Roam-Dashboard.png)  
        您可以使您的 Roam 表、列表和看板变得漂亮且功能强大，但需要一些调整和自定义 CSS 才能实现。不相信我吗？这是我下一篇关于在 Roam 中构建自定义仪表板的帖子的先睹为快
*   Source data
    *   Tana allows for importing data from external graphs, which is excellent if you want to keep things like custom definitions, schema, workflows, or private data separate from your working graph.  
        Tana 允许从外部图表导入数据，如果您想将自定义定义、模式、工作流或私有数据等内容与工作图表分开，这非常有用。

Winner: **Tana**

**Flexibility – What system allows for the most customization?  
灵活性——什么系统允许最多的定制？**

Tana’s supertags have _a lot_ of capabilities that cover probably 99% of use cases. With Tana, however, you are somewhat limited in what the tool allows you to do. In contrast, the Roam + SmartBlocks API will enable you to create, read, update or delete (CRUD) whatever you can imagine and build workflows and commands that are as simple or as complex as you want them to be. Tana’s more approachable (see above) and capable, but Roam + SmartBlocks is limitless.  
Tana 的 supertags 有很多功能，可以覆盖大约 99% 的用例。但是，使用 Tana，您在该工具允许您做的事情上有些受限。相比之下，Roam + SmartBlocks API 将使您能够创建、读取、更新或删除 (CRUD) 您可以想象的任何内容，并构建您想要的简单或复杂的工作流和命令。 Tana 更平易近人（见上文）和能力，但 Roam + SmartBlocks 是无限的。

Winner: **Roam**

**Implementation – What system is the fastest and easiest to use?  
实施——什么系统最快、最容易使用？**

When set up correctly, both systems are relatively easy to use, so this one is close to a draw. What gives Roam a slight leg-up is the natural language processing of dates. That will always be quicker than toggling over to a date picker. This is a 51/49 situation. Both systems are great and can be implemented without touching the mouse.  
如果设置正确，两个系统都相对容易使用，所以这个系统接近平局。使 Roam 略有优势的是日期的自然语言处理。这总是比切换到日期选择器更快。这是一个 51/49 的情况。这两个系统都很棒，无需触摸鼠标即可实现。

Winner: **Roam**

**UX / UI – What’s it like interacting with the SmartBlock / Supertag workflow?  
UX / UI – 与 SmartBlock / Supertag 工作流程交互是什么感觉？**

User experience is a difficult category to be objective about. So much of how you feel about a system comes down to personal preference. I personally like navigating through the workflow prompts in our custom SmartBlock (it’s fast, and I can do it all without touching the mouse), but others may gravitate towards editing inline in their graph. All that said, Tana takes the win here because Tana feels more polished and refined without any customizations.  
用户体验是一个很难客观的类别。您对系统的感受很大程度上取决于个人喜好。我个人喜欢在我们的自定义 SmartBlock 中浏览工作流提示（它很快，我可以在不触摸鼠标的情况下完成所有操作），但其他人可能倾向于在他们的图表中进行内联编辑。总而言之，Tana 在这里取得了胜利，因为 Tana 在没有任何定制的情况下感觉更加精致和精致。

Winner: **Tana**

**Overall – Which system is best?  
总体——哪个系统最好？**

Both workflows are fast. Both allow for an insane level of customization and are backed by helpful and supportive communities. Overall, Tana has some features that, at this time, aren’t easily replicable in Roam (see the _Features_ section above), and I love how refined and polished their default views are. It’s close, but they take the head-to-head by a slight margin (I bet you didn’t see that one coming).  
两种工作流程都很快。两者都允许疯狂的定制水平，并得到乐于助人和支持的社区的支持。总的来说，Tana 有一些功能，目前在 Roam 中不容易复制（参见上面的功能部分），我喜欢他们默认视图的精致和完善。很接近，但他们以微弱优势正面交锋（我敢打赌你没看到那个来了）。

Winner: **Tana**

### **Final thoughts 最后的想法**

Despite what you might have thought when you read the title, this post wasn’t written to bash Tana (Hell, they won the _head-to-head_). That said, it’s easy to get lost in the hype of new tools. I’ve done it personally for Logseq, Obsidian, and Tana. Sometimes the hype has merit, and sometimes it takes a little digging to realize the tool you’re _already_ using can do many of the same things. Sometimes the tool you’re already using can do even more, as you’ll see in future posts.  
尽管您在阅读标题时可能会想到什么，但这篇文章并不是为了抨击塔纳而写的（见鬼，他们赢得了正面交锋）。也就是说，很容易迷失在新工具的炒作中。我亲自为 Logseq、Obsidian 和 Tana 做过。有时炒作是有道理的，有时需要深入挖掘才能意识到您已经在使用的工具可以做很多相同的事情。有时您已经在使用的工具可以做更多的事情，正如您将在以后的帖子中看到的那样。

For those who are head-over-heels in love with Tana, I get it. It’s a fantastic tool with an engaged community. If, like me, you were on the fence about switching because you don’t think Roam can do “X’ thing and tool “Y” can – you should probably stick around and follow The Roam Way on Twitter. We have a lot more content like this coming your way.  
对于那些彻底爱上塔娜的人，我明白了。这是一个拥有参与社区的绝佳工具。如果像我一样，你对转换持观望态度，因为你认为 Roam 不能做 “X” 事情而工具 “Y” 可以 – 你可能应该留下来并在 Twitter 上关注 The Roam Way。我们有更多类似的内容即将到来。

**Next up: Building custom Dashboards in Roam Research  
接下来：在 Roam Research 中构建自定义仪表板**

This post took a while to put together, and I am immensely grateful to anyone who took the time to read it, engage with it or share it. I will talk to you again soon when we build a [custom dashboard in Roam](https://theroamway.com/wp-content/uploads/2022/12/Roam-Dashboard.png)  
这篇文章花了一些时间整理，我非常感谢所有花时间阅读、参与或分享它的人。当我们在 Roam 中构建自定义仪表板时，我会很快再次与您交谈

Reader Interactions
-------------------