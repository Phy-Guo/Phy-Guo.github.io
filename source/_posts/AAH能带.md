---
title: AAH能带
date: 2023-10-07 16:15:38
tags:
---
 根据布洛赫定理，我们可以将布洛赫波分解为一系列平面波的叠加：
 $$
 \psi(\boldsymbol{r}) = \sum_{\boldsymbol{q}} c_{\boldsymbol{q}} e^{i{\boldsymbol{q}}\cdot{\boldsymbol{r}}}
 $$
同时，由于晶格势能的周期性，我们也可以将其按倒格矢进行傅里叶展开：
$$
U(\boldsymbol{r}) = \sum_{\boldsymbol{K}} U_{\boldsymbol{K}} e^{i{\boldsymbol{K}}\cdot {\boldsymbol{r}}}
$$
其中，傅里叶系数$U_{k}$的表达式为：
$$
U_{K} = \frac{1}{v}\int_{cell} dr e^{-iKr}U(r)
$$
根据薛定谔方程：
$$
H\psi = (-\frac{\hbar^2}{2m}\nabla^2 + U(r))\psi = \varepsilon \psi
$$
将上面的展开式代入其中，我们可以得到：
$$
\sum_q e^{iq\cdot r} \{  (\frac{\hbar^2}{2m}q^2-\varepsilon)c_q +\sum_{K}U_{K}c_{q-K} \} = 0
$$
若需等式成立，我们需要让左式每一项都为0.由此，我们可以得到中心方程，其中的一个方程为：
$$
(\frac{\hbar^2}{2m}q^2 - \varepsilon)c_q + \sum_{K} U_{q-K}c_{q-K} = 0
$$

我们从这个思路出发，对一维AAH模型进行能带分析：由理想的一维原子链出发，我们外加一个余弦势场。我们知道在一个固体晶格的电子满足的薛定谔方程为：
$$
H \psi_k = E\psi_k 
$$
其中，哈密顿量满足：
$$
H = -\frac{\hbar ^2}{2m}\nabla^2 + V
$$
我们在一维原子链的基础上外加一个周期势场$V_g(r) = V_0cos(gr+\delta)$,其中$V_0$为势场的峰值，$g$为势场变化的频率。因此，将外加势场加上的哈密顿量为：
$$
H = -\frac{\hbar ^2}{2m}\nabla^2 + V + V_g
$$
## 动量空间方法求解AAH模型
对于AAH模型，我们可以让外加势场变换到动量空间中，这样可以实现动量空间中计算外加势场的一维原子链的能带。在没有外加势场的情况下，我们可以将一维原子链的能带直接写出：我们令原子链的晶格矢量为$a$,倒格矢为$b=2\pi/a$,利用紧束缚方法可以得到哈密顿量为
$$
H_k = -t(e^{ika}+e^{-ika})
$$
外加势场后，我们可以认为外加势场为该原子链的扰动，使得其自身布里渊区内的不同$k$点耦合在一起，其哈密顿量为：
$$
    \begin{bmatrix}
 H_{k_1} & T_{k_1k_2} &  T_{k_1k_3} \\
   T^*_{k_1k_2} & H_{k_2}  & T_{k_2k_3}  \\
  T^*_{k_1k_3}  &  T^*_{k_2k_3}  &H_{k_3} 
\end{bmatrix}
$$
其中$H_{k_i}$为一维原子链布里渊区内$k_i$点的哈密顿量,$T$是不同$k$点之间的耦合哈密顿量。 
 
耦合哈密顿量表达式可以写为：
$$
T_{k_1k_2} = \bra{k_1}H\ket{k_2}
$$
代入原子轨道矢量和Bloch矢量后
$$
T_{k_1k_2} = \frac{1}{ N}\sum_{jl}e^{-ik_1j}\bra{j}H\ket{l}e^{ik_2l}
$$
由于外加势场在$j=l$时有影响，有$\bra{j}H\ket{j} = V_g(j)$，我们在式中将该项独立出来，有
$$
T_{k_1k_2} = \frac{1}{ N}\sum_{j,\Delta \neq 0}e^{-i(k_2-k_1)j}e^{ik_2\Delta}\bra{0}H\ket{\Delta} + \frac{1}{N}\sum_{j}e^{i(k_2-k_1)j}V_g(j)
$$
其中前一项在$k_1\neq k_2$时为0，我们只关注最后一项。

这里我们将外加势场项通过傅里叶变换从正空间变换到动量空间
$$
V_g(j) = \frac{V_0}{2}e^{iK_h j}+\frac{V_0}{2}e^{-iK_h j}
$$
其中，$K_h$为外加势场的倒空间周期。代入到耦合矩阵元内，我们可以得到
$$
T_{k_1k_2} = \frac{1}{N}\sum_{j}e^{i(k_2-k_1)j}( \frac{V_0}{2}e^{iK_h j}+\frac{V_0}{2}e^{-iK_h j})
$$
对$j$求和可以得到
$$
T_{k_1k_2} = \delta_{k_2-k_1+K_h,K}\frac{V_0}{2} + \delta_{k_2-k_1-K_h,K}\frac{V_0}{2} 
$$
其中，$K = 2\pi /a$为原子链的倒空间周期。

# 非简并微扰分析能带
这里我们假定周期势场的空间变化十分微弱，外加势场是小量，电子的行为接近布洛赫电子，将$T_{kk'}$当作微扰处理。
## 零级近似
令$V_g=0$,即只有单势场的情况，此时的电子是布洛赫电子
$$
\begin{cases}
  & \psi_k^0(r)=e^{ikr}u_k(r)\\
  & E^0(k) = -2tcos(ka)
\end{cases}
$$
其中，$u_k(r) = u_k(r+a)$,并且易证明布洛赫基满足正交归一和完备条件。
利用布洛赫基的完备性将波函数写为布洛赫基的线性叠加
$$
\Psi_k(r) = a(k)\psi_k(r)+\sum_{h\neq 0}a(k+K_h)\psi_{k+K_h}(r)
$$
在$V_g$为小量的情况下，可以认为除$a(k)\approx0$外，其余所有$a(k+K_h)$都为小量。将上式代入到哈密顿量方程$H\Psi_k = E\Psi_k$中
$$
(H^0 +V_g-E)\sum_ha(k+K_h)\psi_{k+K_h}=0
$$
用$\ket{k+K_h}$代替$\psi_{k+K_h}$,该基底满足布洛赫基的正交性$\braket{k+K_h|k+K_{h'}}=\delta_{K_h,K_{h'}}$,用$\bra{k+K_{h'}}$作用于上式得到
$$
\sum_h \bra{k+K_{h'}}(H^0+V_g-E(k))\ket{k+K_h}a(k+K_h) = 0
$$
其中，$\ket{k+K_h}$为$H^0$的本征态:
$
H^0\ket{k+K_h} = -2tcos(k+K_h)a\ket{k+K_h}
$
，再利用布洛赫基的正交性，可以得到：
$$
\sum_h\{[-2tcos(k+K_h)a-E(k)]\delta_{K_h,K_{h'}}+\bra{k+K_{h'}}V_g\ket{k+K_h}\}a(k+K_h)=0
$$
其中，
$$
\bra{k+K_{h'}}V_g\ket{k+K_h} = \frac{1}{N}\sum_{jl}e^{-i(k+K_{h'})R_j}\bra{R_j}V_g\ket{R_l}e^{-i(k+K_h)R_l}
$$
可以认为$\bra{R_j}V_g\ket{R_l}$只在$R_j = R_l$时有外加势场影响:$\bra{R_j}V_g\ket{R_l} =V(R_j)\delta_{R_j,R_l}$.代入到上式中
$$\begin{align*}


\bra{k+K_{h'}}V_g\ket{k+K_h}  &= \frac{1}{N}\sum_j e^{-i(K_{h'}-K_{h})R_j}V(R_j)\\
&=V(K_{h'}-K_{h})
\end{align*}
$$
可以利用势场的中心性得到在$K_h=K_{h'}$时，$V(K_h-K_{h'})=0$最后，我们将中心方程化简为
$$
[-2tcos(k+K_{h'})a-E(k)]a(k+K_{h'}) +\sum_{h'\neq h}V(K_{h'}-K_{h})a(k+K_h) = 0 
$$
## 一级近似
在上式中，我们仅保留一阶小量，并用$-2tcos(ka)$代替$E(k)$,替换指标$K_h$与$K_{h'}$,得到
$$
\{-2tcos(k+K_{h})a-[-2tcos(ka)]\}a(k+K_{h}) +V(K_{h})a(k) = 0 
$$
其中，我们可以令$a(k)\approx1$。由此求得：
$$
a(k+K_h) = \frac{V(K_h)}{-2tcos(k+K_{h})a-[-2tcos(ka)]}
$$
代入到波函数方程中，可以得到一级近似波函数
$$
\Psi_k (r)= a(k)\psi_k(r)+\sum_{h\neq 0}\frac{V(K_h)}{-2tcos(k+K_{h})a-[-2tcos(ka)]}\psi_{k+K_h}(r)
$$
其中，$\psi_k(r) = e^{ikr}u_k(r)$。利用布洛赫基的表达式，我们可以得到$\Psi_k(r+a)$的波函数表达式
$$
\Psi_k(r+a) = a(k)\psi_k(r)e^{ika}+\sum_{h\neq 0}\frac{V(K_h)}{-2tcos(k+K_{h})a-[-2tcos(ka)]}\psi_{k+K_h}(r)e^{ika}e^{iK_h a}
$$
明显，该波函数只有在特定条件下才有布洛赫形式，即$K_h=2n\pi/a$,此时
$$
\Psi_k(r+a) = \Psi_k(r)e^{ika}
$$
满足布洛赫解的形式。

令$K_h=0$，并取$a(k)=1$，再将$a(k+K_h)$代入到中心方程中，即得到能量的二级近似解
$$
E(k) = -2tcos(ka)+\sum_h\frac{|V(K_h)|^2}{-2t(cos(k+K_h)a-cos(ka))}
$$
## 简并微扰
注意到当$cos(k+K_h)a-cos(ka)=0$时，非简并微扰失效。这两种相差一个倒格矢的布洛赫电子态有相等能量，微扰此时会引起两个态的耦合，必须用简并微扰考虑。考虑只有$a(k)$与$a(k+K_h)$两支布洛赫基最重要，因此波函数可简化为
$$
\Psi_k (r)= a(k)\psi_k(r)+a(k+K_h)\psi_{k+K_h}(r)
$$
此时我们只需求解一个二阶行列式：
$$
\begin{vmatrix}
  -2tcos(ka)-E(k)&V(-K_h) \\
  V(K_h)&-2tcos(k+K_h)a-E(k)
\end{vmatrix}=0
$$
其中$V(-K_h)=V^*(K_h)$。因此，在该简并点附近有解
$$
E(k) = -2tcos(ka)\pm |V(K_h)|
$$
对应的$k$点解为
$$\begin{align*}

cos(k+K_h)a-cos(ka)&=0\\
-2sin(\frac{ka+ka+K_ha}{2})sin(\frac{-K_ha}{2})&=0\\


\end{align*}$$
即，在$k = \frac{nK}{2}-\frac{K_h}{2}$处打开带隙