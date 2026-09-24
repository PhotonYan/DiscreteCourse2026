# 正规子群

参考：[DF] Dummit–Foote《Abstract Algebra》§3.1（Proposition 7）、§2.2（中心 $Z(G)$）；[DS]《离散数学与结构》§9.5。

## 定义与等价形式

设 $N\le G$。若对每个 $g\in G$ 都有

$$gN=Ng,$$

称 $N$ 为 $G$ 的正规子群（normal subgroup），记作 $N\trianglelefteq G$。等价地，

$$N\trianglelefteq G\iff \forall g\in G,\ gNg^{-1}=N\iff \forall g\in G,\ \forall n\in N,\ gng^{-1}\in N.$$

最后一个单侧条件推出等号的方法：对 $g^{-1}$ 用同一条件得 $g^{-1}Ng\subseteq N$，于是对任意 $x\in N$，有 $x=g(g^{-1}xg)g^{-1}\in gNg^{-1}$，得到反向包含，两边相等。

正规性是 $N$ 在 $G$ 中的性质，不表示 $N$ 自身是 Abel 群：$gng^{-1}\in N$ 与 $gn=ng$ 是两回事。

## 判别与例子

**Abel 群的情形。** 若 $G$ 是 Abel 群，则任意子群 $N$ 都正规，因为 $gng^{-1}=n$；更一般地，$N\le Z(G)$ 时 $N\trianglelefteq G$，其中 $Z(G)=\{g\in G:gx=xg\ \text{对一切}\ x\in G\}$ 是 $G$ 的中心（center）。但 $N$ 本身是 Abel 群远远不够，不正规的子群照样存在（见下例）。

**指数 2。** 若 $|G/N|=2$，则 $N\trianglelefteq G$。证明：$g\in N$ 时 $gN=Ng=N$；$g\notin N$ 时，左陪集 $gN$ 只能等于另一个非 $N$ 的块，即 $G\setminus N$，同理 $Ng=G\setminus N$，所以 $gN=Ng$。

**反例。** $H=\{e,(1\ 2)\}\le S_3$ 不正规，因为

$$(1\ 2\ 3)(1\ 2)(1\ 2\ 3)^{-1}=(2\ 3)\notin H.$$

可见正规性是需要验证的额外条件，子群并不自动正规。

## 传递性

子群的包含关系传递：$K\le H$ 且 $H\le G$ 推出 $K\le G$。正规性没有这种传递性：$K\trianglelefteq H$ 且 $H\trianglelefteq G$ 推不出 $K\trianglelefteq G$（它们只能推出 $gkg^{-1}\in H$，未必落在 $K$ 中）。在 $D_8$ 中取

$$G=D_8,\qquad H=\{e,r^2,s,r^2s\},\qquad K=\{e,s\}.$$

$|G/H|=2$ 给出 $H\trianglelefteq G$；$|H/K|=2$ 给出 $K\trianglelefteq H$。但是

$$rsr^{-1}=r^2s\notin K,$$

所以 $K\not\trianglelefteq G$。正规性取决于子群嵌在哪个大群里，不能只看子群本身。

