---
title: 5_2_各式各样的Attention
draft: false
tags:
  - "#深度学习"
---
 
## 一、怎么使得Self-Attention有效

输入长度 N。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737090369797-44f0edb1-53ab-4903-9ed9-b301fc4a467b.png)

问题就在于 N * N 的计算量过于巨大。

思考：也许不需要计算全部的 N * N 矩阵。

例如：局部Attention。但是类似于CNN。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737090568156-00e4e0bd-917c-48aa-b442-289d1a701f41.png)

Stride Attention

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737090630319-d7fe7183-ce0c-4791-9947-5c9f70da43eb.png)

全局注意：

添加一个token，了解全局资讯。

各部分之间通过token相互了解。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737090816949-92e2b528-5551-433f-8933-58bd35f2387d.png)

在多头注意力的各个头中分别使用不同的处理。

以上都是人工设计的Attention。

但是我们是否能够找到数据驱动的自己寻找保留哪些Attention。

通过基于相似度的 Clustering 聚类实现。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091120470-65c1d56a-1458-43c8-b7f9-4806dee8c120.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091127471-2dd7e015-12f8-4569-8b9f-00820afe04e6.png)

只有相像的才计算Attention。

可学习模式：

用另外一个Net学习Attention。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091255485-d10582e1-2b58-4466-9723-623878de436c.png)

挑选代表，压缩矩阵：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091469533-dd0c93f6-38b2-4b7b-9aa7-d58a57c6251f.png)

问：为什么不挑选q？

输入和输出的长度不同了。

挑选：CNN

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091553065-27d75abb-6c4a-4ce9-b78f-35975ce3383c.png)

降维：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737091584516-4bbbe9b5-c8a0-4cac-b183-10f93bd0a3be.png)

改变矩阵的相乘顺序，可以减少计算量。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092123406-72499528-54b8-4c98-8c02-90fe04b34f39.png)

当然这是我们把Softmax拿走之后的结果。

我们再把Softmax放回来。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092427647-8f870d27-859e-4818-9772-de9a2a7aae9a.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092628933-22b83e13-69bc-4964-9f6b-df68718bc565.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092673204-e3ea9394-7bad-4052-9ddb-dead7821e1dc.png)

可重复利用。运算量少。

先操作k和v。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092777643-85f9956e-5192-44ec-94fe-9b2af0b15603.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737092871012-10f82391-36b7-4a94-8939-650456df8fe7.png)

![](https://cdn.nlark.com/yuque/__latex/430c34c537a59a2e1e151ac4ab3bc1fb.svg)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737093044243-9dec60a5-9c94-4f4a-97bd-ae9b9671379c.png)

Attention也可以被学习。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737093080797-6d477522-5ff3-4253-9eb8-e41944d2f0aa.png)