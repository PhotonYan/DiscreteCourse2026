# 群的公理与基本例子

参考：[DF] Dummit–Foote《Abstract Algebra》§1.1、§1.4；[DS]《离散数学与结构》§9.1。

**本节用到的记号，先一次交代清楚**：

- $G$：本节讨论的集合，后面会要求它带上一个运算构成群。
- $\cdot$：$G$ 上的二元运算 $\cdot:G\times G\to G$，即把两个元素算出第三个元素；简写时把 $a\cdot b$ 写成 $ab$。
- $\times$：集合的笛卡尔积，$G\times G=\{(a,b):a,b\in G\}$；这是二元素运算的定义域。
- $e$：单位元，即满足 $ea=ae=a$ 的元素。
- $a^{-1}$：$a$ 的逆元，即满足 $aa^{-1}=a^{-1}a=e$ 的元素。
- $|G|$：群 $G$ 的阶，即 $G$ 中元素的个数。
- $\mathbb Z,\mathbb Q,\mathbb R,\mathbb C$：整数、有理数、实数、复数；本节用 $\mathbb Z,\mathbb Q,\mathbb R$ 举例。
- $GL_n(F),SL_n(F),M_n(F)$：域 $F$ 上可逆的、行列式为 $1$ 的、以及全体 $n\times n$ 矩阵；本节只作为「矩阵乘法成群」的例子出现，完整讨论在第 7 节。

## 群的定义

群（group）是一对 $(G,\cdot)$，其中 $\cdot$ 是 $G$ 上的二元运算

$$\cdot:\ G\times G\longrightarrow G,$$

且满足三条公理：

- 结合律（associativity）：$(a\cdot b)\cdot c=a\cdot(b\cdot c)$ 对任意 $a,b,c\in G$ 成立；
- 单位元（identity）：存在 $e\in G$，使 $e\cdot a=a\cdot e=a$ 对任意 $a\in G$ 成立；
- 逆元（inverse）：每个 $a\in G$ 都有 $a^{-1}\in G$，使 $a\cdot a^{-1}=a^{-1}\cdot a=e$。

为省事，以下把 $a\cdot b$ 简写成 $ab$。若还满足 $ab=ba$，称 $G$ 为 Abel 群（Abelian group）。如果不是 Abel 群，一般不能调换乘积中两个因子的顺序。

## 单位元、逆元与消去律

**单位元唯一。** 设 $e,f$ 都是单位元。$ef$ 既等于 $e$（因为 $f$ 是单位元），又等于 $f$（因为 $e$ 是单位元），所以 $e=ef=f$。

**逆元唯一。** 设 $b,c$ 都是 $a$ 的逆元，则

$$b=eb=(ca)b=c(ab)=ce=c$$

（各步依次用到：$e$ 是单位元，$c$ 是 $a$ 的逆元，结合律，$b$ 是 $a$ 的逆元，$e$ 是单位元。）

由逆元与结合律得到消去律（cancellation law）：

$$ab=ac\Rightarrow b=c,\qquad ba=ca\Rightarrow b=c.$$

几个常用结论：

- 方程 $ax=b$ 有唯一解 $x=a^{-1}b$，方程 $ya=b$ 有唯一解 $y=ba^{-1}$；
- $(ab)^{-1}=b^{-1}a^{-1}$；
- $(a^{-1})^{-1}=a$。

## 基本例子

- $\mathbb Z,\mathbb Q,\mathbb R,\mathbb C$ 在加法下是 Abel 群，单位元 $0$，逆元 $-a$。
- 域 $F$ 的乘法群 $F^\times=F\setminus\{0\}$；特别地 $\mathbb Q^\times,\mathbb R^\times,\mathbb C^\times$ 在乘法下是 Abel 群（去掉 $0$ 是必要的）。
- $GL_n(F)$（general linear group）是域 $F$ 上可逆 $n\times n$ 矩阵在乘法下构成的群；$SL_n(F)$（special linear group）$=\{A\in GL_n(F):\det A=1\}$ 与正交矩阵全体（$F=\mathbb R$ 时）也各自构成群。矩阵乘法一般 $AB\ne BA$。
- $\mathbb Z_n$ 在模 $n$ 加法下是 Abel 群；$\mathbb Z_n^\times$（与 $n$ 互素的剩余类）在乘法下是 Abel 群。

复合约定：$fg$ 表示先做 $g$ 再做 $f$（从右往左读）。置换和二面体群的计算都按这个约定。

