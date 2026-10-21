# 有限域：存在唯一性与不可约多项式的计数

Lec10 已经证明：有限域的阶必为素数幂 $p^d$。这一节补上反方向——**每个素数幂都存在有限域，且在同构意义下唯一**——并回答一个看似无关的问题：**每个次数 $d$ 是否一定存在 $\mathbb F_p$ 上的 $d$ 次不可约多项式？** 答案（存在）正是手写稿第 3 页上半页的内容；它是下一节“构造有限域并做因式分解”的前提。

**本节用到的记号：** $p$ 为素数，$q=p^r$ 为素数幂（字母 $q$ 在因式分解一节还会出现，含义相同）；$\mathbb F_p=\mathbb Z/p\mathbb Z$；$\mathbb F_q$ 表示 $q$ 元有限域；$f'$ 为形式导数；$\Phi_d(x)$ 表示“$\mathbb F_q$ 上全体 $d$ 次首一不可约多项式之积”（手写稿写成 $\varphi_d$，$q=p$ 时就是 $\mathbb F_p$ 上的情形）；$N_d=N_d(q)$ 表示 $\mathbb F_q$ 上 $d$ 次首一不可约多项式的**个数**（$q=p$ 时即手写稿里的数）；$\mu$ 为 Möbius 函数。

## 有限域的大小（回顾）

设 $E$ 是有限域。$\operatorname{char}(E)$ 不能是 $0$（否则 $E$ 含 $\mathbb Q$，已经无限），故特征为素数 $p$，且 $E$ 含素子域 $\mathbb F_p$。于是 $E$ 是 $\mathbb F_p$ 上的有限维线性空间，设 $[E:\mathbb F_p]=d$，则

$$
|E|=p^d .
$$

**有限域的大小必为素数幂。** 反过来的存在唯一性就是本节主定理。

## Frobenius 引理：特征 $p$ 的“加法变简单”

**引理（Frobenius 引理）。** 设 $K$ 是特征 $p$ 的域。映射

$$
\sigma_p:K\longrightarrow K,\qquad a\longmapsto a^p
$$

是域同态，且是单射；它的不动域 $\{a\in K:a^p=a\}$ 恰为素子域 $\mathbb F_p$。若 $K$ 还是**有限域**，则 $\sigma_p$ 是双射，从而是域自同构。更一般地，$a\mapsto a^{q}$（$q=p^r$）也是域同态，称为 **$q$-Frobenius 映射**（$K$ 有限时同样是自同构）。

**证明。** $(ab)^p=a^pb^p$、$1^p=1$ 是显然的。加法性来自二项式定理：

$$
(a+b)^p=\sum_{k=0}^{p}\binom{p}{k}a^k b^{p-k}=a^p+b^p,
$$

因为中间的二项式系数 $\binom{p}{k}$（$1\le k\le p-1$）都是 $p$ 的倍数，而在特征 $p$ 的域中 $p=0$，这些项都消失。又 $\sigma_p$ 是域同态，由“域同态非零则单射”（第 1 节），它是单射。当 $K$ 是有限域时，从有限集到自身的单射必是双射，所以此时 $\sigma_p$ 是自同构。

不动域是一个子域：若 $a^p=a$、$b^p=b$，则 $(a\pm b)^p=a^p\pm b^p=a\pm b$、$(ab)^p=ab$、$(a^{-1})^p=(a^p)^{-1}=a^{-1}$。$x^p-x$ 在域中至多 $p$ 个根，而 $\mathbb F_p$ 的每个元素都是它的根，所以不动域恰为 $\mathbb F_p$。多次复合 $\sigma_p^r$ 就得到 $\sigma_q$。$\square$

**推论（Fermat 小定理的有限域版）。** 若 $E$ 是 $q$ 元有限域，则任意 $a\in E$ 满足 $a^q=a$；任意 $a\ne0$ 满足 $a^{q-1}=1$。

**证明。** $E^\times$ 是 $q-1$ 阶乘法群，由 Lagrange 定理 $a^{q-1}=1$；再乘 $a$ 得 $a^q=a$；$a=0$ 显然。$\square$

## 存在性：$x^{p^d}-x$ 的分裂域

**定理。** 对任意素数 $p$ 与正整数 $d$，存在 $p^d$ 元有限域。

**证明。** 考虑多项式

$$
f(x)=x^{p^d}-x\ \in\ \mathbb F_p[x].
$$

由上一节，$f$ 在 $\mathbb F_p$ 上有分裂域 $K$，且 $[K:\mathbb F_p]\le(p^d)!$，所以 $K$ 是有限域。下面证明 $K$ 恰有 $p^d$ 个元素。

**第一步：$f$ 没有重根。** 形式导数为

$$
f'(x)=p^d x^{p^d-1}-1=-1\ne0,
$$

因为 $p^d=0$ 于特征 $p$。一般地，多项式有重根当且仅当它与导数有公因式（若 $\alpha$ 是重根，则 $x-\alpha$ 同时整除 $f$ 与 $f'$）；这里 $f'=-1$ 与 $f$ 互质，故 $f$ 无重根。于是 $f$ 在 $K$ 中恰有 $p^d$ 个不同的根。

**第二步：根集是子域。** 记

$$
R=\{a\in K: a^{p^d}=a\}.
$$

它恰是“$f$ 的全部根”的集合。由 Frobenius 引理，$\sigma_{p^d}:a\mapsto a^{p^d}$ 是域同态，于是 $R$ 是 $\sigma_{p^d}$ 的不动点集，因而是 $K$ 的子域：$0,1\in R$，且对 $a,b\in R$ 有 $a\pm b,ab\in R$，$a\ne0$ 时 $a^{-1}\in R$。

也可以直接验证加法封闭性（课堂写法）：由 Frobenius，$(a+b)^{p^d}=a^{p^d}+b^{p^d}=a+b$；乘法同理。

**第三步：$K=R$。** 一方面 $R\subseteq K$。另一方面，$K$ 是 $f$ 的分裂域，即由 $\mathbb F_p$ 与 $f$ 的全部根生成；而全部根都在 $R$ 中，$R$ 又是包含 $\mathbb F_p$ 的域，所以由生成性 $K\subseteq R$。因此 $K=R$，$|K|=|R|=p^d$。$\square$

**这个证明的要点。** 与其“凭空造”一个 $p^d$ 元域，不如拿一个**其根恰好应有 $p^d$ 个且能构成域**的多项式：$x^{p^d}-x$。根集对四则运算封闭（Frobenius 的功劳），而它又自动是分裂域（因为分裂域恰好由这些根生成）。

**记号。** 把 $p^d$ 元有限域记为 $\mathbb F_{p^d}$（也写作 $\operatorname{GF}(p^d)$）。由本定理它是分裂域，故存在。

## 唯一性：任意两个 $p^d$ 元域同构

**定理。** 任意两个 $p^d$ 元有限域都同构。

**证明。** 设 $E$ 是 $p^d$ 元域。它特征为 $p$，含素子域 $\mathbb F_p$，且 $[E:\mathbb F_p]=d$。由 Fermat 小定理的有限域版，每个 $a\in E$ 都满足 $a^{p^d}=a$，即 $E$ 中每个元素都是 $f=x^{p^d}-x$ 的根。于是 $f$ 在 $E$ 上分裂，$E$ 由 $\mathbb F_p$ 与 $f$ 的全部根生成（因为所有元素都是根），所以 $E$ 是 $f$ 在 $\mathbb F_p$ 上的分裂域。由分裂域在 $F$-同构意义下唯一（上一节），$E$ 与上一小节构造的 $\mathbb F_{p^d}$ 同构。$\square$

**注意唯一性的范围。** 唯一的是**同构类**：两个 $p^d$ 元域之间总有保持 $\mathbb F_p$ 不动的同构，但它们作为集合未必相等（例如同一抽象域的不同具体模型）。

## 推广：$\mathbb F_q$ 上的 $x^{q^n}-x$

把上面的论证逐字替换 $p\mapsto q$、$d\mapsto n$，得到：

**定理（一般 $q$ 版）。** 设 $q=p^r$。对任意 $n\ge1$，$x^{q^n}-x$ 在 $\mathbb F_q$ 上的分裂域是 $q^n$ 元域 $\mathbb F_{q^n}$；它是 $\mathbb F_q$ 的唯一（同构意义下）$n$ 次扩域。

证明完全一样：$f'=-1$ 无重根；根集是 Frobenius $\sigma_{q^n}$ 的不动域；分裂域由根生成。以后因式分解一节就在一般的 $\mathbb F_q$ 上工作，取 $q=p$ 就回到手写稿的写法。

**顺带：子域结构。** 对固定的 $p$，$\mathbb F_{p^m}\subseteq\mathbb F_{p^n}$ 当且仅当 $m\mid n$；$\mathbb F_{p^n}$ 的每个子域都是某个 $\mathbb F_{p^m}$（$m\mid n$）。证明：若 $m\mid n$，则 $x^{p^m}=x\Rightarrow x^{p^n}=x$，所以 $\mathbb F_{p^m}$（$x^{p^m}-x$ 的根集）包含于 $\mathbb F_{p^n}$；反之若 $\mathbb F_{p^m}\subseteq\mathbb F_{p^n}$，塔律给出 $n=[\mathbb F_{p^n}:\mathbb F_p]=[\mathbb F_{p^n}:\mathbb F_{p^m}]\cdot m$，故 $m\mid n$。

## 核心分解：$x^{p^d}-x$ 与不可约多项式

这一小节回答“$d$ 次不可约多项式是否存在、有多少个”。

**定理（分解恒等式）。** 设 $q=p^r$，则

$$
x^{q^d}-x=\prod_{e\mid d}\Phi_e(x),
$$

其中 $\Phi_e(x)$ 是 $\mathbb F_q$ 上全体 $e$ 次首一不可约多项式之积。（本讲开头手写稿主要写 $q=p$ 的情形，即 $x^{p^d}-x=\prod_{e\mid d}\Phi_e$。）

**证明。** 两边都是首一多项式。我们证明“每个首一不可约多项式在两边出现的次数相同”。

先说明 $x^{q^d}-x$ 无重根：它的导数是常数 $-1$，与 $x^{q^d}-x$ 本身互质。所以左边每个不可约因子只出现一次。

于是只需证明：**$\mathbb F_q$ 上的首一不可约多项式 $g$ 满足

$$
g\mid x^{q^d}-x\iff \deg g\mid d.
$$

**（$\Rightarrow$）** 设 $g\mid x^{q^d}-x$，取 $g$ 的一个根 $\alpha$（在某个扩域中），则 $\alpha^{q^d}=\alpha$，即 $\alpha$ 属于 $x^{q^d}-x$ 的根集，也就是 $\mathbb F_{q^d}$。于是 $\mathbb F_q(\alpha)\subseteq\mathbb F_{q^d}$。因为 $g$ 不可约，$\mathbb F_q(\alpha)\cong\mathbb F_q[x]/(g)$，故 $[\mathbb F_q(\alpha):\mathbb F_q]=\deg g$，由塔律 $\deg g\mid d$。

**（$\Leftarrow$）** 设 $e=\deg g\mid d$。取 $g$ 的一个根 $\alpha$。因为 $g$ 是 $\mathbb F_q$ 上以 $\alpha$ 为根的首一不可约多项式，所以 $g$ 就是 $\alpha$ 的极小多项式；而极小多项式整除任何以 $\alpha$ 为根的 $\mathbb F_q$ 系数多项式，故 $g\mid x^{q^d}-x$。

（也可以把理由拆开看：由 $\mathbb F_q(\alpha)\cong\mathbb F_{q^e}\subseteq\mathbb F_{q^d}$（子域判据）得 $\alpha^{q^d}=\alpha$，即 $\alpha$ 是 $x^{q^d}-x$ 的根；再用极小多项式性质即可。）

综上，左边的不可约因子恰好是“次数整除 $d$ 的首一不可约多项式”，每个一次，正是右边。$\square$

**这个恒等式在说什么。** 它把 $x^{q^d}-x$ 按“不可约因子的次数”**分层**：所有 $e$ 次不可约多项式（$e\mid d$）之积，恰好等于 $x^{q^d}-x$。这就是手写稿第 3 页上半页的核心。

**补充引理（gcd 形式，课堂提到）。** 对 $a,b\ge1$，

$$
\gcd\bigl(x^{q^a}-x,\ x^{q^b}-x\bigr)=x^{q^{\gcd(a,b)}}-x .
$$

**证明思路。** 不妨设 $a\ge b$。在模 $x^{q^b}-x$ 下 $x^{q^b}\equiv x$，两边取 $q^{a-b}$ 次幂得 $x^{q^a}\equiv x^{q^{a-b}}$，所以 $\gcd(x^{q^a}-x,x^{q^b}-x)=\gcd(x^{q^{a-b}}-x,x^{q^b}-x)$；对指数做辗转相除即得。$\square$

## 计数：$N_d$ 与 Möbius 公式

设 $N_e=N_e(q)$ 为 $\mathbb F_q$ 上 $e$ 次首一不可约多项式的个数。由 $\Phi_e$ 的定义，$\deg\Phi_e=e\,N_e$。对分解恒等式两边比较次数：

$$
q^d=\sum_{e\mid d} e\,N_e .
\qquad(\ast)
$$

这是关于 $N_d$ 的**递归公式**：

$$
d\,N_d=q^d-\sum_{e\mid d,\ e<d} e\,N_e .
$$

**小数值。** 取 $q=p$：

- $N_1=p$（一次首一多项式 $x-a$，$a\in\mathbb F_p$）；
- $N_2=(p^2-p)/2$；
- $N_3=(p^3-p)/3$；
- $N_4=(p^4-p^2)/4$；
- $N_6=(p^6-p^3-p^2+p)/6$。

这些正是手写稿上 $\deg\Phi_1=p$、$\deg\Phi_2=p^2-p$、$\deg\Phi_3=p^3-p$、$\deg\Phi_6=p^6-p^3-p^2+p$ 的除法版本：$\deg\Phi_d=d\,N_d$。

具体数表（首一不可约多项式个数）：

- $p=2$：$N_1,\dots,N_8=2,1,2,3,6,9,18,30$；
- $p=3$：$3,3,8,18,48,116,312,810$。

**Möbius 反演（进阶，手写稿没写，可作补充）。** 定义 Möbius 函数

$$
\mu(n)=
\begin{cases}
1, & n=1,\\
0, & n\ \text{含平方因子},\\
(-1)^k, & n\ \text{是}\ k\ \text{个不同素数之积}.
\end{cases}
$$

由 $(\ast)$ 对 $d$ 做 Möbius 反演得

$$
N_d=\frac1d\sum_{e\mid d}\mu\!\left(\frac de\right)q^e .
$$

验证：$q=2,d=4$ 时 $N_4=\frac14(\mu(1)2^4+\mu(2)2^2+\mu(4)2^1)=\frac14(16-4+0)=3$。

## 每个次数都有不可约多项式

有了 $(\ast)$ 与上面的“$\deg\Phi_e\le q^e$”（因为 $\Phi_e\mid x^{q^e}-x$），可以证明：

**定理。** 对任意素数幂 $q$ 与任意 $d\ge1$，存在 $d$ 次不可约多项式。

**证明。** 由分解恒等式，

$$
\deg\Phi_d=q^d-\sum_{e\mid d,\ e<d}\deg\Phi_e
\ \ge\ q^d-\sum_{e\mid d,\ e<d}q^e .
$$

真正的真因子 $e$ 满足 $e\le d/2$（$d\ge2$ 时）。于是

$$
\sum_{e\mid d,\ e<d}q^e
\le q+q^2+\cdots+q^{\lfloor d/2\rfloor}
=\frac{q^{\lfloor d/2\rfloor+1}-q}{q-1}
<q^{d/2+1}
\le q^d,
$$

最后一步用了 $d\ge2$。因此 $\deg\Phi_d>0$，即至少有一个 $d$ 次不可约多项式。$d=1$ 时 $\deg\Phi_1=q>0$ 显然。$\square$

**这条定理的用途。** 它说明构造 $\mathbb F_{q^d}$ 有两条路：

- **分裂域路线**：取 $x^{q^d}-x$ 的分裂域（存在性证明用的）；
- **商环路线**：任取一个 $d$ 次不可约 $g\in\mathbb F_q[x]$，则 $\mathbb F_q[x]/(g)$ 是 $q^d$ 元域，且 $\mathbb F_{q^d}\cong\mathbb F_q[x]/(g)$。

两条路殊途同归（唯一性保证）。实际计算用第二条：只要找到 $g$ 就能写出域的元素与运算。

## 例子

**例一：$p=2$ 的逐层分解。**

$$
\begin{aligned}
x^2-x&=\Phi_1=x(x+1),\\
x^4-x&=\Phi_1\Phi_2=x(x+1)(x^2+x+1),\\
x^8-x&=\Phi_1\Phi_3=x(x+1)(x^3+x+1)(x^3+x^2+1),\\
x^{16}-x&=\Phi_1\Phi_2\Phi_4=x(x+1)(x^2+x+1)(x^4+x+1)(x^4+x^3+1)(x^4+x^3+x^2+x+1).
\end{aligned}
$$

这里 $d=4$ 的因子只有 $1,2,4$，没有 $3$，所以 $x^{16}-x$ 中不出现三次因子；$N_4=3$ 对应最后三个四次不可约多项式。

**例二：$p=3$ 的逐层分解。**

$$
x^3-x=x(x-1)(x+1),\qquad
x^9-x=x(x-1)(x+1)(x^2+1)(x^2+x-1)(x^2-x-1).
$$

第二个式子中 $N_2=3$，三个二次不可约多项式是 $x^2+1$、$x^2+x-1$、$x^2-x-1$。

**例三：$\mathbb F_{16}$ 的元素按极小多项式分组。** 取 $\mathbb F_{16}=\mathbb F_2[x]/(x^4+x+1)$，16 个元素按“在 $\mathbb F_2$ 上的极小多项式”分类：

- $0$ 对应 $x$，$1$ 对应 $x+1$：2 个元素；
- $x^2+x+1$ 的 2 个根：2 个元素；
- 三个四次不可约多项式各 4 个根：12 个元素。

合计 $2+2+12=16$，与 $\sum_{e\mid4}eN_e=1\cdot2+2\cdot1+4\cdot3=16$ 一致。

**例四：具体构造。**

$$
\mathbb F_4=\mathbb F_2[x]/(x^2+x+1),\qquad
\mathbb F_8=\mathbb F_2[x]/(x^3+x+1),\qquad
\mathbb F_9=\mathbb F_3[x]/(x^2+1).
$$

在 $\mathbb F_9$ 中把 $x$ 的像记为 $i$（$i^2=-1=2$），则元素为 $a+bi$（$a,b\in\mathbb F_3$），按“$i^2=2$ 降次”做乘法。

## 本节的勘误与提醒（对应手写稿第 3 页上半页）

- **手写稿的 $\varphi_d$ 是多项式，不是欧拉函数。** 定义为“全体 $d$ 次首一不可约多项式之积”，所以 $\deg\varphi_d=d\cdot N_d$；它和数论里的欧拉函数 $\varphi(n)$ 只是记号撞车，含义无关。
- **手写稿“$x^{p^6}-x=\varphi_6+\varphi_3+\varphi_2+\varphi_1$”中的加号是笔误，应为乘积。** 依据是分解恒等式；比较次数也对不上加号。
- **不等式的下标是 $d'\mid d$ 且 $d'\ne d$。** 手写稿的 $\sum$ 下方同时写了 $d'\mid d$ 与 $d'\ne d$（即“$d$ 的真因子”，与 $d'<d$ 等价）；读的时候注意别漏掉 $d'\mid d$，否则会变成无穷和。
- **“每个次数都有不可约多项式”的证明不是构造性的。** 它只证明存在；要真正找到一个，可以枚举并检验（或用下一节的算法思想）。
- **$f\mid x^{q^d}-x\iff\deg f\mid d$ 的方向不能反。** 例如 $x+1$（次数 $1$）整除任何 $x^{q^d}-x$；而四次不可约多项式只整除满足 $4\mid d$ 的那些。
- **$x^{q^d}-x$ 无重根。** 这是“分解恒等式”与下一节“按次数分组”算法都依赖的事实；来源是导数 $-1$。
- **有限域大小必须是素数幂**：不存在 $6$ 元域。因为若 $|E|=n$，则 $n=p^{[E:\mathbb F_p]}$。
- **不同不可约多项式给出的域同构，但元素对应关系不同。** 例如 $\mathbb F_4=\mathbb F_2[x]/(x^2+x+1)$ 中 $x$ 的像是“$\omega$”，换一个二次不可约多项式（$\mathbb F_2$ 上只有这一个）没有区别；$\mathbb F_9$ 上不同的二次不可约多项式会给出不同的生成元对应。
- 课堂转写把 Frobenius 的“$(a+b)^{p^d}=a^{p^d}+b^{p^d}$”说成“二项式展开中间项消失了”，这是对的；但注意**只在特征 $p$ 下成立**，一般环里不成立。
