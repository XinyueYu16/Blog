---
layout: post
title:  "误差分析的骚操作"
author: willa
image: "https://img1.baidu.com/it/u=3829756115,105839803&fm=26&fmt=auto"
category: [日常整理]
featured: false
---

学习学习学习！



客户要求拎出来所有导致模型误差率超过10%的特征，老师给出的解决方案：

**将绝对误差率是否超过10%作为target_value，造一颗以recall_score为target_metric的树**。

因为想要了解特征对误差的真实影响，使用**train_test_split**, recall_score针对**验证集**。

其中透出了几层理解：

- 名义变量与其他变量的特征探索（EDA）：使用classification tree

- classification tree: 对数据进行切分，使得切分结果尽可能地pure

  切分的标准：

  - 数值变量/可合并的名义变量（factorize）：if feature<=value; else 
  - one-hot变量：if 当数值<=0.5; else (其实就是0或1的判断)
  - *↑以上的流程区别有针对python和R处理名义变量的意思*

- recall_score：**该案例更重视找到所有的误差超过10%的项目，想要尽量减小Type II Error.**

- 验证集oos metric的使用场景



老师说这个case做完，所有误差分析相关的内容都遍历了，以后再多也不怕了（一次次失望后的平静.jpg）。所以稍微总结一下误差分析的几个阶段：

- 高误差项目：验证输入数据的准确性，排除outlier

- 误差可视化（如地图）：观察有无遗漏特征，如离外溢城市的距离

- 误差和各特征的相关性：其实没做，但是说不定有用

- 高误差特征预警：选择重点特征分析（主要是名义变量，因为简单客户好理解）

  - 分析指标：MAPE、PPE

  - 分析模块

    - 各特征组的数量/占比（数量少的特征模型难以学习）

    - 各特征组的指标情况（找出表现较差的特征组，有高误差风险）

    - 各特征组误差分布情况与全市水平对比（tgi）（如果分布显著不同，则针对该特征组进行预警是有效的）

      TODO：是不是可以直接做ANOVA test来着

  - 结果导向

    - 需要预警的特征
    - 可以加入模型的特征

- 影响误差的特征：如最上

