# Lec 05：数论

这是 `zhangjunshuo` 对课程 Lec 05 的整理版。内容按主题拆成九个章节，保留课堂手记中的主线，并把录音中出现但手记略写的证明补齐。

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

`main.tex` 是总入口，`sections/*.tex` 是由同名 Markdown 生成的排版片段。PDF 中使用 Loom 模板；如果只想继续修改内容，编辑 Markdown 后重新生成对应 TeX 即可。

## 本次整理的约定

- 默认 $\mathbb N=\{0,1,2,\ldots\}$；涉及素数分解时使用正整数。
- $\gcd(0,0)=0$、$\operatorname{lcm}(a,0)=0$ 是单独声明的约定，不与“最大正公因子”和“最小正公倍数”的取值式混写。
- RSA 部分只证明数论正确性，不把“能由分解破解”写成“RSA 与分解已证明等价”。
- Stern--Brocot 部分证明中项在相邻区间内的最小分母性质；不把整条搜索路径错误地称为全局 Pareto 前沿。

## 编译

在本目录运行：

```bash
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```
