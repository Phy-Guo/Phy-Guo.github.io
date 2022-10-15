---
title: Berryology of the Brillouin Zone
date: 2022-10-13 20:37:17
tags: Berry phase
category: Berry phase
---

# Berryology of the Brillouin Zone

之前我们定义了关于Berry Phase的一些基础概念。我们发现对于一些特殊的闭合流形，我们能够从中算出一些拓扑不变量，这种不变量不同于我们所观测到的期望值，是一种新的物理量，并且有着良好的gauge invariant.下面，我们将从Bloch态$|\psi_{nk}\rangle$入手，探究其中是否有之前所描述的性质。

## The choice of berry phase

首先，我们认为后续所描述的能带间是独立的，即在缓慢演化过程中，态矢量不会由能带n跃迁至其他能带。同时，通过量子数$\vec k$标记不同的$|\psi_{n\vec k}\rangle$,可以认为这是一系列抽象至Hilbert空间内的正交归一基，同时也是体系哈密顿量对应的本征矢。最后，我们认为能带n上并无奇点(singularities).\
由于$|\psi_{nk}\rangle=e^{ikr}|u_{nk}\rangle$，我们发现其在整个空间上的积分为
$$\int_{-\infty}^{+\infty}\psi_{nk}^*(x)\psi_{n,k+b}^*(x)dx=\int_{-\infty}^{+\infty}e^{ibx}u_{nk}^*(x)u_{n,k+b}^*(x)dx$$
其中b为有限值。显然，该积分为0，并且依赖于原胞的位置。因此，这里我们选择$|u_{nk}\rangle$作为Berry phase中的态矢量，并选取其中具有归一性的基矢量，将上一篇中的态矢量演化过程表达为：
$$\langle u_{nk}|u_{n,k+b}\rangle=\int_{0}^a u_{nk}^*(x)u_{n,k+b}^*(x)dx$$

## Other formalism

在上述基础上，我们可以进一步将其拓展到2D或3D的布里渊区内，将Berry phase定义为：
$$\phi_n=\oint \vec A_n(\vec k) \cdot d\vec{k}$$
其中的Berry connection 为
$$A_{n\mu}=\langle u_{nk}|i\partial_\mu u_{nk} \rangle$$
也可写为向量形式 $\vec A_n(k)=\langle u_{nk}|i\vec \nabla_k u_{nk} \rangle$.同样，Berry curvature是
$$\Omega_{n,\mu \nu}(k) = \partial_\mu A_{n\nu}- \partial_\nu A_{n\mu}$$
在2维下，布里渊区可看作一个torus，这样Chern numbers为：
$$C_n=\frac{1}{2\pi}\int_{ BZ} \Omega_{n,xy}d^2k$$
同样，在给定的规范变化下，Bloch函数和Brry connection可以写为：
$$|\tilde{u}_{nk}\rangle = e^{-i\beta(k)}|u_{nk}\rangle$$
$$\tilde{A}_n(k)=A_n(k)+\nabla_k\beta(k)$$
其中，Berry connection是明显规范依赖的(gauge-dependent).相应的，Berry curvature和Chern numbers是规范不变的，Berry phase则有着$2\pi$的规范不变量.

##  The calculation of berry phase in BZ

最后，我们需要在实际的BZ中计算一个“闭合路径”的Berry phase.注意到在BZ中，由于周期性边界条件，使得我们可以选取Bloch函数有着k空间上的$2\pi/a$不变性,即
$$\psi_{n,k=2\pi/a}(x)=\psi_{n,k=0}(x)$$
其中，a为给定的一个方向上的周期性晶格长度。但是，我们选取了晶胞周期函数$|u_{nk}\rangle$作为我们的定义Berry connection的基矢量。这样，我们得到的是
$$u_{n,k=2\pi/a}(x)=e^{-2\pi ix/a}u_{n,k=0}(x)$$
可以看到，在边界处基矢量并不严格相等，相差的并非只是一个全局相位，并且与x相关。而这个相位在我们计算Berry phase时也是要必须考虑的。按照之前的定义，我们离散化BZ至N份进行计算，可以得到
$$\phi_n=-Imln[\langle u_{nk_0}|u_{nk_1}\rangle\langle u_{nk_1}|u_{nk_2}\rangle...\langle u_{nk_{N-1}}|e^{-2\pi ix/a}u_{nk_0}\rangle]$$
在计算闭合循环时，注意到我们需要在$k=2\pi/a$返回到$k=0$时有一个相位因子！因此，我们需要在计算时注意这一特性，并把它考虑到闭合路径中的计算，这也是BZ所特有的性质。下一节，我们将进一步利用在BZ中另一种局域性的态矢量来构造Berry connection，即Wannier函数。

![avatar](/Berryology%20of%20the%20Brillouin%20Zone/1.png)