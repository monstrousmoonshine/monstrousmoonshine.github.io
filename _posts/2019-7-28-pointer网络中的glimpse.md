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
!['attention'](https://github.com/monstrousmoonshine/monstrousmoonshine.github.io/blob/master/img/post-2019-7-28-1%20(1).png)
<br/>
<br/>
但论文中还提到了glimpse函数，具体公式如下：
<br/>
<br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;!['attention'](https://github.com/monstrousmoonshine/monstrousmoonshine.github.io/blob/master/img/post-2019-7-28-1%20(2).png)
<br/>
其中的A即为attention操作，一般的，我们之前利用一次attention后就得到了概率序列
，而glimpse机制，顾名思义，就是别只注意一次，多瞥几眼。每次glimpse的query，就是上一次的glimpse向量
!['attention'](https://github.com/monstrousmoonshine/monstrousmoonshine.github.io/blob/master/img/post-2019-7-28-1%20(3).png)
