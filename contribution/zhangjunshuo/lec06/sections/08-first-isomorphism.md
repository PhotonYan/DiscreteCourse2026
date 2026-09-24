# 第一同构定理（First Isomorphism Theorem）

参考：[DF] Dummit–Foote《Abstract Algebra》§3.3（Theorem 16、Corollary 17）；[DS]《离散数学与结构》§9.5。

## 定理

设 $\varphi:G\to H$ 是群同态，则 $\ker\varphi\trianglelefteq G$，且

$$G/\ker\varphi\cong\operatorname{im}\varphi.$$

若 $\varphi$ 是满射，右边就是 $H$，常写成 $G/\ker\varphi\cong H$。

这条定理就是说：$\varphi$ 把核里的元素全压到单位元；把核当成一个点，$G$ 剩下的结构和 $\operatorname{im}\varphi$ 完全一样。例如 $\varphi:\mathbb Z_4\to\mathbb Z_2$，$k\mapsto k\bmod 2$：核是 $\{0,2\}$，把这两个元素压成一个点，$\mathbb Z_4$ 就只剩两个点，正好是 $\mathbb Z_2$。

## 证明

令 $N=\ker\varphi$，定义

$$\overline\varphi:G/N\longrightarrow\operatorname{im}\varphi,\qquad \overline\varphi(gN)=\varphi(g).$$

需要验证四点。

**良定义。** 若 $gN=g'N$，则 $g^{-1}g'\in N$，所以 $\varphi(g^{-1}g')=e_H$，即 $\varphi(g)^{-1}\varphi(g')=e_H$，从而 $\varphi(g)=\varphi(g')$。同一个陪集的代表元给出同一个像。

**同态。** 对 $gN,g'N\in G/N$，

$$\overline\varphi((gN)(g'N))=\overline\varphi(gg'N)=\varphi(gg')=\varphi(g)\varphi(g')=\overline\varphi(gN)\overline\varphi(g'N).$$

**满射。** 任取 $y\in\operatorname{im}\varphi$，有 $y=\varphi(g)=\overline\varphi(gN)$。

**单射。** 若 $\overline\varphi(gN)=e_H$，则 $\varphi(g)=e_H$，即 $g\in N$，所以 $gN=N$ 是单位元，核平凡。

于是 $\overline\varphi$ 是同构，定理得证。

## 例

行列式 $\det:GL_n(F)\to F^\times$ 是满同态，核为 $SL_n(F)$。代入第一同构定理得

$$GL_n(F)/SL_n(F)\cong F^\times.$$

## 推论

- $\varphi$ 单射 $\iff\ker\varphi=\{e\}$；此时 $\varphi$ 给出 $G\cong G/\{e\}$。
- $\varphi$ 满射时 $G/\ker\varphi\cong H$。
- 若 $G$ 有限，则 $|G|=|\ker\varphi|\cdot|\operatorname{im}\varphi|$；一般地 $|G:\ker\varphi|=|\operatorname{im}\varphi|$。
- 对任意 $g,g'$ 有 $\varphi(g)=\varphi(g')\iff g\ker\varphi=g'\ker\varphi$，即每个纤维都是核的陪集。把每个纤维缩成一点，就得到 $G/\ker\varphi\cong\operatorname{im}\varphi$。

