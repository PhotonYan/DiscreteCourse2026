# 一阶逻辑的语法、语义与量词

## 语法与代入

项由变量、常元和函数符号归纳生成；公式由谓词原子式、等式原子式、联结词和量词归纳生成。没有自由变量的公式称为句子；没有变量的项称为闭项。

代入 $\varphi[t/x]$ 只替换 $x$ 的自由出现。若遇到 $Qx$，该辖域内的 $x$ 不再替换；若遇到 $Qy$ 且 $y\ne x$，还必须检查 $t$ 中的自由变量不会被新量词捕获。必要时先对约束变量作 $\alpha$-改名。

## 结构与满足

结构 $\mathcal M$ 给出非空论域 $\Omega$，并解释每个常元、函数符号和关系符号。变量赋值 $s$ 把变量送入论域；项值与公式真值按语法递归定义。

记 $\mathcal M,s\models\varphi$ 为带赋值满足，$\mathcal M\models\varphi$ 为句子满足，$\models\varphi$ 为所有结构中有效，$\Gamma\models\varphi$ 为语义蕴涵。等号按实际相等解释：

$$
\mathcal M,s\models t_1=t_2
\quad\Longleftrightarrow\quad
\llbracket t_1\rrbracket_{\mathcal M,s}=\llbracket t_2\rrbracket_{\mathcal M,s}.
$$

## 量词规则

存在量词可取为缩写 $\exists x\varphi:=\neg\forall x\neg\varphi$。核心规则是

$$
\frac{\Gamma\vdash\varphi}{\Gamma\vdash\forall x\varphi}\ (\forall I),
\qquad
\frac{\Gamma\vdash\forall x\varphi}{\Gamma\vdash\varphi[t/x]}\ (\forall E).
$$

- $\forall I$ 要求 $x$ 不在任何未解除假设中自由出现；
- $\forall E$ 要求 $t$ 对 $x$ 可自由代入；
- 在非空论域中，$\forall x\varphi(x)\vdash\exists x\varphi(x)$；
- 从 $\varphi(t)$ 可推出 $\exists x\varphi(x)$。

例如 $P(x)\vdash\forall x\exists yP(y)$ 是合法的，但不能直接对开放假设中的 $x$ 使用 $\forall I$。合法路线是先得出与 $x$ 无关的 $\exists yP(y)$，再用新的变量 $z$ 做 $\forall I$，最后对绑定变量作 $\alpha$-改名。相反，从开放假设 $P(x)$ 直接得到 $\forall xP(x)$ 是无效的。
