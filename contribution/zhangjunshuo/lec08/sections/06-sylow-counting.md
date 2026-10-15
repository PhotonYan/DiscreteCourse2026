# Sylow 子群的个数

**本节用到的记号，先一次交代清楚**：

- $G$：有限群；$|G|=p^am$，$p$ 素数、$p\nmid m$；$P\in\operatorname{Syl}_p(G)$。
- $n_p=|\operatorname{Syl}_p(G)|$：Sylow $p$-子群的个数，本节要证明 $n_p\mid m$ 且 $n_p\equiv1\pmod p$。
- $N_G(P)$：$P$ 的正规化子；$n_p=[G:N_G(P)]$。
- $C_G(x)$：中心化子；$Z(G)$：中心；$\operatorname{Cl}_G(x)$：共轭类。
- $\equiv\pmod p$：同余，$a\equiv b\pmod p\iff p\mid(a-b)$。
- $\mid$：整除；$\nmid$：不整除。
- $C_n$：$n$ 阶循环群；$\cong$：同构；$\times$：直积；$\trianglelefteq$：正规子群；$\le$：子群。
- $(c_1\ c_2\ \cdots\ c_k)$：轮换记号。

## 第三定理

继续设

$$
|G|=p^a m,\qquad p\nmid m,
$$

并记 $n_p=|\operatorname{Syl}_p(G)|$。Sylow 第三定理给出

$$
n_p\mid m,
\qquad
n_p\equiv1\pmod p.
$$

这两个条件经常一起使用：先把 $m$ 的因数列出来，再筛掉不满足模 $p$ 条件的候选值。

## 先证明 $n_p\mid m$

固定一个 Sylow 子群 $P$。由第二定理，$G$ 通过共轭作用在 $\operatorname{Syl}_p(G)$ 上只有一条轨道，这时称作用是**传递的**（transitive）；$P$ 的稳定子是

$$
\operatorname{Stab}_G(P)=\{g:gPg^{-1}=P\}=N_G(P).
$$

轨道--稳定子定理于是给出

$$
n_p=[G:N_G(P)].
$$

因为 $P\le N_G(P)\le G$，指数可以分解为

$$
[G:P]=[G:N_G(P)]\,[N_G(P):P].
$$

左边 $[G:P]=m$，所以

$$
m=n_p\,[N_G(P):P],
$$

从而 $n_p\mid m$。

这里再次出现的是正规化子 $N_G(P)$。不能把稳定子写成中心化子 $C_G(P)$：中心化子要求逐个元素与 $P$ 中所有元素交换，而共轭作用只要求把整个子群 $P$ 保持为集合。

## 再证明 $n_p\equiv1\pmod p$

让 $P$ 自己通过共轭作用在集合

$$
\mathcal S=\operatorname{Syl}_p(G)
$$

上。把 $\mathcal S$ 分解成 $P$-轨道。轨道 $\mathcal O(Q)$ 的大小为

$$
|\mathcal O(Q)|=[P:\operatorname{Stab}_P(Q)]
=[P:P\cap N_G(Q)].
$$

由于 $P$ 是 $p$-群，每个轨道大小都是 $p$ 的幂。我们要证明：除了 $Q=P$ 这一点轨道外，其余轨道大小都被 $p$ 整除。

### 哪些轨道可能是单点？

显然 $P$ 的共轭轨道是单点，因为对任意 $x\in P$，$xPx^{-1}=P$；也就是说 $P\le N_G(P)$。

反过来，假设某个 $Q\in\mathcal S$ 的轨道也是单点。那么

$$
P\le N_G(Q).
$$

子群 $Q$ 按定义正规于 $N_G(Q)$。因此 $P,Q$ 都是 $N_G(Q)$ 的 $p$-子群，并且 $P$ 已经有阶 $p^a$。由于 $N_G(Q)\le G$，它的阶不可能含有比 $p^a$ 更高的 $p$-幂，所以 $P$ 和 $Q$ 都是 $N_G(Q)$ 的 Sylow $p$-子群。由第二定理，它们在 $N_G(Q)$ 中共轭；但 $Q\trianglelefteq N_G(Q)$，其共轭只能还是 $Q$，故 $P=Q$。

因此

$$
\text{单点轨道只有 }\{P\}.
$$

对任意 $Q\ne P$，其轨道不是单点，所以轨道大小这个 $p$ 的幂至少为 $p$，即被 $p$ 整除。把所有轨道大小相加：

$$
n_p=|\mathcal S|
=1+\sum_{\mathcal O\ne\{P\}}|\mathcal O|
\equiv1\pmod p.
$$

这就得到第二个结论。

## 数数时的标准流程

面对“求 $n_p$ 的可能值”这类题，可以固定以下顺序：

1. 分解 $|G|=p^a m$，先确认 Sylow $p$-子群的阶是 $p^a$。
2. 写出 $n_p\mid m$ 的所有正因数候选。
3. 筛选满足 $n_p\equiv1\pmod p$ 的候选。
4. 若只剩 $n_p=1$，立刻得到 Sylow $p$-子群正规；若仍有多个候选，再结合群作用、共轭类或元素计数。

## 例：$S_3$

$$
|S_3|=6=2\cdot3.
$$

这里 $S_3$ 是 $\{1,2,3\}$ 上的对称群，$A_3$ 是其中的偶置换子群。对 $p=3$，有 $n_3\mid2$ 且 $n_3\equiv1\pmod3$，只能是 $n_3=1$。因此唯一的 Sylow $3$-子群

$$
\langle(1\,2\,3)\rangle=A_3
$$

正规于 $S_3$。

对 $p=2$，有 $n_2\mid3$ 且 $n_2\equiv1\pmod2$，候选为 $1$ 或 $3$。实际上三个换位分别生成三个不同的阶 $2$ 子群，所以 $n_2=3$；它们彼此共轭而没有一个正规。

## 例：阶为 $35$ 的群

设 $|G|=35=5\cdot7$。对 $p=7$，$n_7\mid5$ 且 $n_7\equiv1\pmod7$，故 $n_7=1$。对 $p=5$，$n_5\mid7$ 且 $n_5\equiv1\pmod5$，也只能有 $n_5=1$。

记 $P_5$ 为那个唯一的 Sylow $5$-子群、$P_7$ 为唯一的 Sylow $7$-子群（下标就是对应的素数 $p$，与第 7 节 $P_{11},P_{13}$ 的写法一致）。两者都正规；它们阶**互素**（即 $\gcd(5,7)=1$），所以交集只能是 $\{e\}$；又因为两个正规子群的元素彼此交换，乘积是直积，于是

$$
G\cong P_5\times P_7\cong C_5\times C_7\cong C_{35}.
$$

最后一步用了 $C_m\times C_n\cong C_{mn}$（当 $\gcd(m,n)=1$）。

这里“先由数目得到正规，再用正规子群的乘积”是 Sylow 定理最典型的应用。更大的例子（例如 $11^2\cdot13^2$）还要结合“阶为 $p^2$ 的群必阿贝尔”等结果，不能只凭 $n_p$ 的两个条件直接断言循环。

## 参考对照

- [DF] §4.5，Theorem 18(3) 及其证明。
- [DS] 该书正文与习题都没有 Sylow 定理（第 9 章只到同态与直积，第 14 章是 Pólya 方法），本节以 [DF] §4.5 与本讲第 4--5 节的结论为准。
