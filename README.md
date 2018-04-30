### LFM

LFM的本质是矩阵分解。但是拆解到物理过程上，我们可以理解为通过用户的历史数据学习用户隐向量和物品隐向量，而用户隐向量与物品隐向量的乘积就是模型预测用户对于物品的喜爱程度。

##### 数学公式

用户评分矩阵:$D_{u×i}$

用户隐向量矩阵:$U_{u×h}$

物品隐向量矩阵:$I_{h×i}$

其中：$u$为用户数量，$i$为物品数量，$h$为隐向量维数。

模型残差定义为$\sum_{i,j\space if \space D_{ij}\ne0}(D_{ij} - \sum_{k=1}^h U_{ik}I_{kj} + \sum_kU_{ik}^2 + \sum_k I_{kj}^2)$

其中后面的平方项为L2正则项。