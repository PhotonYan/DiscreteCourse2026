# 对称群

参考：[DF] Dummit–Foote《Abstract Algebra》§1.3；[DS]《离散数学与结构》§9.2。

非空集合 $\Omega$ 上全体双射（置换，permutation）在复合下构成对称群（symmetric group）$\operatorname{Sym}(\Omega)$。当 $\Omega$ 取前 $n$ 个整数时记作 $S_n$；用 $\{1,\ldots,n\}$ 或 $\{0,\ldots,n-1\}$ 编号只是习惯不同。

## 循环记号

以 $\Omega=\{0,1,\ldots,9\}$ 上的置换为例，$\sigma$ 由下表给出（左列是 $a$，右列是 $\sigma(a)$）：

```latex
\begin{center}
\begin{tabular}{cc}
$a$ & $\sigma(a)$\\ \hline
0 & 1\\
1 & 3\\
2 & 5\\
3 & 7\\
4 & 9\\
5 & 2\\
6 & 4\\
7 & 6\\
8 & 8\\
9 & 0
\end{tabular}
\end{center}
```

用循环记号写成

$$\sigma=(0\ 1\ 3\ 7\ 6\ 4\ 9)(2\ 5)(8),$$

含义是 $0\mapsto1\mapsto3\mapsto7\mapsto6\mapsto4\mapsto9\mapsto0$，$2\leftrightarrow5$，$8$ 不动。一般地，循环（cycle）$\tau=(c_1\ c_2\ \cdots\ c_k)$ 表示下面定义的双射：

$$
\tau(x)=
\begin{cases}
c_{(i\bmod k)+1}, & x=c_i\ (1\le i\le k),\\
x, & x\notin\{c_1,\ldots,c_k\}.
\end{cases}
$$

也就是说：循环里的元素换成下一个（最后一个的下一个回到第一个），不在循环里的元素不动。特别地，长度 $1$ 的循环 $(c)$ 把 $c$ 映到它自己，就是恒等映射，所以书写时可以省略。

## 分解的唯一性与书写规则

每个置换都能写成若干互不相交循环的乘积（有限集合上总能做到）。分解式唯一：不计循环之间的书写顺序，也不计每个循环从哪个元素写起。省略长度 $1$ 的循环，$\sigma$ 通常记作 $(0\ 1\ 3\ 7\ 6\ 4\ 9)(2\ 5)$。

## 逆

把每个循环反向读，就得到逆置换：

$$\sigma^{-1}=(9\ 4\ 6\ 7\ 3\ 1\ 0)(5\ 2)(8).$$

因为循环把 $c_i$ 映到 $c_{i+1}$，反过来就把 $c_{i+1}$ 映回 $c_i$。

## 乘积约定

两个置换的乘积从右往左读：$(\alpha\beta)(x)=\alpha(\beta(x))$。

