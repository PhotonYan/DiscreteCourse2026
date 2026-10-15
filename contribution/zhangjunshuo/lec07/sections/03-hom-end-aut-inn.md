# 同态、自同态、自同构与内自同构

**本节用到的记号，先一次交代清楚**：

- $\operatorname{Hom}(G,H)$：$G$ 到 $H$ 的全体同态；$\operatorname{End}(G)=\operatorname{Hom}(G,G)$：自同态（复合下是幺半群）。
- $\operatorname{Aut}(G)$：$G$ 的全体自同构（可逆自同态），在复合下成群；$\operatorname{Aut}(\mathbb Z_n)\cong\mathbb Z_n^\times$。
- $c_g:G\to G,\ c_g(x)=gxg^{-1}$：由 $g$ 决定的共轭（内自同构）；$c_g\circ c_h=c_{gh}$。
- $\operatorname{Inn}(G)=\{c_g:g\in G\}\trianglelefteq\operatorname{Aut}(G)$：内自同构群。
- $\kappa:G\to\operatorname{Aut}(G),\ g\mapsto c_g$：内自同构同态；$\ker\kappa=Z(G)$，故 $\operatorname{Inn}(G)\cong G/Z(G)$。
- $\operatorname{Out}(G)=\operatorname{Aut}(G)/\operatorname{Inn}(G)$：外自同构群。
- $Z(G)$：中心；$G/Z(G)$：商群；$\cong$：同构；$\ker$：核。
- $\varphi\cdot x=\varphi(x)$：自同构群作用于 $G$ 的写法（本节末尾的预告）。
- $\mathbb Z_n^\times$：$\mathbb Z_n$ 的单位群，即与 $n$ 互素的剩余类。

## 四个常用集合

给定群 $G,H$，记

$$
\operatorname{Hom}(G,H)=\{\varphi:G\to H:\varphi\text{ 是群同态}\}.
$$

当定义域和值域相同时，得到

$$
\operatorname{End}(G)=\operatorname{Hom}(G,G),
$$

称为 $G$ 的自同态集合。可逆的自同态组成自同构群

$$
\operatorname{Aut}(G)=\{\varphi:G\to G:\varphi\text{ 是同构}\},
$$

运算是函数复合，单位元是恒等映射，逆元是逆函数。

在复合运算下，$\operatorname{End}(G)$ 通常只是含单位元的幺半群，$\operatorname{Hom}(G,H)$ 一般也没有自然的群结构；只有在额外的交换群或环结构下，才可以讨论点态加法。

## 共轭与内自同构

对每个 $g\in G$，定义共轭映射

$$
 c_g:G\to G,\qquad c_g(x)=gxg^{-1}.
$$

它是自同构，因为

$$
 c_g(xy)=gxyg^{-1}=(gxg^{-1})(gyg^{-1}).
$$

并且 $c_g^{-1}=c_{g^{-1}}$，以及

$$
c_g\circ c_h=c_{gh}.
$$

所有共轭映射组成的集合称为内自同构群：

$$
\operatorname{Inn}(G)=\{c_g:g\in G\}\le \operatorname{Aut}(G).
$$

映射

$$
\kappa:G\longrightarrow\operatorname{Aut}(G),
\qquad g\longmapsto c_g
$$

是群同态，其核为

$$
\ker\kappa=Z(G).
$$

因此由第一同构定理

$$
\operatorname{Inn}(G)\cong G/Z(G).
$$

在 $\operatorname{Aut}(G)$ 中，$\operatorname{Inn}(G)$ 是正规子群；商群 $\operatorname{Aut}(G)/\operatorname{Inn}(G)$ 常记为 $\operatorname{Out}(G)$，但本讲重点是内自同构本身。

正规性可由任意 $\alpha\in\operatorname{Aut}(G)$ 直接看出：

$$
\alpha c_g\alpha^{-1}=c_{\alpha(g)}\in\operatorname{Inn}(G).
$$

## 例：$\operatorname{Aut}(\mathbb Z_n)$

循环群 $\mathbb Z_n$ 由 $\bar 1$ 生成，因此一个同态 $\varphi:\mathbb Z_n\to\mathbb Z_n$ 完全由 $\varphi(\bar 1)=\bar k$ 决定，并且

$$
\varphi(\bar m)=\overline{km}.
$$

该映射是自同构，当且仅当 $\bar k$ 也是生成元；这等价于

$$
\gcd(k,n)=1.
$$

于是

$$
\operatorname{Aut}(\mathbb Z_n)\cong \mathbb Z_n^\times,
$$

其中 $\mathbb Z_n^\times$ 是模 $n$ 的可逆剩余类群，运算为乘法。这里“可逆”不是额外记忆点，而是保证乘法映射有逆映射的必要充分条件。

## 与群作用的预告

自同构群天然作用在 $G$ 上：$\varphi\cdot x=\varphi(x)$。共轭作用就是这个观点的一个特殊情况。下一节把“群元素对集合元素做变换”抽象成一般的群作用。

## 记忆点

- $\operatorname{End}(G)$ 允许不可逆的自映射；$\operatorname{Aut}(G)$ 只保留可逆者。
- $g\mapsto c_g$ 的核是中心，所以 $G/Z(G)$ 描述了真正产生的共轭变换。
- 循环群上的自同构由生成元的像决定；生成元恰好对应模 $n$ 的单位。

## 参考对照

- [DF] 关于 automorphism、inner automorphism 和 $\operatorname{Aut}(\mathbb Z_n)$ 的章节。
- [DS] 群同态与群作用前的自同构例子。
