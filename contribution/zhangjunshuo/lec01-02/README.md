# Lec 01–02：命题逻辑与一阶逻辑入门

阅读入口：[Markdown](lec01-02.md) · [LaTeX](lec01-02.tex) · [PDF](lec01-02.pdf)

这是 Lec 01–02 的合并整理版。本人选课较晚，这两节没有可用的课堂记录；本稿主要依据作业、参考教材和已有推导整理，不能当作逐字课堂笔记。

## 章节

1. [自然演绎与逆否式](sections/01-natural-deduction.md)
2. [子证明作用域与经典相继式](sections/02-scope-sequent.md)
3. [一阶逻辑语法、语义与量词](sections/03-first-order-basics.md)

`lec01-02.tex` 是 XeLaTeX 总入口，`sections/*.md` 与 `sections/*.tex` 成对保存，`lec01-02.pdf` 是本地编译结果。

## 重要记号

- `→I` 从临时假设推出蕴含或否定；经典 `RAA` 从临时假设 `¬φ` 导出矛盾后得到 `φ`。
- `∀I` 必须检查被量化变量没有在未解除假设中自由出现；`∀E` 必须检查代入不会捕获自由变量。
- 本稿的 System K 是经典相继式系统；25–26 讲义后面同名的模态 System K 引入 `□,◇`，不是同一个系统。
