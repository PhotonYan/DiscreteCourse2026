# DanJoshua 课堂笔记索引

本目录按 `00`–`03` 顺序存放四份笔记。每份笔记都包含已编译的 `main.pdf` 与对应 LaTeX 源文件；源文件入口均为各子目录下的 `main.tex`。

| 顺序 | 目录 | 内容 | PDF | 源文件 |
|---|---|---|---|---|
| 00 | [`00-first-order-logic`](./00-first-order-logic/) | 一阶逻辑：代入、语义与完备性 | [`main.pdf`](./00-first-order-logic/main.pdf) | [`main.tex`](./00-first-order-logic/main.tex), [`sections/`](./00-first-order-logic/sections/) |
| 01 | [`01-godel-incompleteness`](./01-godel-incompleteness/) | Gödel 不完备定理：编码、对角线与 Gödel/Rosser | [`main.pdf`](./01-godel-incompleteness/main.pdf) | [`main.tex`](./01-godel-incompleteness/main.tex), [`sections/`](./01-godel-incompleteness/sections/) |
| 02 | [`02-number-theory`](./02-number-theory/) | 数论初步：整除、欧几里得算法、素数分解、同余、Euler 定理、CRT、RSA | [`main.pdf`](./02-number-theory/main.pdf) | [`main.tex`](./02-number-theory/main.tex), [`sections/`](./02-number-theory/sections/) |
| 03 | [`03-stern-brocot`](./03-stern-brocot/) | Stern–Brocot 树：构造、矩阵形式、性质、连分数、Calkin–Wilf、Farey 序列 | [`main.pdf`](./03-stern-brocot/main.pdf) | [`main.tex`](./03-stern-brocot/main.tex), [`sections/`](./03-stern-brocot/sections/) |

## 编译说明

四份笔记都使用 XeLaTeX 与 `loom.cls`。在对应子目录中运行：

```bash
xelatex main.tex
xelatex main.tex
```

或：

```bash
latexmk -xelatex main.tex
```

说明：

- `03-stern-brocot` 依赖同目录下的 `ford-circles.pdf`；`ford-circles-nolabel.svg` 为该图的源文件，便于后续修改。
- 已提交的 `main.pdf` 是由对应 `main.tex` 编译得到的产物；如需复现，请保留 `loom.cls`、`sections/` 与图片资产在同目录相对位置。
