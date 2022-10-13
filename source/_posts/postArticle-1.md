---
Berry Phase
---

add new line

以下仅为自己最近对于berry phase的理解，思考与笔记,如果有什么错误和误解，还请各位批评指正。具体知识可以翻阅David Vanderbilt的Berry Phases in Electronic Structure Theory的第三章内容。

1.Berry connection
对于berry connection,可以给出关于参量 λ 的定义： $A(λ)=<u_λ|i∂_λu_λ>$ 
给予 $\ket u$ 给定的gauge transform，即：$|u_λ>=e−iβ(λ)|uλ>$,我们可以诱导出关于 A~(λ) 的表达式：
A~(λ)=<u~λ|i∂λu~λ>=<uλ|i∂λuλ>+β′(λ)
给出条件|u~1>=|u~0> ，我们可以进一步得到： β(1)=β(0)+2πm ，其中 m 为任意整数。将 A~(λ) 在任一给定的闭合路径 (0→1) 上进行积分，我们得到的是gauge transform下的berry phase的变化：                                       
ϕ~=ϕ+2πm
可以看到，berry phase是gauge-invariant modulo 2π , 对于2π 在 e 指数因子上的表达是相同的，但却不能等同(由于在实验中会出现不同相位的干涉现象，因此必须有物理上的差异)。其中， 不同 m 必然对应不同的物理实在，这在后续的Chern Numbers中会有体现。
2.Berry curvature
在berry connection定义的基础上，我们给出符合Stokes公式的berry curvature。对于给定的闭合路径，有 
∮abA→(λ)⋅dλ→=∫SΩ→⋅dS→

其中 Ω→=∇→×A→ .可以看到，在给定的gauge transform下， 
Ω~→=∇→×A~→=∇→×(A→+∇→β(λ))=∇→×A→=Ω→
3.Chern number
对于任何一个闭合二维流形，有berry flux ΦS 满足：
 
ΦS=∮SΩ→⋅dS→=2πC
 这就是Chern定理。其中 C 为某一整数，被称为Chern number or Chern index，可以认为是一种“拓扑数(topological index)”，显然这是与之前提到的 |uλ→> 有关的。
回顾一下之前提到的berry curvature，我们发现它是gauge-invariant的。因为我们总可以写为以下形式：  
：
∫SΩ→⋅dS→：=∮PA→(λ)⋅dλ→
 其中， 
：
：= 表示，一种一对多的对应关系，即给定一个 Ω→ 在curve S 上的面积分对应多个 A→ 的环路积分。并且，需要注意的是，这并非一个闭合二维流形，而是一个任意曲面。等式成立的原因是，我们总能给出一个关于 βλ→ 的smooth gauge transform，使得这个曲面及其边界连续缓慢变化，使得 A→ 连续地变化至 A~→ ，同时保证等式成立。但如果换一个视角，认为 |uλ→> 是由其边界 P 定义，我们也可以给出一种radical gauge transformation，使得 Φ 产生了一个 2πm 的差值( m≠0 )。这种gauge transformation并不能连续缓慢地变化到 S 内部并不产生一个涡流奇点(vortex-like singularity)。
待续