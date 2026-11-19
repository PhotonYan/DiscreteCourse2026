# Lec 19：无损压缩、Huffman 与侧信息

阅读入口：[Markdown](lec19.md) · [LaTeX](lec19.tex) · [PDF](lec19.pdf)

本目录整理 2026 年 11 月 19 日的课堂，依据用户提供的三页手写稿和两段课堂转写。上一份笔记是 Lec18（11 月 17 日），所以本次编号为 **Lec19**。

**来源说明。** 手写稿是公式与结构的主要依据，转写用于补课堂解释。原始手写稿已归档到 [`../手写稿/Lec19-手写原稿.pdf`](../手写稿/Lec19-手写原稿.pdf)。

课堂主线：**无损变长码** $\to$ **Kraft/Huffman** $\to$ **几乎无损定长码（典型集）** $\to$ **侧信息与 Slepian–Wolf**。

## 分节

1. [无损压缩与变长码](sections/01-lossless-compression.md)
2. [Kraft 不等式与 Huffman 编码](sections/02-kraft-huffman.md)
3. [定长压缩与典型集](sections/03-fixed-length-typical.md)
4. [侧信息与 Slepian–Wolf 压缩](sections/04-side-information.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的几个“必须写清”的点

- **熵界**：$H(X)\le E[L]<H(X)+1$；分块后每符号平均码长趋于 $H$。
- **Kraft**：$\sum_i2^{-l_i}\le1$ 是前缀码存在的充要条件。
- **Huffman**：每次合并两个最小概率，得到最优前缀码。
- **典型集**：大小约 $2^{nH}$；定长码取 $L=n(H+\varepsilon)$ 可高概率恢复。
- **侧信息**：解码器有 $Y$ 时，$L_1>H(X\mid Y)$。
- **Slepian–Wolf**：$L_1\ge H(X\mid Y)$、$L_2\ge H(Y\mid X)$、$L_1+L_2\ge H(X,Y)$。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-lossless-compression.md sections/01-lossless-compression.tex
# 其余分节同理
xelatex lec19.tex
xelatex lec19.tex
xelatex lec19.tex
```

## 参考资料

- 课堂手写稿（2026-11-19，三页）。
- 课堂转写（`11月19日_转写文本`、`11月19日 2_转写文本`）。
- [DS]《离散数学与结构》压缩、熵、Huffman 与信息论相关章节。
- 课程讲义中无损压缩、典型集与信息论相关部分。

## 与前后讲的关系

- 前接 Lec17/18：熵、条件熵、KL、Sanov 与典型集是压缩理论的语言基础。
- 本节把“熵是信息量”落实到“熵是压缩极限”；后续信道编码会用到类似典型集/随机编码思想。
