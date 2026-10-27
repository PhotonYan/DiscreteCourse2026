# Lec 10：唯一分解整环、主理想整环与欧几里得整环

阅读入口：[Markdown](lec10.md) · [LaTeX](lec10.tex) · [PDF](lec10.pdf)

本目录整理 2026 年 10 月 15 日 Lec10，依据三段课堂转写、手写原稿和课程教材整理。

课堂的主线是"环里的元素怎么分解"：单位与相伴 $\to$ 素元与不可约元 $\to$ UFD 及其反例 $\to$ 因子链条件与素性条件 $\to$ ED $\Rightarrow$ PID $\Rightarrow$ UFD；后半段转向"用理想构造域"，以 $F[x]/(f)$ 与分式域两条路线引出域扩张和分裂域。

## 分节

1. [单位、整除与相伴](sections/01-units-divisibility-associates.md)
2. [素元、不可约元与唯一分解整环](sections/02-prime-irreducible-ufd.md)
3. [因子链条件、主理想整环与欧几里得整环](sections/03-ufd-conditions-pid-ed.md)
4. [用理想构造域：商环、域扩张与分裂域](sections/04-field-construction-extensions-splitting.md)

每个分节开头列出本节用到的记号；所有符号在首次使用处给出定义。

## 本讲的两个反例

| 环 | 范数 | 反例 |
|---|---|---|
| $\mathbb Z[\sqrt{-5}]$ | $N(a+b\sqrt{-5})=a^2+5b^2\ge0$ | $6=2\cdot3=(1+\sqrt{-5})(1-\sqrt{-5})$，四个因子都不可约 |
| $\mathbb Z[\sqrt{10}]$ | $N(a+b\sqrt{10})=a^2-10b^2$（可取负） | $6=2\cdot3=(2+\sqrt{10})(-2+\sqrt{10})$ |

两者的区别：$\mathbb Z[\sqrt{-5}]$ 的范数有正下界，可以"画圆"排除因子；$\mathbb Z[\sqrt{10}]$ 的单位群无限（Pell 方程），元素乘单位后可任意接近 $0$，必须改用 $|N|$。

## 编译

修改分节 Markdown 后，先同步同名 TeX，再在本目录编译入口文件：

```bash
python3 ../../../../专题整理/图离散-分节/tools/md_to_tex.py sections/01-units-divisibility-associates.md sections/01-units-divisibility-associates.tex
xelatex lec10.tex
xelatex lec10.tex
```

编译产生的辅助文件不纳入整理目录。

## 参考资料

- [DF] Dummit--Foote, *Abstract Algebra*, 3rd ed.：§8.1（欧几里得整环）、§8.2（主理想整环）、§8.3（唯一分解整环）、§9.3（分式域）、§13.1--13.2（域扩张与代数扩张）、§13.4（分裂域与代数闭包）、§14.3（有限域）。
- [DS]《离散数学与结构》§10.1（整环）、§10.2（理想与主理想；极大/素理想只在习题 10.2#7）、§10.3（特征与素域、定理 10.3.4、定理 10.3.7 有限域）。**该书没有 ED/PID/UFD 这条线，也没有域扩张与分裂域**（"欧几里得""范数""唯一分解""分裂域"全文检索均为 0 次）。
- 课程讲义 `25-26-lecture_notes.pdf` **第 7 章（环）与第 8 章（域）** 是本讲最贴合的材料：§7.3 给出 UFD 的两个等价条件（定理 7.5、7.6）——**这条等价刻画在 [DF] 里没有以定理形式出现**——以及欧式整区、主理想环、素元与不可约元；§8.1--8.3 给出域扩张、分裂域与有限域。注意该讲义是 **2025--2026 秋季**版本（PDF 创建于 2026-06），而本讲是 2026-10-15。
- 原始材料：本地归档（手写原稿与录音转写），不纳入课程仓库。