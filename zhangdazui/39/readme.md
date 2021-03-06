# 39 | 线性回归（上）：如何使用高斯消元求解线性方程组？

## 高斯消元法

高斯消元法主要分为两步，消元（Forward Elimination）和回代（Back Substitution）。

**消元**，就是要减少某些方程中元的数量。如果某个方程中的元只剩一个了 x_m 了，那么这个自变量 x_m 的解就能知道了。

**回代**，就是把已知的解 x_m 代入到方程式中，求出其他未知的解。

## 使用矩阵实现高斯消元法

把高斯消元法转为矩阵的操作，便于自己的理解和记忆。

首先我们要把方程中的系数 b_i 转成矩阵

为了便于后面的回代计算，我们也可以把方程式等号右边的值加入到系数矩阵，我们称这个新的矩阵为增广矩阵。