# Lec 18：互信息、集中不等式与 Sanov 大偏差

阅读入口：[Markdown](lec18.md) · [LaTeX](lec18.tex) · [PDF](lec18.pdf)

本目录整理 2026 年 11 月 17 日的课堂，依据用户提供的三页手写稿、上半节旧转写和下半节重新转写。上一份笔记是 Lec17（11 月 12 日），所以本次编号为 **Lec18**。

**来源说明。** 手写稿是公式与结构的主要依据；转写用于补课堂解释与例子。下半节旧转写不完整，本笔记使用重新转写的版本；逐字稿在 `课堂手记和录音转写/2026-11-17/` 下。手写稿中 CLT 与 Chernoff、Sanov 多项式因子等容易混淆的地方，在总览“勘误与提醒”中说明。

课堂主线：**KL/互信息** $\to$ **Markov/Chebyshev/Chernoff** $\to$ **类型计数与 Sanov** $\to$ **数据处理不等式**。

## 分节

1. [KL 散度、互信息与条件互信息](sections/01-kl-mutual-info.md)
2. [集中不等式：Markov、Chebyshev 与 Chernoff](sections/02-concentration.md)
3. [类型计数与 Sanov 大偏差](sections/03-types-sanov.md)
4. [数据处理不等式（DPI）](sections/04-data-processing.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的几个“必须写清”的点

- **互信息**：$I(X;Y)=H(X)+H(Y)-H(X,Y)=D(P_{XY}\Vert P_XP_Y)$；$I(X;Y)=0\iff X,Y$ 独立。
- **条件互信息**：$I(X;Y\mid Z)=H(X\mid Z)+H(Y\mid Z)-H(X,Y\mid Z)$；可大于也可小于 $I(X;Y)$。
- **Chernoff**：$P(X\ge a)\le\min_{t>0}E[e^{tX}]/e^{ta}$；Bernoulli 和的指数是 $D(q\Vert p)$。
- **类型**：$Q_i=T_i/n$；$|T(Q)|\approx e^{nH(Q)}$；$P^n(T(Q))\approx e^{-nD(Q\Vert P)}$。
- **Sanov**：指数为 $\min_{Q\in\mathcal R}D(Q\Vert P)$，上下界差多项式因子。
- **DPI**：$X\to Y\to Z$ 下 $I(X;Z)\le I(X;Y)$；同一信道下 TV/KL 也收缩。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-kl-mutual-info.md sections/01-kl-mutual-info.tex
# 其余分节同理
xelatex lec18.tex
xelatex lec18.tex
xelatex lec18.tex
```

## 参考资料

- 课堂手写稿（2026-11-17，三页）。
- 上半节旧转写 + 下半节重新转写（`课堂手记和录音转写/2026-11-17/`）。
- [DS]《离散数学与结构》信息论、集中不等式、Sanov 与数据处理不等式相关章节。
- 课程讲义中熵、KL、互信息、Chernoff/Sanov 的相关部分。

## 与前后讲的关系

- 前接 Lec17：熵、条件熵、TV 距离、KL 散度是本节的语言基础。
- 本节把“大偏差概率的指数”统一到 KL 散度；后续压缩、信道编码、假设检验和 Markov 链会继续使用 Sanov/DPI。
