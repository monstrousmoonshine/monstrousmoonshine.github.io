---
layout:     post
title:      关于pointer中的glimpse function
subtitle:   glimpse function
date:       2019-7-28
author:     monstrousmoonshine
header-img: img/post-2019-7-28.jpg
catalog: true
tags:
    - 深度学习
    - 组合优化
---

# glimpse function

pointer网络在Decoder时采用attention机制，算出概率序列，具体公式为
!['attention'](http://wx4.sinaimg.cn/mw1024/007bel6Hgy1g5fox84dpwj30pp05qt9a.jpg)


但论文中还提到了glimpse函数，具体公式如下：

!['attention'](https://wx2.sinaimg.cn/mw1024/007bel6Hgy1g5fox85ejdj30kk04udg8.jpg)

其中的A即为attention操作，一般的，我们之前利用一次attention后就得到了概率序列
，而glimpse机制，顾名思义，就是别只注意一次，多瞥几眼。每次glimpse的query，就是上一次的glimpse向量
!['attention'](https://wx2.sinaimg.cn/mw1024/007bel6Hgy1g5fox85e2sj30c703y0ss.jpg)
