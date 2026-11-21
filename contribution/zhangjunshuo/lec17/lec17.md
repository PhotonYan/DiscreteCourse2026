# Lec 17：熵、TV 距离与 KL 散度

这一讲先用“等待连续两个正面”的例子把上一讲的 PGF 收尾，然后进入信息论的基础语言：**熵**、**条件熵/联合熵与链式法则**、**统计距离（TV）**、**KL 散度与条件 KL**。

**来源与编号说明。** 本讲对应 2026 年 11 月 12 日的课堂，原始材料是两页手写稿和一段完整课堂转写。上一份笔记是 Lec16（11 月 10 日），所以本次编号为 **Lec17**。转写开头仍在讲上一讲的 PGF 例子，之后才进入熵；整理版把它作为“上一讲收尾”放在第 1 节开头。语音识别把“熵、条件熵、TV 距离、KL 散度”等术语识别得较乱，公式以手写稿为准，转写只用于补课堂解释。

## 记号速查

- $H(X)$：随机变量 $X$ 的熵；$H(X\mid Y)$：条件熵；$H(X,Y)$：联合熵。
- $P_X(x)$：分布；$P_{X,Y}(x,y)$：联合分布；$P_{X\mid Y}(x\mid y)$：条件分布。
- $\Delta_{\mathrm{TV}}(P,Q)$：全变差距离（统计距离）。
- $D_{\mathrm{KL}}(P\Vert Q)$：KL 散度；$D_{\mathrm{KL}}(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X)$：条件 KL。
- $\operatorname{supp}(P)$：概率大于 $0$ 的支撑集。

## 本讲的几条主线

1. **PGF 收尾**：等待连续两个正面的 PGF 满足一次函数方程；$E[X]=(1+p)/p^2$。
2. **熵**：$H(X)=\sum_xP(x)\log\frac1{P(x)}$；非负、上界 $\log|\operatorname{supp}|$；二元熵 $h(p)$ 在 $1/2$ 处最大；熵是分布的凹函数。
3. **条件熵与链式法则**：$H(X,Y)=H(Y)+H(X\mid Y)$；$H(X\mid Y)\le H(X)$，等号当且仅当独立。
4. **TV 距离**：$\Delta_{\mathrm{TV}}(P,Q)=\frac12\sum_x|P(x)-Q(x)|$；耦合解释 $\Delta_{\mathrm{TV}}=\min\Pr[X\ne Y]$。
5. **KL 散度**：$D_{\mathrm{KL}}(P\Vert Q)=\sum_xP(x)\log\frac{P(x)}{Q(x)}$；非负、不对称；条件 KL 与链式法则。

## 勘误与提醒

- 手写稿写“$H(X\mid Y)=0$ 当且仅当对任意固定 $Y$，$X$ 是常数”；更准确的说法是 **$X$ 是 $Y$ 的函数**（给定 $Y$ 后 $X$ 没有不确定性）。
- 手写稿在熵的凹性证明处跳步较多；本笔记用“混合随机变量 + 链式法则 + 条件不增加熵”重写，避免把等号误当成不等式。
- TV 距离的耦合证明分两步：任意耦合给下界，构造“最小质量对齐”的耦合给上界；不要只写公式。
- KL 不是距离：它**不对称**，也不满足三角不等式；且当 $Q(x)=0$ 而 $P(x)>0$ 时为 $+\infty$。
- 条件 KL 的权重是 $P_X(x)$，不是 $Q_X(x)$；链式法则中的第二项不要漏掉“条件”。
- 转写里的“商/深度/散度/开发改革/鹌鹑”等大多是语音识别错误，分别对应熵、条件熵、散度、KL divergence 等。

## 分节

1. [PGF 收尾、熵的定义与基本性质](sections/01-entropy-basics.md)
2. [条件熵、联合熵与链式法则](sections/02-conditional-entropy-chain.md)
3. [统计距离（TV 距离）](sections/03-tv-distance.md)
4. [KL 散度与条件 KL](sections/04-kl-divergence.md)

## 一页式总览

- 熵：$H(X)=\sum_xP_X(x)\log\frac1{P_X(x)}$，$H(X)\ge0$，$H(X)\le\log|\operatorname{supp}(X)|$。
- 二元熵：$h(p)=p\log\frac1p+(1-p)\log\frac1{1-p}$，在 $p=1/2$ 最大。
- 联合/条件熵：$H(X,Y)=H(Y)+H(X\mid Y)$；$H(X\mid Y)\le H(X)$，等号 $\iff X,Y$ 独立。
- 全链式：$H(X_1,\dots,X_n)=\sum_iH(X_i\mid X_1,\dots,X_{i-1})$。
- TV：$\Delta_{\mathrm{TV}}(P,Q)=\frac12\|P-Q\|_1=\sum_x\max(0,P(x)-Q(x))=1-\sum_x\min(P(x),Q(x))$。
- 耦合：$\Delta_{\mathrm{TV}}(P,Q)=\min_{\text{coupling}}\Pr[X\ne Y]$。
- KL：$D_{\mathrm{KL}}(P\Vert Q)=\sum_xP(x)\log\frac{P(x)}{Q(x)}\ge0$，等号 $\iff P=Q$。
- KL 链式：$D(P_{XY}\Vert Q_{XY})=D(P_X\Vert Q_X)+D(P_{Y\mid X}\Vert Q_{Y\mid X}\mid P_X)$。
