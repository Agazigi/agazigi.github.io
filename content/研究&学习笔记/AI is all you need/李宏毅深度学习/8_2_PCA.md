---
title: 8_2_PCA
draft: false
tags:
  - "#深度学习"
---
 
## 一、无监督学习

1. 化繁为简 - 聚类、降维
2. 无中生有 - 生成

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737705631201-de644bff-b762-4c8f-8971-5553751116ce.png)

### 2.1 聚类

K-means

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737705822438-2228650b-0cc9-48fd-b7f1-b17024847628.png)

HAC：

计算相似度，最像的相连。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737708353088-921888aa-aeb6-424f-963d-1943dd16ca82.png)

### 2.2 降维

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737708489214-2d2846ed-1ae3-40cb-b300-6d584f2ba4ba.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737709461616-7d4bcf47-6628-4a52-a0ed-cb5989984e8d.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737709527225-9614810d-a922-4b5b-a21c-4110fde37ca6.png)

## 二、PCA

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737709729873-256864d9-672d-4eb6-a3ca-68a69efc61bf.png)

选取方差最大的。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737709809207-0a76c5f1-15ec-474b-9022-5b6162eb7c7e.png)

正交基。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737709826682-131d2a6c-f687-4970-80ee-08214ba364f4.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737710038851-242b475d-878b-4442-99b9-586330ae440f.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737710200061-84f94af0-859c-4afb-ad3b-1d88c6f1c12c.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737710387014-0b740cb3-1f9b-4735-a752-d82d95fbe8f7.png)

特征向量。

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737717469530-3cbdccb5-6b52-4b6b-b131-c9cf51167cc4.png)

PCA的另一种角度理解：

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737717640472-963a67fb-39d5-4dc8-9d52-0bde4cfce8d9.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737717776781-2ef4d023-6517-42d3-81be-4b705aa7acb7.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737718374049-942da16d-543b-41ab-8900-ce67721d0120.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737718569180-23fd5ea7-bf3c-4ad1-8cc2-b9877214fb16.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737719376913-db3160b3-114a-4403-9aff-ec81040c3af2.png)

![](https://cdn.nlark.com/yuque/0/2025/png/43073108/1737719603700-886fdf55-250a-4419-bfc2-72afe43c97dc.png)