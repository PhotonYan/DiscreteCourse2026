# Lec 16：概率与概率生成函数

这一讲开始进入概率论。主线是：**概率空间与条件概率** $\to$ **随机变量与分布** $\to$ **期望与条件期望** $\to$ **方差与协方差** $\to$ **概率生成函数与常见分布**。最后用 PGF 统一处理 Bernoulli、二项、几何、负二项与 Poisson，并说明 Poisson 是二项分布的极限。

**来源与编号说明。** 本讲对应 2026 年 11 月 10 日的课堂，原始材料是三页手写稿和两段课堂转写。按你的说明：上一份整理到 Lec14，中间空过一讲，所以这一讲编号为 **Lec16**（Lec14 + 2）。两段转写的第一段只覆盖开头，第二段从条件期望附近开始，且语音识别把不少术语识别得很乱；整理版以**手写稿的公式与结构**为准，用转写补例子和课堂解释，不一致处在文中标注。

## 记号速查

- $\Omega$：样本空间；$\omega$：样本点；$A,B\subseteq\Omega$：事件。
- $P$：概率测度；$p(\omega)$：样本点概率；$P(A\mid B)$：条件概率。
- $X,Y$：随机变量；$p_X(x)=P(X=x)$：分布；$p_{X,Y}$：联合分布。
- $E[X]$：期望；$E[X\mid Y]$：条件期望（随机变量）；$E[X\mid Y=y]$：条件期望（数值）。
- $\operatorname{Var}(X)$：方差；$\operatorname{Cov}(X,Y)$：协方差。
- $G_X(z)=E[z^X]$：概率生成函数；$\varphi_X(t)=E[e^{itX}]$：特征函数。

## 本讲的几条主线

1. **概率空间**：样本点、事件、概率测度；条件概率把样本空间缩小到已知事件。
2. **条件分布与 Bayes**：$p_B(\omega)=p(\omega)/P(B)$（$\omega\in B$）；乘法公式、全概率公式、Bayes 公式。
3. **随机变量**：随机变量是样本空间上的函数；分布 $p_X(x)=P(X=x)$；独立随机变量的联合分布等于边缘分布之积。
4. **期望**：$E[X]=\sum_\omega P(\omega)X(\omega)$；线性性；条件期望与全期望公式 $E[X]=E[E[X\mid Y]]$。
5. **方差与协方差**：$\operatorname{Var}(X)=E[X^2]-(E[X])^2$；协方差双线性；$\operatorname{Var}(X+Y)=\operatorname{Var}(X)+\operatorname{Var}(Y)+2\operatorname{Cov}(X,Y)$。
6. **PGF**：$G_X(z)=E[z^X]$；$G_X'(1)=E[X]$，$G_X''(1)=E[X(X-1)]$，由此读方差；独立和的 PGF 相乘。
7. **常见分布**：Bernoulli、二项、几何、负二项、Poisson 的 PGF；Poisson 是 $\operatorname{Bin}(n,\lambda/n)$ 的极限。

## 勘误与提醒

- 手写稿把“独立 $\Rightarrow$ 不相关”写成了类似“$\Leftrightarrow$”的形式；**反过来不成立**，不相关不一定独立（见第 3 节反例）。
- 手写稿第 2 页底部的 $\operatorname{Var}(X+Y)$ 展开容易漏掉 $2\operatorname{Cov}(X,Y)$；正确形式见第 3 节。
- 几何分布与负二项分布有两套常见约定：数“试验次数”还是数“失败次数”。两套只差平移，PGF、均值都不同；做题先看题目定义（见第 4 节）。
- 转写把“样本空间、条件分布、协方差、生成函数、Poisson”等识别得很乱；公式以手写稿和本整理为准。
- Poisson 过程在课堂最后只作了直观介绍；本笔记把它标为“补充”，不当作本讲核心考点。

## 分节

1. [概率空间、条件概率与随机变量](sections/01-probability-basics.md)
2. [期望、条件期望与全期望公式](sections/02-expectation-conditional.md)
3. [方差、协方差与双线性](sections/03-variance-covariance.md)
4. [概率生成函数与常见分布](sections/04-pgf.md)

## 一页式总览

- 条件概率：$P(A\mid B)=P(A\cap B)/P(B)$；Bayes：$P(B_i\mid A)=P(B_i)P(A\mid B_i)/\sum_jP(B_j)P(A\mid B_j)$。
- 独立：$P(A\cap B)=P(A)P(B)$；随机变量独立：联合分布 $=$ 边缘分布之积。
- 期望：线性；$E[\mathbf 1_A]=P(A)$；独立时 $E[XY]=E[X]E[Y]$。
- 全期望：$E[X]=E[E[X\mid Y]]=\sum_yP(Y=y)E[X\mid Y=y]$。
- 方差：$\operatorname{Var}(X)=E[X^2]-(E[X])^2$；$\operatorname{Var}(X+Y)=\operatorname{Var}X+\operatorname{Var}Y+2\operatorname{Cov}(X,Y)$。
- PGF：$G_X(z)=\sum_kp_kz^k$；$G_X(1)=1$，$G_X'(1)=E[X]$，$G_X''(1)=E[X(X-1)]$。
- 独立和：$G_{X+Y}=G_XG_Y$。
- 常见 PGF：Bernoulli $1-p+pz$；二项 $(1-p+pz)^n$；几何 $pz/(1-(1-p)z)$；Poisson $e^{\lambda(z-1)}$。
