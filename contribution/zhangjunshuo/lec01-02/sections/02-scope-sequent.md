# 子证明作用域与经典相继式

## 作用域

条件消去是

```text
m | A→B
n | A
  | B          →E m,n
```

可以开启额外假设：

```text
1 | R              PR
2 |   L            AS
3 |   R∧L          ∧I 1,2
4 | L→(R∧L)        →I 2-3
```

第 4 行不再依赖临时假设 $L$，但仍依赖第 1 行的 $R$。关闭子证明后，任何依赖其假设的行都不能在外层继续使用；这正是防止从矛盾假设任意推出结论的作用域条件。

## 相继式的语义

相继式写作 $\Gamma\Rightarrow\Delta$。这里 $\Gamma,\Delta$ 按有限多重集理解，结构规则通常默认可用。它在赋值 $v$ 下为真，当且仅当

$$
\bigl(v\models\gamma\text{ 对所有 }\gamma\in\Gamma\bigr)
\Longrightarrow
\bigl(v\models\delta\text{ 对某个 }\delta\in\Delta\bigr).
$$

## 八类联结词规则

下面只写主公式，未写出的上下文在前后两行保持不变：

- $\neg\Rightarrow$：把左侧的 $\neg\varphi$ 移到右侧的 $\varphi$；$\Rightarrow\neg$：把右侧的 $\neg\varphi$ 移到左侧的 $\varphi$。
- $\land\Rightarrow$：左侧的 $\varphi\land\psi$ 拆成两个左侧公式；$\Rightarrow\land$：右侧合取需要分别证明两个支。
- $\Rightarrow\lor$：右侧析取可展开为两个右侧公式；$\lor\Rightarrow$：左侧析取需要两个分支。
- $\Rightarrow\to$：证明右侧 $\varphi\to\psi$ 时，把 $\varphi$ 放到左侧、$\psi$ 放到右侧；$\to\Rightarrow$：左侧蕴含需要两个分支。

公理模式是 $\Gamma\Rightarrow\Delta$ 且 $\Gamma\cap\Delta\ne\varnothing$。无 cut 推导满足子公式性；做题时通常从目标相继式自下而上选择主公式。

本节的 System K 是手写笔记中的**经典相继式系统**。25–26 讲义后面另有模态逻辑 System K，并使用 $\Box,\Diamond$；不能把两者的规则混在一起。
