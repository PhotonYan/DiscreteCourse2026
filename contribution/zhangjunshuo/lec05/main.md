# Lec 05：数论整理版

本目录把课堂 Lec 05 按九个主题拆开，正文同时提供 Markdown 阅读稿和 Loom 风格的 LaTeX 排版稿。

## 章节

1. [整除与偏序](sections/01-divisibility.md)
2. [最大公因数、最小公倍数与 Bézout 恒等式](sections/02-gcd-bezout.md)
3. [扩展欧几里得算法](sections/03-euclidean-algorithm.md)
4. [素数与算术基本定理](sections/04-prime-factorization.md)
5. [同余、剩余类与逆元](sections/05-congruences.md)
6. [中国剩余定理](sections/06-chinese-remainder.md)
7. [费马小定理、欧拉定理与欧拉函数](sections/07-euler-fermat.md)
8. [RSA：欧拉定理的应用](sections/08-rsa.md)
9. [有理逼近与 Stern--Brocot 树](sections/09-stern-brocot.md)

## 总体关系

整除提供偏序与线性组合的语言；Bézout 恒等式给出扩展欧几里得算法和模逆元；素数分解支撑 Euclid 引理与算术基本定理；同余类形成 $\mathbb Z_m$，费马/欧拉定理描述单位群中的幂；CRT 把互素模数拼成一个模乘积；RSA 将这些事实用于公钥变换；Stern--Brocot 树则把中项搜索、行列式不变量和辗转相除联系起来。

详细阅读请从 `sections/01-divisibility.md` 开始；排版总入口为 `main.tex`。
