---
title: 6_2_GAN理论
draft: false
tags:
  - "#深度学习"
---
 
## 一、引入

GAN用于生成。

即是我们想要找到数据的分布，能够继续生成这个分布中的点。

假设我们的输入是一张图片64 * 64空间中的一个点。（高维空间中的一个点）

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737542379291-83c9a988-84a1-41e3-9ace-991c79b92ab7.png)

解法：最大似然估计

给定数据分布![](https://cdn.nlark.com/yuque/__latex/9338ee0d3b10776fcedd030a5ab860b9.svg)，我们可以从中取样。

我们要去找 ![](https://cdn.nlark.com/yuque/__latex/b019567387b96eb6ab9b9ebd9c5679ec.svg)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737542855554-5b5d4e78-5c68-423a-8d28-df272c3c5857.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737543107886-5c445095-b0d8-4562-9692-e353c62f38e4.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737543421522-3490f670-3269-463e-961a-7e30b530c01e.png)

问题：![](https://cdn.nlark.com/yuque/__latex/ca153abd01adfdf7d4607ec81c84f259.svg) 的公式未知，无法计算Div？

做法：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737543614031-870c507f-f53b-47da-ac7d-8fe4107151e8.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737543707061-b35e7b00-21c7-482b-8993-579b8063baf5.png)

最小化一个最大值

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737544197512-cf27fb95-872f-43a9-a943-a8a759159ffe.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737544364878-c6e2b98d-601a-4d55-80eb-2ed837de8df2.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737544735378-7b65f083-1907-4e3d-b2db-767d18494ce7.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737544985485-71c7d7a1-16e4-4e1a-8274-d7da7480ed7d.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737545081702-fd00afd1-e49e-4322-a8cc-94034713fb88.png)