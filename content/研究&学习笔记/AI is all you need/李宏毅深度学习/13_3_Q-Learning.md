---
title: 13_3_Q-Learning
draft: false
tags:
  - "#深度学习"
---
 
### 目录

Q-Learning的介绍

Q-Learning的小技巧

用于持续动作的Q-Learning

## 一、Q-Learning的介绍

在Q-Learning中是基于值Value的方法。我们要训练的是一个Critic（评判网络）。

Critic的作用是评价了现在的行为有多好或是多么不好。

即给定行动![](https://cdn.nlark.com/yuque/__latex/26d01865f6e830adaa66117e307e316f.svg)，它评价了当前行动的好坏大小![](https://cdn.nlark.com/yuque/__latex/0a9f0229582fec587e14ea664d4b21cb.svg)。

例如状态值函数：

当使用Actor π，拜访到s状态后累积的Reward的期望值有多大。

需要注意的是不能单独有Critic的，它需要和一个Actor进行绑定。

因为还是Critic的定义，在给定状态s时，假设互动的是Actor π，计算的Reward的期望。

即 Critic 取决于Actor 和 State。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739182848914-88e37854-693b-428b-8d90-d70db6313a11.png)

例子：

在不同的时期对相同的状态有不同的评价。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739185044062-8ee5f3aa-01e9-446f-89c1-e53924cf941e.png)

如何去计算 ![](https://cdn.nlark.com/yuque/__latex/0a9f0229582fec587e14ea664d4b21cb.svg)？

- Monte-Carlo蒙特卡洛方法（MC）
- Temporal-Difference时间差分方法（TD）

MC：

回归到 ![](https://cdn.nlark.com/yuque/__latex/4a0a28d238f09f7d3e4842ef0dfe9d1c.svg)。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739185208657-90d88ea2-0651-460c-bede-70f87bb34ed2.png)

TD：

由序列 ![](https://cdn.nlark.com/yuque/__latex/31b95ae143105809fcfaa536a2b10202.svg)即可应用TD方法计算。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739185398904-4e6f22b8-3082-4b5c-8eed-c8c82108d69e.png)

MC v.s. TD：

MC的方差较大，但是较为准确。（常用）

因为G是由多步累加得到的。

TD的方差较小，但不太准确。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739185551464-b0ceca8e-c70b-4119-95da-7e1f12f5074f.png)

例子：

我们互动了8个episodes。

计算期望值：

依据不同的计算方法，计算的结果是不同的。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739186940001-561ad07e-b97c-4d1c-963d-5508c8a2b2db.png)

除了上边的Critic之外，还有Q-Learning值函数用作Critic。

即状态行动值函数 ![](https://cdn.nlark.com/yuque/__latex/d66ee4870de8a9a74dc126e70fbb9c0e.svg)。

某一个状态 s 采取某一个行动 a ，接下来都是Actor π来采取行动，最终得到的Reward的期望值。

Q函数有两种写法：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739187176879-c2157ac6-cee5-4a6c-b9a1-5130e328e9ed.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739187344550-d427c4bb-3fc3-442d-bf26-0da3f5632a48.png)

我们Q函数得到的最大值去更新原本的Actor会比原来的好。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739187601261-c3e72564-92f2-40ac-ab47-cb9091bcc2c1.png)

证明：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739187893327-d8d1c11d-6036-48e1-86c9-7353cef396cf.png)

Tip1： Q+TD = Target Network：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739188053987-31c5cb90-7085-4b40-9443-095bf50c0800.png)

Tip2：Exploration

![](https://cdn.nlark.com/yuque/__latex/7c102e7a7d231bf935f9bc23417779a8.svg)-贪心策略、玻尔兹曼探索：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739188364115-63ed0ba4-2f51-4860-93b9-88f2b4def0b7.png)

Tip3：Replay Buffer

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739188519173-e0ba22d8-db07-459a-8a4b-7543353f3e18.png)

算法：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739188635877-bfd36b08-63f7-471f-90aa-8cd3cbeb179a.png)

## 二、Q-Learning的小技巧

2.1 Double DQN

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739188970823-040b4b4b-d251-46c7-85a8-b828b04e23d9.png)

两个Q-Network。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189118648-b8886166-cb94-495c-a2b2-e1ddcda5b912.png)

2.2 Dueling DQN

改变Network的架构。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189218730-9cf2d8a2-aa04-4eef-9f08-1b95f13cfd73.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189403598-5a4a59f2-fef7-444f-b455-bdd80c3008e3.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189470465-6e412a09-2bc6-4555-b791-e6053db30e31.png)

2.3 Prioritized Reply

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189533594-3d6bb5d8-ac39-4c4d-9d89-f1d5c0a407f8.png)

2.4 Multi-Step

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189605112-a9928af6-a08e-492f-a103-4b18800455e5.png)

2.5 Noisy Net

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189704724-5b27377c-1b18-47a5-8a87-c3807c85e970.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189847224-8eb4ed08-c7f0-4d96-ad38-371213a3fc9e.png)

2.6 Distributional Q-Function

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739189964347-96b10786-1b4b-444b-a20a-0e318a69cf18.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739190167088-8d379d71-5f49-49ae-a2b9-ac6b67fd95f7.png)

2.7 Rainbow

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739190603782-b860fff1-e46d-484d-b53a-aa674bbec191.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1739190664169-47dba727-0c1e-411f-89c2-c1414db9db03.png)