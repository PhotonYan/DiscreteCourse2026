## 1. 群的定义与基本例子

设 $G$ 是非空集合，$\cdot:G\times G\to G$ 是二元运算。$(G,\cdot)$ 是群，若满足：

1. **结合律**：$(ab)c=a(bc)$；
2. **单位元**：存在 $e\in G$，使 $eg=ge=g$；
3. **逆元**：对每个 $g\in G$，存在 $g^{-1}\in G$，使 $gg^{-1}=g^{-1}g=e$。

群的单位元唯一，逆元唯一，且 $(ab)^{-1}=b^{-1}a^{-1}$。若 $ab=ba$ 对所有 $a,b\in G$ 成立，则称 $G$ 为 Abel 群。群运算通常省略乘号，Abel 群也常用加法记号，此时单位元写 $0$，逆元写 $-a$。

**例子**：$(\mathbb Z,+)$、$\mathbb Z/n\mathbb Z$ 是 Abel 群；可逆 $n\times n$ 矩阵在乘法下构成 $GL_n(F)$；$n$ 个元素的置换群为 $S_n$，其阶为 $n!$。Klein 四元群 $V_4\cong C_2\times C_2$。

## 2. 子群、循环群和群的阶

非空 $H\subseteq G$ 是子群（$H\le G$）当且仅当

$$H\ne\varnothing,\qquad a,b\in H\Longrightarrow ab^{-1}\in H.$$

元素 $g$ 生成的循环子群是 $\langle g\rangle=\{g^n:n\in\mathbb Z\}$。元素的阶 $\operatorname{ord}(g)$ 是最小正整数 $n$ 使 $g^n=e$；若不存在则阶为无限。有限循环群阶为 $n$ 时与 $\mathbb Z/n\mathbb Z$ 同构。

有限群 $G$ 的阶记作 $|G|$。循环群 $C_n$ 的每个子群仍为循环群；对每个 $d\mid n$，它恰有一个阶为 $d$ 的子群。

## 3. 陪集、指数与 Lagrange 定理

对 $H\le G$、$g\in G$，左陪集 $gH=\{gh:h\in H\}$，右陪集 $Hg=\{hg:h\in H\}$。任意两个左陪集要么相等、要么不相交；每个陪集与 $H$ 等势。指数 $[G:H]$ 是不同左陪集的个数。

> **Lagrange 定理**：有限群中 $|G|=|H|[G:H]$，因此 $|H|\mid |G|$。

直接推论：元素阶整除群阶；阶为素数的群必循环；若 $|G|=p^2$，则 $G$ Abel。逆命题一般不成立：群阶的每个因数未必都对应某个子群。

## 4. 正规子群与商群

子群 $N\le G$ 正规（$N\trianglelefteq G$）当且仅当

$$gN=Ng\quad\forall g\in G\quad\Longleftrightarrow\quad gNg^{-1}=N\quad\forall g\in G.$$

正规子群的核是典型来源：若 $\varphi:G\to H$ 是同态，则 $\ker\varphi=\{g:\varphi(g)=e_H\}\trianglelefteq G$。当 $N\trianglelefteq G$ 时，陪集集合 $G/N$ 在运算 $(gN)(hN)=(gh)N$ 下成为群，称商群。写出商群运算后要检查它对陪集代表元的选择**良定义**。

## 5. 同态与同构定理

群同态 $\varphi:G\to H$ 满足 $\varphi(ab)=\varphi(a)\varphi(b)$。其像 $\operatorname{im}\varphi\le H$，核 $\ker\varphi\trianglelefteq G$。

> **第一同构定理**：$G/\ker\varphi\cong\operatorname{im}\varphi$，同构由 $g\ker\varphi\mapsto\varphi(g)$ 给出。

进一步常用结论：

- 若 $H\le G$、$N\trianglelefteq G$，则 $HN\le G$ 且 $HN/N\cong H/(H\cap N)$；
- 若 $N\trianglelefteq G$、$N\le K\trianglelefteq G$，则 $(G/N)/(K/N)\cong G/K$；
- $G/N$ 的子群对应于 $G$ 中包含 $N$ 的子群，正规性也在该对应下保留。

## 6. 群作用、轨道与类方程

群 $G$ 在集合 $A$ 上作用，若 $e\cdot a=a$ 且 $(gh)\cdot a=g\cdot(h\cdot a)$。定义

$$\operatorname{Orb}(a)=\{g\cdot a:g\in G\},\qquad \operatorname{Stab}(a)=\{g\in G:g\cdot a=a\}.$$

稳定子是子群，轨道和陪集一一对应：$G/\operatorname{Stab}(a)\to\operatorname{Orb}(a)$，$g\operatorname{Stab}(a)\mapsto g\cdot a$。因此

> **轨道-稳定子定理**：$|\operatorname{Orb}(a)|=[G:\operatorname{Stab}(a)]$；若 $G$ 有限，则 $|\operatorname{Orb}(a)|=|G|/|\operatorname{Stab}(a)|$。

共轭作用 $g\cdot x=gxg^{-1}$ 的轨道是共轭类，稳定子是中心化子 $C_G(x)=\{g:gx=xg\}$。中心 $Z(G)=\{x:gx=xg\ \forall g\}$。取非中心共轭类代表 $x_1,\dots,x_t$，得**类方程**

$$|G|=|Z(G)|+\sum_{i=1}^{t}[G:C_G(x_i)].$$

对非平凡有限 $p$ 群，类方程说明 $p\mid |Z(G)|$，故中心非平凡；这是证明 $p^2$ 阶群 Abel 的常用一步。

## 7. Sylow 定理

设 $|G|=p^k m$ 且 $p\nmid m$。阶为 $p^k$ 的子群称 **Sylow $p$ 子群**，阶为 $p$ 的幂的子群称 **$p$-子群**。

> **Sylow 定理**
>
> 1. **存在**：至少有一个 Sylow $p$ 子群；每个 $p$-子群都包含在某个 Sylow $p$ 子群中。
> 2. **共轭**：任意两个 Sylow $p$ 子群共轭；它们构成一个共轭类。
> 3. **个数**：若 $n_p$ 为 Sylow $p$ 子群个数，则
>    $$n_p\mid m,\qquad n_p\equiv1\pmod p,\qquad n_p=[G:N_G(P)],$$
>    其中 $N_G(P)=\{g\in G:gPg^{-1}=P\}$ 是正规化子。

若 $n_p=1$，唯一的 Sylow $p$ 子群正规；反过来，正规 Sylow $p$ 子群唯一。计算题先列整除和同余约束，再用正规性或共轭作用确定结构。

**例：$|G|=35$。** $n_5\mid7$ 且 $n_5\equiv1\pmod5$，故 $n_5=1$；$n_7\mid5$ 且 $n_7\equiv1\pmod7$，故 $n_7=1$。两个 Sylow 子群正规、阶互素，故 $G\cong C_5\times C_7\cong C_{35}$。

