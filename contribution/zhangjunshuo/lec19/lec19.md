# Lec 19：无损压缩、Huffman 与侧信息

这一讲进入**压缩**：先把无损变长码的极限说清楚（熵、Kraft、Huffman），再讲几乎无损定长压缩（典型集），最后推广到有侧信息的分布式压缩（Slepian–Wolf）。

**来源与编号说明。** 本讲对应 2026 年 11 月 19 日的课堂，依据用户提供的三页手写稿和两段课堂转写整理。上一份笔记是 Lec18（11 月 17 日），所以本次编号为 **Lec19**。手写稿是公式与结构的主要依据，转写补例子和课堂解释。

## 记号速查

- $P$：信源分布；$f$：编码；$g$：解码；$l(x)=|f(x)|$；$L=E[l(X)]$。
- $H(X)$：熵；$H(X\mid Y)$：条件熵；$L^*$：最优前缀码平均码长。
- $T_\varepsilon^{(n)}$：典型集；$L$：定长码长度。
- $L_1,L_2$：两个编码器的速率；Slepian–Wolf 区域。

## 本讲的几条主线

1. **无损变长码**：$H\le E[L]<H+1$；Kraft 不等式；Huffman 码最优。
2. **几乎无损定长码**：典型集大小约 $2^{nH}$，取 $L=n(H+\varepsilon)$ 可高概率恢复。
3. **随机压缩**：分布未知时，随机函数/随机线性映射也能达到 $L\approx nH$。
4. **侧信息**：解码器有 $Y$ 时，$X$ 的速率下界是 $H(X\mid Y)$。
5. **Slepian–Wolf**：两个独立编码器、联合解码器，可达区域由三个熵下界给出。

## 勘误与提醒

- 手写稿的“最优压缩函数”部分先讨论了非前缀码的直观最优映射；本笔记把**前缀码**作为主线，因为后续 Kraft/Huffman 和熵界都针对前缀码。
- Huffman 的例子只给最优码长，不保证合并顺序唯一；不同合并顺序可能得到不同但等价的树。
- 定长压缩的“几乎无损”不是精确无损：$L<n\log|\Omega|$ 时一定有错，只是错误概率可以指数小。
- 典型集大小是 $2^{n(H\pm\varepsilon)}$，不要漏掉 $\varepsilon$。
- 侧信息结论是 $L_1>H(X\mid Y)$，不是 $H(X)$；Slepian–Wolf 还要同时满足三个下界。
- 转写里的 “compression/decompression/typical/side information/Slepian–Wolf” 等术语识别较乱，按上下文与手写稿校正。

## 分节

1. [无损压缩与变长码](sections/01-lossless-compression.md)
2. [Kraft 不等式与 Huffman 编码](sections/02-kraft-huffman.md)
3. [定长压缩与典型集](sections/03-fixed-length-typical.md)
4. [侧信息与 Slepian–Wolf 压缩](sections/04-side-information.md)

## 一页式总览

- 无损变长码：$H(X)\le E[L]<H(X)+1$。
- Kraft：前缀码存在 $\iff\sum_i2^{-l_i}\le1$。
- Huffman：每次合并两个最小概率，最优前缀码。
- 典型集：$|T_\varepsilon^{(n)}|\le2^{n(H+\varepsilon)}$，概率 $\to1$。
- 定长几乎无损：$L=n(H+\varepsilon)$，错误概率指数小。
- 侧信息：$L_1>H(X\mid Y)$。
- Slepian–Wolf：$L_1\ge H(X\mid Y)$，$L_2\ge H(Y\mid X)$，$L_1+L_2\ge H(X,Y)$。
