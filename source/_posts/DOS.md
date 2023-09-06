---
title: DOS
date: 2023-09-06 15:59:27
tags: EnergyBand Calculation
---
# Density of States Calculation

通过能谱的计算，我们可以计算一个给定材料大小的态密度。这里给出态密度的定义：
$$
    D(E) = N(E)/V
$$
其中，$N(E)\delta E$为给定体积$V$系统内$E$到$E+\delta E$内的电子态数量

在计算中，由于我们采取的是离散动量空间计算，因此得到的能量也是离散后的，此时态密度的定义可以认为是：
$$
    D(E) = \frac{1}{V} \sum_{i=1}^N \delta(E - E(\boldsymbol{k}_i))
$$

注意到量纲上,$\delta(E- E(\boldsymbol{k}_i))$为$[{\rm Energy}]^{-1}$. 因此态密度的量纲为: $[{\rm Energy}]^{-1} [{\rm Volume}]^{-1}$、

接着，我们进行求和化积分的操作,可以得到:
$$
    D(E) = \frac{1}{V} \frac{V}{(2\pi)^d} \int_{BZ} dk^{d} \delta(E - E(\boldsymbol{k}))
$$

此处，$d$为空间维度.
在程序中计算时，我们无法使用积分公式进行连续计算.因此，我们在离散化该积分后，我们可以得到最终在程序中使用的态密度公式:
$$
    D(E) = \frac{1}{(2\pi)^d} \sum_{k} \delta(E - E(\boldsymbol{k})) \Delta k
$$
其中,$\Delta k$为动量空间内单个$k$点所占的动量空间体积元($dk \rightarrow \Delta k$)