[TOC]
# 数字逻辑 (Digital Fundamentals)

## 布尔代数 (Boolean algebra)

### 逻辑变量

正如常见的数学变量, 比如 $ x $ , 一般 $ x $ 可取整个实数域. 而逻辑变量只有两个取值 (真值), "真"或"假".  常常也把”真“和“假”分别记成 $ 1 $ 和 $0$. 

电路中, 常将高电压定为逻辑 $1$, 低电压定为逻辑 $0$, 这称为正逻辑. 

### 逻辑运算

布尔代数的基本运算如下 (本文档多采用红色记号):

- 与 (合取)

  常见记法有: $x \land y$	$x \operatorname{AND} y$	  $ x \cdot y $	  $\color{red} x y $ 

- 或 (析取)

  常见记法有: $x \lor y$	$x \operatorname{OR} y$	  $\color{red} x + y $

- 非 (否定)

  常见记法有: $ \neg x $	$\operatorname{NOT} x$	$!x$	$\color{red} \overline x$

逻辑变量常用大写字母表示, 如 $ A $, $ B $, $ X $, $ Y $.

与, 或, 非和日常生活中使用的逻辑 (对应"且", "或", "不" 三种说法) 是一致的. **当且仅当两个命题均为真时, "与"运算得到的才为真; 两个命题只要有一个为真, "或"运算得到就为真.** 所以: " '<font color = red>php 不是最好的语言</font>'且'<font color  = blue>C++是一种高级语言</font>' "是假命题, 因为 php 是最好的语言 :), 所以无论 C++ 是不是高级语言, 这个命题都为假.

> 当然这里需要说明, 经典的逻辑变量的真假性必须是确定的, 可判断的.  正如一个命题的真假必须是确定的. 上面的"最好"判断要求很模糊. 有人觉得最好 🙃 有人觉得不好, 这种模糊性在布尔代数中不被允许. 不过数学上也有专门的分支 (如模糊逻辑). 模糊逻辑采用真实度, 而非二元的"真"和"假"两个真值.

将真记为 $ 1 $, 假记为 $ 0 $, 可以用表格表示与或非的逻辑:

| $ A $ | $ B $ | $ A \cdot B $ | $ A + B $ |
| :---: | :---: | :-----------: | :-------: |
|   0   |   0   |       0       |     0     |
|   0   |   1   |       0       |     1     |
|   1   |   0   |       0       |     1     |
|   1   |   1   |       1       |     1     |

| $ A $ | $ \overline A $ |
| :---: | :-------------: |
|   0   |        1        |
|   1   |        0        |

这样列出所有真值及其对于运算结果的表格称为**真值表 (truth table).**

容易看出"与"和乘法很类似: 

- 假 ($ 0 $) 是与运算 (乘法) 的零元: $ X \cdot 0 = 0 $

- 真 ($ 1$ ) 是与运算的单位元: $ X \cdot 1 = 1 $


而"或"和加法很类似:

- 假 ($ 0 $) 是与运算 (乘法) 的单位元: $ X + 0 = X $

- 真 ($ 1$ ) 是与运算的单位元: $ X + 1 = 1 $

注意此处若是 $ 1 + 1 $ 结果仍为 $ 1 $, 应为变量取值只能为 $ 0 $ 或 $ 1 $.

> 使用一般的数学运算 ($+,\, \times,\, - $), 可以将布尔代数 ($ \land, \, \lor,\, \neg$) 定义为:
> $$
> x \land y = x \times y, \\
> x \lor y = x + y - (x \times y), \\
> \neg x = 1 - x.
> $$

常见的逻辑运算还有与非, 或非, 异或, 同或. 此处略.

### 运算律

1. 单位元
   $$
   A + 0 = A \qquad A \cdot 1 = A
   $$

2. 零元
   $$
   A + 1 = 1 \qquad A \cdot 0 = 0
   $$

3. 幂等律
   $$
   A + A = A \qquad A \cdot A = A
   $$

4. 互补律
   $$
   A + \overline A = 1 \qquad A \cdot \overline A = 0
   $$

5. 对合律
   $$
   \overline{\overline A} = A
   $$

6. 结合律
   $$
   A + (B + C) = (A + B) + C \\
   A (B C) = (A B) C
   $$

7. 交换律
   $$
   A + B = B + A \qquad A \cdot B = B \cdot A
   $$
   
8. 分配律
   $$
   A(B + C) = AB + AC \\
   A + BC = (A + B)(A + C)
   $$

9. 吸收律
   $$
   A + A \cdot B = A \qquad A \cdot (A + B) =  A \\
   A + \overline A B = A + B \\
   AB + \overline A C + BCD = AB + \overline A C
   $$

10. 德·摩根律
$$
\overline{A + B} = \overline A \cdot \overline B \\
   \overline{A \cdot B} = \overline A + \overline B
$$

   > 可推广至 $ n $ 变量:
   >
   > $$
   > \neg\left(\bigwedge_{i = 1}^n x_i\right) = \bigvee_{i = 1}^n (\neg x_i) \\
   > \neg\left(\bigvee_{i = 1}^n x_i\right) = \bigwedge_{i = 1}^n (\neg x_i)
   > $$

11. 常量取反
$$
\overline 0 = 1 \qquad \overline 1 = 0
$$

### 代入规则

任何一个含有变量 $ X $ 的等式, 将 $ X $ 替换成一个逻辑表达式 $ F $, 等式仍然成立.

> 如: $\overline{ X + Y} = \overline X \overline Y $,  将 $ X $ 替换为 $ X + Z $, $\overline{X + Y + Z} = \overline{X + Z} \overline Y = \overline X \overline Y \overline Z$, 该等式仍然成立, 这便是德摩根律的三变量形式.

### 对偶规则

将一个逻辑表达式 $ F $ 中所有的与或交换 (即变为互补运算), 常量 ($ 0 $ 和 $ 1 $) 互换, 变量不变, 得到的表达式称为原表达式的对偶式, 记作 $ F' $.

> 如果 $ F_1 = F_2 $, 则 $ F_1' = F_2'$.

### 反演规则

将一个逻辑表达式 $ F $ 中所有的与或交换 (即变为互补运算), 常量 ($ 0 $ 和 $ 1 $) 互换, 变量也变成反变量, 得到的表达式为原表达式的补, 即 $ \overline F $.

## 其它运算

### 异或 (Exclusive or, XOR)

异或和或类似, 但区别在于, 异或只有在两个输入不同的时候, 输出才是 $1$. 真值表如下:

| $A$  | $B$  | $A + B$ | $A \oplus B$ |
| :--: | :--: | :-----: | :----------: |
|  0   |  0   |    0    |      0       |
|  0   |  1   |    1    |      1       |
|  1   |  0   |    1    |      1       |
|  1   |  1   |    1    |      0       |

异或和或的唯一区别就在最后一行, 两个输入都是 $ 1 $ 时, 异或输出为 $ 0 $.

运用 <a href = "pos_and_sop">真值表和与或表达式的关系</a>, 容易用与和或构造出异或的等价表达式:
$$
A \oplus B = A \overline B + \overline A B
$$

### 同或 (Exclusive nor, XNOR)

同或即异或取反. 用符号 $\odot$ 表示. 所以有
$$
A \odot B = \overline{ A \oplus B} = AB + \overline A\ \overline B
$$


   ## 逻辑门 (Logic gates)

计算机, 或者说数字逻辑的核心内容便是抽象, 抽象使得我们不必关心底层细节. 下面这个这个电路实现了与运算: 只有在两个输入 $ A $, $ B $ 都是高电压 (1) 时, 输出 $ Y $ 才是高电压, 否则就是低电压 (0).

<figure>
  <center><img src=./pic/Cmos_and.svg />
  <figcaption>图引自维基百科</figcaption></center>
</figure>

实现与运算的电路还有很多, 不过我们现在不必关心, 而是将整个电路视作一个整体, 打包成一个元件, 用下面的符号表示, 称为"与门" (AND gate).

<img src=./pic/AND_ANSI.svg />

同理, 还有或门 (OR), 非门 (NOT), 与非门 (NAND), 或非门 (NOR), 异或门 (XOR), 同或 (XNOR) 等等逻辑门, 每一个类似的符号背后都是一堆电路. 

<img src = .\pic\and_gate.png width = 40% />

> 与门, 或门可以有任意数量的输入, 而异或和同或门只接受 2 个输入. $ A B C D$ 和 $ A + B + C + D $ 都是合理的, 但并没有定义 $ A \oplus B \oplus C $, 异或门和同或门只接受两输入, 只有 $(A \oplus B) \oplus C $ 或 $ A \oplus (B \oplus C)$ 才可以运算.

通过抽象出"逻辑门"我们可以忽略底层的细节, 从而能更方便地设计更复杂的电路, 实现更多样的功能. 数字电子技术的主要目的就是使用逻辑门为基本元件搭接各种功能电路.

## 真值表与布尔代数

### 	布尔表达式 (Boolean expression) 的简化

逻辑变量经与或非三种运算得到的式子就是布尔表达式 (也称逻辑函数). 布尔表达式中出现的所有变量的集合称为该表达式的定义域 (domain). 如: $ A + BC + \overline{AC} $ 的定义域就是 $ {A, B, C} $; $ B + \overline A X \overline B + \overline{A + B + C} $ 的定义域就是 $ {A, B, C, X} $. 

### 与或表达式和或与表达式 <a name = "pos_and_sop"></a>

与或表达式就是与项之和 (sum-of-product, SOP); 或与表达式就是和项之积 (product-of-sum, POS). 例如:
$$
AB + BC + ACD \qquad (\mathrm{SOP}) \\
A + \overline{B} \qquad (\mathrm{SOP}) \\
(A + B + C)(A + \overline B) \qquad (\mathrm{POS}) \\
(A + \overline D)C \qquad (\mathrm{POS})
$$
当与或表达式中每一与项都包含了定义域中的所有变量, 且变量只出现了一次, 则称这个表达式为标准与或表达式 (standard SOP form). 同理也有标准或与表达式 (standard POS form). 

有时候, 标准与或表达式中的与项 (如 $ A \overline B C $) 会被称作最小项. 同理标准或与表达式中的或项被称为最大项. 最小项有如下性质:

- 有且只有一种变量组合能使该与项为 $ 1 $, 其余变量组合均使该项为 $ 0 $

- 对于任意一种变量组合, 标准与或表达式中最多只能有 1 项为 $ 1 $, 不会出现多项为 $ 1 $ 的情况

> 对于 $ L = A B C + A \overline B C + A B \overline C $: $ (A, B, C) = (1, 1, 1) $ 时, 第一项为 $ 1 $, 其余项为 $ 0 $; $ (A, B, C) = (1, 1, 0) $ 时, 第三项为 $ 1 $, 其余项为 $ 0 $. 而当 $ (A, B, C) = (0, 1, 1) $ 时, 每一项都为 $ 0 $.

可以看出, 标准与或表达式有多少项, 就有多少种变量组合能使表达式为 $ 1 $. 这就是为什么真值表中为 $ 1 $ 的行能和标准与或表达式中的每一与项对应; 同理, 为 $ 0 $  的行能和标准或与表达式中的每一或项对应. 这就引出了与项和或项的二进制表达方式, 及其于真值表的关系.

以 $ L = \color{red}{A B C} + \color{green}{A \overline B C} + \color{blue}{A B \overline C} $ 为例, 其真值表如下:

|        $ A $        |        $ B $        |        $ C $        |        $ L $        |
| :-----------------: | :-----------------: | :-----------------: | :-----------------: |
|          0          |          0          |          0          |          0          |
|          0          |          0          |          1          |          0          |
|          0          |          1          |          0          |          0          |
|          0          |          1          |          1          |          0          |
|          1          |          0          |          0          |          0          |
| $ \color{green} 1 $ | $ \color{green} 0 $ | $ \color{green} 1 $ | $ \color{green} 1 $ |
|  $ \color{blue}1 $  |  $ \color{blue}1 $  |  $ \color{blue}0 $  |  $ \color{blue}1 $  |
|  $ \color{red} 1$   |  $ \color{red} 1$   |  $ \color{red} 1$   |  $ \color{red} 1$   |

比如 $ A B \overline C $, 使得该项为 $ 1 $ 的变量组合为 $ A = 1, B = 1, C = 0 $.
$$
A B \overline C = 1 \cdot 1 \cdot \overline 0 = 1
$$
正好对应了真值表中蓝色一行. 于是我们把 $ 1 1 0 $ 作为 $ A B \overline C $ 项的二进制表达方式, 同理 $ A B C $ 对应 $ 111 $, $A \overline B C $ 对应 $101$.

与项的二进制表达如下:

> *Digital Fundamentals, 11E (4.7 p. 218)*
>
> To determine the standard SOP expression represented by a truth table, list the binary values of the input variables for which the output is 1. **Convert each binary value to the corresponding product term by replacing each 1 with the corresponding variable and each 0 with the corresponding variable complement.** For example, the binary value 1010 is converted to a product term as follows:
> $$
> 1010 \longrightarrow A \overline B C \overline D
> $$
> If you substitute, you can see that the product term is $1$:
> $$
> A \overline B C \overline D = 1 \cdot \overline 0 \cdot 1 \cdot \overline 0 = 1 \cdot 1 \cdot 1 \cdot 1 = 1
> $$

或项的二进制表达如下:

> To determine the standard POS expression represented by a truth table, list the binary values for which the output is 0. **Convert each binary value to the corresponding sum term by replacing each 1 with the corresponding variable complement and each 0 with the corresponding variable.** For example, the binary value 1001 is converted to a sum term as follows:
> $$
> 1001 \longrightarrow \overline A + B + C + \overline D
> $$
> If you substitue, you can see that the sum term is $ 0 $:
> $$
> \overline A + B + C + \overline D = \overline 1 + 0 + 0 + \overline 1 = 0 + 0 + 0 + 0 = 0
> $$

## 加法器

加法器在计算机中极其重要, 曾经的计算机诞生的目的就是为了做算数. 而从某种角度上, 加法是计算机最基础的运算, 许多运算 (如乘法), 最终都被归结成加法. 而使用数字电路, 我们可以让电路实现这一功能. 

### 半加器 (half adder)

半加器用于两位相加. 观察两位相加可能出现的情况:
$$
0 + 0 = 0 \qquad 0 + 1 = 1 \qquad 1 + 1 = {\color{red}1}0
$$
可以看到 $1 + 1$ 是会产生进位的. 我们将进位 (carry bit) 和本位相加的结果分开, 用真值表表示:

| $A$  | $B$  | 进位 $C_{\mathrm{out}}$ | 和 $\Sigma$ |
| :--: | :--: | :---------------------: | :---------: |
|  0   |  0   |            0            |      0      |
|  0   |  1   |            0            |      1      |
|  1   |  0   |            0            |      1      |
|  1   |  1   |            1            |      0      |

可以看出, "和" 列和异或运算结果对应, "进位" 和与运算结果对应. 所以对于两位的运算, 可以用一个与门和一个异或门搭接.

<center>
    <img src="./pic/half_adder1.png" width=35%></img>
</center>

检验不同输出是否正确:

<center>
    <img src="./pic/half_adder2.png" width=80%></img>
</center>

可以看出, 上面的电路实现了一位对一位的加法. 将其封装成一个部件, 命名为半加器 (half adder).

<center>
    <img src="./pic/half_adder.png" width=40%></img>
</center>

