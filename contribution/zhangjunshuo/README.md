# Zhangjunshuo：图离散课程笔记

这里按课程讲次保存整理后的入口文件。每一讲的 `lecXX.md` 是主要阅读入口，`lecXX.tex` 用于排版，`lecXX.pdf` 是对应的编译结果；各目录下的 `sections/*.md` 是分节编辑来源，配套的 `sections/*.tex` 需与其同步。

本人选课较晚，Lec 01–02 没有可用的课堂记录，相关笔记主要依据作业、参考资料和已有推导整理，不能视为课堂逐字记录。

| 讲次 | 主题 | Markdown | TeX | PDF |
|---|---|---|---|---|
| Lec 01–02 | 命题逻辑与一阶逻辑入门 | [lec01-02.md](lec01-02/lec01-02.md) | [lec01-02.tex](lec01-02/lec01-02.tex) | [lec01-02.pdf](lec01-02/lec01-02.pdf) |
| Lec 03 | 量词、等号、Peano 算术与完备性 | [lec03.md](lec03/lec03.md) | [lec03.tex](lec03/lec03.tex) | [lec03.pdf](lec03/lec03.pdf) |
| Lec 04 | ZFC、算术化与 Gödel 不完备定理 | [lec04.md](lec04/lec04.md) | [lec04.tex](lec04/lec04.tex) | [lec04.pdf](lec04/lec04.pdf) |
| Lec 05 | 数论 | [lec05.md](lec05/lec05.md) | [lec05.tex](lec05/lec05.tex) | [lec05.pdf](lec05/lec05.pdf) |
| Lec 06 | 群、正规子群、群同态与同构定理（含 Oct 9 / Oct 14 分节） | [lec06.md](lec06/lec06.md) | [lec06.tex](lec06/lec06.tex) | [lec06.pdf](lec06/lec06.pdf) |
| Lec 07 | 有限生成阿贝尔群、同构定理续与群作用 | [lec07.md](lec07/lec07.md) | [lec07.tex](lec07/lec07.tex) | [lec07.pdf](lec07/lec07.pdf) |
| Lec 08 | 共轭、类方程、Burnside 引理与 Sylow 定理 | [lec08.md](lec08/lec08.md) | [lec08.tex](lec08/lec08.tex) | [lec08.pdf](lec08/lec08.pdf) |
| Lec 09 | 环、理想、商环与中国剩余定理 | [lec09.md](lec09/lec09.md) | [lec09.tex](lec09/lec09.tex) | [lec09.pdf](lec09/lec09.pdf) |
| Lec 10 | 唯一分解整环、主理想整环与欧几里得整环 | [lec10.md](lec10/lec10.md) | [lec10.tex](lec10/lec10.tex) | [lec10.pdf](lec10/lec10.pdf) |
| Lec 11 | 分裂域、有限域与有限域上的多项式因式分解 | [lec11.md](lec11/lec11.md) | [lec11.tex](lec11/lec11.tex) | [lec11.pdf](lec11/lec11.pdf) |
| Lec 12 | 组合计数：基本计数、组合恒等式、卡特兰数、球与桶、容斥与抽屉原理 | [lec12.md](lec12/lec12.md) | [lec12.tex](lec12/lec12.tex) | [lec12.pdf](lec12/lec12.pdf) |
| Lec 13 | 生成函数：OGF/EGF、Catalan、3×n 覆盖、幂和与 Bernoulli 数（附 OGF vs EGF 讲解稿） | [lec13.md](lec13/lec13.md) | [lec13.tex](lec13/lec13.tex) | [lec13.pdf](lec13/lec13.pdf) |
| Lec 14 | Burnside 引理与 Pólya 计数：群作用、循环指数、染色计数、无标号树 | [lec14.md](lec14/lec14.md) | [lec14.tex](lec14/lec14.tex) | [lec14.pdf](lec14/lec14.pdf) |

## 目录约定

- `lec01-02/`、`lec03/`、`lec04/`、`lec05/`、`lec06/`、`lec07/`、`lec08/`、`lec09/`、`lec10/`、`lec11/`、`lec12/`、`lec13/`、`lec14/` 分别对应课程讲次；Lec 01 与 Lec 02 因材料来源合并整理。
- Lec 06 统一收录 Oct 9 的群与正规子群、Oct 14 的群同态与同构定理；手写页首标为“Lec05”，但其内容是群论，现有 Lec 05 保留为数论。
- Lec 11 的手写稿页首写的是日期“10.20”而非“Lec11”；按讲次顺序归档为 Lec 11。
- 每个讲次目录的 `README.md` 提供章节说明和本目录内的编译提示。
- 修改内容时编辑对应的 `sections/*.md`；生成或更新同名 `.tex` 后，再通过讲次入口 TeX 编译 PDF。
- 本索引只链接仓库内文件，便于后续直接提交到课程仓库。
