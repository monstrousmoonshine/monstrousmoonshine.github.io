---
layout:     post
title:      latex中创建minted新环境
subtitle:   latex
date:       2019-11-22
author:     monstrousmoonshine
header-img: img/post-2019-11-22.jpg
catalog: true
tags:
    - latex
---

# 如何创建latex中minted新环境
minted使latex渲染代码的一个宏包，支持中文注释，昨天用latex写一下C语言作业的报告，listings包不知道怎么都法显示中文注释，于是转战minted。
显示结果确实很漂亮，但是每导入一个代码块就要复制一遍参数设置，着实很麻烦。

用\newenenvironment不知道为什么一直没法创建基于minted的新环境
刚刚查到发现minted宏包提供了\newminted命令用于定义一个新的环境。


如下
```
\newminted{c}{encoding=utf8,tabsize=4,linenos,frame=single,rulecolor=purple!50!black,texcl=true}
\begin{ccode}
#include<stdio.h>

int strrindex(char s[],char t[])
{
	int i, j, k;
	int loc = -1;
	for (i = 0; s[i] != '\0'; i++)
	{
		for (j = i, k = 0; t[k] != '\0' && s[j] != '\0' && s[j] == t[k]; j++, k++)
			;
		if (k > 0 && t[k] == '\0')
			loc = i;//每找到一个即记录，一直至最右
	}

	if (loc >= 0)
		return loc;
	else
		return -1;
}

\end{ccode}
```
效果如下，还蛮好的
!['figure'](http://wx2.sinaimg.cn/mw1024/007P0Y0dly1g974oh7je2j30mj0estb5.jpg)
