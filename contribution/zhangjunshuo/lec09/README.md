# Lec 09：环、理想与商环

阅读入口：[Markdown](lec09.md) · [LaTeX](lec09.tex) · [PDF](lec09.pdf)

本目录整理 2026 年 10 月 13 日 Lec09，依据两段课堂转写、手写原稿和课程教材整理。课堂主线是环的基本概念、理想与商环、环同态基本定理、极大理想/素理想、中国剩余定理，以及单位、分式域和特征。不同教材对“是否要求环含单位”的约定可能不同，正文在开头明确采用的约定。

课堂对不少标准结论只给了一句话或留作习题（[DS] §10.2 明确要求“叙述并证明环的第一、第二和第三同构定理”）。整理版补齐了这些部分并标注出处：零因子与消去律的等价、环的层级表、有限整环是域（第 1 节）、理想与子环的区别、第二/第三同构定理与 $M_n(F)$ 无平凡理想、求值同态 $R[x]/(x-c)\cong R$（第 2 节）、中国剩余定理的满射证明与正交幂等元（第 3 节）、$R[x]$ 单位的完整分层与素子环、做题检查清单（第 4 节）。

## 分节

1. [环的定义与典型例子](sections/01-rings-and-examples.md)
2. [理想与商环](sections/02-ideals-and-quotient-rings.md)
3. [极大理想、素理想与中国剩余定理](sections/03-maximal-prime-crt.md)
4. [单位、分式域与环的特征](sections/04-units-fractions-characteristic.md)

## 编译

修改分节 Markdown 后，先同步同名 TeX，再在本目录编译入口文件：

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-rings-and-examples.md sections/01-rings-and-examples.tex
xelatex lec09.tex
xelatex lec09.tex
```

编译产生的辅助文件不纳入整理目录。

## 参考资料

- [DF] Dummit--Foote, *Abstract Algebra*, 3rd ed.：§§7.1--7.5（环、多项式环、商环、特征与素子环）、§9.3（分式域）。
- [DS]《离散数学与结构》§§10.1--10.3（环和域、同态与理想、有限域）。该书没有分式域与素理想的一般讨论，这两部分以 [DF] 为准。
- 原始材料：本地归档（手写原稿与录音转写），不纳入课程仓库。

