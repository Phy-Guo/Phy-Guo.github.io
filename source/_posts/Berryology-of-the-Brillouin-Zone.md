---
title: Berryology of the Brillouin Zone
date: 2022-10-13 20:37:17
tags: Berry phase
---
# Berryology of the Brillouin Zone
之前我们定义了关于Berry Phase的一些基础概念。我们发现对于一些特殊的闭合流形，我们能够从中算出一些拓扑不变量，这种不变量不同于我们所观测到的期望值，是一种新的物理量，并且有着良好的gauge invariant.下面，我们将从Bloch态$|\psi_{nk}\rangle$入手，探究其中是否有之前所描述的性质。
## The choice of berry phase
首先，我们认为后续所描述的能带间是独立的，即在缓慢演化过程中，态矢量不会由能带n跃迁至其他能带。同时，通过量子数$\vec k$标记不同的$|\psi_{n\vec k}\rangle$,可以认为这是一系列抽象至Hilbert空间内的正交归一基，同时也是体系哈密顿量对应的本征矢。最后，我们认为能带n上并无奇点(singularities)。\
由于$|\psi_{nk}\rangle=e^{ikr}|u_{nk}\rangle$，我们发现其在整个空间上的积分为
$$\int_{-\infty}^{+\infty}\psi_{nk}^*(x)\psi_{n,k+b}^*(x)dx=\int_{-\infty}^{+\infty}e^{ibx}u_{nk}^*(x)u_{n,k+b}^*(x)dx$$
其中b为有限值。显然，该积分为0，并且依赖于原胞的位置。因此，这里我们选择$|u_{nk}\rangle$作为Berry phase中的态矢量，并选取其中具有归一性的基矢量，将上一篇中的态矢量演化过程表达为：
$$\langle u_{nk}|u_{n,k+b}\rangle=\int_{0}^a u_{nk}^*(x)u_{n,k+b}^*(x)dx$$
### 待续 

