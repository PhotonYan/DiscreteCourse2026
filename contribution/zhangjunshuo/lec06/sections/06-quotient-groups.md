# 商集与商群

参考：[DF] Dummit–Foote《Abstract Algebra》§3.1–3.2；[DS]《离散数学与结构》§9.5。

**本节用到的记号，先一次交代清楚**：

- $G$：群；$e$：单位元；$|G|$：群的阶；$H\le G$：子群。
- $gH$：左陪集；$[G:H]$：指数，即左陪集的个数。
- $N\trianglelefteq G$：$N$ 是正规子群，即对一切 $g\in G$ 有 $gN=Ng$。
- $G/N=\{gN:g\in G\}$：商群，元素是陪集；乘法为 $(gN)(hN)=ghN$，单位元是 $N$。
- $\sim$：本节用来把「在同一个陪集里」写成等价关系，即 $a\sim b\iff a^{-1}b\in H$。
- $\cong$：同构，$G\cong H$ 表示两个群有完全相同的乘法结构；本节用它陈述商群与已知群的对应。
- $GL_n(F),SL_n(F)$：域 $F$ 上可逆矩阵群与行列式为 $1$ 的矩阵群；$F^\times=F\setminus\{0\}$ 是 $F$ 的乘法群。
- $\times$：群的直积，按分量运算。

对任意子群 $N\le G$，左陪集都能收集成一个商集；但只有 $N\trianglelefteq G$ 时，按代表元相乘才给出良定义的群运算，得到商群（quotient group）$G/N$。

## 商集与乘法的良定义性

设 $N\le G$。左陪集把 $G$ 分割成互不相交的块，收集起来得到商集

$$G/N=\{gN:g\in G\}.$$

若 $N\trianglelefteq G$，在商集上定义

$$(gN)(hN)=(gh)N.$$

问题是：陪集的代表元不唯一，右边是否与选择无关？设 $g'=gn$、$h'=hm$，其中 $n,m\in N$，则

$$g'h'=(gn)(hm)=gh\,(h^{-1}nh)\,m.$$

由正规性 $h^{-1}nh\in N$，再由 $N$ 对乘法封闭得 $(h^{-1}nh)m\in N$，所以

$$g'h'N=ghN.$$

乘积只由两个陪集决定，这就是良定义性。

反过来，正规性也是必要条件。假设上述乘法良定义。任取 $g\in G,n\in N$，由 $1N=nN$ 和良定义性，

$$(1N)(g^{-1}N)=(nN)(g^{-1}N),$$

即 $g^{-1}N=(ng^{-1})N$，所以 $ng^{-1}\in g^{-1}N$，存在 $n'\in N$ 使 $ng^{-1}=g^{-1}n'$。左乘 $g$ 得 $gng^{-1}=n'\in N$。于是 $N\trianglelefteq G$。所以“正规”正是代表元乘法合法的充要条件。

## 商群的群公理

当 $N\trianglelefteq G$ 时，上述运算构成群。结合律由 $G$ 的结合律诱导：

$$((gN)(hN))(kN)=((gh)k)N=(g(hk))N=(gN)((hN)(kN)).$$

单位元是 $N$：$(gN)N=(ge)N=gN$，同理 $N(gN)=gN$。逆元是 $g^{-1}N$：

$$(gN)(g^{-1}N)=N=(g^{-1}N)(gN).$$

于是 $G/N$ 是一个群。

## 例

**整数模 $n$。** 加法群 $\mathbb Z$ 中 $n\mathbb Z$ 是正规子群，商群元素是剩余类（residue class）

$$a+n\mathbb Z=\{a+kn:k\in\mathbb Z\},$$

运算为 $(a+n\mathbb Z)+(b+n\mathbb Z)=(a+b)+n\mathbb Z$，即熟悉的 $\mathbb Z/n\mathbb Z$（也记作 $\mathbb Z_n$）。

**可逆矩阵商掉行列式为 1 的矩阵。** 行列式相同的两个矩阵相差一个 $SL_n(F)$ 中的因子：$\det(AB^{-1})=\det A\,(\det B)^{-1}$，所以每个陪集恰好由行列式相同的矩阵组成。于是

$$GL_n(F)/SL_n(F)\cong F^\times.$$

