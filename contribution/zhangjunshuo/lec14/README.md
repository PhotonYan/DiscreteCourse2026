# Lec 14：Burnside 引理与 Pólya 计数

阅读入口：[Markdown](lec14.md) · [LaTeX](lec14.tex) · [PDF](lec14.pdf)

本目录整理 2026 年 10 月 29 日 Lec14，依据三页手写稿、可用的第二段课堂转写，并以课程讲义 §9.10–9.12、教材 [DS] 第 14 章补全证明细节。

**来源说明。** 第一段转写文件只有一句“。”，实际内容以第二段转写 + 手写稿为准；手写稿第 1 页的 EGF 回顾（带标号二叉树、排列/轮换）转写中缺失，按手写稿与第 13 讲补全。整理版对手写稿与转写的不一致处给出勘误（见 `lec14.md` 与各节末尾）。

课堂主线：**Burnside 引理**（群作用、轨道--稳定子、双计数证明、$GL_2$ 共轭类例子）$\to$ **循环指数**（$C_n,D_n$ 的循环指数、轮换型）$\to$ **Pólya 计数**（颜色权重代入、四珠染色、一般项链公式、特殊颜色/奇偶筛选）$\to$ **无标号有根树**（$S_3$ 循环指数方程、前几项、与带标号树对照）。

## 分节

1. [从 EGF 到树与排列：本讲的前置例子](sections/01-egf-recap.md)
2. [群作用、轨道与 Burnside 引理](sections/02-group-actions-burnside.md)
3. [循环指数与 Pólya 计数](sections/03-cycle-index-polya.md)
4. [应用：无标号有根树与 Pólya 方程](sections/04-unlabelled-trees.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的几个"必须写清"的点

- **Burnside 公式**：$|S/G|=\frac1{|G|}\sum_{g\in G}|\operatorname{Fix}(g)|$；$\operatorname{Fix}(g)$ 必须对整个 $S$ 数。
- **循环指数**：$Z_{C_n}=\frac1n\sum_{d\mid n}\varphi(d)t_d^{n/d}$；$Z_{D_n}$ 的翻转项分 $n$ 奇偶。
- **Pólya 代入**：$t_i=\sum_j w_j^i$；所有权重取 $1$ 时 $t_i=C$。
- **无标号树**：$R(x)=1+\frac{x}{6}(R(x)^3+3R(x)R(x^2)+2R(x^3))$，非空计数 $1,1,2,4,8,17,\dots$。

## 编译

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-egf-recap.md sections/01-egf-recap.tex
xelatex lec14.tex
xelatex lec14.tex
xelatex lec14.tex
```

（其余分节同理；`sections/*.tex` 要与 `sections/*.md` 同步。）

## 参考资料

- [DS]《离散数学与结构》**第 14 章 Pólya 方法**：§14.1 群作用和计数原理、§14.2 Burnside 引理、§14.3 Pólya 定理（含带权 Pólya）。
- 课程讲义 **§9.10 Burnside's Lemma**、**§9.11 Polya Counting**、**§9.12 共轭类计数**：Burnside 证明、循环染色公式、轮换指数、$GL_2$ 共轭类与一卤代烷/无标号树例子。
- 原始材料：本地归档（手写原稿 PDF、第二段转写）；第一段转写不可用。

## 与前后讲的关系

- 第 13 讲给出 EGF、二项卷积、$\exp$ 集合构造；本讲用 Burnside/Pólya 处理“同构算一种”的无标号计数，并用 $S_3$ 循环指数得到无标号树的函数方程。
- 第 8 讲的群作用、轨道--稳定子、Burnside 引理在本讲被系统化为循环指数；第 12 讲的染色/计数模型在本讲获得“对称去重”的工具。
