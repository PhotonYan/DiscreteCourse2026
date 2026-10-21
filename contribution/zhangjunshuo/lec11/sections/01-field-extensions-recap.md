# 域扩张回顾：次数、三种造域方式与代数元

Lec10 的结尾用理想构造了域，并引出域扩张与分裂域。这一节先把那批工具整理成 Lec11 反复使用的语言：**域扩张的次数**、**三种造域方式**、**域同态为什么总是单射**，以及**代数元与极小多项式**。分裂域、有限域、因式分解三部分都建立在这些语言上，所以这一节的控制目标是：后面出现 $[K:F]$、$F(\alpha)$、极小多项式时，不再需要回头查定义。

**本节用到的记号：** $F,K,E,H$ 为域，$F\subseteq K$ 表示 $F$ 是 $K$ 的子域；$K/F$ 表示扩域（读作“$K$ over $F$”）；$[K:F]=\dim_F K$ 为扩张次数；$F[x]$ 为多项式环，$(f)$ 为 $f$ 生成的主理想；$F(\alpha)$ 为 $K$ 中包含 $F$ 与 $\alpha$ 的最小子域；$\operatorname{Frac}(R)$ 为分式域；$\mathbb F_p=\mathbb Z/p\mathbb Z$；$\operatorname{char}(F)$ 为特征。

## 域扩张与次数

设 $F\subseteq K$ 都是域，且 $F$ 的加法、乘法与 $K$ 一致。此时 $K$ 自然地是 $F$ 上的**线性空间**：向量加法就是 $K$ 的加法，标量乘法就是 $F$ 中元素乘 $K$ 中元素。它的维数记作

$$
[K:F]=\dim_F K,
$$

称为扩张 $K/F$ 的**次数**。当 $[K:F]<\infty$ 时称 $K/F$ 为**有限扩张**，否则称为**无限扩张**。

这个“把扩域看成线性空间”的视角是整讲的计算引擎：次数可乘（塔律）、元素有极小多项式、有限域大小是 $p^d$，全部从它推出来。

## 三种造域方式（回顾）

Lec10 已经给出三条从已知域造出新域的路线，这里只列结论并把课上强调的细节补全。

**路线一：商掉一个不可约多项式。** 设 $F$ 是域、$f\in F[x]$ 不可约、$\deg f=n\ge1$，则 $(f)$ 是极大理想，商环

$$
F[x]/(f)
$$

是域。它的每个元素有唯一代表元

$$
a_0+a_1\bar x+\cdots+a_{n-1}\bar x^{\,n-1},\qquad a_i\in F,
$$

其中 $\bar x$ 是 $x$ 的像。因此 $[F[x]/(f):F]=n$，且 $|F[x]/(f)|=|F|^n$。

**路线二：取分式域。** 从整环 $R$ 出发，把除法补进去得到 $\operatorname{Frac}(R)$。本讲最常用的是 $R=F[x]$，此时

$$
\operatorname{Frac}(F[x])=F(x)=\left\{\frac{g(x)}{h(x)}:g,h\in F[x],\ h\ne0\right\},
$$

称为 $F$ 上的**有理函数域**。它是 $F$ 的无限扩张。

**路线三：在一个更大的域里添一个元素。** 设 $K/F$ 是扩域、$\alpha\in K$。记 $F(\alpha)$ 为 $K$ 中包含 $F$ 与 $\alpha$ 的**最小子域**。它是 $F$ 的扩域，且 $[F(\alpha):F]$ 可以是有限，也可以是无限。

三条路线的关系：路线一造出“形式上的根”，路线三在具体扩域里“取一个真实的根”，路线二则负责“添分母”。下一小节说明路线一与路线三在“根”这件事上完全一致。

## 添一个根：$F[x]/(f)\cong F(\alpha)$

**定理。** 设 $F$ 是域、$f\in F[x]$ 不可约、$K/F$ 是扩域、$\alpha\in K$ 满足 $f(\alpha)=0$。则存在域同构

$$
F[x]/(f)\ \cong\ F(\alpha),
$$

它保持 $F$ 中元素不动，并把 $\bar x$ 送到 $\alpha$。

**证明。** 定义求值映射

$$
\varphi:F[x]\longrightarrow F(\alpha),\qquad g(x)\longmapsto g(\alpha).
$$

它是环同态：$\varphi(g+h)=g(\alpha)+h(\alpha)$、$\varphi(gh)=g(\alpha)h(\alpha)$，且 $\varphi$ 在 $F$ 上是恒等映射。下面三步。

**(1) 核是 $(f)$。** 显然 $f\in\ker\varphi$，所以 $(f)\subseteq\ker\varphi$。设 $g\in\ker\varphi$，即 $g(\alpha)=0$。因为 $f$ 不可约，$(f)$ 是极大理想，而 $\ker\varphi$ 是包含 $(f)$ 的理想，所以 $\ker\varphi$ 只能是 $(f)$ 或整个 $F[x]$。后者不可能，因为 $\varphi(1)=1\ne0$ 说明 $1\notin\ker\varphi$。故 $\ker\varphi=(f)$。

（同一件事也可以这样看：取 $d=\gcd(f,g)$。因为 $d$ 是 $f,g$ 的 $F[x]$-线性组合，所以 $d(\alpha)=0$；但 $f$ 不可约说明 $d$ 是常数或 $f$ 的相伴元，而常数不可能有 $d(\alpha)=0$，故 $f\mid g$，即 $g\in(f)$。这种写法在 Lec10 用过，等价于“极大理想”论证。）

**(2) 满射。** 任取 $\beta\in F(\alpha)$。由 $F(\alpha)$ 的定义，它是 $F$ 与 $\alpha$ 生成的域，其中每个元素都可以写成 $\alpha$ 的有理式；又因 $f(\alpha)=0$，用带余除法可以把 $\alpha$ 的高次幂降到低于 $n=\deg f$，所以存在多项式 $g\in F[x]$ 使 $\beta=g(\alpha)$。故 $\varphi$ 满。

**(3) 由第一同构定理。** $\varphi$ 诱导 $F[x]/\ker\varphi\cong\operatorname{im}\varphi$，即 $F[x]/(f)\cong F(\alpha)$；$\bar x$ 的像为 $\varphi(x)=\alpha$。$\square$

**这条定理在说什么。** 它把两件事绑定在一起：**“在抽象商环里添一个形式根”与“在具体扩域里取一个真实根”得到同一个域**。所以以后想造 $n$ 次扩域，只要找一个 $n$ 次不可约多项式即可。

**一个容易忽略的前提。** $f$ 的不可约性不能省。若 $f$ 可约，$(f)$ 不是极大理想，$F[x]/(f)$ 只是环而不是域。例如 $\mathbb R[x]/(x^2-1)$ 有零因子，它不是域。

**同构不唯一。** 若 $\alpha,\alpha'$ 是同一个不可约多项式 $f$ 的两个不同根，则 $F(\alpha)\cong F[x]/(f)\cong F(\alpha')$，但把 $\alpha$ 送到 $\alpha'$ 还是送到别的根，得到的是不同的同构。这正是分裂域“同构意义下唯一”的伏笔。

## 域同态只有两种：单射或零映射

**命题。** 设 $\varphi:F\to F'$ 是域同态，则 $\varphi$ 要么是单射，要么是零映射（把所有元素送到 $0$）。

**证明。** $\ker\varphi$ 是 $F$ 的理想。域只有两个理想：$(0)$ 和 $F$ 本身。若 $\ker\varphi=(0)$，则 $\varphi$ 是单射；若 $\ker\varphi=F$，则 $\varphi$ 是零映射。$\square$

这条命题的用法：**两个域之间的非零同态一定是嵌入（单射）**。因此本讲后面说“保持 $F$ 不动的同态”时，自动就是“把 $F$ 的扩域嵌入另一个扩域”。

**推论。** 若 $\varphi:F\to F'$ 是非零域同态，则 $\varphi(F)$ 是与 $F$ 同构的子域。

## 代数元、超越元与极小多项式

设 $K/F$ 是扩域、$\alpha\in K$。

- 若存在**非零**多项式 $g\in F[x]$ 使 $g(\alpha)=0$，称 $\alpha$ 在 $F$ 上**代数**；
- 否则称 $\alpha$ 在 $F$ 上**超越**。

**等价刻画。** $\alpha$ 在 $F$ 上代数 $\iff$ $[F(\alpha):F]<\infty$。

**证明思路。** 若 $\alpha$ 代数，取一个非零多项式 $g$ 使 $g(\alpha)=0$，设 $\deg g=n$。则 $1,\alpha,\dots,\alpha^n$ 在 $F$ 上线性相关（因为 $g$ 给出一个非平凡线性关系），于是 $[F(\alpha):F]\le n<\infty$（更精细地，次数等于极小多项式的次数，见下）。反过来，若 $[F(\alpha):F]=n<\infty$，则 $1,\alpha,\dots,\alpha^n$ 这 $n+1$ 个元素在 $n$ 维空间里线性相关，给出非零多项式 $g$ 使 $g(\alpha)=0$。$\square$

**极小多项式。** 设 $\alpha$ 在 $F$ 上代数。在所有满足 $g(\alpha)=0$ 的非零多项式中，取次数最小者，再除以首项系数使它**首一**，得到的多项式称为 $\alpha$ 在 $F$ 上的**极小多项式**，记作 $m_{\alpha,F}(x)$（或简记 $m_\alpha$）。它有两个基本性质：

**(1) 极小多项式不可约。** 若 $m_\alpha=gh$ 且 $g,h$ 次数都小于 $\deg m_\alpha$，则由 $0=m_\alpha(\alpha)=g(\alpha)h(\alpha)$ 及 $F(\alpha)$ 是域（无零因子）得 $g(\alpha)=0$ 或 $h(\alpha)=0$，与极小性矛盾。故 $m_\alpha$ 不可约。

**(2) 极小多项式整除任何以 $\alpha$ 为根的多项式。** 设 $g(\alpha)=0$。作带余除法 $g=q\,m_\alpha+r$，$\deg r<\deg m_\alpha$。代入 $\alpha$ 得 $r(\alpha)=0$，由极小性 $r=0$，故 $m_\alpha\mid g$。

**推论（次数公式）。** $[F(\alpha):F]=\deg m_{\alpha,F}$。

**证明。** 由上面的定理取 $f=m_\alpha$（它不可约、以 $\alpha$ 为根），得 $F(\alpha)\cong F[x]/(m_\alpha)$，而后者在 $F$ 上的维数是 $\deg m_\alpha$。$\square$

**超越元的情形。** 若 $\alpha$ 超越，则映射

$$
F[x]\longrightarrow F(\alpha),\qquad g(x)\longmapsto g(\alpha)
$$

没有非零核元素，所以是单射；它自然延拓到分式域得到

$$
\operatorname{Frac}(F[x])=F(x)\ \cong\ F(\alpha),\qquad \frac{g(x)}{h(x)}\longmapsto\frac{g(\alpha)}{h(\alpha)}.
$$

（良定义：$h\ne0$ 且 $\alpha$ 超越，故 $h(\alpha)\ne0$；与分数表示无关由交叉相乘验证；单射由 $g(\alpha)=0\Rightarrow g=0$；满射由 $F(\alpha)$ 中元素都是 $\alpha$ 的有理式。）于是 $[F(\alpha):F]=\infty$。这正是“超越 $=$ 无限次扩张”的含义。

**有限扩张必代数。** 若 $[K:F]<\infty$，则任意 $\alpha\in K$ 都满足 $[F(\alpha):F]\le[K:F]<\infty$，故 $\alpha$ 在 $F$ 上代数。**反之不然**：存在无限次代数扩张（例如 $\mathbb Q$ 在 $\mathbb C$ 中的代数闭包），但本讲不展开。

## 几个必须记住的例子

- $\alpha=\sqrt2$ 在 $\mathbb Q$ 上代数，$m_\alpha=x^2-2$，$[\mathbb Q(\sqrt2):\mathbb Q]=2$。
- $\alpha=\sqrt[3]{2}$ 在 $\mathbb Q$ 上代数，$m_\alpha=x^3-2$（在 $\mathbb Q$ 上不可约：有理根只能是 $\pm1,\pm2$，代入都不为 $0$），$[\mathbb Q(\sqrt[3]{2}):\mathbb Q]=3$。
- $\pi$ 在 $\mathbb Q$ 上超越（Lindemann 1882），$[\mathbb Q(\pi):\mathbb Q]=\infty$。本课程不给证明，只作为“无限扩张”的例子使用。
- 设 $F$ 是域、$x$ 是形式变量，则 $x$ 在 $F$ 上超越，$F(x)$ 是 $F$ 的无限扩张（路线二）。
- $\mathbb C/\mathbb R$：$[\mathbb C:\mathbb R]=2$，$m_i=x^2+1$。

## 本节的勘误与提醒

- **$F[x]/(f)\cong F(\alpha)$ 不是“等于”。** 商环的元素是陪集，$F(\alpha)$ 的元素是扩域中的元素，二者之间只有同构；同构由 $\bar x\mapsto\alpha$ 决定。
- **$f$ 不可约是商环成为域的前提；$f(\alpha)=0$ 是把 $\bar x$ 送到 $\alpha$ 的前提。** 两个条件缺一不可。
- **极小多项式必须首一**，否则“唯一”不成立（$2x^2-4$ 与 $x^2-2$ 只差常数倍）。
- **极小多项式的次数等于扩张次数，不是“不超过”。** 上文的线性相关只给出 $\le n$，真正等号来自 $F(\alpha)\cong F[x]/(m_\alpha)$。
- **“代数”与“有限扩张”不是同一个概念。** 代数元给出有限扩张，但扩域可以是无限次代数扩张；有限扩张则一定是代数扩张。
- 课堂转写里“$K$ 是一个 $F$-linear space”“$[K:F]$ 是维数”这类句子识别得很乱，以本节定义为准。
