# 条件熵、联合熵与链式法则

熵描述单个随机变量的不确定性；条件熵描述“已知 $Y$ 之后，$X$ 还剩多少不确定性”。本节的核心公式是链式法则

$$
H(X,Y)=H(Y)+H(X\mid Y),
$$

以及“条件不会增加熵”：

$$
H(X\mid Y)\le H(X).
$$

**本节用到的记号：** $P_{X,Y}(x,y)=P(X=x,Y=y)$；$P_{X\mid Y}(x\mid y)=P(X=x\mid Y=y)$；$H(X\mid Y=y)$ 为给定 $Y=y$ 的条件熵；$H(X\mid Y)$ 为对这些条件熵按 $Y$ 的分布取平均。

## 条件熵的定义

给定 $Y=y$，条件分布为 $P_{X\mid Y=y}$，其熵为

$$
H(X\mid Y=y)
=\sum_xP_{X\mid Y}(x\mid y)\log\frac1{P_{X\mid Y}(x\mid y)}.
$$

再对 $Y$ 的取值按 $P_Y(y)$ 加权平均，得到**条件熵**：

$$
H(X\mid Y)
=\sum_yP_Y(y)H(X\mid Y=y).
$$

**注意.** $H(X\mid Y=y)$ 是一个数；$H(X\mid Y)$ 是一个数（不是随机变量）——它已经把 $Y$ 平均掉了。若把 $H(X\mid Y)$ 写成随机变量，应先定义 $H(X\mid Y)(\omega)$，再取期望；本课程不需要这样写。

**特例.** 若 $Y$ 是常数，则 $H(X\mid Y)=H(X)$；若 $Y=X$，则 $H(X\mid Y)=0$。

## 联合熵

两个随机变量的联合熵为

$$
H(X,Y)
=\sum_{x,y}P_{X,Y}(x,y)\log\frac1{P_{X,Y}(x,y)}.
$$

它衡量的是“同时观察 $X,Y$ 时总的平均不确定性”。

## 链式法则

**定理.**

$$
\boxed{
H(X,Y)=H(Y)+H(X\mid Y)
}
$$

对称地也有 $H(X,Y)=H(X)+H(Y\mid X)$。

**证明.** 把联合分布写成 $P_{X,Y}(x,y)=P_Y(y)P_{X\mid Y}(x\mid y)$：

$$
\begin{aligned}
H(X,Y)
&=\sum_{x,y}P_{X,Y}(x,y)\log\frac1{P_{X,Y}(x,y)}\\
&=\sum_{x,y}P_{X,Y}(x,y)\left[
\log\frac1{P_Y(y)}+\log\frac1{P_{X\mid Y}(x\mid y)}
\right]\\
&=\sum_yP_Y(y)\log\frac1{P_Y(y)}
+\sum_{x,y}P_{X,Y}(x,y)\log\frac1{P_{X\mid Y}(x\mid y)}\\
&=H(Y)+H(X\mid Y).
\end{aligned}
$$

最后一项正是条件熵的定义。

**多变量链式法则.** 对 $X_1,\dots,X_n$，

$$
H(X_1,\dots,X_n)
=H(X_1)+H(X_2\mid X_1)+\cdots
+H(X_n\mid X_1,\dots,X_{n-1}).
$$

证明：反复用两变量链式法则，把最后一个变量单独提出来：

$$
H(X_1,\dots,X_n)=H(X_1,\dots,X_{n-1})+H(X_n\mid X_1,\dots,X_{n-1}),
$$

再对前 $n-1$ 个变量归纳。

## 熵的凹性（Jensen 证明）

先单独证明熵作为分布的函数是**凹函数**；这一步只用 Jensen，不用 KL，也不用条件熵，所以后面证明“条件不增加熵”不会循环论证。

**引理.** 设 $P_0,P_1$ 是两个分布，$\lambda\in[0,1]$，$P=\lambda P_0+(1-\lambda)P_1$。则

$$
\boxed{
H(P)\ge\lambda H(P_0)+(1-\lambda)H(P_1)
}.
$$

**证明.** 对每个 $x$，函数

$$
\varphi(t)=-t\log t\qquad(t\ge0)
$$

是凹函数，因为

$$
\varphi''(t)=-\frac1t<0\qquad(t>0).
$$

由 Jensen（或直接由凹函数定义），

$$
\varphi\bigl(\lambda P_0(x)+(1-\lambda)P_1(x)\bigr)
\ge
\lambda\varphi(P_0(x))+(1-\lambda)\varphi(P_1(x)).
$$

对 $x$ 求和，左边正好是 $H(P)$，右边是 $\lambda H(P_0)+(1-\lambda)H(P_1)$。因此凹性成立。由于 $\varphi$ 严格凹，$0<\lambda<1$ 时等号当且仅当 $P_0=P_1$。

## 条件熵的非负性与“条件不增加熵”

**非负性.**

$$
H(X\mid Y)\ge0.
$$

因为它是若干条件分布的熵的加权平均，而每个熵都非负。

**条件不增加熵.**

$$
\boxed{
H(X\mid Y)\le H(X)
}
$$

等号成立当且仅当 $X,Y$ 独立。

**证明（用熵的凹性）.** 把条件熵写成“条件分布的熵的加权平均”：

$$
H(X\mid Y)
=\sum_yP_Y(y)H(P_{X\mid Y=y}).
$$

由上面的凹性引理，把 $P_{X\mid Y=y}$ 按权重 $P_Y(y)$ 混合，得到

$$
\sum_yP_Y(y)H(P_{X\mid Y=y})
\le
H\Bigl(\sum_yP_Y(y)P_{X\mid Y=y}\Bigr).
$$

而括号里的混合分布正是 $X$ 的边缘分布 $P_X$，所以

$$
H(X\mid Y)\le H(P_X)=H(X).
$$

**等号条件.** 凹性取等需要所有（$P_Y(y)>0$ 的）条件分布 $P_{X\mid Y=y}$ 都相同；此时

$$
P_{X,Y}(x,y)=P_Y(y)P_X(x),
$$

即 $X,Y$ 独立。反过来，若 $X,Y$ 独立，则每个条件分布都等于 $P_X$，等号成立。

**说明.** 这里没有用 KL 散度非负性——KL 是本节之后才引入的；用凹性引理是更直接、也不会循环的证法。

**联合熵的上界.** 由链式法则和条件熵不等式，

$$
H(X,Y)=H(X)+H(Y\mid X)\le H(X)+H(Y),
$$

等号当且仅当 $X,Y$ 独立。多变量情形同样有

$$
H(X_1,\dots,X_n)\le\sum_iH(X_i).
$$

## 条件熵为零的含义

$$
H(X\mid Y)=0
$$

当且仅当：给定 $Y$ 后，$X$ 没有不确定性，即 $X$ 是 $Y$ 的函数（存在可测函数 $f$ 使 $X=f(Y)$ 几乎必然）。

这与“$H(X,Y)=H(Y)$”等价：联合的不确定性全在 $Y$ 上。

## 常见错误

- 把 $H(X\mid Y)$ 与 $H(X\mid Y=y)$ 混为一谈：前者是平均后的数。
- 把链式法则写成 $H(X,Y)=H(X)+H(Y)$；只有独立时才能这样拆。
- 认为 $H(X\mid Y)\le H(X)$ 的等号总是成立；等号要求独立。
- 忘记“条件熵”是“平均条件熵”，不是“某个 $y$ 下的条件熵”。
