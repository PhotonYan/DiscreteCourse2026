# Lec 07：有限生成阿贝尔群、同构定理续与群作用

本讲根据 2026 年 9 月 29 日的两份课堂转写、手写原稿和教材重新整理。转写中有较多口语识别错误；涉及定义、定理和记号的地方，以手写稿和 [DF]、[DS] 的标准表述校正。课堂对有限生成阿贝尔群结构定理主要给出证明提纲，本文把这部分明确标作“证明提纲”。

## 章节

1. [有限生成阿贝尔群与直积](sections/01-fg-abelian-direct-products.md)
2. [商群的三个同构定理与中心化子](sections/02-quotient-refinements.md)
3. [同态、自同态、自同构与内自同构](sections/03-hom-end-aut-inn.md)
4. [群作用](sections/04-group-actions.md)
5. [轨道、稳定子与轨道--稳定子定理](sections/05-orbits-stabilizers.md)

## 记号速查

- $G,H,K$：群；$e$：单位元；$|G|$：群的阶；$H\le G$：子群；$N\trianglelefteq G$：正规子群。
- $\langle S\rangle$：由 $S$ 生成的最小子群；$\langle g\rangle$：循环子群。
- $G\times H$：外部直积；$G=H\times K$（内部直积）表示乘法映射 $(h,k)\mapsto hk$ 是同构。
- $\mathbb Z_n=\mathbb Z/n\mathbb Z$；$\mathbb Z_n^\times$：模 $n$ 的单位群；$\mathbb Z^r$：自由阿贝尔部分。
- $Z(G)$：中心；$C_G(A)$：集合 $A$ 的中心化子；$c_g(x)=gxg^{-1}$：共轭映射。
- $\operatorname{Hom}(G,H)$、$\operatorname{End}(G)$、$\operatorname{Aut}(G)$、$\operatorname{Inn}(G)$：同态、自同态、自同构、内自同构集合或群。
- $G\curvearrowright X$：$G$ 作用在 $X$ 上；$G\cdot x$：轨道；$G_x$：稳定子；$[G:G_x]$：指数。
- 二面体群按 [DF] 记 $D_{2n}$，阶为 $2n$；正方形的对称群写作 $D_8$。

## 与 Lec06 的衔接

Lec06 已整理群、正规子群、商群、群同态、第一同构定理和对应定理。本讲继续使用商映射和核的语言，先补充第二、第三同构定理，再进入自同构与群作用。前两节之间的同构定理不是彼此孤立的公式：它们都由自然映射和第一同构定理统一推出。

## 参考文献

- [DF] D. S. Dummit, R. M. Foote. *Abstract Algebra*, 3rd ed. §§1.7, 2.2, 5.1--5.2。
- [DS] 邓小铁、王畅。《离散数学与结构》。未定稿，2023。§§9.6, 14.1。
