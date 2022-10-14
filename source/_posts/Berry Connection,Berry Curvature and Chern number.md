---
title: Berry Connection,Berry Curvature and Chern number
date: 2022-10-12 20:37:17
tags: Berry phase
category: Berry phase
---
以下仅为自己最近对于berry phase的理解，思考与笔记。具体知识可以翻阅David Vanderbilt的Berry Phases in Electronic Structure Theory的第三章内容。

## Berry connection

对于berry connection,可以给出关于参量 $λ$ 的定义： $A(λ)=\langle u_λ|i∂_λu_λ\rangle$ 
给予 $|u \rangle$ 给定的gauge transform，即：$|u_λ\rangle=e^{−iβ(λ)}|u_λ\rangle$,我们可以诱导出关于$\tilde{A}(λ)$ 的表达式：
$$\tilde{A}(λ)=\langle {\tilde{u}_λ|i∂_λ\tilde{u}_λ \rangle}=\langle u_λ|i∂_λu_{λ} \rangle +β^{′}(λ)$$
给出条件$|\tilde{u}_1\rangle=|\tilde{u}_0\rangle$ ，我们可以进一步得到：$β(1)=β(0)+2πm$，其中$m$为任意整数。将$\tilde{A}(\lambda)$在任一给定的闭合路径 (0→1) 上进行积分，我们得到的是gauge transform下的berry phase的变化：

$$\tilde{\phi}=\phi+2πm$$
可以看到，berry phase是gauge-invariant modulo 2π , 2π 在 e 指数因子上的表达是相同的，但却不能等同(由于在实验中会出现不同相位的干涉现象，因此必须有物理上的差异)。其中， 不同$m$必然对应不同的物理实在，这在后续的Chern Numbers中会有体现。 

## Berry curvature
  
在berry connection定义的基础上，我们给出符合Stokes公式的berry curvature。对于给定的闭合路径，有 
$$∮\vec A(λ)⋅d\vec λ=∫_S\vec Ω⋅d\vec S$$

其中 $\vec{Ω}=\vec{\nabla}×\vec A$.可以看到，在给定的gauge transform下， 
$$\vec{\tilde{Ω}}=\vec {\nabla }×\vec{\tilde{A}}=\vec ∇×(\vec A+\vec ∇β(λ))=\vec ∇×\vec A=\vec Ω$$

## Chern number

对于任何一个闭合二维流形，有berry flux $Φ_S$ 满足：
 
$$Φ_S=∮_{S}\vec Ω⋅d\vec S=2πC$$
 这就是Chern定理。其中 $C$ 为某一整数，被称为**Chern number or Chern index**，可以认为是一种“拓扑数(topological index)”，显然这是与之前提到的 $|\vec u_\lambda\rangle$ 有关的。回顾一下之前提到的berry curvature，我们发现它是gauge-invariant的。因为我们总可以写为以下形式：  
$$
∫_S\vec Ω⋅d\vec S:=∮_P\vec A(λ)⋅d\vec λ
$$
 其中， := 表示，一种一对多的对应关系，即给定一个 $\vec Ω$ 在curve S 上的面积分对应多个 $\vec A$ 的环路积分。并且，需要注意的是，这并非一个闭合二维流形，而是一个任意曲面。等式成立的原因是，我们总能给出一个关于 $\vec β(\lambda)$ 的smooth gauge transform，使得这个曲面及其边界连续缓慢变化，使得 $\vec A$ 连续地变化至 $\vec {\tilde{A}}$  ，同时保证等式成立。但如果换一个视角，认为 $| {\vec u_λ}\rangle$ 是由其边界 $P$定义，我们也可以给出一种radical gauge transformation，使得 $Φ$ 产生了一个 $2πm$ 的差值( $m≠0$ )。这种gauge transformation并不能连续缓慢地变化到 S 内部并不产生一个涡流奇点(vortex-like singularity)。
 


