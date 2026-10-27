# Lec 13：生成函数

阅读入口：[Markdown](lec13.md) · [LaTeX](lec13.tex) · [PDF](lec13.pdf)

本目录整理 2026 年 10 月 27 日 Lec13，依据两页手写稿与两段课堂转写整理，并以课程讲义 §9.9、教材 [DS] 第 13 章补全证明细节。

**来源说明。** 手写稿是两页高密度公式清单（基本生成函数、运算表、找零、Catalan、3×n 覆盖的辅助状态、EGF、Bernoulli）；转写包含口述解释、3×n 覆盖的图形分解、教室/集合/树的 EGF 解释与幂和推导。整理版按"取并集"处理：只在一处出现的内容予以保留并注明；两边冲突或疑似笔误处给出勘误（见 `lec13.md` 与各节末尾）。

课堂主线：**普通生成函数**（定义、基本表、运算、多米诺/斐波那契、找零、部分分式/Binet）$\to$ **组合方程**（Catalan、3×n 覆盖）$\to$ **指数生成函数**（二项卷积、$\exp$/集合、教室、集合划分、标号树）$\to$ **幂和与 Bernoulli 数**。

## 分节

1. [普通生成函数：定义、基本例子与运算](sections/01-ogf-basics.md)
2. [有理生成函数、部分分式与线性递推](sections/02-rational-partial-fractions.md)
3. [卡特兰数的生成函数：从组合方程到通项](sections/03-catalan-generating-function.md)
4. [3×n 多米诺覆盖：辅助状态与生成函数方程组](sections/04-3xn-domino-states.md)
5. [指数生成函数与带标号结构](sections/05-exponential-generating-functions.md)
6. [幂和与 Bernoulli 数：用 EGF 把求和变成乘法](sections/06-power-sums-bernoulli.md)

## 附加讲解稿

- [普通生成函数 vs 指数生成函数（PDF）](explainer-ogf-vs-egf.pdf)：为什么有两种生成函数、各自的性质、判别准则、经典例子对照、常见错误与自测题。源稿 [explainer-ogf-vs-egf.md](explainer-ogf-vs-egf.md)。

## 本讲的几个"必须写清"的点

- **OGF 乘法 = 普通卷积；EGF 乘法 = 二项卷积**：$\sum a_ib_{n-i}$ 与 $\sum\binom ni a_ib_{n-i}$ 的差别就是"要不要先分标签"。
- **Catalan 是 OGF 的典型**：$C=1+xC^2$；用 EGF 不能直接套这个方程。
- **3×n 覆盖**：$C(x)=\dfrac{1-x^2}{1-4x^2+x^4}$，$a_n=4a_{n-2}-a_{n-4}$（$n$ 为偶数）；整理版把 V/Λ 缺口状态统一为 C/V/W/Z 轮廓。
- **Bernoulli 幂和公式**：统一用 $B_1^+=1/2$ 的约定，公式为 $S_m(n)=\frac{1}{m+1}\sum_{j=0}^m\binom{m+1}{j}B_j^+n^{m+1-j}$。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-ogf-basics.md sections/01-ogf-basics.tex
xelatex lec13.tex
xelatex lec13.tex
xelatex lec13.tex
```

（其余分节同理；`sections/*.tex` 要与 `sections/*.md` 同步。）

## 参考资料

- [DS]《离散数学与结构》**第 13 章（生成函数）**：§13.1 用生成函数求解递归式、§13.2 一般生成函数、§13.3 指数生成函数。本章的多重集组合/排列、Bell 数、Catalan、二项卷积等与本讲直接对应。
- 课程讲义 **§9.9 生成函数**：定义、基本生成函数表、运算表、找零问题、有理函数与部分分式、Fibonacci、Catalan。
- 原始材料：本地归档（手写原稿 PDF、两段转写），不纳入课程仓库。

## 与前后讲的关系

- 上一讲 Lec12（组合计数）已经得到 Catalan 数、二项式系数、容斥与抽屉原理；本讲用生成函数重新推出 Catalan 通项，并把"求和/递推"系统化。
- 本讲是后续"离散概率"（[DS] 第 12 章）与"生成函数/组合结构"的预备；附加讲解稿把 OGF 与 EGF 的使用场景做了系统对照。
