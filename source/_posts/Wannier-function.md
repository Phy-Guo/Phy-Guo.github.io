---
title: Wannier function
date: 2022-10-16 21:49:52
tags: Berry phase
category: Berry phase
---

# Wannier Functions

考虑到一个独立的能带$E_n(k)$，同时在$k$空间内平滑具有周期性。其傅里叶变化形式表达如下：
$$E_{nR} = \frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}E_{nk}d^3k$$
$$E_{nk}=\sum\limits_{R}e^{ikR}E_{nR}$$
如上我们认为$E_n(k)$是连续缓慢变化的，因此我们预计其傅里叶变换形势下的$E_{nR}$则是在实空间原点附近较大，并随着$|R|$的增加迅速衰减(类似$\delta(r)$)。
在上述基础上，我们选取$E_n(k)$上的Bloch函数$|\psi_{nk}\rangle$，同时对这组态矢量进行傅里叶变换：
$$|w_{nR}\rangle=\frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}|\psi_{nk}\rangle d^3k$$
$$|\psi_{nk}\rangle=\sum\limits_{R}e^{ikR}|w_{nR}\rangle$$
其中，我们将$|w_{nR}\rangle$定义为在能带n上的$Wannier\,function$.

## Properties of the Wannier Functions

Wannier functions有着以下性质：

1. *局域性*
$$|w_{nR}(r)\rangle \rightarrow 0 ,as\ |r-R|\ get\ large$$
2. *平移对称性*
$$w_{nR}(r)=w_{n0}(r-R)$$
3. *正交性*
$$\langle w_{nR}|w_{nR^{'}}\rangle=\delta_{RR^{'}}$$
4. *投影算符* 形式
$$P_n=\sum\limits_{R}|w_{nR}\rangle\langle w_{nR}|$$
5. 哈密顿量矩阵元在Wannier函数下是带对角(band diagonal)的，并且这些对角元正是$E_{nR}$:
   $$\langle w_{n0}|H|w_{nR}\rangle=E_{nR}$$
6. Wannier函数间的位置矩阵元是：
   $$\langle w_{n0}|r|w_{nR}\rangle=A_{nR}$$
   实际上，后面我们会看到，$A_{nR}$正是Berry connection $A_n
   (k)$的傅里叶变换系数。  

通过上述结论，我们可以得到哈密顿量作用在Wannier function上的结果：
$$H|w_{nR}\rangle=\frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}H|\psi_{nk}\rangle d^3k$$
同时，我们在等式两端左乘上$\langle w_{n0}|$，可以得到：
$$\langle w_{n0}|H|w_{nR}\rangle=\frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}\langle u_{nk}|H|u_{nk}\rangle d^3k$$
其中，利用了变换$\langle \psi_k|\chi_{k^{'}}\rangle=\frac{(2\pi)^3}{V_{cell}}\langle u_k |v_{k^{'}}\rangle \delta(k-k^{'})$,具体证明见附录(还没写)。我们还看到实际上$E_{nk}=\langle u_{nk}|H|u_{nk}\rangle$，这意味着我们可以通过构造Wannier函数来获得能带n上的精确的紧束缚表示。

我们还能看到性质5实际上有着更多的意义。这是坐标算符在Wannier函数下的矩阵元。正如我们上面提到的，这实际上有着Berry phase的形式。其中一种比较特别的形式便是*电荷中心*，定义如下：
$$\bar{r}_n = \langle w_{n0}|r|w_{n0}\rangle$$
也就是$A_{n,R=0}$,也可以表达为：
$$
\begin{align}
   \bar{r}_n &= \frac {V_{cell}}{(2\pi)^3}\int_{BZ}A_n(k)d^3k \nonumber\\ &= \frac {V_{cell}}{(2\pi)^3}\int_{BZ}\langle u_{nk} | i\nabla_k u_{nk}\rangle d^3k\nonumber
\end{align} $$
其中，利用了$A_{nR} = \frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}A_{nk}d^3k$.在一维情形下，我们很容易就能类比得到：
$$\bar{x}_n = (a/2\pi)\int_{0}^{2\pi/a} \langle u_{nk} | i\partial_k u_{nk}\rangle dk$$
其中$\langle u_{nk} | i\partial_k u_{nk}\rangle$就是我们熟知的berry phase—$\phi_n$.换句话来说，对于变化了$2\pi$的berry phase，相当于在BZ内Wannier中心由$x=0$演化到了$x=a$.由Wannier函数的性质我们也可以预期，在移动了给定晶格常数a的长度后，Wannier中心会回到自己移动前的位置，但是却产生了一个晶格常数倍数的位移，这也会导致$\phi_n$发生变化。  
下面我们还需要证明一下性质6。假定在一维的BZ内，有一个对Wannier函数的坐标操作：
$$
\begin{align}
   (x-R)|w_{nR}\rangle &= \frac{a}{2\pi}\int_{0}^{2\pi/a}(x-R)e^{ik(x-R)}|u_{nk}\rangle dk \nonumber 
   \\&=\frac{a}{2\pi}\int_{0}^{2\pi/a}(-i\partial_ke^{ik(x-R)}|u_{nk}\rangle dk) \nonumber 
   \\&=\frac{a}{2\pi}\int_{0}^{2\pi/a}e^{ik(x-R)}(i\partial_k|u_{nk}\rangle )dk \nonumber
\end{align}$$
扩展至3维，并稍微移动一项到等式右边我们就能得到：
$$r|w_{nR}\rangle= \frac {V_{cell}}{(2\pi)^3} \int_{BZ} e^{ikR}[e^{ikr}(R+i\nabla_k)|u_{nk}\rangle]d^3k$$
左乘上$\langle w_{n0}|$，其中包含R的项在积分后等于$R\delta_{0,R}=0$,最后得到的是：
$$\langle w_{n0}|r|w_{nR}\rangle=\frac{V_{cell}}{(2\pi)^3}\int_{BZ}e^{-ikR}\langle u_{nk}|i\nabla_k u_{nk}\rangle d^3k$$
等式右边便是我们之前定义的$A_{nR}$项.  

综上所述，我们得到了一种新的视角，即固体中能带上的性质可以通过Wannier函数来表达。其中，对于Wannier函数中哈密顿量矩阵元可以用于表示电子在各个最近邻晶格间的Hopping，同时对于On-site能也可以通过$E_{n0}$表达(取R=0)；并且，我们还得到了与Berry phase相关的Wannier函数中心$\langle w_{n0}|x|w_{n0}\rangle$。在第四章我们能看到，Wan-nier函数中心的位移正是绝缘体中电极化理论的核心。
