# 对应定理（Correspondence Theorem）

参考：[DF] Dummit–Foote《Abstract Algebra》§3.3（Theorem 20）；[DS]《离散数学与结构》§9.5。

**本节用到的记号，先一次交代清楚**：

- $G$：群；$N\trianglelefteq G$：正规子群；$\pi:G\to G/N$：自然投影。
- $H\le G$：子群；$H/N=\pi(H)=\{hN:h\in H\}$：$H$ 在商群中的像。
- $\overline{H}\le G/N$：商群里的子群；$\pi^{-1}(\overline{H})$：它在 $G$ 中的原像。
- $[G:H]$：指数；对应关系保持指数，即 $[A:B]=[A/N:B/N]$。
- $G/N$：商群；$\cong$：同构（本节用于陈述对应定理的环论版本）。
- $\{H\le G:N\le H\}$：$G$ 中包含 $N$ 的子群全体——对应定理的左边。
- $\mathbb Z,n\mathbb Z$：本节用 $\mathbb Z\to\mathbb Z/n\mathbb Z$ 演示对应关系。

设 $N\trianglelefteq G$，$\pi:G\to G/N$。则

$$\{H\le G:N\le H\}\longleftrightarrow\{\overline H\le G/N\},\qquad H\longmapsto H/N,\quad K\longmapsto\pi^{-1}(K),$$

是一一对应，两个方向互为逆映射。对应保持结构：对 $N\le A,B\le G$，

$$A\le B\iff A/N\le B/N,\qquad A\trianglelefteq G\iff A/N\trianglelefteq G/N.$$

也就是说，$G/N$ 的子群恰好是包含 $N$ 的子群商掉 $N$ 得到的。

