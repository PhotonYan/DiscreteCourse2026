# Lec 08：共轭、类方程与 Sylow 定理

阅读入口：[Markdown](lec08.md) · [LaTeX](lec08.tex) · [PDF](lec08.pdf)

本目录整理 2026 年 10 月 8 日 Lec08。内容依据两段课堂转写、手写原稿和 Dummit--Foote《Abstract Algebra》、 《离散数学与结构》核对。转写里的“正规化子/中心化子”、$11^2\cdot13^2$ 和 $S_4$ 类大小等容易混淆处，已按手写稿与教材修正；补充证明会明确标注为整理补全。

分节次序按课堂讲授次序排列：组合列 → Burnside 引理与 $S_n$ 共轭类 → 共轭作用与类方程 → Sylow I--III → 小阶群应用。

## 分节

1. [组合列、单群与有限群分解](sections/01-composition-series.md)
2. [Burnside 引理与对称群中的共轭类](sections/02-burnside-symmetric-groups.md)
3. [共轭作用与类方程](sections/03-conjugacy-class-equation.md)
4. [Sylow 定理 I：存在性](sections/04-sylow-existence.md)
5. [Sylow 定理 II：包含性与共轭性](sections/05-sylow-conjugacy.md)
6. [Sylow 定理 III：个数与正规性](sections/06-sylow-counting.md)
7. [Sylow 定理的应用：小阶群与 $pq$ 群](sections/07-applications-and-pq-groups.md)

## 编译

修改分节 Markdown 后，使用 `专题整理/图离散-分节/tools/md_to_tex.py` 生成同名 TeX，再在本目录编译入口文件：

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-composition-series.md sections/01-composition-series.tex
xelatex lec08.tex
xelatex lec08.tex
xelatex lec08.tex
```

编译产生的辅助文件不纳入整理目录。

## 参考资料

- [DF] Dummit--Foote, *Abstract Algebra*, 3rd ed.：§3.4（组合列与 Jordan--Hölder，含 $A_n$ 的单性）、§4.3（群作用与类方程）、§4.5（Sylow 定理，Theorem 18 与 Corollary 20）、§§5.1、5.5（$S_n$ 的共轭类与类方程）。
- [DS]《离散数学与结构》：§9.1--9.6（群、置换群、子群、Lagrange、同态与直积）与 §14.1--14.2（群作用与 Burnside 引理）提供背景与轨道计数的写法。该书正文与目录都没有 Sylow 定理和类方程，[DS] 只用于对齐群作用与计数的语言；Sylow 部分以课堂手写稿和 [DF] §4.5 为准。
- 原始材料：本地归档（手写原稿与录音转写），不纳入课程仓库。
