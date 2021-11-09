---
layout: post
title:  "用户行为分析"
author: willa
category: [学习笔记, 商业分析]
featured: false
---

<br>

准备大众点评数据的时候看到的[老哥的分析](https://zhuanlan.zhihu.com/p/122367076)，把淘宝用户行为数据按照咨询的框架进行了“人、货、场”的拆分，并在每个部分套用模型：人-RFM，货-波士顿矩阵，场-用户漏斗进行分析。虽然只用了MySQL（不过使用了窗口函数，参数），但是分析的结果依然深入。想想一年前的我脑子里还都是这些东西，现在我满脑子只有pandas，多少有些唏嘘。

以及那位作者的思维导图非常有用，稍微留档记录一下。
以及作者的数据来源：[天池](https://tianchi.aliyun.com/dataset/dataDetail?dataId=649&userId=1)
