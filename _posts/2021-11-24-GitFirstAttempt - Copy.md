---
layout: post
title:  "使用Git参与多人项目的第一次"
author: willa
image: "https://img2.baidu.com/it/u=1848906865,844650420&fm=253&fmt=auto&app=138&f=JPG?w=667&h=500"
category: [日常整理]
featured: false
---

紧张 > 3< 但其实也好简单？



**任务：**参与开发ETL，增加时间格式和html unescape功能的文档和测试

**Takeaway**：

- 写好文档

  ```python
  def this_function(param1:str = 'abc') -> pd.DataFrame:
  	'''
  	这个function是用来做abc的，
  	如: ...
  	
  	:param param1: param1, 是str， 默认为'abc'
  	:return: pd.DataFrame
  	'''
  ```

  

- 写好测试，保证test的高覆盖率

  - pytest的验证html通过每行是否被运行来计算覆盖率

**GIT操作**：git stash save ->  git checkout -> git fetch -> git pull -> git checkout -> HEAD git rebase -> git stash apply-> git add -> git commit -> git push (git squash)

git squash: 多commit合并
git stash(暂存功能): [详解](https://www.cnblogs.com/tocy/p/git-stash-reference.html)

