$$
\newcommand{\ve}[1]{\boldsymbol{\mathbf{#1}}}
\newcommand{\unit}[1]{\boldsymbol{\mathbf{\hat{#1}}}}
\newcommand{\cal}{\mathcal}
\newcommand{\scr}{\mathscr}
\newcommand{\r}{\mathrm}
\newcommand{\R}{\mathbb R}
\newcommand{\Z}{\mathbb Z}
\newcommand{\N}{\mathbb N}
\newcommand{\Q}{\mathbb Q}
\newcommand{\C}{\mathbb C}
\def \DD #1.#2.#3 {\dfrac{d^{#1} #2}{d #3^{#1}}}
\def \PP #1.#2.#3 {\dfrac{\partial^{#1} #2}{\partial #3^{#1}}}
\def \dd #1.#2 {\dfrac{d #1}{d #2}}
\def \pp #1.#2 {\dfrac{\partial #1}{\partial #2}} 
\newcommand{\transp}{^{\top}}
\DeclareMathOperator{\tr}{tr}
$$



# 布尔代数 
将 $ T $ 视作 $ 1 $ (非零), $ F $ 视作 $ 0 $. 则可将逻辑或运算符视作加法, 逻辑与运算符视作乘法.
$$
1 \lor 1 \Rightarrow 1 + 1 = 1,
$$

$$
1 \lor 0 \Rightarrow 1 + 0 = 1,
$$

$$
0 \lor 0 \Rightarrow 0 + 0 = 0.
$$

以及,
\[ 1 \land 1 \Rightarrow 1 \times 1 = 1 \,,\]

\[ 1 \land 0 \Rightarrow 1 \times 0 = 0 \,,\]

\[ 0 \land 0 \Rightarrow 0 \times 0 = 0 \,.\]

> 更准确地:
> $ a \land b = ab = \min(a, b) $,
> $ a \lor b = a + b - ab = \max(a, b) $,
> $ \neg a = 1 - a $.
> 在集合论中, 也有: $ A \cup B = A + B - A \cap B $.

# 数理逻辑
## 析取与合取
### 单位元/零元
- 合取 (与, $ \land $) 的零元为 $ F $
- 析取 (或, $ \lor $) 的零元为 $ T $
\[ \begin{array}{c}
    p \land F = F \\
    p \lor T = T 
\end{array} \,.\]

- 合取 ($ \land $) 的单位元为 $ T $
- 析取 ($ \lor $) 的单位元为 $ F $
\[ \begin{array}{c}
    p \land T = p \\
    p \lor F = p
\end{array}
\,.\]

## 异或
真值表

$ p $ | $ q $ | $ \oplus $
-|-|-
$ T $ | $ T $ | $ F $
$ T $ | $ F $ | $ T $
$ F $ | $ T $ | $ T $
$ F $ | $ F $ | $ F $
即: 真值相同得到假, 真值不同得到真.

性质:
- 与真异或翻转真值: $ p \oplus T = \neg p $
- 与假异或保持不变: $ p \oplus F = p $

## 德摩根律
\[ \neg (p \lor q) \equiv \neg p \land \neg q \,,\]

\[ \neg (p \land q) \equiv \neg p \lor \neg q \,.\]

推广:
\[ \neg \left( \bigwedge_{i=1}^{n} p_i \right) = \bigvee_{i=1}^{n} (\neg p_i) \,,\]

\[ \neg \left( \bigvee_{i=1}^{n} p_i \right) = \bigwedge_{i=1}^{n} (\neg p_i) \,.\]

## 实质蕴涵
句子 "若 $ p $, 则 $ q $" 可以表示为
\[ p \to q \,.\]

其中 $ p $ 称为前件, $ q $ 为后件. 真值表如下
$ A $ | $ B $ | $ A \to B $
-|-|-
$ F $ | $ F $ | $ T $
$ F $ | $ T $ | $ T $
$ T $ | $ F $ | $ F $
$ T $ | $ T $ | $ T $

只有在前件为真且后件为假的情况下, 该条件命题真值为假. 要理解实质蕴涵:
- $ p \to q $ 为真保证了: 当 $ p $ 为真的时候, $ q $ 也为真
- 若 $ p $ 为假, $ q $ 无论真假, 均不违背 $ p \to q $ 的含义 (即"保证")

> 例: 考满分 $ \to $ 得 A
> 若未考满分, 无论是否得 A, 都无法否定 "考满分 $ \to $ 得 A" 这个命题的真实性. 只有在考了满分且没得 A 时, 这个命题才能被否定.

所以 $ p \to q $ 的准确含义为: "要么 $ \neg p $, 要么 $ q $". 即
\[ p \to q \equiv \neg p \lor q \,.\]

"考满分 $ \to $ 得 A" 应该理解为: "要么没考满分, 要么得 A".

**与自然语言的区别**:
自然语言中的 "若 $ p $, 则 $ q $" 往往含有一种因果关系, 且人们倾向在 $ p $ 为真的情景下考虑 $ q $ 的情况. 对一个成绩不好的男孩说: "如果你是女孩(假), 那么你成绩很好(真/假)", 人们会理解成: "假如你真的是女孩('真'), 那么你成绩会很好('真')" . 可见自然语言描述受语义影响, 所以由假命题出发, 最后得到真命题似乎违背常理. 

而数学中的实质蕴含 $ p \to q $, 则是关注 $ p $, $ q $ 的真值, 以及它们之间的逻辑关系. $ p \to q $ 的真假, 完全由 $ p $ 和 $ q $ 的真值决定, 命题的自然语义则被抹去. 自然语言中, 前假后真的命题似乎有悖逻辑, 但数学上是可以接受的.

所以在数学中, "如果地球不在太阳系(假), 那么我就早睡早起(假)" 以及 "如果 3 是无理数(假), 则地球是圆的(真)" 都是真命题. 


# 附录
## 二元运算
### 封闭性
若对某个集合的成员进行一种运算, 生成的仍然是这个集合的成员, 则该集合被称为在这个运算下封闭. 即对于集合 $ S $ 和二元运算 $ \circ $, 若对 $ \forall a, b \in S $ 均有: $ a \circ b \in S $, 则称 $ S $ 对 $ \circ $ 封闭.

### 单位元
当单位元 (identity element, neutral element) 与其它元素结合时, 不会改变那些元素.
\[ a \circ i = a \quad (\text{右单位元}) \,,\]

\[ i \circ a = a \quad (\text{左单位元}) \,.\]

称 $ i $ 为 $ \circ $ 下的单位元, 若 $ i $ 即是二元运算 $ \circ $ 下的左单位元又是其右单位元.

### 零元 (吸收元)
零元 (zero element, absorbing element) 与任意元素结合, 得到零元.
\[ z \circ a = z \quad (左零元) \,,\]

\[ a \circ z = z \quad (右零元) \,.\]

> 例:
> - 实数乘法零元: $ 0 $
> - 矩阵乘法零元: 零矩阵

### 逆元
逆元与某元素结合得到单位元
\[ a \circ a^{-1} = i \,,\]

\[ a^{-1} \circ a = i \,.\]

> - 实数加法逆元: 相反数
> - 实数乘法逆元: 倒数
> - 矩阵加法逆元: 相反矩阵
> - 矩阵乘法逆元: 逆矩阵

## 运算律
### 分配律
称 $ \circ $ 对 $ * $ 满足左分配律, 若满足:
\[ a \circ (b * c) = a \circ b * a \circ c \,,\]

称 $ \circ $ 对 $ * $ 满足右分配律, 若满足:
\[ (b * c) \circ a = b \circ a * c \circ a \,.\]

> 注意左分配律, $ a $ 始终在 $ b $ 和 $ c $ 的左边, 右分配律同理.

称 $ \circ $ 对 $ * $ 满足分配律, 若其既满足左分配律和右分配律.

### 结合律
\[ (a * b) * c = a * (b * c) \,,\]

运算顺序不影响结果, 故省略括号, 写作 $ a * b * c $.

### 交换律
若 $ * $ 满足:
\[ a * b = b * a \,,\]

则称 $ * $ 满足交换律.

### 反交换律
称二元运算 $ * $ 满足反交换律.
\[ a * b = - (b * a) \,,\]

同理, 对于多元运算, $ *(x_1, x_2, \dots, x_n) $, 若
\[ *(x_1, x_2, \dots, x_n) = \operatorname{sgn} \sigma *\big( \sigma(x_1), \dots, \sigma (x_n) \big) \,,\]

则称 $ * $ 满足反交换律.

> 由于对换改变排列的奇偶性,
> $ *(x_1, \dots, x_i, \dots, x_j, \dots, x_n) = - *(x_1, \dots, x_j, \dots, x_i, \dots, x_n) $.
> 当 $ n = 2 $ 时, 即得到 $ x_1 * x_2 = x_2 * x_1 $.

### 吸收律
若一对二元运算 $ \circ $ 和 $ * $ 满足:
\[ a \circ (a * b) = a * (a \circ b) = a \,,\]

则称 $ \circ $ 和 $ * $ 服从吸收律, 这一对运算被称为对偶对.

> 逻辑与 ($ \land $) 和逻辑或 ($ \lor $) 服从吸收律
> \[ p \land (p \lor q) = p \,,\]
>
> \[ p \lor (p \land q) = p \,.\]