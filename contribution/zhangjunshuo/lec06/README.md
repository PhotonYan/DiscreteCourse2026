# Lec 06：群、子群、陪集、正规子群与群同态

阅读入口：[Markdown](lec06.md) · [LaTeX](lec06.tex) · [PDF](lec06.pdf)

本目录统一保存我们的 Lec06，正文结合笔记与教材按主题整理。

本版记号按 [DF] Dummit–Foote《Abstract Algebra》对齐：`D_{2n}`（[DS]《离散数学与结构》的 `D_n` 是同一个群）、`|g|`、`Z_n`、`|G/H|`；单位元记 `e`（[DF] 写作 `1`）。

## 章节

1. [群的公理与基本例子](sections/01-group-axioms.md)
2. [二面体群与自由群](sections/02-dihedral-free-groups.md)
3. [对称群](sections/03-permutations.md)
4. [子群与陪集](sections/04-subgroups-cosets.md)
5. [正规子群](sections/05-normal-subgroups.md)
6. [商集与商群](sections/06-quotient-groups.md)
7. [群同态：定义、核与像](sections/07-homomorphisms.md)
8. [第一同构定理](sections/08-first-isomorphism.md)
9. [对应定理](sections/09-isomorphism-theorems.md)

## 参考文献

- [DF] D. S. Dummit, R. M. Foote. *Abstract Algebra*, 3rd ed. John Wiley & Sons, 2004.
- [DS] 邓小铁、王畅. 《离散数学与结构》. 未定稿, 2023.

修改分节 Markdown 后，先用 `md_to_tex.py` 生成同名 TeX，再在本目录运行三次（首次编译生成目录，后续编译校准页码）：

```bash
xelatex -interaction=nonstopmode -halt-on-error lec06.tex
xelatex -interaction=nonstopmode -halt-on-error lec06.tex
xelatex -interaction=nonstopmode -halt-on-error lec06.tex
```
