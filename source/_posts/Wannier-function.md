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
其中，利用了变换$\langle \psi_k|\chi_{k^{'}}\rangle=\frac{(2\pi)^3}{V_{cell}}\langle u_k |v_{k^{'}}\rangle \delta(k-k^{'})$,具体证明见附录。我们还看到实际上$E_{nk}=\langle u_{nk}|H|u_{nk}\rangle$，这意味着我们可以通过构造Wannier函数来获得能带n上的精确的紧束缚表示。

### 待续
