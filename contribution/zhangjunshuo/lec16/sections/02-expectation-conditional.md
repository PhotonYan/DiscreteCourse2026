# 期望、条件期望与全期望公式

期望把“随机变量的取值”按概率加权平均。本节先把期望的基本性质立起来，再讲条件期望——这里最容易出的错，是把 $E[X\mid Y=y]$（一个数）和 $E[X\mid Y]$（一个随机变量）混为一谈。

**本节用到的记号：** $E[X]$ 为期望；$p_X(x)=P(X=x)$；$p_{X,Y}(x,y)=P(X=x,Y=y)$ 为联合分布；$p_{X\mid Y}(x\mid y)$ 为条件分布；$E[X\mid Y]$ 为条件期望（随机变量），$E[X\mid Y=y]$ 为给定 $Y=y$ 后的数值。

## 期望的定义

离散随机变量 $X$ 的期望定义为

$$
E[X]=\sum_{\omega\in\Omega}P(\omega)X(\omega)
=\sum_{x}x\,p_X(x).
$$

两个写法等价：前者按样本点加权，后者按 $X$ 的取值合并同类项。

**基本性质.**

- 线性：$E[aX+bY]=aE[X]+bE[Y]$。
- 单调：$X\le Y$ 恒成立 $\Rightarrow E[X]\le E[Y]$。
- 指示变量：$E[\mathbf 1_A]=P(A)$。
- 函数期望：若 $g$ 是实值函数，则
  $$
  E[g(X)]=\sum_x g(x)p_X(x).
  $$
- 独立乘积：若 $X,Y$ 独立且期望存在，则
  $$
  E[XY]=E[X]E[Y].
  $$

独立乘积的证明：把联合分布按乘积展开，

$$
E[XY]=\sum_{x,y}xy\,p_X(x)p_Y(y)
=\Bigl(\sum_x x p_X(x)\Bigr)\Bigl(\sum_y y p_Y(y)\Bigr).
$$

## 条件期望

给定事件 $B$，条件期望是

$$
E[X\mid B]=\sum_x x\,p_{X\mid B}(x)
=\sum_{\omega\in B}\frac{P(\omega)}{P(B)}X(\omega).
$$

给定 $Y=y$，条件期望是

$$
E[X\mid Y=y]=\sum_x x\,p_{X\mid Y}(x\mid y).
$$

它是一个数。

**关键区别.**

- $E[X\mid Y=y]$：给定一个具体值 $y$，得到**数值**；
- $E[X\mid Y]$：还没有给定 $Y$ 的值，它是 $Y$ 的函数，因此是一个**随机变量**。

所以 $E[X\mid Y]$ 可以继续取期望。

## 全期望公式

若 $Y$ 是离散随机变量，则

$$
E[X]=E\bigl[E[X\mid Y]\bigr]
=\sum_y P(Y=y)E[X\mid Y=y].
$$

**证明.** 把右边展开：

$$
\begin{aligned}
\sum_y P(Y=y)E[X\mid Y=y]
&=\sum_y P(Y=y)\sum_x x\frac{P(X=x,Y=y)}{P(Y=y)}\\
&=\sum_{x,y}xP(X=x,Y=y)\\
&=\sum_x xP(X=x)=E[X].
\end{aligned}
$$

这条公式也叫**塔性质**（tower property）：先对 $Y$ 分层，再对每层求条件期望，最后按 $Y$ 的分布加权。

## 联合分布、边缘分布与条件分布

两个随机变量的联合分布是

$$
p_{X,Y}(x,y)=P(X=x,Y=y).
$$

边缘分布由“把另一个变量求和掉”得到：

$$
p_X(x)=\sum_y p_{X,Y}(x,y),\qquad
p_Y(y)=\sum_x p_{X,Y}(x,y).
$$

条件分布为

$$
p_{X\mid Y}(x\mid y)=\frac{p_{X,Y}(x,y)}{p_Y(y)}
\quad(P(Y=y)>0).
$$

因此联合分布可以拆成

$$
p_{X,Y}(x,y)=p_Y(y)p_{X\mid Y}(x\mid y).
$$

对称地也有 $p_{X,Y}=p_Xp_{Y\mid X}$。

**链式法则.** 对多个随机变量，

$$
p_{X_1,\dots,X_n}
=p_{X_1}p_{X_2\mid X_1}p_{X_3\mid X_1,X_2}\cdots
p_{X_n\mid X_1,\dots,X_{n-1}}.
$$

**与马尔可夫链的联系.** 如果 $X_{t+1}$ 在给定 $X_t$ 后与更早的历史条件独立，那么

$$
p_{X_{t+1}\mid X_0,\dots,X_t}
=p_{X_{t+1}\mid X_t},
$$

这就是“转移核”/Markov 核。后面马尔可夫链的分布演化就是“当前分布乘以转移核”。

## 期望的例题

**例 1（指示变量分解）.** 设 $X$ 是 $n$ 次试验中的成功次数，$X=\sum_{i=1}^n\mathbf 1_{A_i}$，其中 $A_i$ 为第 $i$ 次成功。则

$$
E[X]=\sum_{i=1}^nE[\mathbf 1_{A_i}]=\sum_{i=1}^nP(A_i)=np
$$

（同分布时）。这一步不需要独立性；线性期望永远成立。

**例 2（条件期望）.** 掷一枚公平骰子，$Y$ 为点数。给定 $Y$ 为偶数，求 $E[Y\mid Y\text{ 为偶数}]$：

$$
E[Y\mid Y\in\{2,4,6\}]
=\frac{2+4+6}{3}=4.
$$

**例 3（全期望）.** 先抛一枚公平硬币：正面则掷 $2$ 次骰子，反面则掷 $1$ 次；$X$ 为点数之和。令 $N$ 为掷骰次数，则

$$
E[X]=E\bigl[E[X\mid N]\bigr]
=\frac12\cdot 2\cdot\frac72+\frac12\cdot 1\cdot\frac72
=\frac{21}{4}.
$$

这里 $E[X\mid N]=N\cdot 7/2$，再对 $N$ 取期望。
