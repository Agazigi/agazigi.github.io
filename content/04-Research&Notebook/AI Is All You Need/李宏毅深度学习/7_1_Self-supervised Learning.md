---
title: 7_1_Self-supervised Learning
draft: false
tags:
  - "#深度学习"
---
 
## 一、模型家族

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737363224125-45bb1db8-b395-4c4f-8a2b-43859eb57dbf.png)

巨大的参数：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737364317177-6d82f3fc-4bb7-440a-a626-e427233e6b24.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737364346725-f186019c-ce4a-41d7-a2e6-55b78c78a876.png)

## 二、自监督学习

监督学习的做法:

我们是有标签的

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737364588529-c0ca7d6f-d7fa-4d9d-a1ea-771e933d747c.png)

而自监督学习：

在没有标签的情况下，自己做标注。

将原本数据分成两部分，一部分做输入，一部分作为标签。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737364713474-8327d398-4a7d-49d5-a523-729377e76da0.png)

## 三、BERT

BERT就是Transformer的Encoder。

输入一个Seq。

然后将输入随机掩盖。

指的是：1. MASK 2.随机

学会做填空题。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737365032912-0e225e69-a848-4905-a363-89e6b9cfcd1a.png)

预测两个句子是否相接。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737365140056-85f49664-009f-4e05-a0b2-475e87ec4ba6.png)

对BERT进行微调，满足下游任务：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737365316888-7cef246d-8787-4e63-a50b-32e2e4b6cb17.png)

下游任务：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737365439130-ae9f3bfb-4421-40f4-86d1-1c63684b4af4.png)

半监督学习说的是，我们BERT的训练是（自监督学习）无监督的学习，而做下游任务的时候是监督学习。

情感分类

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737369472033-c0e68583-9fc3-4c39-a313-045a2ae7419e.png)

词性标注

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737369552349-c9a6b129-7594-497e-b108-c68bb5f2946a.png)

前提、假设推断

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737369700338-b74f66f6-4b94-43bf-b88d-e3d2bfdb4220.png)

问答

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737369987051-e8e733f1-b19e-41f7-a53a-618fe4956f3c.png)

Seq2Seq

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737465859551-946bbdb7-45cd-4e89-9989-52d740d7784e.png)

## 四、为什么BERT有用？

词嵌入。考虑上下文将token向量化。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737530497415-ce454f66-f0d7-44f3-b714-346b5264da65.png)

计算一下余弦相似度：即学会饿了区分“果”的不同。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737530938330-b6076d34-9341-47ee-91ae-ada55308f403.png)

学会了文字的意思。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737531124262-84a9cce1-8fe1-4b0d-b1ce-5f099d1ed0b1.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737531400872-6c3b2d5e-15a0-4bac-bcaa-e93079bf7c47.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737531428149-274e9fa9-b23b-485c-929a-e3a0e5c43cb9.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737531713172-ee54d5b4-24ba-4c68-9300-9ca36bed8f01.png)

## 五、GPT

预测接下来的token。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737531944415-e69e2d4a-3307-4f7c-b13a-846a48a3f3b6.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737466349340-b9a47a76-d7c2-465a-9840-f9a00c08d5cb.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737466514549-c4daf5bf-bb09-4f2d-892e-5167d7f57ebb.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737466705331-6405d58d-eadb-46e2-9a35-d7cbfea150e8.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737466723357-f0afa855-d95c-4f3c-afb0-e2710a7ca502.png)

BERT和GPT区别：

Encoder和Decoder