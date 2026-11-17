# Lec 16：概率与概率生成函数

阅读入口：[Markdown](lec16.md) · [LaTeX](lec16.tex) · [PDF](lec16.pdf)

本目录整理 2026 年 11 月 10 日的课堂，依据三页手写稿与两段课堂转写，并以课程中的概率/生成函数语言补全解释。按你的编号约定：上一份笔记到 Lec14，中间空过一讲，所以这一次编号为 **Lec16**。

**来源说明。** 三页手写稿是公式与结构的主要依据；第一段转写只覆盖开头（概率空间、条件概率、随机变量），第二段从条件期望附近开始，语音识别把不少术语识别错（如“条件分布”“协方差”“生成函数”“Poisson”）。整理版以手写稿为准，用转写补例子和课堂解释；手写稿中容易误读的符号与约定在 `lec16.md` 的“勘误与提醒”中说明。

课堂主线：**概率空间** $\to$ **条件概率/条件分布/Bayes** $\to$ **随机变量与独立性** $\to$ **期望与条件期望** $\to$ **方差/协方差** $\to$ **PGF 与常见分布** $\to$ **Poisson 极限/过程**。

## 分节

1. [概率空间、条件概率与随机变量](sections/01-probability-basics.md)
2. [期望、条件期望与全期望公式](sections/02-expectation-conditional.md)
3. [方差、协方差与双线性](sections/03-variance-covariance.md)
4. [概率生成函数与常见分布](sections/04-pgf.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的几个“必须写清”的点

- **条件分布**：$p_B(\omega)=p(\omega)/P(B)$（$\omega\in B$），否则为 $0$；它本身是一个概率分布。
- **全期望公式**：$E[X]=E[E[X\mid Y]]$；$E[X\mid Y]$ 是随机变量，$E[X\mid Y=y]$ 是数。
- **方差展开**：$\operatorname{Var}(X+Y)=\operatorname{Var}X+\operatorname{Var}Y+2\operatorname{Cov}(X,Y)$；独立时协方差项为 $0$。
- **独立 vs 不相关**：独立 $\Rightarrow$ 不相关；不相关 $\nRightarrow$ 独立。
- **PGF 读矩**：$G_X'(1)=E[X]$，$G_X''(1)=E[X(X-1)]$，所以 $E[X^2]=G_X''(1)+G_X'(1)$。
- **几何/负二项约定**：数“试验次数”还是“失败次数”会改变 PGF 的平移与均值；先看题目定义。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-probability-basics.md sections/01-probability-basics.tex
# 其余分节同理
xelatex lec16.tex
xelatex lec16.tex
xelatex lec16.tex
```

## 参考资料

- 课堂手写稿（2026-11-10，三页）与两段课堂转写。
- [DS]《离散数学与结构》概率与生成函数相关章节。
- 课程讲义中概率、条件期望、概率生成函数与 Poisson 分布的相关部分。

## 与前后讲的关系

- 前接 Lec12 的组合计数与 Lec13 的生成函数：PGF 是“系数为概率的 OGF”，独立和对应乘法与 EGF/OGF 的卷积思想一致。
- 后续马尔可夫链会把“条件分布”写成转移核；本讲的条件分布与链式法则就是其语言基础。
