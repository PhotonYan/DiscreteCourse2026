# 说明

这是我学习代数学时所写的笔记，其中包含了一些更“自然”的想法。

其内容（最终）应该会比课上讲的抽象代数内容更丰富一些，供参考。

由于大部分内容写的时候比较急，字比较丑，请见谅。😘

以下内容均为AI生成，我并未仔细检查。

## 阅读导航

可按下表选择一份笔记，也可在[知识点索引](#知识点索引)中按主题查找。页码均为 **PDF 文件从 1 开始的实际页序**（包含空白页），不是讲义页码。链接打开 GitHub 中对应的 PDF，打开后按标注页码定位。

## 按日期的文件索引

| 日期／文件 | PDF 页数 | 内容简介 |
| --- | --- | --- |
| [2026.9.7.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) | 6（内容 p. 1–5） | 群的定义与基本性质；二面体群、对称群、生成元与关系；群同构、子群、循环群、元素的阶及四元数群。 |
| [2026.9.10.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) | 7（内容 p. 1–6） | 陪集、指数与 Lagrange 定理；正规子群、商群、同态与核；子群乘积；第一同构定理及证明。 |
| [2026.9.17.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) | 8（内容 p. 1–7） | 第二至第四同构定理、商群泛性质；单群及有限单群分类概览；合成列与 Jordan–Hölder 定理及证明。 |
| [2026.9.21.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) | 4（内容 p. 1–3） | 可解群；置换符号与交错群；A_n（n≥5）单群性的证明；有限生成阿贝尔群分类定理的陈述。 |
| [2026.9.24.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) | 5（内容 p. 1–4） | 中国剩余定理与阿贝尔群分类的素数幂形式；直积；群作用、Cayley 定理、自同构群；半直积及例子。 |
| [2026.10.8.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) | 6（内容 p. 1–5） | 稳定子、轨道与共轭类；中心化子、中心、正规化子；轨道与陪集的对应、类方程、p-群中心；内外自同构、特征子群。 |
| [2026.10.15.pdf](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) | 5（内容 p. 1–4） | Sylow 三定理及证明；Sylow 子群的正规化子、正规子群与商群中的 Sylow 子群；pq 阶群分类、132 阶与 105 阶群例题；交换子与导子群。 |

## 知识点索引

仅索引上述七份笔记中实际出现的内容；“陈述”“概览”“练习”用于区分其展开程度。2026.10.15 笔记第 8 节已开始讨论交换子与导子群；幂零群目前仅见于章节标题，尚无展开。

主题导航：[群论基础与典型群](#群论基础与典型群) · [子群、陪集与正规子群](#子群陪集与正规子群) · [群同态、商群与同构定理](#群同态商群与同构定理) · [单群、合成列、可解群与阿贝尔群分类](#单群合成列可解群与阿贝尔群分类) · [直积、群作用与半直积](#直积群作用与半直积) · [Sylow 定理及应用](#sylow-定理及应用) · [交换子与导子群](#交换子与导子群)

### 群论基础与典型群

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 群、阿贝尔群、半群与幺半群；单位元和逆元的唯一性、消去律 | [2026.9.7.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 二面体群 D_{2n}：几何对称、生成元与关系 | [2026.9.7.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 生成元、字、关系与群的表示 | [2026.9.7.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 对称群 S_n、循环表示、不交循环分解；生成 S_n 的换位集合（练习） | [2026.9.7.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 群同构及例子：指数映射、单位根；六阶群分类的陈述 | [2026.9.7.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 循环群、有限与无限循环群；元素的阶；四元数群 Q_8 | [2026.9.7.pdf，p. 5](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| Lagrange 定理及证明；元素阶整除群阶、Euler 定理、素数阶群为循环群 | [2026.9.10.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 置换符号同态、奇偶性与交错群 A_n | [2026.9.21.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) |

### 子群、陪集与正规子群

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 子群定义与判别条件；生成子群 | [2026.9.7.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 子群格示例：Z/12Z 与 D_6 | [2026.9.7.pdf，p. 5](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 左右陪集、陪集相等或不交及证明；陪集分解、指数 | [2026.9.10.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 共轭元素、共轭子群；正规子群及左右陪集刻画；二面体群例子 | [2026.9.10.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 子群乘积 HK 的大小公式及证明 | [2026.9.10.pdf，p. 4–5](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| HK 未必为子群的 D_6 例子；HK=KH 时为子群；正规子群乘积 | [2026.9.10.pdf，p. 5–6](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 中心化子 C_G(S)、中心 Z(G)、正规化子 N_G(H)；正规性的正规化子刻画 | [2026.10.8.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| 特征子群定义 | [2026.10.8.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| 特征子群的性质：特征蕴含正规、唯一同阶子群、传递性；D_8 中的反例 | [2026.10.8.pdf，p. 5](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |

### 群同态、商群与同构定理

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 商群运算的良定义、单位元与逆元 | [2026.9.10.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 群同态定义与性质；自然投影；像为子群、核为正规子群及证明 | [2026.9.10.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 同态单射当且仅当核平凡及证明 | [2026.9.10.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 用生成元与关系构造同态；求所有 D_{2n}→C^× 的同态 | [2026.9.10.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 第一同构定理及证明 | [2026.9.10.pdf，p. 6](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.10.pdf) |
| 第二同构定理及证明；只需 H 正规化 K 的推广；证明商群同构的方法 | [2026.9.17.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| 第三同构定理及证明 | [2026.9.17.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| 第四（子群格／对应）同构定理（证明留作练习） | [2026.9.17.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| 商群泛性质：同态经 G/N 分解的条件与交换图；Z/nZ→C^× 的例子 | [2026.9.17.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |

### 单群、合成列、可解群与阿贝尔群分类

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 单群定义与例子；Hölder 纲领、有限单群分类及 Feit–Thompson 定理概览 | [2026.9.17.pdf，p. 3–4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| 合成列、合成因子；D_8 的两条合成列 | [2026.9.17.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| Jordan–Hölder 定理及证明：存在性、链的加细、因子的对应 | [2026.9.17.pdf，p. 4–7](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.17.pdf) |
| 可解群定义、合成因子刻画、正规子群与商群的可解性；上三角矩阵群例子 | [2026.9.21.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) |
| A_n（n≥5）为非阿贝尔单群的证明：3-循环生成、共轭、从非平凡正规子群取出 3-循环 | [2026.9.21.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) |
| A_3、A_4 的例子；六十阶单群同构于 A_5（仅陈述） | [2026.9.21.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) |
| 有限生成阿贝尔群分类：不变因子形式（陈述，未给完整证明） | [2026.9.21.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.21.pdf) |
| 中国剩余定理的互素情形及证明；有限生成阿贝尔群分类的素数幂形式 | [2026.9.24.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |

### 直积、群作用与半直积

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 直积定义 | [2026.9.7.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.7.pdf) |
| 直积的嵌入、投影、商群与泛性质；无限直积和直和的提及 | [2026.9.24.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 识别内直积的条件与证明 | [2026.9.24.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 左群作用定义与例子：S_n、D_{2n}、限制作用、左右平移 | [2026.9.24.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 共轭作用、右群作用；群作用与 G→Sym(X) 同态的等价性 | [2026.9.24.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 忠实作用、平凡作用；Cayley 定理及证明；Aut(G) | [2026.9.24.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 保持群结构的作用 G→Aut(X)；半直积定义、嵌入与投影 | [2026.9.24.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 识别内半直积的条件及证明；Z/4Z 的反例、二面体群的半直积表示 | [2026.9.24.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.9.24.pdf) |
| 稳定子与轨道；轨道相等或不交；稳定子的共轭关系 | [2026.10.8.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| 共轭类及例子：GL_n(C) 的 Jordan 形、S_n 的循环类型 | [2026.10.8.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| G-等变映射、传递作用；轨道—稳定子的陪集对应及证明 | [2026.10.8.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| 轨道分解为陪集空间；共轭类大小、类方程及证明 | [2026.10.8.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| p-群定义；非平凡有限 p-群中心非平凡及证明 | [2026.10.8.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| 内自同构群 Inn(G) 的定义与正规性证明；外自同构群 Out(G) | [2026.10.8.pdf，p. 3–4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |
| S_n 的自同构现象；用 PGL_2(F_5) 构造 S_6 外自同构的笔记 | [2026.10.8.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.8.pdf) |

### Sylow 定理及应用

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| p-群、Sylow p-子群、Syl_p(G) 与数量 n_p 的定义；Sylow 三定理的陈述 | [2026.10.15.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 第一 Sylow 定理的证明：按群阶归纳，对中心的 p-部分取商，或用类方程转向中心化子 | [2026.10.15.pdf，p. 1–2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 各阶 p^k 子群存在（0≤k≤r）的加强结论（旁注陈述，未给证明） | [2026.10.15.pdf，p. 1](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 第二 Sylow 定理的证明：p-子群作用于陪集集 G/P，寻找单点轨道；包含性与共轭性 | [2026.10.15.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| Sylow p-子群唯一当且仅当正规 | [2026.10.15.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| Sylow 子群 P 的正规化子：P 是 N_G(P) 中唯一的 Sylow p-子群；N_G(N_G(P))=N_G(P) 及证明 | [2026.10.15.pdf，p. 2](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 第三 Sylow 定理的证明：n_p=[G:N_G(P)]、整除条件与 n_p≡1 (mod p) | [2026.10.15.pdf，p. 2–3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| pq 阶群分类（p<q 为素数）：正规 Sylow q-子群与半直积；不同非平凡作用所得半直积的同构（练习） | [2026.10.15.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 不存在 132 阶单群：结合 Sylow 子群数量与元素计数的证明 | [2026.10.15.pdf，p. 3](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 正规子群与商群中的 Sylow 子群：H∩N 与 π(H) 的结论及证明 | [2026.10.15.pdf，p. 3–4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 105 阶群若有正规 Sylow 3-子群，则为循环群：共轭作用、中心及正规化子的应用 | [2026.10.15.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |

### 交换子与导子群

| 知识点／证明／例题 | 文件与页码 |
| --- | --- |
| 交换子 [x,y]=x⁻¹y⁻¹xy 的定义、与交换性的关系及共轭公式 | [2026.10.15.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |
| 交换子群／导子群 G′=[G,G] 的定义；由交换子生成的子群与单个交换子的区别；G′ 正规、G/G′ 阿贝尔 | [2026.10.15.pdf，p. 4](https://github.com/PhotonYan/DiscreteCourse2026/blob/main/contribution/zhengzhuo/algebra/2026.10.15.pdf) |

