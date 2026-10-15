# 不动点引理与停机问题

## 不动点引理

对只有一个自由变量的公式 $\varphi(x)$，存在句子 $\psi$ 使

$$
\mathrm{PA}\vdash\psi\leftrightarrow\varphi(\ulcorner\psi\urcorner).
$$

构造思路是令

$$
\theta(x):=\varphi(S(x,x)),
$$

取 $m=\ulcorner\theta\urcorner$，再令 $\psi=\theta(\overline m)$。此时 $S(m,m)$ 正是 $\psi$ 的编码，因而 $\psi$ 可以谈论自身的编码。

令 $\varphi(x)=\neg\operatorname{Prov}(x)$，得到 Gödel 句

$$
\psi\leftrightarrow\neg\operatorname{Prov}(\ulcorner\psi\urcorner).
$$

## 停机问题

不存在总程序 $H$，对每个程序编码 $\ulcorner M\urcorner$ 和输入 $x$ 判断 $M(x)$ 是否停机。若存在，构造程序 $D$：

1. 运行 $H(\ulcorner D\urcorner,\ulcorner D\urcorner)$；
2. 若 $H$ 说停机，则进入死循环；
3. 若 $H$ 说不停机，则立即停机。

运行 $D$ 自身会产生矛盾：$H$ 的预测永远与实际相反。

## 与证明枚举的关系

在有效公理化理论中，有限证明可以机械检查，所以定理集至少是递归可枚举的。若一个足够强的理论同时能判定每个句子或其否定，就可以并行枚举两类证明得到判定器；这会与相应的不可判定性结果冲突。这里的“证明可检查”和“理论足够强”都是必要前提。
