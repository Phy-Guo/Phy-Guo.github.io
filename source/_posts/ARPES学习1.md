---
title: ARPES学习1
date: 2023-09-08 10:46:47
tags:
---
以下是对Angle Resolved Photoemssion Spectroscopy(ARPES) 的理论推导内容：
## 基本原理
ARPES的基本原理是基于实验过程和结果。通过光激发使得电子由初态$i$，波函数为$\Psi_i$到终态$f$，波函数为$\Psi_f$,其中光场的矢势为$A$.
假设有一微扰$H_{int}$作用于N-电子态的初态$\Psi_i$激发至$\Psi_f$，其跃迁概率可以由费米黄金规则描述：
$$
 w \propto \frac{2\pi}{\hbar} |<{\Psi}|H_{int}|{\Psi}>|^2\delta(E_f - E_i -\hbar w),
$$
在非相对论极限下，光与物质相互作用可以写为：
$$
H_{int} = \sum_{i=1}^N [\frac{e}{m} \boldsymbol{A}(\boldsymbol{r}_i) \cdot \hat{\boldsymbol{p}_i} + \frac{e^2}{2m} \boldsymbol{A}^2(\boldsymbol{r}_i) + \frac{e\hbar}{2m} \hat{\boldsymbol{\sigma}}_i\cdot\nabla \times \boldsymbol{A}(\boldsymbol{r}_i )- \frac{e^2\hbar}{(2mc)^2} \hat{\sigma}_i \cdot \frac{\partial \boldsymbol{A}_i(\boldsymbol{r}_i)}{\partial t} \times \boldsymbol{A}(\boldsymbol{r}_i)],
$$
忽略自旋相关项和二次项，我们可以得到近似的相互作用哈密顿量：
$$
H_{int} ~ \frac{e}{m} \sum_{i=1}^N \boldsymbol{A}(\boldsymbol{r}_i) \cdot \hat{\boldsymbol{p}_i} = \frac{e}{mc}\sum_{i=1}^Ne^{i\boldsymbol{k}_{h\nu} \cdot \boldsymbol{r}_i }\boldsymbol{\epsilon} \cdot \hat{\boldsymbol{p}_i} = -i\frac{\hbar e}{mc}\sum_{i=1}^Ne^{i\boldsymbol{k}_{h\nu} \cdot \boldsymbol{r}_i } \boldsymbol{\epsilon} \cdot  \nabla_i ,
$$
其中$\boldsymbol{\epsilon}$为偏振方向.二次量子化后的哈密顿量为：
$$
H_{int} = \sum_{\boldsymbol{k}_f,\boldsymbol{k}}M_{\boldsymbol{k}_f\boldsymbol{k}} \hat{c}_{\boldsymbol{k}_f}^{\dagger} \hat{c}_{\boldsymbol{k}},
$$
