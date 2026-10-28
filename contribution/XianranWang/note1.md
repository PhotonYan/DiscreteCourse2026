# 9.8

## 集合的势

等势：

$$
|S|=|T|
\iff
\exists\text{ bijection }f:S\to T
$$

大小：

$$
|S|\le |T|
\iff
\exists\text{ injection }f:S\to T
$$

### Schröder–Bernstein

$$
|S|\le |T|,\quad |T|\le |S|
\Rightarrow
|S|=|T|
$$

设

$$
f:S\to T,\qquad g:T\to S
$$

都是单射。

直观考虑：把 $S,T$ 画成两列，连边$f,g$。

连通块有这几种：

- 有起点的无限链
- 双向无限链
- 环

每一块里选一个方向的边做配对，配出双射。

---

## Cantor theorem

$$
|S|<|2^S|
$$

显然

$$
|S|\le |2^S|
$$

只需证不存在满射

$$
f:S\to 2^S
$$

反设存在，定义

$$
T=\{s\in S:s\notin f(s)\}
$$

则 $T\subseteq S$，所以 $T\in 2^S$。

若

$$
f(a)=T
$$

则

$$
a\in T
\iff
a\notin f(a)
\iff
a\notin T
$$

矛盾。

所以

$$
|S|<|2^S|
$$

---

## 熟知

$$
|\mathbb Q|=|\mathbb N|
$$
$$
|\mathbb R|=|2^{\mathbb N}|
$$

$2^{\mathbb N}\to\mathbb R$ 可以想成：

$$
(a_1,a_2,\ldots)
\mapsto
\sum_{i=1}^{\infty}a_i2^{-i}
$$

但有重复表示：

$$
0.01111\cdots=0.10000\cdots
$$

注：可以换成三进制的0/2避免碰撞

---

# 几个延伸问题

### Q1

$$
|S\cup T|=|\mathbb N|
\stackrel{?}{\Rightarrow}
|S|=|\mathbb N|
\ \vee\
|T|=|\mathbb N|
$$

显然对，因为$S,T$ 都至多可数。

### Q2

$$
\left|
\bigcup_{i=1}^{\infty}S_i
\right|=
|\mathbb R|
\stackrel{?}{\Rightarrow}
\exists i,\ |S_i|=|\mathbb R|
$$


### Q3

$$
|S|\ge |\mathbb N|
\stackrel{?}{\Rightarrow}
|S\times\mathbb N|=|S|
$$

### Q4 戴德金有穷是否是有穷？

$S$ 是 Dedekind-finite，是指
$$
\forall T\subsetneq S,\quad |T|<|S|
$$

---

# 补充：选择公理、ZFC、连续统假设

## AC
AC(选择公理，Axiom of Choice):
对任意非空集合的族$\mathcal F$ ，存在一个函数（也称选择函数）
$$
f:\mathcal F\to \bigcup\mathcal F
$$
满足
$$
\forall A\in\mathcal F,\quad f(A)\in A.
$$

亦即：对任意一族非空集合，可以同时从每个集合里选一个元素。

等价地，如果 $\{A_i\}，{i\in I}$ 全部非空，则

$$
\prod_{i\in I}A_i\neq\varnothing.
$$

AC的直观理解例子：有无限多双完全没有标签、左右之分的袜子，每双都能随手拿出一只，但没有统一规则告诉你“每双该拿哪只”。选择公理说：即使没有这样的规则，仍然可以认为存在一种整体的选择方式，能从每一双里各选一只。

在ZF上，AC的两个等价形式：
1.对任意无限集S，$|S\times S|=|S|$
2.任意两个集合的势都可以比较。

## ZFC

$$
\mathrm{ZFC}=\mathrm{ZF}+\mathrm{AC}
$$


如果承认ZFC，上面问题中的后三个都成立（第一个显然不依赖ZFC）。

---

## 连续统假设

连续统假设（CH，Continuum Hypothesis）：

$$
\nexists\kappa,\qquad
\aleph_0<\kappa<2^{\aleph_0}
$$

即

$$
2^{\aleph_0}=\aleph_1
$$

CH 独立于 ZFC。

---

## 幂集和势

若$|S|\le |T|$，则$|2^S|\le |2^T|$。因为单射$f:S\to T$诱导
$$
A\subseteq S
\mapsto
f(A)\subseteq T
$$

所以 ZFC 下：

$$
|2^S|>|2^T|
\Rightarrow
|S|>|T|
$$

但是

$$
|S|<|T|
$$

不一定推出

$$
|2^S|<|2^T|
$$

---

# Proposition Logic

$$
\boxed{\text{Syntax}}
\qquad
\boxed{\text{Semantics}}
$$


## Syntax

Alphabet $\Sigma$：

proposition symbols：$p,q,r,p_1,p_2,\ldots$

false：$\bot$

connectives：$\neg,\quad\land,\quad\lor,\quad\to$

brackets：$(,)$

$\Sigma^*$：所有 symbol 组成的有限字符串。

但不是所有 string 都是 合法公式（formula）。

---

### Formula / FOR

记合法公式集合为 FOR。

它是满足下面条件的最小集合：

1. atomic：$p_i,\bot\in\mathrm{FOR}$

2. 如果$\varphi\in\mathrm{FOR}$，则$\neg\varphi\in\mathrm{FOR}$

3. 如果$\varphi,\psi\in\mathrm{FOR}$，则$(\varphi\land\psi),\quad(\varphi\lor\psi),\quad(\varphi\to\psi)\in\mathrm{FOR}$

---

### 结构归纳

想证

$$
\forall\varphi\in\mathrm{FOR},\quad A(\varphi)
$$

只需：

- atomic 情况成立
- 对各个生成规则封闭

即$A(\varphi)\RightarrowA(\neg\varphi)$和$A(\varphi),A(\psi)\RightarrowA(\varphi\land\psi),A(\varphi\lor\psi),A(\varphi\to\psi)$

这就是结构归纳。

---

# Semantics

先给 proposition symbols 一个 valuation：

$$
v:\text{Prop}\to\{0,1\}
$$

然后递归扩展到所有 formula。

记 $[[\varphi]]_v$ 为 $\varphi$ 在 $v$ 下的truth value。

$$
[[\bot]]_v=0
$$

$$
[[\neg\varphi]]_v=1-[[\varphi]]_v
$$

$$
[[\varphi\land\psi]]_v=\min([[\varphi]]_v,[[\psi]]_v)
$$

$$
[[\varphi\lor\psi]]_v
=\max([[\varphi]]_v,[[\psi]]_v)
$$

$$
[[\varphi\to\psi]]_v=1-[[\varphi]]_v(1-[[\psi]]_v)
$$

也就是 implication 只有

$$
1\to0
$$

是假。

---

## Tautology

如果

$$
\forall v,\quad
[[\varphi]]_v=1
$$

则 $\varphi$ 是 tautology。

记：

$$
\models\varphi
$$

例如

$$
\models p\to p
$$

$$
\models\neg\bot
$$

---

## Semantic entailment

$$
\Gamma\models\psi
$$

表示：

对任意 valuation $v$，

如果 $\Gamma$ 中所有命题都为真，

那么 $\psi$ 也为真。

例如：

$$
p,\ p\to q\models q
$$

---

# Natural Deduction

（syntax）

$$
\Gamma\vdash\varphi
$$

表示从$\Gamma$ 出发，按演绎规则可以推出 $\varphi$。



## 蕴含

蕴含消去（elimination）：

$$
\frac{
\varphi
\qquad
\varphi\to\psi
}{
\psi
}
\to E
$$

蕴含引入（introduction）：

$$
\frac{
[\varphi]
\quad
\quad
\psi
}{
\varphi\to\psi
}
\to I
$$

即：临时假设 $\varphi$，如果最后推出了 $\psi$，就可以释放假设。

---

## 且
$$
\frac{
\varphi
\qquad
\psi
}{
\varphi\land\psi
}
\land I
$$

$$
\frac{\varphi\land\psi}{\varphi}
\land E
\qquad
\frac{\varphi\land\psi}{\psi}
\land E
$$

---

## negation

定义（否定就是推出矛盾）

$$
\neg\varphi:=\varphi\to\bot
$$

因此 $\varphi,\neg\varphi \vdash \bot$

爆炸：

$$
\frac{\bot}{\varphi}
$$

RAA：

$$
\frac{
[\neg\varphi]
\quad
\quad
\bot
}{
\varphi
}
$$

---

# 几个 deduction

## $P\vdash\neg\neg P$

已有 $P$ ，假设 $[\neg P]=[P\to\bot]$
则

$$
P,\ P\to\bot
\vdash
\bot
$$

所以

$$
(P\to\bot)\to\bot
$$

即

$$
P\vdash\neg\neg P
$$

这个方向不需要 RAA。

---

## $\neg\neg P\vdash P$

已有 $\neg\neg P$，假设 $[\neg P]$，则推出$\bot$

RAA 得$P$

所以$\neg\neg P\vdash P$

---

## 逆否命题

想证：

$$
P\to Q
\vdash
\neg Q\to\neg P
$$

已有：$P\to Q$，假设 $[\neg Q]$，再假设 $[P]$

由 $P,\quad P\to Q$ 得 $Q$

和 $\neg Q$ 得 $\bot$

所以 $\neg P$

即证