---
title: 0_2_Pytorch教程
draft: false
tags:
  - "#深度学习"
---
 
## 一、什么是Pytorch？

机器学习框架。

主要功能：自动微分计算、GPUs运算。

## 二、模型的评估

训练、验证、测试

## 三、加载数据

#### 1.torch.Dataset

读取数据。

#### 2.torch.Dataloader

加载数据batch。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1736842757346-40d38e5a-5941-4f36-9fdd-2321c4f9fded.png)

## 四、自定义数据加载类

就是Dataloader。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1736842803190-17ef5873-fc85-4165-8e38-2cfccc83a784.png)

## 五、Tensor

## 六、torch.nn

layer = nn.Linear # 线性层

.weight .bias

## 七、torch.optim

SGD。

梯度清零、反向传播、梯度更新。

## 八、训练

net.train() 训练

net.eval() + with torch.no_grad() 验证、测试

torch.save(net.state_dict(), path) 保存参数

x = torch.load(path)

net.load_state_dict(x) 加载参数

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1736843814993-cbb3da5c-a08e-47b6-b36e-c971a8f00935.png)

## 九、Colab

免费GPU。

code cell、text cell。

!用于指定指令。

!nvidia-smi

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1736844918736-13db7c49-2c3d-432d-b376-d12d443c13f2.png)