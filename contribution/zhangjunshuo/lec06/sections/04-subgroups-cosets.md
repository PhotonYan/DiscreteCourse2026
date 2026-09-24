# 子群与陪集

参考：[DF] Dummit–Foote《Abstract Algebra》§2.1、§3.2（Lagrange 定理即 [DF] Theorem 8）；[DS]《离散数学与结构》§9.3–9.4。

## 子群判定

设 $G$ 是群。非空子集 $H\subseteq G$ 若在 $G$ 的运算下仍是群，称为 $G$ 的子群（subgroup），记 $H\le G$。子群单独看也是一个群；它的单位元必与 $G$ 的单位元相同：若 $e_H\in H$ 在 $H$ 中当单位元，则 $e_He_H=e_H=e_He$，在 $G$ 中消去 $e_H$ 得 $e_H=e$。

直接验证子群时，实际需要的是两条比较简单的封闭性规则：

- 乘法封闭：$a,b\in H\Rightarrow ab\in H$；
- 逆元封闭：$a\in H\Rightarrow a^{-1}\in H$。

（再加上 $H$ 非空；结合律由 $G$ 继承，不必重验。）下面这条判定准则（subgroup criterion）把两条压成一条：

$$H\le G\iff H\ne\varnothing\ \text{且}\ \forall a,b\in H,\ ab^{-1}\in H.$$

证明两个方向。若准则成立，逐条验证 $H$ 满足群的性质：

- 结合律：由 $G$ 继承；
- 单位元：取 $a=b\in H$ 得 $e=aa^{-1}\in H$；
- 逆元：取 $a=e$ 得 $b^{-1}\in H$；
- 乘法封闭：于是 $a(b^{-1})^{-1}=ab\in H$。

所以 $H$ 满足群的性质，是 $G$ 的子群。反过来，若 $H$ 非空且满足群的性质，则对任意 $a,b\in H$，先有 $b^{-1}\in H$，再由乘法封闭得 $ab^{-1}\in H$，准则成立。

例：$\mathbb Z\le\mathbb Q\le\mathbb R\le\mathbb C$（都看成加法群）是子群链；$n\mathbb Z=\{na:a\in\mathbb Z\}\le\mathbb Z$。

## 陪集

设 $H\le G$，$g\in G$。左陪集（left coset）为 $gH=\{gh:h\in H\}$，右陪集（right coset）为 $Hg=\{hg:h\in H\}$。把陪集（coset）看成等价类：$g$ 与 $g'$ 落在同一个左陪集里，当且仅当 $g^{-1}g'\in H$，这是一个等价关系。

**两个左陪集要么相等，要么不交。** 先看一个元素是否属于 $gH$ 的几种等价说法：

$$g'\in gH\iff(\exists h\in H)\ g'=gh\iff g^{-1}g'\in H\iff (g')^{-1}g\in H.$$

再证相交的情形必相等。设 $gH\cap g'H\ne\varnothing$，取公共元素 $x=gh_1=g'h_2$（$h_1,h_2\in H$），则 $g^{-1}g'=h_1h_2^{-1}\in H$。任取 $gh\in gH$，

$$gh=g\,(g^{-1}g')\,(g^{-1}g')^{-1}h=g'\bigl((g^{-1}g')^{-1}h\bigr)\in g'H,$$

所以 $gH\subseteq g'H$；同理（把 $g,g'$ 互换）得 $g'H\subseteq gH$，于是 $gH=g'H$。

由此，左陪集两两不交，把 $G$ 分成若干块。两个左陪集相等的条件可以直接写成

$$gH=g'H\iff g^{-1}g'\in H.$$

左陪集的集合记作 $G/H=\{gH:g\in G\}$，右陪集的集合记作 $H\backslash G=\{Hg:g\in G\}$；左陪集的个数 $|G/H|$ 称为 $H$ 在 $G$ 中的指数（index）。每个陪集都与 $H$ 一样大：固定 $g$，$h\mapsto gh$ 是 $H$ 到 $gH$ 的双射。所以若 $G$ 有限，则

$$|G/H|=\frac{|G|}{|H|},\qquad |G|=|G/H|\cdot|H|,$$

例如 $\mathbb Z_6=\{0,1,\ldots,5\}$ 中取 $H=\{0,3\}$：陪集有三个（$\{0,3\}$、$\{1,4\}$、$\{2,5\}$），每块 $2$ 个元素，$6=3\cdot 2$。

特别地 $|H|$ 整除 $|G|$。几点说明：

- 无限群不能直接做这种除法：陪集个数要按基数理解。
- 逆命题方向：$d\mid|G|$ 不保证存在 $d$ 阶子群——正四面体的旋转对称群有 $12$ 个元素，却没有 $6$ 阶子群。

例：$\mathbb Z$ 中取 $H=n\mathbb Z$，陪集是

$$1+n\mathbb Z,\quad 2+n\mathbb Z,\quad\ldots,\quad(n-1)+n\mathbb Z,$$

即按模 $n$ 的余数分出的类（$0+n\mathbb Z$ 就是 $n\mathbb Z$ 自己）。

