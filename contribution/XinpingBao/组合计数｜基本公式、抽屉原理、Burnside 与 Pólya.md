## 1. 排列、组合与基本恒等式

$$P(n,k)=\frac{n!}{(n-k)!},\qquad \binom nk=\frac{n!}{k!(n-k)!}.$$

组合数满足

$$\binom nk=\binom n{n-k}=\binom{n-1}k+\binom{n-1}{k-1},\qquad k\binom nk=n\binom{n-1}{k-1}.$$

多项式系数（把 $n$ 个不同元素放入 $r$ 个有标记组，组大小为 $k_i$）：

$$\binom{n}{k_1,\ldots,k_r}=\frac{n!}{k_1!\cdots k_r!},\quad \sum_i k_i=n.$$

二项式定理：

$$ (x+y)^n=\sum_{k=0}^{n}\binom nk x^k y^{n-k}.$$

常用求和式：

$$\sum_{k=0}^n\binom nk=2^n,\quad \sum_{k=r}^n\binom kr=\binom{n+1}{r+1},\quad \sum_{k=0}^n\binom nk^2=\binom{2n}n,$$
$$\sum_{k=0}^n k\binom nk=n2^{n-1},\qquad \sum_{k=0}^n\binom rk\binom s{n-k}=\binom{r+s}n.$$

## 2. 抽屉原理

> **抽屉原理**：把 $N$ 个物件放入 $k$ 个盒子，至少有一个盒子包含不少于 $\lceil N/k\rceil$ 个物件。特别地，$k+1$ 个物件放进 $k$ 个盒子，必有两个落在同一盒。

**证明**：若每盒至多 $\lceil N/k\rceil-1$ 个，则总数小于 $N$，矛盾。等价地，若每盒最多 $r$ 个，则物件总数最多 $kr$。

**常见应用：单调子序列**。任意 $rs+1$ 个互异实数序列，必有长度至少 $r+1$ 的递增子序列或长度至少 $s+1$ 的递减子序列。对每个位置记以该项结尾的最长递增、递减长度 $(a_i,b_i)$；若两种长度分别不超过 $r,s$，这些二元组只能有 $rs$ 种，但互异性使不同位置的二元组不同，矛盾。

## 3. 容斥原理

$$\left|\bigcup_{i=1}^n A_i\right|=\sum_i|A_i|-\sum_{i<j}|A_i\cap A_j|+\sum_{i<j<k}|A_i\cap A_j\cap A_k|-\cdots.$$

一般地，$\left|\bigcup_i A_i\right|=\sum_{\varnothing\ne J\subseteq[n]}(-1)^{|J|+1}\left|\bigcap_{j\in J}A_j\right|$。容斥适合“至少满足一个禁条件”的计数；先数每个交集，再按交集大小交替加减。

## 4. 普通与指数生成函数

序列 $(a_n)$ 的普通生成函数（OGF）和指数生成函数（EGF）分别为

$$A(x)=\sum_{n\ge0}a_nx^n,\qquad \widehat A(x)=\sum_{n\ge0}a_n\frac{x^n}{n!}.$$

若 OGF 相乘 $C=AB$，则 $c_n=\sum_{k=0}^n a_kb_{n-k}$；若 EGF 相乘 $\widehat C=\widehat A\widehat B$，则 $c_n=\sum_{k=0}^n\binom nk a_kb_{n-k}$。

| 系数 $a_n$ | OGF $\sum a_nx^n$ | 备注 |
|:--|:--|:--|
| $1$ | $1/(1-x)$ | 任意个同类部件 |
| $n+1$ | $1/(1-x)^2$ | 两个非负整数之和为 $n$ |
| $n$ | $x/(1-x)^2$ | $n\ge0$ |
| $\binom{n}{k}$（固定 $k$） | $x^k/(1-x)^{k+1}$ | 按广义二项式定理 |
| Fibonacci 型 $f_0=f_1=1,\ f_n=f_{n-1}+f_{n-2}$ | $1/(1-x-x^2)$ | 长度 $1,2$ 瓷砖铺长度 $n$ |

求递推的生成函数：将递推乘 $x^n$ 后对有效 $n$ 求和，代入初值，解出 $A(x)$。乘积生成函数表示有序独立部件的组合；权重与对象需先定义清楚。

## 5. 群作用与 Burnside 引理

设有限群 $G$ 作用于有限集合 $S$，其中轨道代表在所给对称下等价的对象。记 $\operatorname{Fix}(g)=\{s:g\cdot s=s\}$。Burnside 引理：

$$\boxed{\#(S/G)=\frac1{|G|}\sum_{g\in G}|\operatorname{Fix}(g)|.}$$

**用法**：列出群元素（或共轭类），算每个置换固定多少配置，再取平均。旋转等价时通常取循环群；旋转与翻转都等价时取二面体群。Burnside 数的是轨道，也就是不同等价类数。

## 6. Pólya 计数与循环指标

对 $G$ 在 $n$ 个位置上的置换作用，置换 $g$ 若有 $c_i(g)$ 个长度为 $i$ 的循环，则其循环指标为

$$Z_G(a_1,\ldots,a_n)=\frac1{|G|}\sum_{g\in G}\prod_{i=1}^n a_i^{c_i(g)}.$$

这是把 Burnside 固定染色数按循环结构汇总的形式。若有 $q$ 种颜色，允许重复且只求染色总数，令每个 $a_i=q$：

$$\#\text{染色}=Z_G(q,q,\ldots,q).$$

若要记录每种颜色的使用次数，设颜色权变量为 $x_1,\dots,x_q$，代入

$$a_i=x_1^i+\cdots+x_q^i.$$

代入后的多项式中，$x_1^{m_1}\cdots x_q^{m_q}$ 的系数即颜色 $j$ 恰用 $m_j$ 次的不同染色数。

### 6.1 常见循环指标

循环群 $C_n$（对正 $n$ 边形只考虑旋转）：

$$Z_{C_n}=\frac1n\sum_{d\mid n}\varphi(d)a_d^{n/d},$$

其中 $\varphi$ 是 Euler 函数。二面体群 $D_n$（阶 $2n$，包括 $n$ 次旋转和 $n$ 个反射）可直接由各旋转、反射的循环型逐个相加，再除以 $2n$；不同 $n$ 奇偶时反射循环型不同，计算前应单独检查。

### 6.2 例：正方形顶点用两色染色

正方形对称群 $D_4$ 在四个顶点上的循环型为：恒等置换 $1^4$ 一种；$90^\circ$ 和 $270^\circ$ 旋转为 $4$-循环两种；$180^\circ$ 旋转及两条边轴反射为 $2^2$ 三种；两条顶点轴反射为 $1^2 2$ 两种。因此

$$Z_{D_4}=\frac18\left(a_1^4+2a_4+3a_2^2+2a_1^2a_2\right).$$

用黑白两色染色，代入 $a_i=2$：

$$\#=Z_{D_4}(2,2,2,2)=\frac18(16+4+12+16)=6.$$

这就是 正方形顶点黑白染色，在旋转和翻转下视为相同 的计数。



