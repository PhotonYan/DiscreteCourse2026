# 统计距离（TV 距离）

比较两个概率分布有多“像”，最基础的工具是**统计距离**，也叫**全变差距离**（total variation distance, TV distance）。它的定义非常直观：把两个分布逐点相减，取绝对值再求和，最后除以 $2$。

**本节用到的记号：** $P,Q$ 是同一可数集合 $\mathcal X$ 上的两个概率分布；$P(x),Q(x)$ 为概率质量函数；$\Delta_{\mathrm{TV}}(P,Q)$ 为 TV 距离；$\operatorname{supp}(P)$ 为支撑集。

## 定义与等价形式

$$
\boxed{
\Delta_{\mathrm{TV}}(P,Q)
=\frac12\sum_{x\in\mathcal X}|P(x)-Q(x)|
}.
$$

它恰好是 $P-Q$ 的 $L^1$ 范数的一半。因为两个分布的总质量都为 $1$，所以：

$$
\Delta_{\mathrm{TV}}(P,Q)
=\sum_{x:P(x)>Q(x)}(P(x)-Q(x))
=\sum_{x:Q(x)>P(x)}(Q(x)-P(x)).
$$

也可以写成

$$
\Delta_{\mathrm{TV}}(P,Q)
=\sum_x\max\{0,P(x)-Q(x)\}.
$$

以及

$$
\Delta_{\mathrm{TV}}(P,Q)
=1-\sum_x\min\{P(x),Q(x)\}.
$$

最后一条的直观：两个分布“重叠”的质量是 $\sum_x\min(P(x),Q(x))$，剩下的部分就是它们不同的质量；由于总质量各为 $1$，不同部分两边各占一半，所以除以 $2$ 正好是 TV。

**例（Bernoulli）.** 若 $P=\mathrm{Bern}(p)$、$Q=\mathrm{Bern}(q)$，则

$$
\Delta_{\mathrm{TV}}(P,Q)=|p-q|.
$$

**基本性质.**

- $0\le\Delta_{\mathrm{TV}}(P,Q)\le1$；
- 对称：$\Delta_{\mathrm{TV}}(P,Q)=\Delta_{\mathrm{TV}}(Q,P)$；
- 同一分布距离为 $0$：$\Delta_{\mathrm{TV}}(P,P)=0$；
- 满足三角不等式：$\Delta_{\mathrm{TV}}(P,R)\le\Delta_{\mathrm{TV}}(P,Q)+\Delta_{\mathrm{TV}}(Q,R)$。

所以 TV 是一个真正的距离（度量）。

## 耦合解释

TV 距离还有一个非常重要、也非常好用的等价定义：**两个分布的最优耦合下，两个随机变量不相等的概率**。

设随机变量 $(X,Y)$ 的联合分布以 $P$ 为 $X$ 的边缘、$Q$ 为 $Y$ 的边缘（称为 $P,Q$ 的一个**耦合**）。则

$$
\boxed{
\Delta_{\mathrm{TV}}(P,Q)
=\min_{\text{coupling }(X,Y)}\Pr[X\ne Y]
}.
$$

**下界.** 对任意耦合，

$$
\begin{aligned}
\Pr[X\ne Y]
&\ge\Pr[X=x,Y\ne x]\quad\text{对某个 }x\\
&\ge P(x)-Q(x)\quad\text{当 }P(x)>Q(x).
\end{aligned}
$$

对所有 $x$ 取正部并求和，得到 $\Pr[X\ne Y]\ge\Delta_{\mathrm{TV}}(P,Q)$。

**上界（构造最优耦合）.** 令

$$
m=\sum_x\min\{P(x),Q(x)\}=1-\Delta_{\mathrm{TV}}(P,Q).
$$

构造联合分布：

- 以 $\min(P(x),Q(x))$ 的概率令 $X=Y=x$（对每个 $x$）；
- 剩下的概率 $1-m=\Delta_{\mathrm{TV}}(P,Q)$ 放在 $X\ne Y$ 的部分，并按 $P,Q$ 超出最小值的部分分配。

这样边缘分别是 $P,Q$，且 $\Pr[X\ne Y]=\Delta_{\mathrm{TV}}(P,Q)$，达到下界。

**直观.** TV 就是“把两个分布配成一对时，最少有多少概率会不相等”；能配得越像，TV 越小。

## 一个例子：两个 Bernoulli

设 $P=\mathrm{Bern}(1/3)$，$Q=\mathrm{Bern}(2/3)$。则

$$
\Delta_{\mathrm{TV}}(P,Q)
=\frac12\left(\left|\frac13-\frac23\right|
+\left|\frac23-\frac13\right|\right)
=\frac13.
$$

最优耦合下，两个随机变量不相等的概率可以做到 $1/3$；任何耦合下都至少是 $1/3$。

## TV 与“不可区分”

若 $\Delta_{\mathrm{TV}}(P,Q)\le\varepsilon$，则对任何事件 $A$，

$$
|P(A)-Q(A)|\le\varepsilon.
$$

**证明.** 因为

$$
P(A)-Q(A)=\sum_{x\in A}(P(x)-Q(x)),
$$

取绝对值后不超过 $\sum_x|P(x)-Q(x)|=2\Delta_{\mathrm{TV}}(P,Q)$，所以差不超过 $\varepsilon$。

这说明：如果两个分布 TV 很小，那么任何统计实验都很难区分它们；这就是“统计距离”的名字来源。
