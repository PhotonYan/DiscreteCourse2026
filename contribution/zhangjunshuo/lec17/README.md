# Lec 17：熵、TV 距离与 KL 散度

阅读入口：[Markdown](lec17.md) · [LaTeX](lec17.tex) · [PDF](lec17.pdf)

本目录整理 2026 年 11 月 12 日的课堂，依据两页手写稿与一段完整课堂转写。上一份笔记是 Lec16（11 月 10 日），所以本次编号为 **Lec17**。

**来源说明。** 转写开头仍在讲上一讲的 PGF 例子（等待连续两个正面），之后进入熵与信息论；整理版把 PGF 收尾放在第 1 节开头。语音识别对“熵/条件熵/TV 距离/KL 散度”等术语错误很多，公式以手写稿为准，转写用于补课堂解释；不一致处见 `lec17.md` 的“勘误与提醒”。

课堂主线：**PGF 收尾** $\to$ **熵与二元熵** $\to$ **条件熵/联合熵/链式法则** $\to$ **TV 距离与耦合** $\to$ **KL 散度与条件 KL**。

## 分节

1. [PGF 收尾、熵的定义与基本性质](sections/01-entropy-basics.md)
2. [条件熵、联合熵与链式法则](sections/02-conditional-entropy-chain.md)
3. [统计距离（TV 距离）](sections/03-tv-distance.md)
4. [KL 散度与条件 KL](sections/04-kl-divergence.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的几个“必须写清”的点

- **熵的底数**：不固定；换底只差常数，bit/nat/byte 分别对应 $\log_2,\ln,\log_{256}$。
- **条件熵**：$H(X\mid Y)=\sum_yP_Y(y)H(X\mid Y=y)$；它是数，不是随机变量。
- **链式法则**：$H(X,Y)=H(Y)+H(X\mid Y)$；只有独立时才能把 $H(X\mid Y)$ 换成 $H(X)$。
- **TV 距离**：$\Delta_{\mathrm{TV}}=\frac12\|P-Q\|_1=1-\sum_x\min(P(x),Q(x))$；耦合解释是最优不相等概率。
- **KL**：非负、不对称、可无穷；$0\log0=0$，$Q(x)=0<P(x)$ 时为 $+\infty$。
- **条件 KL**：权重是 $P_X(x)$；链式法则见第 4 节。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-entropy-basics.md sections/01-entropy-basics.tex
# 其余分节同理
xelatex lec17.tex
xelatex lec17.tex
xelatex lec17.tex
```

## 参考资料

- 课堂手写稿（2026-11-12，两页）与课堂转写。
- [DS]《离散数学与结构》信息论、熵与 KL 散度相关章节。
- 课程讲义中概率、熵、条件熵、TV 距离与 KL 散度相关部分。

## 与前后讲的关系

- 前接 Lec16：条件分布、条件期望与 PGF 是理解“熵/条件熵”的概率语言基础。
- 本节把“不确定性”定量化；后续压缩、信道编码、Markov 链与集中不等式都会用到熵、TV、KL。
