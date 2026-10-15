# Lec 07：有限生成阿贝尔群、同构定理续与群作用

阅读入口：[Markdown](lec07.md) · [LaTeX](lec07.tex) · [PDF](lec07.pdf)

本目录整理 2026 年 9 月 29 日课堂内容，材料包括两份录音转写、手写原稿和参考教材。转写中的识别错误已按手写页与教材校正；有限生成阿贝尔群部分保留课堂的证明提纲，并补充标准结构定理表述。

## 分节

1. [有限生成阿贝尔群与直积](sections/01-fg-abelian-direct-products.md)
2. [商群的三个同构定理与中心化子](sections/02-quotient-refinements.md)
3. [同态、自同态、自同构与内自同构](sections/03-hom-end-aut-inn.md)
4. [群作用](sections/04-group-actions.md)
5. [轨道、稳定子与轨道--稳定子定理](sections/05-orbits-stabilizers.md)

## 编译

修改分节 Markdown 后，运行：

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-fg-abelian-direct-products.md sections/01-fg-abelian-direct-products.tex
```

对每个分节生成同名 TeX 后，在本目录运行三次 `xelatex lec07.tex`，得到入口 PDF。编译产生的辅助文件不纳入整理目录。

## 参考资料

- [DF] Dummit--Foote, *Abstract Algebra*, §§1.7, 2.2, 5.1--5.2。
- [DS]《离散数学与结构》，§§9.6, 14.1。
