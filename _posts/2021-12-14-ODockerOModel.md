---
layout: post
title:  "当你有个不能自动同步代码的Docker真的很头痛"
author: willa
image: "https://img.devrant.com/devrant/rant/r_1573214_eEdqG.jpg"
category: [日常整理]
featured: false

---

当你的代码还要求装不同版本的多个包，并且主运行程序里并没有因为你多个包的不同实现方式切换分支，就更加头痛了。



## 1214学习到的内容

### 再次强调：**代码修改记得兼容老旧版本/多个包**

环境：**renv.lock**相当于pyenv/requirements.txt，如果依赖的包产生了变化，记得 renv.snapshot()


## 1222学习到的内容

1. 不要太依赖于超前者帮你debug，学会理解：
  - 代码在干什么（输出）
  - 代码的依赖是什么（输入）
  - 代码为什么要这么写（构成）
  - 代码如何debug（解构）

2. 当你写代码时，假如写了两个功能，**就一定要都debug到，不然记得加test**

3. 发版的本质是控制进度可回溯，所以即使是修bug，只要会影响产出结果，就得patch

