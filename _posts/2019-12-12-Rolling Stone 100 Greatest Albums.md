---
layout: post
title:  "Tableau仪表盘设计 —— 滚石：史上最伟大的100张专辑"
author: willa
image: "https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/rollingstone1.png"
category: [ 可视化 ]
featured: false
---

"__可视化的核心不在于靓丽的视觉设计，而在于传递信息的效率。__"
 
 <br />
 <br />

## Tableau仪表盘设计 —— 滚石：史上最伟大的100张专辑

这个仪表盘是我硕士期间 Data Visualization 课的期终作业。主题是我出于摇滚爱好者的私心选择的，通过可视化仪表盘展示滚石评出的“史上最伟大的100张摇滚专辑”。

我花了整2天的时间，进行数据处理，仪表盘设计和可视化实现。在这个过程中，我刻意尝试了许多平时接触不到的图表形式（如`甜甜圈图`），视觉美化（如叠加在柱形图上的`音符标志`），交互形式（如`仪表盘的Tab切换`，`专辑图片的显示切换`）。
整个过程在探索和钻研中充满（与Tableau玩耍的）乐趣与（安利喜欢的摇滚乐队的）自豪。

唯一可惜的是，这份最终作业交上去并没获得优异的成绩。但是在和老师深入沟通后，我学到了可视化最重要的理念：__可视化的核心不在于靓丽的视觉设计，而在于传递信息的效率。__



[仪表盘公布在 Tableau Public](https://public.tableau.com/profile/willa.yu#!/vizhome/RollingStone100greatestalbums-DataVizFinal-WillaYu/WhatsRollingStone100GreatestAlbums)

### 数据来源
- [滚石榜单：Kaggle](https://www.kaggle.com/notgibs/500-greatest-albums-of-all-time-rolling-stone)
- 乐队国籍：Wikipedia

__分析反思：__
- 改进点：
  - 本仪表盘使用的数据维度较为简单，仅包括`排名`、`专辑名`、`乐队`、`乐队国籍`、`专辑类别`。数据维度的缺少也限制了后续可视化内容的深度。
  - 如果要充实数据维度的话其实可以引入`Spotify Analytics`的数据，如专辑平均`energy`等。
  - 另外，在为专辑匹配乐手国籍的时候，我是凭借记忆+Wiki搜索手动增加的信息。其实 __爬虫+手动调整爬虫结果__ 会更有效率。

 <br />
 <br />
 
### 仪表盘设计
#### Tab 1: 
![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/rollingstone1.png)


第一个版面用来交代可视化项目的主题与背景。包括对滚石的介绍，和可视化分析的问题：
- 哪个时代的专辑最受欢迎？
- 哪个类型的专辑最受欢迎？
- 哪个乐队/歌手的专辑最受欢迎？
- 哪个国家的专辑最受欢迎？

__改进分析：__
- 字太多+太小了：可视化如同PPT，在表达方面追求以视觉表述代替文字，不得不写的文字则力求精简。

<br />
<br />

#### Tab 2:  
![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/rollingstone2.png)


第二个版面用来交代最受欢迎的时代及类型。在这个部分我较为满意的设计有：
- 视觉形象：在柱形图上叠加散点图，并将散点图的形状替换为音符，在呈现音乐主题的内容时非常贴切；
- 文字注释：在每个部分都通过文字注释明确回答了该版面提出的问题；
- 互动效果：在设计仪表盘的时候，我在上下两个部分都进行了filter联动，比如框选柱形图的一部分，会对整个仪表盘呈现的数据有所影响，方便读者快速了解在不同时代，入选专辑的数量和类型信息。

__改进分析：__
- 字太多+重点缺失：虽然所有的文字都在表达信息，但是必须从呈现形式上进行区分，不然读者的理解成本就太高了。 _比如在介绍整体趋势的时候可以用提示框框起来，根据互动显示的信息可以用不同的颜色等。_
- __视觉垃圾__：老师在点评作业的时候直接说我很满意的音符标志是“视觉垃圾”。因为音符的加入，不能带来更多的信息，甚至会导致用户不能一眼看出来柱形图的真实高低，对于本来数值较小的柱形图而言，这个影响更严重。(如图)![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/tone1.png)

  - 在视觉可视化中，有一个专有名词叫 __ink-ratio__ ，直译为图形中的数据墨水量除以图形中的总墨水量，其衡量的是可视化表达信息的效率。在意识到这一点后，我在设计可视化甚至PPT的时候，都严格遵循了这一点。

  - 举一个我做过的简单（夸张）例子：
  ![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/01 远程办公好处.png)

    字体大小直接和数据比例相关，非常直观。

<br />
<br />
 
#### Tab 3: 
![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/rollingstone3.png)


第三个版面用来交代最受欢迎的乐手国籍及乐手。在这个部分我较为满意的设计有：
- 互动效果丰富：主要是在点击Beatles专辑的时候能切换不同的封面 ^ ^ 

  ![alt text](https://raw.githubusercontent.com/XinyueYu16/blog/master/assets/images/rollingstone/detail2.png)

__改进分析：__
- __可视化形式选择的失误__：与 Tab 2 相比，Tab 3 的内容排布明显混乱了起来，有凑版面之嫌疑。其中一个主要原因就是可视化形式选择的失误：
  - 甜甜圈图：这是在本仪表盘出现的 _第三种_ 表示比例的图表形式，虽然新颖，但是 __同信息类型的传达方式最好有一致性__ ，以降低读者的学习成本；
  - 柱状图：在该图建立可视化的时候，没有恰当使用aggregate函数，导致出现了以每张专辑为单位的分层。当时为了掩饰该尴尬，附加了渐变色表示专辑的排名，然而 __渐变色传递信息的效率很低__ ，不如去掉。
  - 箱线图：依据定性数据进行聚合的定量数据，使用箱线图表示是恰当的。但是排名这种定量数据与普遍的定量数据意义不同，普通数据越大越好，而排名数据越小越好。因此在呈现时，应该使 __x轴方向对调__ ，才能恰当地展现排名。
