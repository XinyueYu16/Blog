---
layout: post
title:  "当你有个不能自动同步代码的Docker真的很头痛"
author: willa
image: "https://img.devrant.com/devrant/rant/r_1573214_eEdqG.jpg"
category: [日常整理]
featured: false

---

当你的代码还要求装不同版本的多个包，并且主运行程序里并没有因为你多个包的不同实现方式切换分支，就更加头痛了。



## 今天学习到的内容

### 再次强调：**代码修改记得兼容老旧版本/多个包**

环境：**renv.lock**相当于pyenv/requirements.txt，如果依赖的包产生了变化，记得 renv.snapshot()

