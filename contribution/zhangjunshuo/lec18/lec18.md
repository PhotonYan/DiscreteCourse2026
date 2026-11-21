# Lec 18：互信息、集中不等式与 Sanov 大偏差

这一讲从 KL/互信息出发，先建立**集中不等式**（Markov、Chebyshev、Chernoff），再引入**类型计数**与 **Sanov 大偏差**，最后用**数据处理不等式**说明“信息处理不会增加信息”。

**来源与编号说明。** 本讲对应 2026 年 11 月 17 日的课堂，整理依据是用户提供的三页手写稿、上半节旧转写，以及下半节的重新转写。上一份笔记是 Lec17（11 月 12 日），所以本次编号为 **Lec18**。手写稿是公式和结构的主要依据；转写用于补课堂解释与例子。下半节旧转写不完整，本笔记使用重新转写的版本。

## 记号速查

- $\operatorname{Bern}(p)$：伯努利分布；$X_1,\dots,X_n$ iid $\sim P$。
- $H(X)$：熵；$I(X;Y)$：互信息；$I(X;Y\mid Z)$：条件互信息。
- $D(P\Vert Q)$：KL 散度；$D(q\Vert p)$：二元 KL。
- $T_i=\#\{j:X_j=i\}$：频数；$Q_i=T_i/n$：经验分布/类型。
- $\Delta_{\mathrm{TV}}$：TV 距离；$X\to Y\to Z$：马尔可夫链。

## 本讲的几条主线

1. **KL 与互信息**：$D(P\Vert U)=\log n-H(P)$；$I(X;Y)=H(X)+H(Y)-H(X,Y)=D(P_{XY}\Vert P_XP_Y)$；条件互信息可增可减。
2. **Markov/Chebyshev**：非负性给 $1/a$ 尾界，方差给 $1/a^2$ 尾界。
3. **Chernoff**：用指数矩得到 $e^{-\Theta(n)}$ 尾界；Bernoulli 和的指数为 $D(q\Vert p)$。
4. **类型计数**：类型类大小约 $e^{nH(Q)}$，类型概率约 $e^{-nD(Q\Vert P)}$。
5. **Sanov**：$P(Q\in\mathcal R)\asymp e^{-n\min_{Q\in\mathcal R}D(Q\Vert P)}$；指数紧，差多项式因子。
6. **DPI**：马尔可夫链 $X\to Y\to Z$ 下，$I(X;Z)\le I(X;Y)$，TV/KL 也收缩。

## 勘误与提醒

- 手写稿把 CLT 的正态尾近似与 Chernoff 严格上界放在一起比较；**CLT 只是近似**，严格上界要用 Chernoff（或 Hoeffding）。两者指数相同，但证明地位不同。
- 手写稿的 $D(q\Vert p)\ge2\log e\,(p-q)^2$ 要注意 $\log$ 的底：自然对数下系数为 $2$；以 $2$ 为底时要保留 $\log_2e$。
- Sanov 界的上下界差 $(n+1)^{k-1}$ 级别的多项式因子；不要把它当成精确等式。
- 类型类大小和类型概率中的 $H(Q)$、$D(Q\Vert P)$ 不要混淆：前者是“有多少序列”，后者是“这些序列的概率”。
- 转写里的 “Sanov/散诺/萨等”“Chernoff/春放/冲浪棒”“type/态度/肽”“KL/斗鱼”等是识别错误，按上下文替换。

## 分节

1. [KL 散度、互信息与条件互信息](sections/01-kl-mutual-info.md)
2. [集中不等式：Markov、Chebyshev 与 Chernoff](sections/02-concentration.md)
3. [类型计数与 Sanov 大偏差](sections/03-types-sanov.md)
4. [数据处理不等式（DPI）](sections/04-data-processing.md)

## 一页式总览

- $D(P\Vert U)=\log n-H(P)$。
- $I(X;Y)=H(X)+H(Y)-H(X,Y)=D(P_{XY}\Vert P_XP_Y)$。
- Markov：$P(X\ge a)\le E[X]/a$。
- Chebyshev：$P(|X-EX|\ge a)\le\operatorname{Var}(X)/a^2$。
- Chernoff：$P(X\ge a)\le\min_{t>0}E[e^{tX}]/e^{ta}$。
- Bernoulli：$P(\sum X_i\ge qn)\le e^{-nD(q\Vert p)}$。
- Sanov：$P(Q\in\mathcal R)\asymp e^{-n\min_{Q\in\mathcal R}D(Q\Vert P)}$。
- DPI：$X\to Y\to Z$ $\Rightarrow$ $I(X;Z)\le I(X;Y)$。
