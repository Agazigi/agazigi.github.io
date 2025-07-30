---
title: 6_1_GAN
draft: false
tags:
  - "#深度学习"
---

## 一、生成式网络

特点，同时输入ｘ和ｚ得出ｙ。

ｘ是条件。

由一种简单的分布到另外一种复杂的分布的网络。

依据给定简单分布（可以是正态分布）的不同得到多种不同的输出。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737288724170-6d9e8384-e9d3-40e6-ba6e-811f338f357a.png)

分为unconditional GAN和conditional GAN。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737289222000-ebe99079-73ac-4648-be02-7259c2bb5fa7.png)

## 二、GAN

在GAN中，除了生成器之外，我们还要多训练一个东西。

discriminator判别器，也是个NN。

将生成结果输入，得到一个标量，标识着我们结果的好坏。、

（标量越大代表越像）

就是将我们的结果进行判别。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737289414771-c913815c-cccd-4a01-aa02-bad3006f94f7.png)

gan的原理：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737289551782-d9e6f3c7-a25b-4944-aa9a-c658f44be2ed.png)

步骤：

1. 生成器G、判别器D都初始化参数。
2. 固定G，更新D。

2.1 随机样本输入G，得到输出。

2.2 选取正确的样本，和G的输出进行比较。

2.3 D去学习分辨正确的和误差的。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737289811504-8da9a5c2-a692-4bc9-ab9d-29151a6d3095.png)

3. 固定D，更新G

3.1 随机样本输入G，得到输出。

3.2 将输出给予D，由此得到评分。（我们希望越大越好）

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737290045132-61adcec9-6580-4483-b62a-25ee8dc474c6.png)

4. 重复上述步骤![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737290333122-51454faf-7b86-454f-a4fb-4f420b44cebd.png)

## 三、GAN理论

我们的目的：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737290633741-8ef3b70b-c135-4d08-81f9-afafcc9265c7.png)

也就是：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737290667178-b2c81002-74f2-40dd-947c-82201b6d4cfe.png)

当然我们不知道生成分布和数据分布长什么样？差异如何度量？

但是我们可以获得样本：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737290839068-d72bb767-fdc2-4033-8f26-285faa9f4d8c.png)

我们只需要通过样本的差异就可以衡量分布的差异。

这是通过GAN的判别器所实现的。

我们的判别器看见来自生成的样本就给低分，来自数据的样本就给高分。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291069384-6a95ffe0-0cf6-4ac5-a50c-7d941e8893ed.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291227083-4e953f78-a478-48a2-887f-0738e6a72209.png)

GAN比较难训练。

## 四、GAN训练技巧

1. ![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291523386-be8ef8ed-49dd-49a1-aecc-86b082efdcee.png)
2. ![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291619108-4f8c3847-2214-402c-b521-8f099d4e1654.png)
3. ![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291820659-a409cfc2-7cb2-48b4-8165-81a375350572.png)
4. ![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291871610-1cefc2b2-34f8-4d58-abae-da59bdbd7337.png)
5. 这张图片中的x改成y，代表一张图片。D必须是一个足够平滑的分布。![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737291973061-a7c56ece-f606-43c7-9fc7-198ccc51f074.png)

训练过程中如果有一方不发生变化，那么会导致整体的停止。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737295819336-3e36c76a-5dfd-495e-9ca3-2ba0cf69e92d.png)

## 五、GAN评估

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737296950796-644f563c-8397-438d-978a-d7237bb79c72.png)

盲点

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297045522-cf713b8c-c87a-44d2-8102-5fe66b31c2b1.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297127111-c6982897-7e07-48e3-8998-276c0c217a9b.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297362030-0bb670d8-e853-4c08-905f-d02ad2378111.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297517105-56459b2b-9675-4698-a5ff-6683a6cf8630.png)

## 六、条件生成Conditional Generator

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297690828-630fa570-75a8-41be-90c6-763edaa6756d.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737297732297-a31080b3-2752-4023-8fa1-7fff55b44354.png)

## 七、GAN+Unsupervised Learning

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737298114829-8f0a0c62-10f9-4431-831e-2ea98d4b4b24.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737298136420-0d4bf0b0-9de5-43a0-91be-c1a77ec91bc1.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737298253147-1e0294ce-ff22-4fae-8311-6c4390d502b2.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737298405054-f1fd2082-e7e8-494a-a5ed-35700d6bdcd0.png)