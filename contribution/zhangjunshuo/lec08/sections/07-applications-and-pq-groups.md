# Sylow 定理的应用：小阶群与 $pq$ 群

**本节用到的记号，先一次交代清楚**：

- $G$：有限群；$|G|$：阶；$H,K\le G$：子群；$P,Q$：Sylow 子群（分别对应两个不同的素数）。
- $n_p$：Sylow $p$-子群的个数；判据 $n_p\mid m$ 且 $n_p\equiv1\pmod p$；$n_p=1\iff$ 该 Sylow 子群正规。
- $P_p$：当 $n_p=1$ 时记那个唯一的 Sylow $p$-子群（如 $P_5,P_7,P_{11},P_{13}$）。
- $HK=\{hk\}$：子群乘积；$H\cap K$：交；$[x,y]=xyx^{-1}y^{-1}$：交换子，$[x,y]=e\iff xy=yx$。
- 内部直积：$HK=G$、$H\cap K=\{e\}$（且两者都正规）时 $G\cong H\times K$。
- $C_n$：$n$ 阶循环群；$C_q\rtimes_\varphi C_p$：半直积（$\varphi$ 平凡时退化为直积 $\times$）。
- $\varphi:C_p\to\operatorname{Aut}(C_q)$：把共轭作用写成自同构；$s\in(\mathbb Z/q\mathbb Z)^\times$ 满足 $s^p\equiv1\pmod q$。
- $\operatorname{Aut}(C_q)\cong(\mathbb Z/q\mathbb Z)^\times$：阶为 $q-1$ 的群；$\cong$：同构；$\trianglelefteq$：正规子群。

这一节把 Sylow III 的两个条件
$$
n_p\mid m,\qquad n_p\equiv 1\pmod p
$$
当作“筛选器”使用。先列出可能的 $n_p$，再利用正规性和共轭作用完成结构判断。做题时不要一上来猜群的乘法表。

## 阶为 $35$ 的群

设 $|G|=35=5\cdot 7$。对 Sylow 子群分别计数：

- $n_7\mid 5$ 且 $n_7\equiv1\pmod7$，所以 $n_7=1$；
- $n_5\mid 7$ 且 $n_5\equiv1\pmod5$，所以 $n_5=1$。

因此 Sylow $7$-子群 $Q$ 与 Sylow $5$-子群 $P$ 都正规。它们的交只有单位元，因为 $|P\cap Q|$ 同时整除 $5$ 和 $7$。对任意 $x\in P,y\in Q$，交换子
$$
[x,y]=xyx^{-1}y^{-1}
$$
属于 $P$（因为 $P\trianglelefteq G$），也属于 $Q$（因为 $Q\trianglelefteq G$），所以 $[x,y]=e$。两子群逐点交换，于是 $PQ$ 是子群，而且
$$
|PQ|=\frac{|P||Q|}{|P\cap Q|}=35=|G|,
$$
从而 $G=PQ\cong P\times Q\cong C_5\times C_7\cong C_{35}$。这说明阶 $35$ 的群必为循环群。

## 阶为 $11^2\cdot13^2$ 的群：先判定阿贝尔，不急着判定循环

设 $|G|=11^2\cdot13^2=20449$。Sylow 条件给出
$$
 n_{11}\mid13^2,\quad n_{11}\equiv1\pmod{11},
$$
所以 $n_{11}\in\{1,13,169\}$ 中只有 $1$ 满足同余条件。类似地，
$$
 n_{13}\mid11^2,\quad n_{13}\equiv1\pmod{13},
$$
而 $n_{13}\in\{1,11,121\}$ 中只有 $1$ 满足条件。因此两个 Sylow 子群都正规；下面记 $P_p$ 为那个唯一的 Sylow $p$-子群（即 $P_{11}$ 是 Sylow $11$-子群、$P_{13}$ 是 Sylow $13$-子群，下标就是素数 $p$）。

阶为 $p^2$ 的群是阿贝尔群（见本讲类方程部分），所以 $P_{11}$ 与 $P_{13}$ 都阿贝尔。与阶 $35$ 的论证相同，两个正规、互素阶子群逐点交换，并且乘积等于 $G$。故 $G$ 阿贝尔。

这里要停在“阿贝尔”：$P_{11}$ 可以是 $C_{121}$ 或 $C_{11}\times C_{11}$，$P_{13}$ 也有两种选择，所以不能仅凭阶数断言 $G\cong C_{20449}$。这正是“先判定整体性质，再区分阿贝尔分类”的例子。

## 阶为 $pq$ 的群（$p<q$ 为素数）

设 $|G|=pq$。Sylow 条件先给出
$$
 n_q\mid p,\qquad n_q\equiv1\pmod q.
$$
因为 $p<q$，只有 $n_q=1$，所以 Sylow $q$-子群 $Q=\langle a\rangle$ 正规，且 $|a|=q$（$\langle a\rangle$ 表示由 $a$ 生成的循环子群）。令 $P=\langle b\rangle$ 为 Sylow $p$-子群，$|b|=p$。由于 $|P||Q|=|G|$ 且交只有单位元，$G=QP$，每个元素都可写成 $a^i b^j$（$i=0,\dots,q-1$，$j=0,\dots,p-1$）。

### 共轭作用给出分类分岔

正规性保证 $bab^{-1}\in Q$。$Q$ 是阶 $q$ 的循环群，因此存在整数 $s$ 使 $bab^{-1}=a^s$。这里 $s$ 只能取自模 $q$ 的**单位群**

$$
(\mathbb Z/q\mathbb Z)^\times=\{s\bmod q:\gcd(s,q)=1\},
$$

它由所有与 $q$ 互素的剩余类组成，在乘法下构成群，阶为 $q-1$（$q$ 为素数时每个非零剩余类都可逆）。取这样的 $s$（而不是任意的 $s$）是因为 $a\mapsto a^s$ 必须是 $Q$ 的自同构。于是
$$
bab^{-1}=a^s.
$$
因为 $b^p=e$，反复共轭得到
$$
a=b^pab^{-p}=a^{s^p},
$$
即 $s^p\equiv1\pmod q$。于是只有两种情形：

- $s=1$。此时 $a$ 与 $b$ 交换，$G\cong C_q\times C_p\cong C_{pq}$；
- $s\ne1$。此时 $s$ 在单位群 $(\mathbb Z/q\mathbb Z)^\times$ 中的阶为 $p$（因为 $s^p\equiv1$ 而 $s\ne1$）。单位群的阶是 $q-1$，由拉格朗日定理 $p$ 整除 $q-1$，所以必须有 $p\mid(q-1)$。这给出非阿贝尔的**半直积**关系
  $$
  \langle a,b\mid a^q=b^p=e,\;bab^{-1}=a^s\rangle.
  $$

  （**半直积**的记号写在下面 [DF] 的写法里：$C_q\rtimes_\varphi C_p$。粗说就是“$C_q$ 正规、$C_p$ 通过自同构 $\varphi$ 作用于它”，当 $\varphi$ 不是恒等映射时结果不是直积。它的一般定义这里不展开，本讲只需要上面这一组生成元与关系。）

课堂上最后一个“唯一性”步骤只写到改变 $b$ 的生成元。这里用两种方式补齐，先给一个只用到多项式根的初等写法，再给教材的写法。

**初等写法。** 若 $s$ 与 $t$ 都是阶 $p$ 的非平凡元，则 $s$ 的 $p$ 个幂已经是方程 $X^p=1$ 在模 $q$ 下的全部根（一个次数为 $p$ 的多项式至多有 $p$ 个根）。所以 $t=s^r$，其中 $1\le r<p$。把生成元 $b$ 换成 $b^r$，共轭指数就变成 $s^r=t$。因此在固定的 $p,q$ 下，非阿贝尔情形至多有一个同构类型；它存在当且仅当 $p\mid(q-1)$。

**[DF] 的写法：换成自同构群。** 这里的 $\operatorname{Aut}(C_q)$ 表示 $C_q$ 的**自同构群**（$C_q$ 到自身的全体同构在复合下构成的群），同样有 $\operatorname{Aut}(C_q)\cong(\mathbb Z/q\mathbb Z)^\times$。正规性把共轭作用变成一个同态

$$
\varphi:C_p\longrightarrow\operatorname{Aut}(C_q),\qquad \varphi(b)=\bigl(a\mapsto bab^{-1}\bigr).
$$

因为 $C_q$ 是循环群，$\operatorname{Aut}(C_q)\cong(\mathbb Z/q\mathbb Z)^\times$ 是 $q-1$ 阶群。同态的像的阶同时整除 $p$ 与 $q-1$，所以只有两种可能：像平凡，或像的阶为 $p$。

- 像平凡：$b$ 与 $a$ 交换，群是直积 $C_p\times C_q\cong C_{pq}$；
- 像的阶为 $p$：这要求 $p\mid(q-1)$，群是半直积 $C_q\rtimes_\varphi C_p$。

至于唯一性：$(\mathbb Z/q\mathbb Z)^\times$ 是循环群，所以其中阶为 $p$ 的子群至多一个，记作 $H$。任何像的阶为 $p$ 的同态，其像都等于这个唯一的 $H$；而 $H$ 循环，$\varphi(b)$ 必须是 $H$ 的生成元。于是两个这样的同态 $\varphi,\psi$ 满足 $\psi(b)=\varphi(b)^r$（某个 $1\le r<p$），即 $\psi=\varphi^r$。把 $b$ 换成 $b^r$ 就把 $\varphi$ 变成 $\psi$，两个半直积同构。**所以 $pq$ 阶群恰好有两种同构类型（循环群，以及 $p\mid(q-1)$ 时唯一的非阿贝尔群）**，这正是 [DF] §4.5 里“$p\nmid q-1$ 时必循环”的结论。

两种写法算的是同一件事：初等写法直接数“方程 $X^p=1$ 的根”，教材写法数“阶为 $p$ 的自同构”，而 $(\mathbb Z/q\mathbb Z)^\times$ 循环这件事实保证了这个“阶为 $p$ 的东西”只有一个。

为了看见这个群确实存在，可以在集合 $\mathbb Z/q\mathbb Z\times\mathbb Z/p\mathbb Z$ 上定义
$$
(i,j)(k,\ell)=(i+s^j k,\,j+\ell),
$$
其中第一坐标模 $q$、第二坐标模 $p$，并取 $s^p\equiv1\pmod q$。$\rtimes$ 读作“半直积”，$C_q\rtimes_\varphi C_p$ 中下标 $\varphi$ 指明 $C_p$ 通过哪个自同构作用在 $C_q$ 上。这正是 $C_q\rtimes C_p$ 的乘法；它有 $pq$ 个元素，且 $(1,0)$、$(0,1)$ 满足上面的关系。

### 两个小例子

- $|G|=6$：$p=2,q=3$，非平凡指数只能是 $s=2\equiv-1\pmod3$，得到
  $$
  \langle a,b\mid a^3=b^2=e,\;bab^{-1}=a^{-1}\rangle\cong S_3.
  $$
- $|G|=21$：$p=3,q=7$，因为 $3\mid6$，除了循环群外还可能有非阿贝尔群。取 $s=2$（$2^3\equiv1\pmod7$），关系为 $bab^{-1}=a^2$；取 $s=4=2^2$ 只是把 $b$ 换成 $b^2$ 后的同一同构类型。

## 做题检查清单

1. 写出 $|G|=p^a m$，先用 Sylow III 筛掉不可能的 $n_p$。
2. $n_p=1$ 才能直接写出 $P\trianglelefteq G$；“所有 Sylow 子群共轭”不等于“只有一个”。
3. 需要证明阿贝尔时，检查正规子群的交与交换子；需要分类时，再研究共轭作用 $P\to\operatorname{Aut}(Q)$。
4. 关系式中的指数在 $(\mathbb Z/q\mathbb Z)^\times$ 中计算，最后别忘了验证 $s^p\equiv1$。
