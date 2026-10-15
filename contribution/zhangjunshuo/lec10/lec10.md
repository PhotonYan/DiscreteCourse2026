# Lec 10：唯一分解整环、主理想整环与欧几里得整环

本讲把整数的唯一分解推广到一般整环，主线是：

1. 先厘清**单位、整除、相伴**，说明"唯一分解"为什么必须在相伴意义下说；
2. 定义**素元**与**不可约元**，指出素元必不可约、反之不然；
3. 写出 **UFD** 的定义，用 $\mathbb Z[\sqrt{-5}]$ 与 $\mathbb Z[\sqrt{10}]$ 说明整环未必是 UFD；
4. 把 UFD 拆成**因子链条件 $+$ 素性条件**两条可分别验证的条件，沿 **ED $\Rightarrow$ PID $\Rightarrow$ UFD** 下来说明常见环都满足；
5. 换成"用理想构造域"的方向：$F[x]/(f)$（$f$ 不可约）与分式域两条路线，然后是域扩张、特征与素子域、分裂域。

## 记号速查

- $R$：整环；$R^\times$：单位群；$a\mid b$：$a$ 整除 $b$；$a\approx b$：相伴（相差一个单位）。
- $(a)=\{ra:r\in R\}$：主理想；$(a)\subseteq(b)\iff b\mid a$（整除与包含方向相反）。
- 素元：$p\mid ab\Rightarrow p\mid a$ 或 $p\mid b$；不可约元：$p=ab\Rightarrow a$ 或 $b$ 是单位。
- UFD：唯一分解整环；PID：主理想整环；ED：欧几里得整环。
- $N$：范数。$\mathbb Z[\sqrt{-5}]$ 用 $N(a+b\sqrt{-5})=a^2+5b^2$；$\mathbb Z[\sqrt{10}]$ 用 $N(a+b\sqrt{10})=a^2-10b^2$（会取负值，需取绝对值）。
- $\mathbb Z[\sqrt d]=\{a+b\sqrt d:a,b\in\mathbb Z\}$；$F[x]$：域 $F$ 上的多项式环；$(f)$：$f$ 生成的主理想。
- $[E:F]$：扩域 $E/F$ 的次数；$\operatorname{Frac}(R)$：分式域；$\mathbb F_p=\mathbb Z/p\mathbb Z$。

## 勘误与提醒

课堂转写与手写稿里有几处需要写清前提或纠正方向，正文都已订正：

- **手写稿的环的层级链不能读成"ED 一定是域"。** 手写稿写的是
  $$\text{Commutative Ring}\to\text{Integral Domain}\to\text{UFD}\to\text{PID}\to\text{Euclidean Domain}\to\text{Field},$$
  并把它记作包含关系。正确的读法是**越往右条件越强**：域 $\Rightarrow$ ED $\Rightarrow$ PID $\Rightarrow$ UFD $\Rightarrow$ 整环。$\mathbb Z$ 是 ED 但不是域，所以"ED $\Rightarrow$ 域"是错的；一个 ED 是域当且仅当它的每个非零元都可逆。
- **"整环中互相整除 $\Rightarrow$ 相等"应改成"相伴"。** 在 $\mathbb Z$ 中 $2\mid(-2)$ 且 $(-2)\mid2$，但 $2\ne-2$，它们只差一个单位。
- **素元与不可约元在一般整环中不等价。** 课堂上说的"素元必不可约，反之不然"是对的；$\mathbb Z[\sqrt{-5}]$ 中的 $2$ 就是不可约但不素的例子。
- **$\mathbb Z[\sqrt{10}]$ 的范数会取负值，且单位群无限。** 因此不能照搬 $\mathbb Z[\sqrt{-5}]$ 的"画圆排除因子"，必须用 $|N|$ 与 Pell 方程的性质（详见第 2 节）。
- **$F[x]$ 是欧几里得整环要求 $F$ 是域**，否则带余除法不成立（例如 $\mathbb Z[x]$ 中无法用 $2x$ 除 $x$）。
- **分裂域的"唯一"是同构意义下的唯一**，不是集合相等；且分裂域不含多余元素，是"最小"的那个。

## 分节

1. [单位、整除与相伴](sections/01-units-divisibility-associates.md)
2. [素元、不可约元与唯一分解整环](sections/02-prime-irreducible-ufd.md)
3. [因子链条件、主理想整环与欧几里得整环](sections/03-ufd-conditions-pid-ed.md)
4. [用理想构造域：商环、域扩张与分裂域](sections/04-field-construction-extensions-splitting.md)