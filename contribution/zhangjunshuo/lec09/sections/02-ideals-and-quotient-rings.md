# 理想与商环

## 理想

环 $R$ 的加法子群 $I$ 称为（双边）理想，若对任意 $r\in R$、$a\in I$ 都有
$$ra\in I,\qquad ar\in I.$$
在交换环中左右条件相同。理想是环同态核的正确替代物；任意子环未必能作为商环的陪集。

**理想与子环的关系要分清。** 由定义，理想对减法封闭、对自身乘法封闭，所以它是“非含幺意义下”的子环；但它还额外要求吸收整个环的乘法。在含幺环里这个差别立刻显现：**理想 $I\ne R$ 不可能包含 $1_R$**，因为一旦 $1\in I$ 就有 $r=r\cdot1\in I$ 对所有 $r$ 成立，于是 $I=R$。

所以同态的核是理想，而且一般**不是**含幺子环——例如 $\mathbb Z\to\mathbb Z/2\mathbb Z$ 的核 $2\mathbb Z$ 不含 $1$。课堂手写稿里写的“$\ker f$ 是子环”，在含幺约定下应改述为“$\ker f$ 是理想，因而只是非含幺意义下的子环”。反过来，子环 $A\le R$ 成为理想，当且仅当它吸收乘法：$rA\subseteq A$ 且 $Ar\subseteq A$ 对所有 $r\in R$。

**理想的基本运算。** 设 $I,J\trianglelefteq R$。和与交定义为

$$
I+J=\{a+b:a\in I,\ b\in J\},\qquad I\cap J=\{x:x\in I\text{ 且 }x\in J\},
$$

两者都是理想：$I+J$ 还是包含 $I\cup J$ 的最小理想（即 $I\cup J$ 生成的理想），$I\cap J$ 是同时包含于两者的最大理想。三者之间有包含链

$$
IJ\;\subseteq\;I\cap J\;\subseteq\;I+J\;\subseteq\;R,
$$

其中 $IJ\subseteq I\cap J\subseteq I+J$ 由定义直接看出。此外成立分配律

$$
I(J+K)=IJ+IK,\qquad (I+J)K=IK+JK,
$$

并可以定义幂 $I^n=\underbrace{I\cdots I}_{n}$。注意一般的 $I\cup J$ **不是**理想（例如 $\mathbb Z$ 中 $(2)\cup(3)$ 对加法不封闭），这正是需要引入 $I+J$ 的原因。

理想的交仍是理想（任意多个理想的交仍是理想）。由子集 $X\subseteq R$ 生成的理想记为 $(X)$，是包含 $X$ 的最小理想。对单元素 $a$，$(a)$ 称主理想；在交换含幺环中
$$ (a)=\{ra:r\in R\}.$$
一般的双边生成理想由有限和
$$\sum_i r_i x_i s_i$$
组成；交换环中可写成 $\sum_i r_i x_i$。这里 $r_i,s_i$ 遍历整个 $R$，$x_i$ 遍历 $X$，项数有限。之所以必须写成这种“两侧都乘”的形式：非交换时 $ra$ 与 $as$ 未必相同，而理想要求对左右乘法都封闭。验证也不难——两个这样的有限和相加仍是有限和，再左乘或右乘一个 $r\in R$ 只是把每项变成 $r(r_ix_is_i)= (rr_i)x_is_i$，形式不变，所以这个集合确实是对左右乘法封闭的加法子群，因而是理想；又因为每一项都必须落在任何包含 $X$ 的理想里，它是最小的。

在 $\mathbb Z$ 中每个理想都是主理想：$I=(d)=d\mathbb Z$，其中 $d$ 是 $I$ 中非零元素的最大公因数。于是
$$ (a)\cap(b)=(\operatorname{lcm}(a,b)),\qquad (a)+(b)=(\gcd(a,b)). $$

理想的乘积定义为
$$
IJ=\left\{\sum_{k=1}^n a_kb_k:a_k\in I,\ b_k\in J,\ n\ge1\right\}.
$$
它是包含所有 $ab$（$a\in I,b\in J$）的最小理想；不能把它误写成只含单个乘积的集合。

对**主理想**，乘积直接由生成元给出：在交换环中

$$
(a)(b)=(ab),\qquad (a_1)(a_2)\cdots(a_k)=(a_1a_2\cdots a_k).
$$

这不是 $\mathbb Z$ 才有的性质，任何交换环都成立（[DF] §7.6）。容易和它混淆的是另一个式子：一般理想只有 $IJ\subseteq I\cap J$（每一项 $ab$ 既在 $I$ 又在 $J$），反向包含需要 $I+J=R$，见第 3 节。

## 商环的构造

理想 $I\trianglelefteq R$ 给出加法陪集
$$R/I=\{a+I:a\in R\}.$$
定义
$$ (a+I)+(b+I)=(a+b)+I,\qquad (a+I)(b+I)=ab+I.$$
乘法良定义的关键是：若 $a'=a+i$、$b'=b+j$，则
$$a'b'-ab=aj+ib+ij\in I.$$
因此 $R/I$ 成为环，零元为 $I$，单位元为 $1+I$（若 $R$ 含幺）。

## 同构定理

对环同态 $f:R\to S$，定义
$$\bar f:R/\ker f\longrightarrow\operatorname{im}f,\qquad a+\ker f\longmapsto f(a).$$
它良定义、双射且保持运算，因此
$$R/\ker f\cong\operatorname{im}f.$$

特别地，对理想 $I$ 的自然投影 $\pi:R\to R/I$ 的核正是 $I$。若 $f:R\to S$ 为满射，则 $R/\ker f\cong S$。

## 第二、第三同构定理

第一同构定理只处理一个同态。群论里还有两条同构定理，环论中逐字平行，证法也是把第一同构定理套到合适的映射上。课程教材把它们留作习题，这里补全陈述。

**第二同构定理。** 设 $A\le R$ 是子环，$I\trianglelefteq R$ 是理想。则 $A\cap I$ 是 $A$ 的理想、$A+I$ 是 $R$ 的子环，并且

$$
A/(A\cap I)\;\cong\;(A+I)/I.
$$

**证明提纲。** 考虑复合映射 $A\hookrightarrow A+I\twoheadrightarrow(A+I)/I$。它是满射，因为 $A+I$ 中每个元素 $a+i$（$a\in A$、$i\in I$）的像都是 $a+I$。它的核是 $\{a\in A:a\in I\}=A\cap I$。对 $A\to(A+I)/I$ 用第一同构定理即得。$\square$

**第三同构定理。** 设 $I\subseteq J$ 都是 $R$ 的理想。则 $J/I$ 是 $R/I$ 的理想，并且

$$
(R/I)\big/(J/I)\;\cong\;R/J.
$$

**证明提纲。** 考虑复合映射 $R\twoheadrightarrow R/I\twoheadrightarrow(R/I)/(J/I)$。它满，且核是 $\{r\in R:r+I\in J/I\}=J$。再用第一同构定理。$\square$

读这两条时建议回到 [Lec 06](../lec06/lec06.md) 的群版本对照：结构完全一样，只是“正规子群”换成了“理想”，而“子群”换成了“子环”。

## 例：$M_n(F)$ 没有非平凡理想

设 $F$ 是域、$n\ge2$，则矩阵环 $M_n(F)$ 只有零理想和自身。这是一个“非交换环里理想不一定多”的典型例子，也是“$M_n(F)$ 不是域”的根本原因：域要求没有非平凡理想，而 $M_n(F)$ 的非零元大多不可逆，却并不能靠理想把它切开。

**证明提纲。** 取非零理想 $I\ne(0)$，选 $0\ne A\in I$，则 $A$ 有某个非零元 $a_{ij}\ne0$。用矩阵单位 $E_{kl}$（只有一个位置为 $1$ 的矩阵）左乘、右乘 $A$，可以把 $A$ 的单个非零元“搬运”到任意位置：

$$
E_{ki}\,A\,E_{jl}=a_{ij}E_{kl}.
$$

于是 $a_{ij}E_{kl}\in I$。再用对角矩阵 $\operatorname{diag}(a_{ij}^{-1},1,\dots,1)$ 乘一次，得到 $E_{kl}\in I$。所有矩阵单位都在 $I$ 中，而它们线性张成整个 $M_n(F)$，所以 $I=M_n(F)$。$\square$

## 例：求值同态与 $(x-c)$

设 $R$ 是交换含幺环，固定 $c\in R$。求值映射

$$
\operatorname{ev}_c:R[x]\longrightarrow R,\qquad f\longmapsto f(c)
$$

是满环同态：它保持加法和乘法，且 $\operatorname{ev}_c(1)=1$。它的核是所有以 $c$ 为根的多项式。

$$
\ker\operatorname{ev}_c=(x-c).
$$

包含关系 $(x-c)\subseteq\ker\operatorname{ev}_c$ 是显然的。反向包含用带余除法：在 $R[x]$ 中除以首一多项式 $x-c$，得

$$
f(x)=q(x)(x-c)+r,\qquad r\in R,
$$

若 $f(c)=0$ 则 $r=f(c)=0$，所以 $f\in(x-c)$。于是第一同构定理给出

$$
R[x]/(x-c)\;\cong\;R .
$$

这是“把 $R[x]$ 中 $x$ 的取值钉在 $c$ 上”的严格说法，也是后面构造域扩张（例如 $\mathbb R[x]/(x^2+1)\cong\mathbb C$）的模板。

## 理想对应定理

设 $I\trianglelefteq R$，$\pi:R\to R/I$ 是自然投影。则

$$
\{J\trianglelefteq R:I\subseteq J\}\;\longleftrightarrow\;\{K\trianglelefteq R/I\},
\qquad J\longmapsto J/I,\qquad \pi^{-1}(K)\longleftarrow K
$$

是一一对应。它保持包含关系（$J_1\subseteq J_2$ 当且仅当 $J_1/I\subseteq J_2/I$），并把和与交对应到和与交：

$$
(J_1+J_2)/I=(J_1/I)+(J_2/I),\qquad (J_1\cap J_2)/I=(J_1/I)\cap(J_2/I).
$$

注意乘积**不**被简单保持：一般只有 $(J_1/I)(J_2/I)=(J_1J_2+I)/I$，分母上多出的 $I$ 不能省。

这是群的对应定理在环论中的平行版本。下一节要用它的一个特例：$M\trianglelefteq R$ 是极大理想，当且仅当商环 $R/M$ 只有零理想和自身，也就是 $R/M$ 是域。

## 参考对照

- [DF] §7.3（同态、理想、商环与第一同构定理）、§7.4（理想的和、积、商与对应定理）；第二、第三同构定理的平行版本在群论 §3.3。
- [DS] §10.2（环同态与理想）；该书把环的第二、第三同构定理留作习题。
- 原始材料：`../../../课堂手记和录音转写/Lec09/`。

