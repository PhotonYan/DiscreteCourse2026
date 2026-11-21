# KL 散度与条件 KL

TV 距离是对称的、取值在 $[0,1]$ 的“统计距离”；本节介绍的 **Kullback–Leibler 散度**（KL divergence）不是对称的，取值可以到 $+\infty$，但它和熵、条件熵、最大似然、假设检验都有很深的关系。

**本节用到的记号：** $P,Q$ 为同一可数集合上的分布；$P(x),Q(x)$ 为概率质量；$D_{\mathrm{KL}}(P\Vert Q)$ 为 KL 散度；$P_{XY},Q_{XY}$ 为联合分布；$P_{Y\mid X},Q_{Y\mid X}$ 为条件分布。

## 定义

$$
\boxed{
D_{\mathrm{KL}}(P\Vert Q)
=\sum_xP(x)\log\frac{P(x)}{Q(x)}
}.
$$

约定：

- $P(x)=0$ 时，该项为 $0$（即 $0\log\frac00=0$）；
- 若 $Q(x)=0$ 而 $P(x)>0$，则 $D_{\mathrm{KL}}(P\Vert Q)=+\infty$。

因此 KL 只在 $P$ 的支撑集包含于 $Q$ 的支撑集时有限；否则为无穷。

**直观.** $D_{\mathrm{KL}}(P\Vert Q)$ 衡量“用分布 $Q$ 去编码/近似真实分布 $P$”时平均多付出的信息量；$P$ 与 $Q$ 越不像，值越大。

## 基本性质

**非负性（Gibbs 不等式）.**

$$
D_{\mathrm{KL}}(P\Vert Q)\ge0,
$$

等号当且仅当 $P=Q$。

**证明（Jensen）.** 令 $f(t)=t\log t$，它是凸函数。则

$$
\begin{aligned}
D_{\mathrm{KL}}(P\Vert Q)
&=\sum_xQ(x)\frac{P(x)}{Q(x)}
\log\frac{P(x)}{Q(x)}\\
&=\sum_xQ(x)f\left(\frac{P(x)}{Q(x)}\right)\\
&\ge f\left(\sum_xQ(x)\frac{P(x)}{Q(x)}\right)\\
&=f(1)=0.
\end{aligned}
$$

这里用了 $f$ 的凸性和 $\sum_xP(x)=\sum_xQ(x)=1$。等号条件由 $f$ 严格凸给出：$P(x)/Q(x)$ 对所有 $x$ 相同，即 $P=Q$。

**其他性质.**

- $D_{\mathrm{KL}}(P\Vert P)=0$。
- **不对称**：一般 $D_{\mathrm{KL}}(P\Vert Q)\ne D_{\mathrm{KL}}(Q\Vert P)$。
- **不满足三角不等式**，所以不是距离。
- 对 $Q$ 是凸函数；对 $(P,Q)$ 是联合凸函数。

**与熵的关系.** 若 $H(P)=-\sum_xP(x)\log P(x)$，则

$$
D_{\mathrm{KL}}(P\Vert Q)
=\sum_xP(x)\log\frac1{Q(x)}-H(P).
$$

第一项是“用 $Q$ 编码 $P$ 的交叉熵”，减去 $P$ 自身的熵，就是多出来的部分。

## 二元 KL

设 $P=\mathrm{Bern}(p)$、$Q=\mathrm{Bern}(q)$，记

$$
d(p\Vert q)
=p\log\frac pq+(1-p)\log\frac{1-p}{1-q}.
$$

（$p,q\in(0,1)$；端点按极限理解。）

**性质.**

- $d(p\Vert q)\ge0$，等号当且仅当 $p=q$；
- $d(p\Vert q)\ne d(q\Vert p)$（一般不对称）；
- 固定 $q$，$d(p\Vert q)$ 关于 $p$ 是凸函数；
- 二阶导数
  $$
  \frac{\partial^2}{\partial p^2}d(p\Vert q)
  =\frac1p+\frac1{1-p}\ge4.
  $$
  因此 $d(p\Vert q)$ 在 $p=q$ 处取最小值 $0$，并且有二次下界
  $$
  d(p\Vert q)\ge2(p-q)^2.
  $$

最后一条可由“$d(q\Vert q)=0$、一阶导在 $q$ 处为 $0$、二阶导至少 $4$”得到：把 $d(\cdot\Vert q)$ 在 $q$ 处 Taylor 展开，二次项系数至少 $2$。

## 条件 KL

给定 $X$，比较两个条件分布 $P_{Y\mid X}$ 与 $Q_{Y\mid X}$。定义**条件 KL 散度**为

$$
D_{\mathrm{KL}}(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X)
=\sum_xP_X(x)\,
D_{\mathrm{KL}}(P_{Y\mid X=x}\Vert Q_{Y\mid X=x}).
$$

它先固定 $X=x$ 比较两个条件分布，再按 $P_X$ 加权平均。

## KL 的链式法则

设

$$
P_{XY}=P_XP_{Y\mid X},\qquad
Q_{XY}=Q_XQ_{Y\mid X}.
$$

则

$$
\boxed{
D_{\mathrm{KL}}(P_{XY}\Vert Q_{XY})
=D_{\mathrm{KL}}(P_X\Vert Q_X)
+D_{\mathrm{KL}}(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X)
}.
$$

**证明.** 把对数拆开：

$$
\begin{aligned}
D_{\mathrm{KL}}(P_{XY}\Vert Q_{XY})
&=\sum_{x,y}P_{XY}(x,y)
\log\frac{P_X(x)P_{Y\mid X}(y\mid x)}
{Q_X(x)Q_{Y\mid X}(y\mid x)}\\
&=\sum_{x,y}P_{XY}(x,y)\log\frac{P_X(x)}{Q_X(x)}\\
&\quad+\sum_{x,y}P_{XY}(x,y)
\log\frac{P_{Y\mid X}(y\mid x)}{Q_{Y\mid X}(y\mid x)}.
\end{aligned}
$$

第一项对 $y$ 求和得

$$
\sum_xP_X(x)\log\frac{P_X(x)}{Q_X(x)}
=D_{\mathrm{KL}}(P_X\Vert Q_X).
$$

第二项按条件 KL 定义就是

$$
\sum_xP_X(x)\sum_yP_{Y\mid X}(y\mid x)
\log\frac{P_{Y\mid X}(y\mid x)}{Q_{Y\mid X}(y\mid x)}
=D_{\mathrm{KL}}(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X).
$$

所以链式法则成立。

**推论（条件 KL 非负）.**

$$
D_{\mathrm{KL}}(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X)\ge0,
$$

因为它是若干非负 KL 的加权平均。

**推论（联合 KL 的分解）.**

$$
D_{\mathrm{KL}}(P_{XY}\Vert Q_{XY})
\ge D_{\mathrm{KL}}(P_X\Vert Q_X),
$$

等号当且仅当条件分布相同（$P_{Y\mid X}=Q_{Y\mid X}$，在 $P_X$ 几乎处处意义下）。

## 与 TV 的对比

- **对称性**：TV 对称；KL 一般不对称。
- **三角不等式**：TV 满足；KL 不满足。
- **取值范围**：TV 在 $[0,1]$；KL 在 $[0,+\infty]$。
- **相同分布**：两者都为 $0$。
- **支撑集不匹配**：TV 仍然有限；KL 可能为 $+\infty$。
- **常见用途**：TV 用于统计不可区分、耦合；KL 用于编码、假设检验、最大似然。

两者也有联系（Pinsker 不等式等），本讲只要求理解定义与链式法则，后续遇到再补。

## 常见错误

- 把 KL 当成距离：它不对称，也不满足三角不等式。
- 忘记约定 $0\log0=0$；以及在 $Q(x)=0,P(x)>0$ 时 KL 为 $+\infty$。
- 条件 KL 的权重用错：应当用 $P_X(x)$，不是 $Q_X(x)$。
- 链式法则中第二项漏掉“条件”符号，写成普通的 $D(P_Y\Vert Q_Y)$。
- 把 $D(P\Vert Q)=0$ 误认为“$P,Q$ 只是很像”；它实际上等价于 $P=Q$。
