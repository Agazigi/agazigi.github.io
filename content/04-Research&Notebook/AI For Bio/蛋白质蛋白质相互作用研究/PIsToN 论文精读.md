---
title: PIsToN 论文精读
draft: true
tags:
  - "#深度学习"
  - 生物信息学
  - "#PIsToN"
---
> [!note] 本篇说明
> 本篇论文是 **弗罗里达国际大学** 的研究人员发表在 **[《Nature Machine Intelligence》](https://www.nature.com/articles/s42256-023-00715-4)** 上的一篇研究论文，该团队利用以 **Transformer** 架构为基础的 **[[ViT（Vision in Transformer）]]** 模型进行 **蛋白质-蛋白质结合界面（PPI）** 的打分评估，能够对天然蛋白质复合物和不正确构象进行准确区分。具体来说，研究人员参考先前工作（i.e. [[MaSIF]]）将蛋白质结合界面转换成二维图像的集合，其中每一张图像对应着界面的几何或生化特性，利用 **ViT** 模型进行界面结合分数评估。同时作者也结合生物物理前验知识，进行了混合能量项、多注意力模块、对比学习的多项改进增强，从而获得了更好的评估性能。

> [!tip] 相关资料
> 该论文的预印本发表在 **[bioRxiv](https://www.biorxiv.org/content/10.1101/2023.01.03.522623v2)** 上。
> 该项目的测试数据和代码均为开源：**[测试数据](https://zenodo.org/records/7948337)** & **[代码](https://github.com/stebliankin/piston)** 。

# 蛋白质蛋白质相互作用



# PIsToN 训练数据处理

![[Pasted image 20260121002434.png]]

# PIsToN 模型架构

![[Pasted image 20260121002448.png]]

# PIsToN 训练流程

## 对比学习

![[Pasted image 20260121002501.png]]
## Loss



# 实验

## BenchMark

### MaSIF-test
### CAPRI-score

### PDB-2023


## Lab1：

![[Pasted image 20260121002528.png]]

![[Pasted image 20260121002549.png]]

![[Pasted image 20260121002600.png]]

![[Pasted image 20260121002618.png]]

![[Pasted image 20260121002725.png]]


# 相关工作

1. MaSIF
2. PUMBA



---
> [!success] 结语
> 

