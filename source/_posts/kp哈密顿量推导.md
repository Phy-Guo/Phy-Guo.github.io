---
title: kp哈密顿量推导
date: 2022-11-12 14:07:03
tags: graphene
category: graphene
---
# Kp Hamiltonian form

As for monolayer graphene, we often use tight-binding method to calculate its hamiltonian.If we only take consider with the nearest-neighbor for the hopping energy.We could attain the hamiltonian form of TB method:
$$
    \hat{H}_{TB} = -t \sum\limits_{i,j = n}(a_{i}^{\dagger}b_{j}+H.c.)
$$
in grahene,there are two inequal sublattices.We laber them as A and B lattice below.By introducing three nearest neighbor vector as opposed to lattice A:
$$
    \delta_1 = \frac{a}{2}(1,\sqrt{3}), \qquad \delta_2 = \frac{a}{2}(1,-\sqrt{3}),\qquad \delta_2 = -a(1,0)
$$
Through the reducing bove, we could attian the final hamiltonian in k space
$$
    \hat{H}_k = 
        \begin{bmatrix}
         0 & \Delta_k\\
        \Delta_k^* & 0
         \end{bmatrix}
$$
where$\Delta_k = -t\sum\limits_{l=1}^3 exp(i\vec{k}\cdot\vec{\delta}_l)$.Through (2) we could expand $\Delta_k$ 
$$
\begin{aligned} 
    \Delta_k & = -t\cdot (exp\frac{a}{2}(ik_x+i\sqrt{3}k_y)+exp\frac{a}{2}(ik_x-i\sqrt{3}k_y)+exp(-ik_xa)) \\
    & = -t\cdot exp(-ik_xa)(1+exp(i \frac{3}{2}k_xa)[exp(i \frac{\sqrt{3}}{2}k_y a )+exp(-i \frac{\sqrt{3}}{2}k_y a )])\nonumber \\
    & = -t\cdot exp(-ik_xa)(1+2exp(i\frac{3}{2}k_xa)cos\frac{\sqrt3}{2}k_ya)
\end{aligned}
$$

![avatar](/grahene/kp1.png)


substituting the solution to (3), two solutions would be obtained with the hamiltonian matrix
$$
    \begin{aligned} 
    \epsilon_k &= \pm |\Delta_k| \\
    &= \pm t(1+4cos^2\frac{\sqrt{3}}{2}k_ya+4cos\frac{3}{2}k_xacos\frac{\sqrt{3}}{2}k_ya)^\frac{1}{2}
    \end{aligned}
$$
when $\epsilon_k = 0$,it is clear that such value must satisfy the conditions:
$$
    k_x = \frac{2\pi}{3a}\qquad k_y = \pm \frac{2\pi}{3\sqrt{3}a}
$$
which we usually label as the Dirac points.For the reson that sometimes(for example in continuum model) we need to calculate the k points near the Dirac points, so it is necessary to 
deal with the solution which might be possible to simplified.We take the k points close to the Dirac points as $k = K + q$,where $q$ is a small compared with k ,so it is convenient to expand the expression 
for $\Delta_k$ above:
$$
    \begin{aligned}
    \Delta_k & = \Delta_{k = K,K'} + \vec{\nabla}_q(\Delta_k)|_{k=K,K'}\cdot\vec{q}\\
            & = 0 + \vec{q} \cdot (-t)\vec{\nabla}_k \{ exp(-ik_xa)+2exp(\frac{i}{2}k_xa)cos\frac{\sqrt{3}}{2}k_ya\}|_{k=K,K'}\\
            & = (-t) \cdot \{ (-ia)exp(-iK_xa)qx + 2[(\frac{ia}{2})exp(\frac{i}{2}K_xa)cos\frac{\sqrt{3}}{2}K_yaq_x]\\
            & + exp(\frac{i}{2}K_xa)(\frac{-\sqrt{3}}{2}a)sin(\frac{3}{2}K_ya)\cdot q_y \}\\
            & = (-ta) exp(\frac{\pi}{3}i) \{ iq_x + \frac{i}{x}q_x \mp \frac{3}{2}q_y \} \\
            & = (-\frac{3}{2}ta)exp(\frac{\pi}{3}i)(iq_x \mp q_y) 
    \end{aligned}
$$
finally,we attian the expression of $\Delta (q)$:
$$
    \Delta(q)=\hbar v_F (q_x \pm iq_y)(1 + O(q/K)^2)
$$
where we extract an overall constant factor$ (-iexp(i\pi/3) )$,and $v_F = 3ta/2\hbar $.At last, we write the Hamiltonian in the form
$$
    \hat{H}_k = \hbar v_F
    \begin{bmatrix}
     0 & q_x \pm iq_y\\
     q_x \mp iq_y & 0
     \end{bmatrix}
     =\eta \hbar v_F   \hat{\sigma}\cdot q 
$$
where $k = K, \eta = -1;k = K' ,\eta = +1$\\
When the grahene rotates with an angle $\theta$, the condition of the equation will change to:
$$
    \left\{
    \begin{aligned}
        \Delta_k(\theta) &=-t\sum_{l=1}^3 exp(i\vec{k}R(\theta)\vec{\delta}_l) = 0 \\
        \Delta_q(\theta) &= -t \sum_{l=1}^3 i\vec{q}R(\theta)\cdot \vec{\delta}_l exp(i\vec{k} R(\theta)\vec{\delta}_l)
    \end{aligned}
    \right .
$$
and $R(\theta) = (cos(\theta),sin(\theta);-sin(\theta)cos(\theta))$.It is convenient to choose 
$$
    \begin{aligned}
    \tilde{\vec{q}} &= \vec{q}R(\theta) \\
    \tilde{\vec{k}} &= \vec{k}R(\theta)        
    \end{aligned}
$$
with the solution of (9) invariant.So (8) changes to the form
$$
    \hat{H}_k = \hbar v_F
    \begin{bmatrix}
     0 & \tilde{q_x} \pm i\tilde{q_y}\\
     \tilde{q_x} \mp i\tilde{q_y} & 0
     \end{bmatrix}
     =\eta \hbar v_F   \hat{\sigma}\cdot \tilde{\vec{q}}  = \eta \hbar v_F   \hat{\sigma}\cdot \vec{q}R(\theta)
$$
with the Dirac points $k = \vec{K}R(\theta)$ when $\eta = -1$ and $k = \vec{K'}R(\theta)$ when $\eta = +1$