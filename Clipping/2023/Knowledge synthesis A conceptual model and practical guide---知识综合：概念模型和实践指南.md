---
created: 2023-02-06T03:39:57 (UTC +08:00)
tags: []
source: https://www.instapaper.com/read/1576447691
author: Joel Chan陈乔尔
---

# Knowledge synthesis: A conceptual model and practical guide

> ## Excerpt
> A simple tool for saving web pages to read later on your iPhone, iPad, Android, computer, or Kindle.

---
> **NOTE (March 10th, 2022): The system in this guide has remained stable and useful since the last release, with some minimal implementation-level tweaks. If it helps, you can view some “game film” [here](https://youtube.com/playlist?list=PLamynaCFSYPHePR9vGMgm0qMc5GtdFNTL). I have also developed an experimental [software extension in RoamResearch](https://oasis-lab.gitbook.io/roamresearch-discourse-graph-extension/) that smooths this process considerably. This extension shows up in the more recent (from late 2021) videos in the game film playlist. 注意（2022 年 3 月 10 日）：本指南中的系统自上次发布以来一直保持稳定和有用，并进行了一些最小的实现级别调整。如果有帮助，您可以在这里观看一些“游戏电影”。我还在 RoamResearch 中开发了一个实验性软件扩展，它大大简化了这个过程。此扩展程序出现在游戏电影播放列表中最近（从 2021 年底开始）的视频中。**
> 
> **This article will be updated soon to reflect these changes. Sooner if there are more requests!本文将很快更新以反映这些变化。如果有更多的要求，会更快！**

## Motivation动机

This document shares a conceptual model and practical approach for knowledge synthesis that I have developed for myself. 本文档分享了我为自己开发的知识综合的概念模型和实用方法。

It is forged in practice, and adapted from other practices, but also with an eye to being as theoretically grounded as possible. Creative knowledge work is my area of research, after all, and knowledge synthesis is an inherently creative act.它是在实践中形成的，并从其他实践中改编而来，但也着眼于尽可能地以理论为基础。毕竟，创造性知识工作是我的研究领域，而知识综合本质上是一种创造性行为。

My initial audience for this document is researchers who struggle with **knowledge synthesis** (aka a “real” literature review"), which is the nebulous “black box” in between这份文件的最初读者是那些努力进行知识综合（又名“真实”文献综述）的研究人员，这是介于两者之间的模糊“黑匣子”

> “I have found a bunch of papers to read” “我找到了一堆论文要读”

and 和

> “I now have synthesized the literature and have a set of promising angles of attack on my research problem”“我现在已经综合了文献，并对我的研究问题有了一套有前途的攻击角度”

This used to include me! I’m still learning, but this approach has really really helped me gain traction on this problem, and learn how to be able to develop this skill further, and pass it on to my students.这曾经包括我！我仍在学习，但这种方法确实帮助我解决了这个问题，并学习如何进一步发展这项技能，并将其传授给我的学生。

My hope is that you, the reader, will be equipped by this document to:我希望您，读者，能够通过这份文件来：

1.  Replicate my system for knowledge synthesis for your own work, should you choose to do so如果您选择这样做，请为您自己的工作复制我的知识综合系统
    
2.  Understand the rationale and theoretical grounding of the system enough to adapt it to the particulars of your context and/or be inspired to develop your own system充分了解系统的基本原理和理论基础，使其适应您的具体情况和/或受到启发开发您自己的系统
    

I suspect this document will be most successful at achieving these goals if you resonate with the challenges I describe below for a synthesis system (ideally by having experienced them!), and have some familiarity with RoamResearch (or related networked notebooks like [Obdisian.md](https://obsidian.md/), [Remnote](https://www.remnote.io/), [TiddlyWiki](https://tiddlywiki.com/), or [Tinderbox](https://www.eastgate.com/Tinderbox/)).我怀疑如果您对我在下面描述的合成系统挑战产生共鸣（最好是体验过它们！），并且对 RoamResearch（或相关的网络笔记本，如 Obdisian.md， Remnote、TiddlyWiki 或 Tinderbox）。

## What is synthesis?什么是综合？

Before we go further, let’s define our target: what is **synthesis?**在我们继续之前，让我们定义我们的目标：什么是综合？

A good place to start is to compare extreme examples:一个好的起点是比较极端的例子：

Here is a “lit review” of observations with no synthesis:这是对没有综合的观察结果的“简单回顾”：

> Species vary: some variations are bad, and some help with survival. Species struggle to survive. Some, but not all, organisms pass on new offspring.物种不同：有些变异是有害的，有些变异有助于生存。物种为生存而斗争。一些（但不是全部）生物体会传递新的后代。

And here is the same set of observations, synthesized:这是同一组观察结果，经过综合：

> Species struggle to survive. Species also vary, and some variations are good and some are bad for survival. Therefore, one precondition for species to survive and pass on offspring is by having or inheriting beneficial variations. This variation and selection process explains how we get the diversity of species we see today.物种为生存而斗争。物种也各不相同，有些变异对生存有利，有些对生存不利。因此，物种生存和传递后代的一个先决条件是拥有或继承有益的变异。这种变异和选择过程解释了我们如何获得今天看到的物种多样性。

You may recognize the topic here: it’s Darwin’s theory of evolution by natural selection! 你可能认得这里的主题：达尔文的自然选择进化论！

Notice how the second example _**creates something new**_, greater than the sum of its parts, namely the explanation for the origin of species. This is a core aspect of synthesis: the _**construction**_ of a new point of view from a set of observations, that directly advances knowledge and/or opens up a path to advancing knowledge.请注意第二个例子是如何创造出比其各部分之和更大的新事物，即对物种起源的解释。这是综合的一个核心方面：从一组观察中构建一个新的观点，直接推进知识和/或开辟一条推进知识的道路。

In this case, the synthesis yielded a _**theory**_, which to me is a paradigmatic example of synthesis. But a good synthesis can also take other forms, such as a critical literature review that leads to a set of powerful new research questions, or a design argument or problem frame.在这种情况下，综合产生了一个理论，对我来说这是综合的一个典型例子。但一个好的综合也可以采取其他形式，例如导致一系列强有力的新研究问题的批判性文献综述，或者设计论证或问题框架。

I won’t belabor this point further, but I do recommend these sources for understanding what synthesis is and what it looks like (and what it does \*not\* look like):我不会进一步强调这一点，但我确实推荐这些资源来理解合成是什么以及它看起来像什么（以及它\*不\*看起来像什么）：

-   [Strike & Posner (1983). Types of synthesis and their criteria.斯特莱克和波斯纳 (1983)。综合类型及其标准。](https://casci.umd.edu/wp-content/uploads/2020/02/Strike_Posner_1983_Types-of-synthesis-and-their-criteria.pdf)
    
-   [Levy & J. Ellis (2006). A Systems Approach to Conduct an Effective Literature Review in Support of Information Systems Research. Informing Science: The International Journal of an Emerging TransdisciplineLevy & J. Ellis (2006)。进行有效文献综述以支持信息系统研究的系统方法。信息科学：新兴跨学科的国际期刊](https://www.informingscience.org/Publications/479)
    
-   [Boote & Beile (2005). Scholars Before Researchers: On the Centrality of the Dissertation Literature Review in Research Preparation. Educational Researcher布特和贝勒 (2005)。研究人员之前的学者：关于论文文献审查在研究准备中的中心地位。教育研究员](http://journals.sagepub.com/doi/10.3102/0013189X034006003)
    
-   [Blake & Pratt (2006). Collaborative information synthesis I: A model of information behaviors of scientists in medicine and public health. Journal of the American Society for Information Science and Technology布莱克和普拉特 (2006)。协同信息综合 I：医学和公共卫生领域科学家的信息行为模型。美国信息科学技术学会杂志](https://onlinelibrary.wiley.com/doi/abs/10.1002/asi.20487)
    
-   [Holbrook (2008). Levels of success in the use of the literature in a doctorate. South African Journal of Higher Education霍尔布鲁克（2008 年）。在博士学位中使用文献的成功程度。南非高等教育杂志](http://www.ajol.info/index.php/sajhe/article/view/25757)
    

Suffice it to say that this kind of intellectual product is what I’m optimizing my system for, to help me do this in a sustainable way. It is my job, after all!我只想说这种智能产品就是我优化系统的目的，以帮助我以可持续的方式做到这一点。毕竟这是我的工作！

## Challenges and desiderata for a synthesis system1Aayush Kucheria合成系统的挑战和需求 1个 阿尤什库切里亚  

Here are some common failure modes for a synthesis system and process that I have experienced and observed in others (not mutually exclusive!):以下是我在其他人中经历和观察到的合成系统和过程的一些常见故障模式（不相互排斥！）：

1.  **Too much detail** (too low-level, missing forest for trees). This manifests as a lack of higher-level synthesis of what a collection of results means. A common manifestation is the “x said this, y said this, z said this” form of literature review.细节太多（太低级，树木不见森林）。这表现为缺乏对结果集合含义的更高层次的综合。一种常见的表现形式是“x说这个，y说这个，z说这个”形式的文献综述。
    
2.  **Too little detail** (too high-level, missing the devil/diamonds in the details). This manifests as overgeneralization of claims, or glossing over critical inconsistencies or contradictions. A good example of this is debates about the role of “children” in COVID-19 transmission that ignore the details of differences between young children (under 10).细节太少（太高级，细节中缺少魔鬼/钻石）。这表现为对主张的过度概括，或掩盖关键的不一致或矛盾。一个很好的例子是关于“儿童”在 COVID-19 传播中的作用的辩论忽略了幼儿（10 岁以下）之间差异的细节。
    
3.  **Insufficient context**. This is related to the lack of details, but separate in that context can also come from connection to other claims: if this is missing, even observation notes can be lost because their significance isn’t recognized.上下文不足。这与缺乏细节有关，但在这种情况下，分离也可能来自与其他主张的联系：如果缺少细节，甚至观察笔记也可能丢失，因为它们的重要性未得到认可。
    
4.  **Information silos.** This manifests in part also due to inordinate detail-orientedness, where important connections across disciplines or topics are ignored. This can also come from too little detail! If results are described at too high a level, we might miss important connections at the subproblem level between problems and results.信息孤岛。这在一定程度上也表现在过分注重细节，忽略了跨学科或主题的重要联系。这也可能来自细节太少！如果在太高的层次上描述结果，我们可能会错过问题和结果之间子问题层次上的重要联系。
    
5.  **Information overload**. There are often too many papers to read and process in a rigorous and iterative way, which leads to / exacerbates the preceding set of problems!信息超载。经常有太多的论文无法以严谨和迭代的方式阅读和处理，这导致/加剧了前面的一系列问题！
    

I won’t spend too much more space here to give fully fleshed out concrete examples of this for this release, but if you recognize/resonate with these, then this document is for you!我不会在这里花太多篇幅来为这个版本提供充分充实的具体示例，但如果您认可/对此产生共鸣，那么本文档就是为您准备的！

This is a future that I want: a research group can confidently aim their sights at a complex, interdisciplinary problem area, and construct an effective synthesis together with minimal "busywork overhead”: they can just focus on the core task of synthesis, instead of fighting to extract the “trapped data” (Knight, Wilson, Brailsford, & Milic-Frayling, 2019) in PDFs and long documents! The results _and_ intermediate products of their synthesis work also provide a stronger foundation for themselves and others in the future to build on.这是我想要的未来：一个研究小组可以自信地将他们的目光投向一个复杂的、跨学科的问题领域，并以最小的“繁琐开销”构建一个有效的综合：他们可以只专注于综合的核心任务，而不是努力提取 PDF 和长文档中的“陷阱数据”（Knight, Wilson, Brailsford, & Milic-Frayling, 2019）！他们综合工作的结果和中间产品也为他们自己和其他人将来提供更强大的基础建立在。

For this to be true, we need a system that helps us **achieve a generative dialectic** between compression/divergence/abstraction/theory and context/convergence/particulars/data. We also need the system to enable us to **accrete insight over boundaries of time and projects/disciplines**. We don't always have the luxury of being able to devote (funded) time and attention at an intense level for a given project. We often have multiple irons in the fire (good for creativity), and we often want to reuse and remix ideas from the past (Blake & Pratt, 2006). Finally, we need the system to enable us to **distribute work across multiple people**. There are just too many papers for any one person to absorb by themselves!为了实现这一点，我们需要一个系统来帮助我们在压缩/发散/抽象/理论和上下文/收敛/细节/数据之间实现生成辩证法。我们还需要该系统使我们能够在时间和项目/学科的边界上积累洞察力。我们并不总是能够为给定的项目投入（资助的）时间和注意力。我们经常有多个熨斗在火中（有利于创造力），我们经常想重复使用和重新混合过去的想法（Blake & Pratt，2006）。最后，我们需要该系统使我们能够在多人之间分配工作。论文太多了，任何人都无法自己吸收！

In the next section, I’ll start to describe a conceptual model I’ve found helpful for thinking about and implementing a synthesis system that meets these requirements. I also describe in detail how I implement this in my own work, with hopefully enough detail that you, the reader, can try it out. In later releases, I will also add some discussions of open problems and ideas for improving the system.在下一节中，我将开始描述我发现有助于思考和实施满足这些要求的综合系统的概念模型。我还详细描述了我如何在自己的作品中实现这一点，希望有足够的细节让读者可以尝试一下。在以后的版本中，我还会添加一些对未解决问题的讨论和改进系统的想法。

## The conceptual model概念模型

## “Data model”“数据模型”

In this model, we create and update four basic kinds of entities in the synthesis process: 在这个模型中，我们在合成过程中创建和更新四种基本类型的实体：

1.  **Question** notes, which express an open research question,1Sean Vosler问题笔记，表达了一个开放的研究问题， 1个 肖恩沃斯勒  
    
2.  **Synthesis** notes, which express a single, generalized idea, such as a claim,综合笔记，它表达了一个单一的、概括的想法，比如一个主张，
    
3.  **Observation** notes, which express a single, highly contextualized and specific observation that, together with other observation notes, can form the basis of a synthesis note, and观察笔记，它表达了一个单一的、高度语境化的和具体的观察，与其他观察笔记一起，可以构成综合笔记的基础，以及
    
4.  **Context snippet** notes, which help to ground and contextualize observation notes.语境片段笔记，这有助于将观察笔记作为基础和语境化。
    

Let’s consider each kind of entity in a bit more detail.让我们更详细地考虑每种实体。

### QUESTION notes问题笔记

Question notes express an open question (e.g., _“What is the effect of analogical distance of inspirations on creative output?”_). They can be readily mapped to research questions in research projects.问题笔记表达了一个开放性问题（例如，“灵感的类比距离对创意输出的影响是什么？”）。它们可以很容易地映射到研究项目中的研究问题。

### SYNTHESIS notes综合笔记

Synthesis notes articulate a single, generalized idea, such as a claim (e.g., _“Inspirations that are of intermediate distance from the problem domain strike the best balance between benefits for novelty and quality of ideas”_). In some cases, a synthesis note can encapsulate a more complex single idea, such as a theory (e.g., _“Darwinian theory of evolution by natural selection”_), high level argument (_“Scientific observations are theory-laden”_) or problem (e.g., _“The demarcation problem in philosophy of science”_)综合笔记阐明了一个单一的、概括的想法，例如一个主张（例如，“与问题领域处于中间距离的灵感在新颖性和想法质量之间取得了最佳平衡”）。在某些情况下，综合笔记可以包含一个更复杂的单一想法，例如理论（例如，“达尔文自然选择进化论”）、高层次论证（“科学观察充满理论”）或问题（例如, “科学哲学中的分界问题”)

By generalized, we mean that synthesis notes should aim at something that is true of an _equivalence class_ of instances instead of expressing a bounded statement about a single instance. 1Qi Zhang概括地说，我们的意思是综合笔记应该针对实例的等价类的真实情况，而不是表达关于单个实例的有界陈述。 1个 张琪  

Synthesis notes can be mapped to citation statements in academic publications, which are typically generalized and drawing on more than a single source. They are also similar in flavor to “claims” in the micropublications model (Clark, Ciccarese, & Goble, 2014) (although it can encompass more complex things than a simple assertion), and “permanent notes” in the Zettelkasten method.综合笔记可以映射到学术出版物中的引用声明，这些声明通常是概括的并且借鉴了多个来源。它们在风格上也类似于微型出版物模型中的“声明”（Clark、Ciccarese 和 Goble，2014 年）（尽管它可以包含比简单断言更复杂的事物）和 Zettelkasten 方法中的“永久注释”。

### OBSERVATION notes观察笔记

Observation notes articulate a single, highly contextualized observation (e.g., _“the finches on the island had different colored beaks after two generations”_). 观察笔记阐明了一个单一的、高度背景化的观察结果（例如，“岛上的雀类在两代之后有不同颜色的喙”）。

By contextualized, we mean that observation notes should tend towards being bounded in the particulars of time, authorship, and setting, as opposed to trying to describe a generalized claim that holds over an equivalence class (that is the function of synthesis notes). The intuition is that observation notes should be as close to “the data” as possible. They should be similar to how results are described in results sections of academic publications.通过语境化，我们的意思是观察笔记应该倾向于受时间、作者身份和背景等细节的限制，而不是试图描述一个适用于等价类的概括性主张（这是综合笔记的功能）。直觉是观察笔记应该尽可能接近“数据”。它们应该类似于学术出版物结果部分中描述结果的方式。

By convention, we write them in the past tense (to ground them in _time_), bind them to an assertor where possible (to ground them in the standpoint of the author), and tend towards lower levels of abstraction (to ground them in relevant particulars).按照惯例，我们用过去时来写它们（以时间为基础），尽可能将它们绑定到断言者（以作者的立场为基础），并倾向于较低层次的抽象（以相关的方式为基础）细节）。

Observation notes can be mapped to “literature notes” in the Zettelkasten method, or “lines of evidence” in models of scholarly argumentation like the SEPIO model (Brush, Shefchek, & Haendel, 2016)观察笔记可以映射到 Zettelkasten 方法中的“文献笔记”，或学术论证模型（如 SEPIO 模型）中的“证据线”（Brush、Shefchek 和 Haendel，2016 年）  

### CONTEXT SNIPPET notes上下文片段注释

Context snippet notes capture (and optionally describe) contextual details that ground the observation notes. 上下文片段笔记捕获（并可选地描述）作为观察笔记基础的上下文细节。

Contextual details is a broad term, but generally includes things like specific figures, data items, tables, or quotes that are the basis for an observation, as well as metadata (e.g., authors, year, publication) and methodological details that are important for understanding and evaluating an observation note.上下文细节是一个广义术语，但通常包括作为观察基础的特定数字、数据项、表格或引述，以及元数据（例如，作者、年份、出版物）和对观察很重要的方法细节。理解和评价观察笔记。

As a practical matter, I’ve found it more useful to use screenshots as context snippets, rather than plain text grabs. I find that this gives me the freedom to be a bit more sloppy and inclusive in the context of the quote (vs. very precisely specifying something), easier handling of images/figures/tables, and forces me to redescribe the context snippet, which enhances comprehension and recall. I also don’t need to waste time fixing up text (OCR mistakes, formatting, etc.)1!1adam KLEIN实际上，我发现使用屏幕截图作为上下文片段比纯文本抓取更有用。我发现这让我可以自由地在引用的上下文中更加草率和包容（与非常精确地指定某些东西相比），更容易处理图像/数字/表格，并迫使我重新描述上下文片段，这增强理解力和记忆力。我也不需要浪费时间修复文本（OCR 错误、格式等）1！ 1个 亚当·克莱因  

### Relationship between entities实体之间的关系

Here is a visual diagram of the entities and how they relate to each other to form a system for synthesis.这是实体的可视化图表以及它们如何相互关联以形成综合系统。

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6Im1rcGZwdjB2LzExNjA4MzA2MjIwMzM2LnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6MTYwMCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

There is a hierarchical relationship between the artifacts: **question** and **synthesis** notes (at the top "layer") are supported/opposed/informed by one or more **observation** notes (at the middle "layer"), which are substantiated/contextualized by one or more **context snippet** notes (at the bottom "layer"). 工件之间存在层次关系：问题和综合笔记（在顶部“层”）由一个或多个观察笔记（在中间“层”）支持/反对/告知，这些笔记由一个或更多上下文片段注释（在底部的“层”）。

Synthesis notes can also be composed into more complex structures (such as arguments or theories or models) through relations with other synthesis notes that vary in complexity from simple "relates to", to implication/explanation and support/opposition.综合笔记也可以通过与其他综合笔记的关系组成更复杂的结构（例如论证或理论或模型），这些综合笔记的复杂程度从简单的“相关”到暗示/解释和支持/反对不等。

From a practical standpoint, it’s probably most important to implement the typed distinction between entities (synthesis vs. observation vs. context snippet); typed distinctions between relations could significantly enhance the system's ability to augment human synthesis, but significant boosts in synthesis will likely accrue with implementation of only the three distinct artifacts (without explicit typed distinctions between relations). 1Asif Mehedi从实际的角度来看，实现实体之间的类型区分可能是最重要的（综合与观察与上下文片段）；关系之间的类型化区分可以显着增强系统增强人类综合的能力，但是仅实现三个不同的工件（关系之间没有明确的类型化区分）可能会显着提高综合能力。 1个 阿西夫·梅赫迪  

Thus, a minimal implementation of our model will include distinctions between the three types of entities, and explicit (but optionally typed) links between them.因此，我们模型的最小实现将包括三种类型实体之间的区别，以及它们之间的显式（但可选类型化）链接。

## Some examples一些例子

This discussion has been quite abstract. Let’s see how this conceptual model plays out with some examples. These are concrete, real examples from my own work (one personal, trying to figure out some decisions regarding COVID, which requires synthesis, and two from my own research projects).这个讨论已经很抽象了。让我们通过一些例子看看这个概念模型是如何发挥作用的。这些是我自己工作中的具体、真实的例子（一个是个人的，试图找出一些关于 COVID 的决定，这需要综合，两个是我自己的研究项目）。

Note: while synthesis notes should, whenever possible, be supported/opposed by multiple observation notes, for simplicity here I will only show a single thread through from context snippet to observation to question/synthesis.注意：虽然综合笔记应该尽可能由多个观察笔记支持/反对，但为了简单起见，我在这里只展示从上下文片段到观察再到问题/综合的单一线程。

### Understanding COVID-19 transmission risks with children1Asif Mehedi了解儿童的 COVID-19 传播风险 1个 阿西夫·梅赫迪  

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6ImZnNHdxOW0wLzAxNjA3NDYyMzY4NzczLnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6MTYwMCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

In this example, we have:在这个例子中，我们有：

1.  A **synthesis** note that _“Children are approximately half as likely to contract COVID given equivalent exposure”_综合说明“在同等暴露条件下，儿童感染 COVID 的可能性大约是其一半”
    
2.  An **observation note** from a paper (Somekh et al., 2020) that _“in an exhaustive contact tracing study of 13 families in Central Israel, the COVID secondary attack rates for children < 10yo was ~2x lower than adults”._ This observation note supports the synthesis note.一篇论文的观察记录（Somekh 等人，2020 年）指出，“在对以色列中部 13 个家庭进行的详尽的接触者追踪研究中，10 岁以下儿童的 COVID 二次发病率比成人低约 2 倍”。该观察笔记支持综合笔记。
    
3.  Three **context snippets**, including a screenshot of the raw descriptive results and test statistics for the differences between age groups, one context snippet about the exhaustive testing regime (i.e., regardless of symptoms), and the number of participants and setting. These context snippets ground the observation note, and are extracted from the paper’s PDF.三个上下文片段，包括原始描述性结果的屏幕截图和年龄组之间差异的测试统计数据，一个关于详尽测试制度（即不考虑症状）的上下文片段，以及参与者的数量和设置。这些上下文片段以观察笔记为基础，并从论文的 PDF 中提取。
    

This bundle of synthesis, observation, and context snippet notes is embedded in a larger network of synthesis/observation/context notes that is focused on understanding the risk of reopening schools for elementary school-aged children (a personal concern of mine!). The following figure demonstrates this. The focal synthesis note we just discussed is highlighted in bold.这组综合、观察和上下文片段注释被嵌入到一个更大的综合/观察/上下文注释网络中，该网络侧重于了解为小学适龄儿童重新开学的风险（我个人关心的问题！）。下图演示了这一点。我们刚刚讨论的焦点综合注释以粗体突出显示。

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6ImNiY3c4Y3F2LzMxNjA3NDYyNzg2NzI2LnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6MTYwMCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

Finally, let me illustrate how this is instantiated in RoamResearch, which provides many rich affordances for linking granular information items. 最后，让我说明一下这是如何在 RoamResearch 中实例化的，它提供了许多丰富的功能可供链接粒度信息项。

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6IngxYWFubGo4LzAxNjA3NDYxODI3NTEwLnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6MTYwMCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

Here, the focal synthesis note is instantiated as a page. 在这里，焦点综合笔记被实例化为一页。

The observation note about secondary attack rates is _transcluded_ into (via block reference, and therefore a _part-of_) the synthesis page. 关于二次攻击率的观察记录被包含在（通过块引用，因此是一部分）综合页面中。

The context snippets are linked to the observation note via indentation in the outline as well as via hyperlinks to their block references, all of which create explicit bi-directional links in the underlying database between the items. Note here also how one of the context snippets includes a crucial detail that the testing regime was exhaustive (regardless of symptoms), which lends additional strength to the observation and how it might support a more informed synthesis claim about COVID transmission risks for children.上下文片段通过大纲中的缩进以及到它们的块引用的超链接链接到观察笔记，所有这些都在项目之间的基础数据库中创建明确的双向链接。此处还要注意其中一个上下文片段如何包含一个关键细节，即测试制度是详尽无遗的（无论症状如何），这为观察提供了额外的力量，以及它如何支持关于儿童 COVID 传播风险的更明智的综合声明。

Both observation notes and context snippets are also _part-of_ a page dedicated to the particular paper from which they came. In this way, other metadata such as the authors, institutions, year of publication, as well as high-level observations about the paper’s context (e.g., number of citations, status as preprint or peer-reviewed) are also explicitly available as context for the observation note.观察笔记和上下文片段也是专门针对它们所来自的特定论文的页面的一部分。通过这种方式，其他元数据，如作者、机构、出版年份，以及对论文背景的高级观察（例如，引用次数、预印本或同行评审状态）也可明确用作论文的背景观察笔记。

### Understanding whether/how deep learning models of language might enable us to model analogical similarity了解语言的深度学习模型是否/如何使我们能够模拟类比相似性

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6IjM4dDRmMmNzLzcxNjA3NDY0MTMyMDI1LnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6MTYwMCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

In this example, we have:在这个例子中，我们有：

1.  A **question** note, asking _“Can deep learning really discover analogical representations?”._ 一个问题笔记，询问“深度学习真的能发现类比表征吗？”。
    
2.  A **synthesis** note, that “_Vector-space models of language struggle with relational similarity”,_ which informs the question note.一个综合注释，即“语言的向量空间模型与关系相似性斗争”，它为问题注释提供了信息。
    
3.  An **observation note** from a paper (Schwartz, Reichart, & Rappoport, 2016) that a _“skip-gram model with vanilla BOW contexts performed ~50% worse on verbs compared to nouns and adjectives in terms of predicting human similarity judgment son SimLex999”._ This observation note supports the synthesis note.一篇论文（Schwartz、Reichart 和 Rappoport，2016 年）的观察笔记指出，“在预测人类相似性判断 son SimLex999 方面，与名词和形容词相比，具有普通 BOW 上下文的 skip-gram 模型在动词上的表现要差 ~50%”。该观察笔记支持综合笔记。
    
4.  Three **context snippets**, including a screenshot of the raw descriptive results, one context snippet with details about the model, and one context snippet with details about the similarity judgments task. These context snippets ground the observation note, and are extracted from the paper’s PDF. Note that the last observation is crucial for interpreting this result, since in technical terms, association and similarity are quite different (e.g., sit and stand are associated, but not similar), and tests of association may not reveal quite as stark of a difference in performance.三个上下文片段，包括原始描述性结果的屏幕截图，一个包含模型详细信息的上下文片段，以及一个包含相似性判断任务详细信息的上下文片段。这些上下文片段以观察笔记为基础，并从论文的 PDF 中提取。请注意，最后的观察对于解释此结果至关重要，因为在技术术语中，关联和相似性是完全不同的（例如，坐和站是相关的，但不相似），并且关联测试可能不会揭示出如此明显的差异在性能上。
    

### Understanding how the setup details of a participatory design influence how inclusive it is了解参与式设计的设置细节如何影响它的包容性

![](https://resize-v3.pubpub.org/eyJidWNrZXQiOiJhc3NldHMucHVicHViLm9yZyIsImtleSI6InR5MmpnM2thLzUxNjA3NDY0NjE2OTgyLnBuZyIsImVkaXRzIjp7InJlc2l6ZSI6eyJ3aWR0aCI6Mzg0MCwiZml0IjoiaW5zaWRlIiwid2l0aG91dEVubGFyZ2VtZW50Ijp0cnVlfX19)

In this example, we have:在这个例子中，我们有：

1.  A **question** note, asking _“What tension points exist in the quest for greater inclusion in participatory design?”._ Note that in the page here, there is the beginning of a synthesis note, to the effect of _“There may be unhelpful associations with some of the \*materials\* that are typically used in design sessions, such as crayons and sticky notes”_. However, I have refrained from making this a synthesis note proper until I see it show up in at least one other observation note, so I can write a sharper note. This choice also reflects the relatively early stage of this inquiry. More on this later when I talk about the process.一个问题说明，询问“在寻求更大程度地参与参与式设计时存在哪些紧张点？”。请注意，在此处的页面中，有一个综合注释的开头，其效果是“可能与一些通常在设计会话中使用的\*材料\*有无益的关联，例如蜡笔和便利贴”。但是，在我至少看到它出现在其他观察笔记中之前，我一直没有将其作为综合笔记，这样我就可以写出更清晰的笔记。这个选择也反映了这个查询的相对早期阶段。稍后当我谈论这个过程时会详细介绍这一点。
    
2.  An **observation note** from a paper (Harrington, Erete, & Piper, 2019) that _“Codesign participants said that the ideation materials used for the brainstorming sessions (e.g., markers, colored pencils, sketching paper) felt “infantilizing and belittling” and incongruent with the seriousness of their problems”._ This observation note supports the draft synthesis note, but also stands by itself as a possible answer to the question note.一篇论文（Harrington、Erete 和 Piper，2019 年）的观察笔记指出，“协同设计参与者表示，用于头脑风暴会议的构思材料（例如，记号笔、彩色铅笔、素描纸）让人感觉“幼稚和轻视”并且与他们问题的严重性”。这份观察笔记支持综合笔记草案，但它本身也可以作为对问题笔记的可能答案。
    
3.  Two **context snippets**, including a screenshot of the quotes from the participants, and one context snippet with details about the co-design setting and participants. These context snippets ground the observation note, and are extracted from the paper’s PDF. Here, both context snippets are especially crucial for me, since I am relatively new to this topic, and the core observation here depends on a \*lot\* of rich qualitative details that I would be foolish to lose.两个上下文片段，包括参与者引述的屏幕截图，以及一个包含有关协同设计设置和参与者详细信息的上下文片段。这些上下文片段以观察笔记为基础，并从论文的 PDF 中提取。在这里，这两个上下文片段对我来说都特别重要，因为我对这个话题还比较陌生，而且这里的核心观察取决于\*很多\*丰富的定性细节，如果我丢失这些细节，那将是愚蠢的。
    

This example illustrates how this approach can start to generalize from more quantitative empirical work. In later releases, I will discuss how other genres of research, such as formal modeling, simulations, philosophical arguments, and case studies, might also be instantiated in this model. My short answer for now is that they can.这个例子说明了这种方法如何从更多的定量实证工作中开始推广。在以后的版本中，我将讨论其他类型的研究，例如正式建模、模拟、哲学论证和案例研究，也可能在此模型中实例化。我现在的简短回答是他们可以。

## Process过程

How does the model play out in my _**process**_ of synthesis?该模型在我的综合过程中如何发挥作用？

At a high level, I begin with 在高层次上，我从

> a set of question notes and papers一组问题笔记和论文

and end with 并以

> a network of synthesis notes grounded in observation notes that are themselves grounded in context snippet notes, and (usually) one or more new compelling question or synthesis notes that are not as well supported by observation notes and may be contradictory in some interesting ways. These indicate promising next steps for research.以观察笔记为基础的综合笔记网络，这些笔记本身以上下文片段笔记为基础，以及（通常）一个或多个新的引人注目的问题或综合笔记，这些问题或综合笔记没有得到观察笔记的支持，并且在某些有趣的方面可能相互矛盾。这些表明有希望的下一步研究。

There is forward progression in this model, but the process in between is iterative and nonlinear. It goes roughly as follows.在这个模型中有前向进展，但中间的过程是迭代的和非线性的。大致如下。

### Phase 1: Articulate question notes. 第 1 阶段：阐明问题笔记。

Every project is aimed at one or more high level research questions. These questions are expressed as question notes. 每个项目都针对一个或多个高级研究问题。这些问题以问题注释的形式表示。

These questions frames how I collect and process papers: every paper is considered or read with these key questions in mind2.这些问题构成了我收集和处理论文的方式：在考虑或阅读每篇论文时都会牢记这些关键问题2。

### Phase 2: Create observation notes from papers. 第 2 阶段：根据论文创建观察笔记。

Next, I select and read sources (e.g., papers, books, early reports of data from colleagues) that have the potential to inform one or more questions of interest. 接下来，我选择并阅读有可能为一个或多个感兴趣的问题提供信息的资源（例如，论文、书籍、同事的早期数据报告）。

Reading will produce a variety of scratch notes and annotations, but should culminate in one or more observation notes that inform question notes. 阅读会产生各种各样的草稿笔记和注释，但最终应该形成一个或多个观察笔记，这些观察笔记为问题笔记提供信息。

These observation notes are grounded in at least one context snippet note, and explicitly linked to relevant question notes3. 这些观察笔记至少基于一个上下文片段笔记，并明确链接到相关问题笔记 3。

### Phase 3: Develop synthesis notes. 第 3 阶段：开发综合笔记。

As I begin to accumulate observation notes4, I can then begin to articulate synthesis notes: what does the literature have to say about my questions of interest? Synthesis notes get explicitly linked to the relevant question note. 当我开始积累观察笔记 4 时，我就可以开始清晰地表达综合笔记：文献对我感兴趣的问题有什么看法？综合笔记明确链接到相关的问题笔记。

The process of developing synthesis notes is iterative with the previous phase. As interesting claims surface, I sometimes return to previous papers2Evan Miyazono, Karola Kirsanow, or collect new papers, to stress test the ideas and find points of uncertainty. Revisiting papers and collecting new ones in turn often spawns new observation notes. These new observation notes then may also in turn spawn yet more question or synthesis notes. The process of refining and juxtaposing synthesis notes may also spur refinement of observation notes (e.g., sharpening a description, adding context snippets that turn out to be important), or new question notes.开发综合笔记的过程与前一阶段是迭代的。随着有趣的声明浮出水面，我有时会回到以前的论文 2个 埃文·宫园，卡罗拉·科萨诺 ，或收集新论文，以对想法进行压力测试并找到不确定点。依次回顾论文和收集新论文通常会产生新的观察笔记。然后，这些新的观察笔记也可能反过来产生更多的问题或综合笔记。提炼和并列综合笔记的过程也可能会刺激观察笔记的提炼（例如，加强描述，添加事实证明很重要的上下文片段）或新的问题笔记。

### Phase 4: Compose synthesis notes into arguments or theories 第 4 阶段：将综合笔记写成论据或理论

The process culminates as I compose these synthesis notes into arguments or theories for my high-level question(s) of interest. 当我将这些综合笔记撰写成我感兴趣的高级问题的论据或理论时，该过程达到高潮。

If done well, this process reveals further, sharpened question notes that lack satisfactory answers from the literature. Operationally, in this model, these question notes would be ones that cannot be traced to a sufficient critical mass of observation notes, or ones where there are multiple competing synthesis notes that require additional data to resolve. These would signal high-value directions to explore next to maximize knowledge gain.如果做得好，这个过程会揭示进一步的、尖锐的问题笔记，而这些问题笔记缺乏来自文献的令人满意的答案。在操作上，在这个模型中，这些问题笔记将是无法追溯到足够临界质量的观察笔记的问题，或者是存在多个需要额外数据才能解决的竞争综合笔记的问题笔记。这些将标志着下一步要探索的高价值方向，以最大限度地增加知识增益。

Note also that this phase is likely to be iterative with the previous two steps: as a higher-level argument or theory begins to emerge, I will discover, or seek to discover, points of weakness or uncertainty, and dive back down to reconsider and refine synthesis and observation notes to further develop the argument or theory.另请注意，此阶段可能与前两个步骤重复：随着更高层次的论点或理论开始出现，我将发现或寻求发现弱点或不确定性，然后潜入重新考虑和完善综合和观察笔记以进一步发展论点或理论。

These compositions of synthesis notes can be encapsulated into complex synthesis notes (if I think I might want to reuse the whole package), or simply collated together in the body of a question note.这些综合笔记的组成可以封装到复杂的综合笔记中（如果我认为我可能想重复使用整个包），或者简单地在问题笔记的正文中整理在一起。

Frequently, these compositions will also inform the drafting of a research argument, components of a research proposal, or other shareable scholarly artifact, expressed externally (e.g., in a pubpub draft, LaTeX document, or otherwise). Alternatively, the composition could also form the basis of a contribution its 1Asif Mehediown right, as a published review/synthesis paper, or theoretical paper.通常，这些作品还会为研究论点、研究提案的组成部分或其他可共享的学术成果的起草提供信息，这些成果在外部表达（例如，在 pubpub 草稿、LaTeX 文档或其他方式中）。或者，该组合物也可以构成其贡献的基础 1个 阿西夫·梅赫迪 自己的权利，作为已发表的评论/综合论文或理论论文。

## Practical guide实用指南

I believe this model and process can be (at least in principle) implemented with three things:我相信这个模型和过程可以（至少在原则上）通过三件事来实现：

1.  A PDF reader一个PDF阅读器
    
2.  A reference manager (to make it easier to capture and manage metadata)参考管理器（以便更轻松地捕获和管理元数据）
    
3.  A networked notebook, such as RoamResearch, Obsidian, Tiddlywiki, RemNote, Notion, or any tool that implements bi-directional linking (some other pointers [here](https://github.com/prathyvsh/networked-notebooks)).联网笔记本，例如 RoamResearch、Obsidian、Tiddlywiki、RemNote、Notion 或任何实现双向链接的工具（此处提供一些其他提示）。
    

As I note above, I am implementing this conceptual model and process in the software RoamResearch, with some support from Zotero, and regular PDF reader. In upcoming releases, I may share here how I do this in more detail5.正如我在上面提到的，我在软件 RoamResearch 中实现了这个概念模型和过程，并得到了 Zotero 和常规 PDF 阅读器的一些支持。在即将发布的版本中，我可能会在这里更详细地分享我是如何做到这一点的。

But for now, here is a video of a synthesis session to get started, where I write observation notes from a paper, and use the resulting ideas to develop a synthesis note (in this case a question that was described ): 但就目前而言，这是一个综合会议的视频，可以开始，我从论文中写下观察笔记，并使用由此产生的想法来开发一个综合笔记（在这种情况下是上面描述的问题）：

<iframe src="https://www.youtube.com/embed/uUF0XWk0bns?feature=oembed"></iframe>

Knowledge synthesis session in RoamResearch | 2020-11-28

RoamResearch 中的知识综合会议 | 2020-11-28

##   
What does this model buy us?这个模型给我们带来了什么？

I want to test these claims more rigorously (that is in part why I’m sharing this document!), but here are some benefits that theory predicts and/or I’ve experienced personally. In later releases I will flesh out the conceptual and theoretical basis for this model more fully.我想更严格地检验这些说法（这也是我分享这份文件的部分原因！），但这里有一些理论预测的和/或我亲身经历过的好处。在以后的版本中，我将更全面地充实该模型的概念和理论基础。

## Effective synthesis有效合成

This model allows for rich layers of context to aid synthesis.该模型允许丰富的上下文层来帮助综合。

Distinguishing between observation notes and synthesis notes helps prevent me from rushing too quickly to generalizations, and allows for careful, nuanced questioning of past claims (e.g., does X really not work?), and consideration of possible syntheses between opposing claims. Directly including context snippets also allows me to have crucial details “on hand” that are necessary for this nuanced questioning. 区分观察笔记和综合笔记有助于防止我过快地进行概括，并允许对过去的主张进行仔细、细致的质疑（例如，X 真的不起作用吗？），并考虑对立主张之间可能的综合。直接包括上下文片段也让我“手头上”有关键细节，这些细节对于这种细微的提问是必要的。

In this way, the conceptual and process model helps mitigate the core challenge of lossy compression or premature ossification. Writing a synthesis note involves abstraction, which is a form of compression: removing details to generalize. If this is done in a way that breaks connections with the details (e.g., by writing a note without referencing even a page number, or even functionally breaking the reference by simply noting the bibliographic source), this compression is lossy. I believe compression that is more lossy or descriptions that are more reified are ok at much later stages of knowledge production, where there is sufficiently high confidence in the articulation and certainty of those ideas. But I suspect this is rare when working on hard, creative, open-ended knowledge problems like in research!通过这种方式，概念和过程模型有助于减轻有损压缩或过早僵化的核心挑战。撰写综合笔记涉及抽象，这是一种压缩形式：删除细节以进行概括。如果这样做的方式会破坏与细节的联系（例如，在不引用页码的情况下写注释，或者甚至通过简单地注明书目来源在功能上破坏引用），则这种压缩是有损的。我相信在知识生产的后期阶段，有更多损失的压缩或更具体化的描述是可以的，在这些阶段对这些想法的清晰度和确定性有足够高的信心。但我怀疑在像研究这样艰苦的、创造性的、开放式的知识问题上工作时，这种情况很少见！

So my belief is that knowledge synthesis is severely hampered by lossy compression. This relates to Strike and Posner’s (1983) observation that an effective synthesis clarifies and resolves, rather than obscures, inconsistencies and tensions between material synthesized.所以我认为有损压缩严重阻碍了知识合成。这与 Strike 和 Posner (1983) 的观察有关，即有效的综合澄清和解决，而不是模糊，综合材料之间的不一致和紧张。

## Reusability of ideas across barriers of time, people, projects, and disciplines跨越时间、人员、项目和学科障碍的想法的可重用性

I believe this flexible compression not only helps synthesis right now, but also enables me to earn compound interest on the notes over time. One mechanism by which this happens is that the overhead for regaining context for my notes is reduced for my future self, and possibly for others as well, since the details are much more directly accessible through the three-part model. This is important, because the devil/diamond is in the details, and details fade over time from memory. I suspect that synthesis notes and systems that omit details (or at least make it hard to access details later), will have a much shorter half-life.我相信这种灵活的压缩不仅有助于现在的合成，而且还能让我随着时间的推移从音符上赚取复利。发生这种情况的一种机制是，为我未来的自己（可能也为其他人）减少了为我的笔记重新获得上下文的开销，因为通过三部分模型可以更直接地访问详细信息。这很重要，因为魔鬼/钻石在细节中，随着时间的推移，细节会从记忆中消失。我怀疑省略细节（或至少使以后难以访问细节）的合成笔记和系统的半衰期会短得多。

A less obvious benefit of retaining context is an increased capacity to notice points for intellectual progress, since anomalies and inconsistent results can often be a pointer to where a conceptual breakthrough is most needed (see, e.g., Kuhn’s ideas about scientific revolutions). I can also question results more readily, and/or remix ideas for different settings.保留上下文的一个不太明显的好处是提高了注意智力进步点的能力，因为异常和不一致的结果通常可以指示最需要概念突破的地方（例如，参见库恩关于科学革命的想法）。我还可以更轻松地质疑结果，和/或针对不同的设置重新混合想法。

I view the time I take to write notes in this structure in this way: instead of making one-off purchases, I am trying to amortize the cost of sensemaking by making investments that can pay off over time.我以这种方式看待我在这种结构中写笔记所花的时间：我不是一次性购买，而是试图通过可以随着时间的推移获得回报的投资来分摊意义建构的成本。

Note: For shorter-term or one-off cases, a lightweight version of what I describe here, like a [synthesis matrix](https://guides.library.vcu.edu/ld.php?content_id=1720465), is probably ok.注意：对于短期或一次性案例，我在这里描述的轻量级版本，如综合矩阵，可能就可以了。

## The ability to distribute the synthesis process分发合成过程的能力

If I’m right that these sorts of notes are more shareable, then I should be able to distribute the process across a team of people. Hopefully this also means we get to substantially reduce the time needed to do effective synthesis1Samuel Klein. I am testing this hypothesis right now with my lab, and hope to get others to join me. Stay tuned on this!如果我是对的，这些类型的笔记更容易分享，那么我应该能够将这个过程分配给一个团队。希望这也意味着我们可以大大减少进行有效合成所需的时间 1个 塞缪尔·克莱因 .我现在正在我的实验室测试这个假设，并希望让其他人加入我的行列。敬请期待！
