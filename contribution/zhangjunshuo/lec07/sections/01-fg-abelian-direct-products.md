# 有限生成阿贝尔群与直积

**本节用到的记号，先一次交代清楚**（第 6 讲已逐个定义过，这里只复述结论，方便单独阅读本节）：

- $G$：群；$e$：单位元；$|G|$：群的阶；$H\le G$：子群。
- $S\subseteq G$：$G$ 的一个子集；$\langle S\rangle=\bigcap_{S\subseteq H\le G}H$：由 $S$ 生成的子群，即包含 $S$ 的所有子群的交。
- $G=\langle g\rangle$：由单个元素生成，此时 $G$ 是**循环群**。
- $C_n,\mathbb Z_n$：$n$ 阶循环群与整数模 $n$ 的剩余类群；$\mathbb Z$ 是无限循环群。
- $\varphi:G\to H$：群同态；$\ker\varphi$：核；$\operatorname{im}\varphi$：像；$G/\ker\varphi\cong\operatorname{im}\varphi$。
- $N\trianglelefteq G$：正规子群；$G/N$：商群；$\cong$：同构。
- $G_1\times G_2$：群的直积，按分量运算 $(g_1,g_2)(h_1,h_2)=(g_1h_1,g_2h_2)$；$H,K\le G$ 且 $H\cap K=\{e\}$、$HK=G$ 时称**内部直积**。
- $\gcd(m,n)$：最大公因数；$\mathbb Z_m\times\mathbb Z_n\cong\mathbb Z_{mn}\iff\gcd(m,n)=1$。
- $|G|$ 的素幂分解：有限生成阿贝尔群结构定理写成 $\mathbb Z^r\times\mathbb Z_{p_1^{a_1}}\times\cdots$。

## 生成子群与循环群

设 $G$ 是群，$S\subseteq G$。由 $S$ 生成的子群记为 $\langle S\rangle$，它是包含 $S$ 的所有子群的交：

$$
\langle S\rangle=\bigcap_{S\subseteq H\le G}H.
$$

如果存在有限集 $S$ 使得 $G=\langle S\rangle$，就说 $G$ 是**有限生成群**。这和“有限群”不同：$\mathbb Z$ 是一个无限的有限生成群，而 $(\mathbb R,+)$ 不是有限生成群。

若 $G=\langle g\rangle$，则 $G$ 称为循环群。考虑

$$
\varphi_g:\mathbb Z\longrightarrow G,\qquad n\longmapsto g^n.
$$

这是一个满同态。若 $g$ 的阶为有限值 $m$，则

$$
\ker\varphi_g=m\mathbb Z,
\qquad G\cong\mathbb Z/m\mathbb Z=\mathbb Z_m.
$$

若 $g$ 的阶为无穷，则 $\ker\varphi_g=\{0\}$，从而 $G\cong\mathbb Z$。因此循环群恰好分为 $\mathbb Z$ 和 $\mathbb Z_m$ 两类；循环群都是阿贝尔群。

## 直积与内部直积

给定群 $G_1,G_2$，它们的外部直积为

$$
G_1\times G_2=\{(g_1,g_2):g_i\in G_i\},
$$

运算按分量定义：

$$
(g_1,g_2)(h_1,h_2)=(g_1h_1,g_2h_2).
$$

单位元是 $(e_1,e_2)$，逆元是 $(g_1^{-1},g_2^{-1})$。有限个群的直积递归地定义。

若 $H,K\le G$ 满足

$$
H\trianglelefteq G,\qquad K\trianglelefteq G,\qquad H\cap K=\{e\},\qquad HK=G,
$$

则称 $G$ 是 $H,K$ 的内部直积，并且

$$
G\cong H\times K,
\qquad (h,k)\longmapsto hk
$$

是一个同构。课堂证明中常用的等价条件是：$H\cap K=\{e\}$、$HK=G$，且 $hk=kh$ 对所有 $h\in H,k\in K$ 成立；存在性来自 $HK=G$，唯一性来自 $H\cap K=\{e\}$；交换性保证乘法映射保持群运算。

一个常用判据是：若 $\gcd(m,n)=1$，则

$$
\mathbb Z_m\times\mathbb Z_n\cong\mathbb Z_{mn};
$$

若 $\gcd(m,n)>1$，则直积中任一元素的阶都不能达到 $mn$，所以它不是循环群。

## 有限生成阿贝尔群结构定理

**结构定理（初等因子形式）**。每个有限生成阿贝尔群 $G$ 都同构于

$$
\mathbb Z^r\times
\mathbb Z_{p_1^{a_1}}\times\cdots\times
\mathbb Z_{p_t^{a_t}},
$$

其中 $r\ge 0$，每个 $p_i$ 是素数，$a_i\ge 1$。有限群时 $r=0$；自由秩 $r$ 以及素数幂因子的多重集合由 $G$ 唯一决定（因子次序除外）。

等价地，可以使用不变因子形式（这里采用 [DS] 常见的升序整除链记法；[DF] §5.2 常按降序编号，但内容相同）：

$$
G\cong \mathbb Z^r\times\mathbb Z_{d_1}\times\cdots\times\mathbb Z_{d_s},
\qquad d_1\mid d_2\mid\cdots\mid d_s,
$$

其中 $d_i>1$。这两种写法描述同一分类：前者把每个素数幂分开，后者把不同素数幂重新组合成整除链。

这里的“有限生成”是必要条件。比如 $(\mathbb R,+)$ 中任意有限生成子群都是可数的，而 $\mathbb R$ 不可数，因此 $\mathbb R$ 不可能由有限多个元素生成。

## 课堂证明提纲：从一个最小关系开始

课堂上给出的证明思路是对生成元个数归纳。设

$$
G=\langle a_1,\ldots,a_t\rangle
$$

是有限生成阿贝尔群，并考虑满同态

$$
\Phi:\mathbb Z^t\longrightarrow G,
\qquad (c_1,\ldots,c_t)\longmapsto c_1a_1+\cdots+c_ta_t.
$$

若 $\ker\Phi=\{0\}$，则 $G\cong\mathbb Z^t$。若核非零，则课堂上的“最小关系”有一个具体含义：在所有 $t$ 元生成元组 $(a_1,\ldots,a_t)$ 以及相应的非零整数关系 $(c_1,\ldots,c_t)\in\ker\Phi$ 中，按 $\sum_i|c_i|$ 取最小值；交换生成元、变号和做初等整数变换仍然属于同一类选择。音频中“把两个系数相减”指的正是这种生成元变换，和欧几里得算法的步骤相同。

通过可逆的整数初等变换（也就是把生成元换成另一组生成元 $b_1,\ldots,b_t$），可以把关系化为只有一个坐标非零：

$$
(d,0,\ldots,0)\in\ker\Phi,\qquad d>0.
$$

这里 $d$ 取为经过这些变换后能够出现的最小正首坐标。把任意关系的首坐标 $k$ 写成 $k=qd+r$，再减去 $q(d,0,\ldots,0)$；若 $r\ne0$，就会得到更小的正首坐标，矛盾。因此 $d\mid k$，特别地 $b_1$ 的阶正好是 $d$。

令 $B=\langle b_2,\ldots,b_t\rangle$。若 $k b_1\in B$，上面的整除性说明 $d\mid k$；于是 $\langle b_1\rangle\cap B=\{0\}$，而 $G$ 由这两个子群生成。由于 $G$ 阿贝尔，乘法映射 $\langle b_1\rangle\times B\to G$ 是同构。再对 $B$ 的生成元个数归纳，就得到有限个循环群的直积；$d=1$ 时删去平凡因子。

这段是课堂给出的存在性证明轮廓；初等因子和不变因子分解的唯一性仍采用教材中的有限生成 $\mathbb Z$-模结构定理。

## 记忆点

- $\mathbb Z$ 是无限但有限生成；有限生成不等于有限。
- 循环群由一个元素决定，分类来自 $\mathbb Z$ 的核是 $0$ 还是 $m\mathbb Z$。
- 外部直积把群放在有序对上；内部直积把同样的结构放回一个大群中。
- 有限生成阿贝尔群的自由部分是 $\mathbb Z^r$，挠部分是有限循环群的直积。
- 课堂证明用“最小关系 + 归纳”说明分解的存在性；唯一性通常用有限生成 $\mathbb Z$-模的结构定理。

## 参考对照

- [DF] §§5.1–5.2：Direct Products 与 Fundamental Theorem of Finitely Generated Abelian Groups。
- [DS] §9.6：直积、内部直积与有限阿贝尔群结构定理。
