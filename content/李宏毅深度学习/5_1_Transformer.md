---
title: 5_1_Transformer
draft: false
tags:
  - "#深度学习"
---
 
## 一、Transformer

Seq2Seq 的模型。

输出长度取决于模型。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737041628665-d05e08a7-873e-4f5e-87a0-3b9062d0cc60.png)

Text-to-Speech、Speech-to-Text、Chatbot。

## 二、EncoderDecoder

1. Encoder

给定一排向量，输出一排向量。

可以使用RNN、CNN、Attention。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737042424040-cc0b7359-dd07-418c-be34-89fdddfff5cd.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737042648364-24764acf-a1d0-489a-b82a-3e60ac7c0708.png)

Transformer中的Block：

引入残差网络。

使用层归一化Layer Norm。（计算mean、std）

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737042839041-7a0c9a30-70bc-4979-8060-75402ed906ce.png)

Transformer更改。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737043326390-44e25238-e824-4f2a-9eed-a5b85f6141e4.png)

2. Decoder

2.1 Autoregressive

从<bos>开始。

输出文字的概率softmax。

取最高分数的文字。

接着使用预测出来的和<bos>得出新的输出。

以此类推。

问题：当一步预测错误，后续的都会在错误之上进行预测。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737082122424-21c31d57-947e-42c6-844e-4f0a88e44ad7.png)

Decoder：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737083061315-f61c264f-858e-4b16-934c-cbc4217b03bb.png)

其实Encoder和Decoder差不多：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737083137457-9bec2648-98bd-43ab-9d57-b664ba91985b.png)

其中不一样的地方在于：

1.1 Masked 掩码机制

掩码机制就是说我们不继续考虑全局的资讯，而是专注于在此之前的资讯。

就是Masked Self-attention

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737083244575-9ede98eb-fa65-4595-af1c-7b8d4a99eb85.png)

输出的长度是不定的。

输出<eos>结束符之后就结束。

2.2 Non Autoregressive（NAT）

一次产生整个句子。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737085560318-00cb7d35-06a7-41e2-8dfc-933923a156f1.png)

优点：平行化、控制输出的长度。

缺点：表现不好

3. Transformer

Decoder和Encoder的交互。

通过交叉注意力。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737085719504-21079fe7-e3ad-44f4-9bb4-87cea2f13463.png)

Decoder以<bos>开始。

进行掩码自注意力得到输出。

接着乘以q查询矩阵、k键矩阵。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737085976113-28dc83cf-fcee-47bb-bdcf-ace7c9066ce3.png)

计算注意力分数。

接着乘以v值矩阵。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737088392809-ee85920d-008f-4602-8e44-62bf1c2a893b.png)

## 三、训练

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737088680681-3ef077c4-3c56-42cf-8ebd-2f0c2466e791.png)  
  

计算交叉熵损失。

再训练的时候会给予正确的答案。这样的操作叫做强制教学Teacher Forcing。

## 四、束搜索、Guided Attention

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737089202936-0374a909-6fee-4c77-9f15-231c1c069923.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737089394870-b7b28e89-30e7-4bc2-802f-e8d86aea63c4.png)

## 五、评估

Bleu分数。

当我们不知道如何优化的时候，我们使用强化学习RL。

曝光偏差：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737089516204-e6b0064a-1bbd-466b-8906-c3899ab09205.png)

训练的时候又不要全部给定正确的，加入部分的错误。

Scheduled Sampling。

Encoder可以做并行。