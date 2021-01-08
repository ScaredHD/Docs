<center><font size=7>电工学</font></center>
[TOC]

$ 
\newcommand{\ve}[1]{\boldsymbol{\mathbf{#1}}}
\newcommand{\unit}[1]{\boldsymbol{\mathbf{\hat{#1}}}}
\newcommand{\r}{\mathrm}
\newcommand{\cal}{\mathcal}
\newcommand{\scr}{\mathscr}
\newcommand{\E}{\mathrm e}
\renewcommand{\I}{\mathrm i}
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
\let\Im\Relax
\let\Re\Relax
\DeclareMathOperator{\Im}{Im}
\DeclareMathOperator{\Re}{Re}
$

# 电路基本概念
## 电流, 电压
电流表示为单位时间通过导体或元件任意横截面的电荷量, 数学上表示为电荷量对时间的导数: \[ i = \dfrac{dq}{dt} .\] 所以: \[ q(t) = \int_{t_0}^t i(t) \,dt + q(t_0) .\]
### 电流的参考方向 (Reference direction)
为分析和计算方便, 常假定一个方向为电流的方向, 称为电流的参考方向. 若实际电流方向与参考方向一致, 则电流值为正; 实际方向与参考方向相反, 则电流值为负.

电流的参考方向可以用双下标表示法: $ i_{ab} \ (\text{电流从 } a \text{ 流向 } b) $, 或直接用箭头表示.

### 电压的参考极性 (Reference polarities)
如果电压的实际极性和参考极性一致, 则电压值为正; 否则为负.

电压也可以用双下标表示: $ v_{ab} \ (a \text{ 电势高于 } b) $, 亦可用箭头表示. 还可以直接标注 $ + $, $ - $.

$ A $, $ B $ 间的电压 $ V_{AB} $ 定义为两点间的电势差, 即
\[ V_{AB} = V_A - V_B .\]

所以:
\[ V_{AB} = V_{AC} + V_{CB} = V_{CB} - V_{CA} .\]

> 若无特殊说明, 皆是参考方向, 而不是绝对方向.

## 电功率
### 关联参考方向
若电流的参考方向与电压降低方向相同 (电流的参考方向是从电压的正极流入), 则称这种参考方向为**关联参考方向** (passive sign convention). 反之, 则称为非关联参考方向 (active sign convention).

<center><img src="./pic/sign_convention.svg" width=50% /></center>

### 电功率
功率是测量能量转换速率的量, 表示做功的快慢. 定义为: \[ p = \dfrac{dW}{dt} .\]  
关联参考方向下, 功率计算公式: \[ p = v i .\] 若为非关联参考方向, 则要带上负号, \[ p = - v i .\] 借助欧姆定律(1.6.), 功率可以表式为: \[ p = \dfrac{v^2}{R} = i^2 R .\]

> 可以看出, 由于电阻不可能为负 (见欧姆定律), $ v^2 / R $ 和 $ i^2 R $ 只可能为正值. 但功率显然式可以为负. 问题处在参考方向的关联与否上, 若是非关联参考方向, 应添加负号: $ p = - i^2 R $.

对于某一系统, 若功率为正, 表示系统内部吸收电能; 功率为负表示放出能量(电能传输到电路中其他部分).

<center><img src="./pic/sign_of_power.svg" width=50% /></center>

## 独立源
### 理想电压源
理想电压源输出电压不受其他元件的影响, 一直保持不变, 这个电压完全独立于流过它的电流.


## 受控源
若电源的输出电流或电压是电路中其他部分的电压或电流的函数, 我们称这类电源为受控源 (dependent source). 当控制的电压或电流为 $ 0 $ 时, 受控的电压或电流也将为 $ 0 $.

受控源可分为:
  - 电压控制电压源, voltage-controlled voltage source, 简称 VCVS
  - 电压控制电流源, voltage-controlled current source, 简称 VCCS
  - 电流控制电流源, current-controlled current source, 简称 CCCS
  - 电流控制电压源, current-controlled voltage source, 简称 CCVS
</br>
<center><img src="./pic/dependent_source.svg" width=60%></center>

> 注意各系数的量纲, $ \mu $ 和 $ \beta $ 无量纲. 而 $ v_2 = \gamma i_1 $, 即 $ \gamma = v_2 / i_1 $, 故 $ \gamma $ 具有 $ \mathrm{V/A} $ (电阻) 的量纲; $ g = i_2 / v_1 $, 具有 $ \mathrm{A / V} $ (电导) 的量纲.

## 端口

## 等电位点原理
若电路中两点电位 (电势) 相等, 则称这两点为等电位点. **等电位点之间连接任意阻值的电阻, 都不会改变其他支路的变量.**

换句话说, 可以任意改变等电位点之间的电路, 而保证电路其他部分不发生改变. 可以直接将等电位点之间断开, 或短路, 或改变阻值, 电路其他支路中的电流, 电压不会发生改变.

**注意 1: 改变后的电路一定要是可解的**

> 如图, (a) 为原电路, (c) 和 (d) 的添加方式都是不影响原电路的. (b) 添加后, 由于导线理想化, 电路不再可解 (有唯一解), 故不可以如图直接添加导线.  
> <center><img src="./pic/solvable.svg" width=50% /></center>
> 更一般地, 在任意两点间并联两条理想导线, 由于电阻为零, 分流关系不确定, 电路没有唯一解.

**注意 2: 只能在等电位点间添加电阻支路, 而不能去掉原有支路**


# 电路分析
## 欧姆定律
关联参考方向下的欧姆定律: \[ v = i R .\] 非关联参考方向下只需添加符号即可.

> 电阻只有非负值的说法

### 电导
定义电导为电阻的导数: \[ G = \dfrac{1}{R} = \dfrac{i}{v} .\] 单位为西门子 ($ \mathrm{S} $).

电导形式的欧姆定律: \[ i = v G .\]



## 基尔霍夫定律
### 基尔霍夫电流定律 (KCL)
流向节点的电流代数和为零. 即: $ \displaystyle \sum_{k = 1}^n i_k = 0 $.

<center><img src="./pic/kcl.svg" width=20% /></center>

如图, $ i_1 + i_2 + i_3 + i_4 + i_5 = 0 $.

> 注意: 应确定电流参考方向, 也就是说 $ i_k $ 可能是正值也可能是负值. 本文档规定, 流入节点为正, 流出节点为负.

也可表达为, 流入电流总和等于流出电流总和. 
\[ i_{\r{in}} = i_{\r{out}} .\]

> 例: <center><img src="./pic/kcl_example.svg" width=20% /></center>
> 按照流入为正, 流出为负的规定: 
> \[ 2 - 4 - i - 6 = 0 \]
>
> 解得: $ i = - 8 $. 因此此处实际是流入.


### 广义节点的 KCL
将包含多个节点的**闭合区域**定义为广义节点 (super node). 对于广义节点, KCL 仍然适用, 如图:
<center><img src="./pic/super_node.svg" width=35% /></center>

### 基尔霍夫电压定律 (KVL)
沿着任意闭合回路的电压的代数和为零. 即: $\displaystyle \sum_{k = 1}^n v_k = 0 $. 

上面的 $ v_k $ 也是有参考方向的, 符号一般按下面几种等价的方式确定:
- 沿着绕行方向的电压取正号, 逆着绕行方向的电压取负号
- 沿着绕行方向, 电压降低取正, 电压升高取负
- 先遇到元件电压正极取正, 先遇到负极取负

> 例: 电压和电阻的大小已在图中标出, 电流参考方向为外侧的箭头方向, 选择回路的绕行方向为内部的绿色箭头 (顺时针).  
> <center><img src="./pic/kvl_example.svg" width=40% /></center>
> 判断符号:
> 
> - $ v_1 $ 方向向下, 绕行方向向上, 逆绕行方向取负, 得到 $ -v_1 $
> - $ R_1 $ 为关联方向, $ v_{R_1} = +iR_1 $; 沿绕行方向电压降低, 取正号, $ +(+iR_1) $, 得到 $ iR_1 $
> - 绕行回路至 $ v_2 $ 时, 先遇到其电压正极, 符号取正, 得到 $ v_2 $
> - $ R_2 $ 为非关联方向, $ v_{R_2} = -iR_2 $, $ R_2 $ 电压方向和绕行方向相反, 取负号, $ -(-iR_2) $, 得到 $ iR_2 $
>
> 列 KVL 方程:
> \[ -v_1 + iR_1 + v_2 + iR_2 = 0 .\]

对于未知电压极性的元件, 选取关联或非关联方向不会影响最终符号.

<center><img src="./pic/kvl_sign.svg" /></center>

a) 的电压 $ +(+iR) $, 
b) 的电压 $ -(-iR) $, 
c) 的电压 $ +(-iR) $,
d) 的电压 $ -(+iR) $.

a) b) 为一组, c) d) 为一组, 每一组中只有元件电压极性发生了改变, 但这个改变导致欧姆定律中符号和绕行符号的同时改变, 变号效果抵消.

所以如果元件极性未知, 无论如何选取极性, 最终结果都是正确的. 一般为了方便, 直接假定其为关联方向, 因此可以直接通过绕行方向和电流方向 (因电流方向即是电压降低方向) 判断最终符号 (同向取正, 异向取负).

> 另一种理解方式: 回路压降 (压升视为负压降) 总和为 $ 0 $, 或回路压降总和 $ = $ 压升总和.
> <center><img src="./pic/KVL_exp2.svg" width=50% /></center>
> 如图, 电流的实际流向为逆时针, 按逆时针回路看, 电源处压降为 $ -V_{\r{DD}} $; $ R_1 $ 处参考方向的压降计算得到 $ -IR_1 $, 即向下压降为 $ -IR_1 $, 则向上压降为 $ IR_1 $; $ R_2 $ 压降 $ -(-IR_2) = IR_2 $; $ R_3 $ 压降 $ IR_3 $. 再次印证, KVL 方程的书写与电阻电压极性无关. 
>
> 因此, 回路压降总和为 $ 0 $: $ -V_{\r{DD}} + IR_1 + IR_2 + IR_3 = 0 $.
>
> 同时, 如果要求 $ R_2 $ 两端电压, 可以用 $ R_2 $ 两端压降 $ = $ 回路其他部分压升来计算. 此时取顺时针的绕行方向, $ R_1 $ 压升为其压降的相反数 $ -(-IR_1) = IR_1 $, 从正极到负极电压压升 $ -V_{\r{DD}} $; $ R_3 $ 压升 $ IR_3 $.
>  
> 压降 = 压升, 所以有 $ V_{R_2} = IR_1 - V_{\r{DD}} + IR_3 $.

### 广义回路/虚回路(super loop)
KVL 可以推广到任意假象回路, 即使无支路存在, 如:
<center><img src="./pic/super_loop.svg" width=30% /></center>

对于回路 $ abca $, $ ac $ 之间并无支路, 但仍可使用 KVL:
\[ v_1 - v_2 + v_{ca} = 0 .\]

### 独立方程
设节点数为 $ n $, 支路数为 $ b $, 则最多可列 $ n - 1 $ 个独立的 KCL 方程和 $ b - n + 1 $ 个独立的 KVL 方程.

此外, 还有**网孔数 $ = $ 独立 KVL 方程数**.

## 等效电阻与等效变换
结构、元件参数不相同的两部分电路 (网络) $ N_1 $ 和 $ N_2 $ 若具有**相同的伏安特性** $ v = f(i) $, 则用任意一个替换另一个也不会导致其他部分电流、电压改变, 因此称这两个电路网络是等效的.

### 电阻串并联
略
### Y-△ 变换
用 $ (a, b, c) $ 作为三角形三边上的电阻下标, 用 $ (1, 2, 3) $ 作为三角形内部电阻的下标, $ (R_a, R_b, R_c) $ 分别与 $ (R_1, R_2, R_3) $ 一一对应, 几何上也存在如图相对的关系.

<center><img src="./pic/delta-Y.svg" width=30% /></center>

则两种颜色的电阻可以等效, 大小满足:

\[ R_\Delta = \dfrac{\sum R_{\r{Y1}}' R_{\r{Y2}}' }{R_{\r{Y}}} ,\]

\[ R_{Y} = \dfrac{ R_{\r{\Delta1}}' R_{\r{\Delta2}}' }{\sum R_{\Delta}} .\]

上标撇号表示邻边.

特殊情况, $ R_a = R_b = R_c $ 或 $ R_1 = R_2 = R_3 $ 时:
\[ R_\Delta = 3 R_Y .\]

### 加压求流/加流求压
在端口处外加测试电压 $ V_{\r t} $, 求端口电流 $ I_{\r t} $, 等效电阻为 $ R_{\r eq} = \dfrac{V_{\r t}}{I_{\r t}} $.

也可以外加测试电流, 求测试电压.

> 加压求流/加流求压的方法适用于纯电阻电路和含受控源的电路. 而串并联, $ Y $-$ \Delta $ 变换仅适用于纯电阻电路.

## 电源变换
### 戴维宁定理
含源二端网络, 可以等效为一个理想电压源和等效电阻串联的模型. 其中, **等效电压源大小等于开路电压.** 等效电阻可由两种方法确定:
- 断路短路法: 将输出端断开, 得开路电压 $ V_{\r{oc}} $; 输出端短接, 得短路电流 $ I_{\r{sc}} $. 等效电阻 $ R_{\r{eq}} = V_{\r{oc}} / I_{\r{sc}} $
- 将**独立电源**置零 (电压源短路, 电流源开路), 然后运用求端口等效电阻的方法:
  - 根据等效变换直接求等效电阻 (无受控源情况)
  - 外加电压 $ V_{\r t} $ 求电流 $ I_{\r t} $, $ R_{\r{eq}} = V_{\r t} / I_{\r t} $; 或外加电流求电压 (有无受控源都可用)
### 诺顿定理
含源二端网络, 可以等效为一个理想电流源和等效电阻并联的模型. 其中, **等效电流源大小等于短路电流.** 
等效电阻确定方法同上.

综上, 戴维宁和诺顿定理的等效电源: $ V = V_{\r{oc}} $, $ I = I_{\r{sc}} $, 等效电阻 $ R_{\r{eq}} = \dfrac{V_{\r{oc}}}{I_{\r{sc}}} = \dfrac{V_{\r t}}{I_{\r t}} $.

## 最大功率传输定理
当且仅当负载电阻等于含源二段网络的等效电阻时, 负载取得最大功率. 此电源为电源提供功率的一半:
\[ P_{L\r{max}} = \dfrac{V_{\r{oc}}}{4 R_{\r{eq}}} \]

<center><img src="./pic/max_power.svg" width=50% /></center>

在图中取得最值的条件即为: $ R_{\r{eq}} = R_L $.

## 叠加原理
**由电阻, 线性受控受控源和独立源组成的系统称为线性系统.**

一个含多个独立源的双边线性电路的任何支路的响应（电压或电流）, 等于每个独立源单独作用时的响应的代数和, 此时所有其他独立源被替换成他们各自的阻抗.

在由 $ n $ 个独立源存在的线性电路中, 当只有第 $ i $ 个**独立源单独作用**, 其它独立源置零, 记此时得到的响应为 $ k_i $. 则所有独立源同时作用的响应:
\[ k = \sum_{i = 1}^{n} k_i .\]

> 注意: 受控源不单独作用, 运用叠加原理时, 将其视作元件, 不会单独隔离开看.

> 功率是电压或电流的二次函数, 不可叠加.

## 齐性定理
**含源线性网络若只含一个激励(独立源), 可以证明其响应与激励成正比, 且比例系数不依赖于该激励.**

如单独立电压源线性网络, 其激励 (电压) 和响应 (电流) 成正比 $ i = kv $.
当电压为 $ v_0 $ 时, 响应电流为 $ i_0 $. 则可推出比例系数: $ k = i_0 / v_0 $.
当电压为 $ v_1 $ 时, 响应电流 $ i_1 = k v_1 = \dfrac{i_0}{v_0} v_1 $.

结合叠加原理, 若有多个激励 ($ e_1, \dots, e_n $), 则各自的响应 ($ r_1, \dots, r_n $) 与各个激励成正比; 且分响应之和等于总响应:
\[ r = r_1 + \cdots + r_n = k_1 e_1 + \cdots + k_n e_n .\]

# 瞬态分析
## 元件关系式
电容及其参数满足关系式: \[ i_C = C \dfrac{d v}{dt} .\]

电感及其参数满足关系是: \[ v_L = L \dfrac{d i}{d t} .\]

## 换路定则
由于电容元件的电压和电感元件的电流不能突变, 因此换路前后瞬间, 电容电压不变, 电感电流不变. 用表达式表示:
\[ v_C(0^-) = v_C(0^+) \qquad i_L(0^-) = v_L(0^+) \]

旧稳态(第一稳态): $ f(0^-) $
初始值: $ f(0^+) $
新稳态(第二稳态): $ f(\infty) $

### 第一稳态的计算方法
1. 画出**换路前**的电路图, 达到稳态后, **电容视作断路**, **电感视作短路**.
2. 求解电路中的其他变量

### 初始值的计算方法
1. 由换路定则, 得到 $ t = 0^+ $ 时, 电容的电压 $ v_C(0^+) $ 和电感的电流 $ i_L(0^+) $.
2. 画出**换路后**的电路图, **电容视作 $ v_C(0^+) $ 大小的电压源, 电感视作 $ i_L(0^+) $ 大小的电流源**.
3. 求解电路中的其他变量

### 第二稳态的计算方法
1. 画出**换路后**的电路图, 达到稳态后, **电容视作断路**, **电感视作短路**.
2. 求解电路中的其他变量

## 一阶 RC 和 RL 电路的响应确定
只含一个储能元件 (电容, 电感) 的电路被称为一阶电路.

零输入响应: 换路后没有外加激励, 由储能元件的初始储能引起的响应
零状态响应: 换路前储能元件无初始储能, 完全由激励产生能量

两种响应叠加得到全响应.

### 三要素法
换路后, $ f(t) $ 表示电压或电流, 则 $ f(t) = \text{稳态分量} + \text{瞬态分量} $.

换路后全响应可以由下面公式计算得到:
\[ f(t) = \color{blue}{ f(\infty) } + \color{red}{ \big[ f(0^+) - f(\infty) \big] e^{-t/\tau} } \quad t\in [0^+, \infty) .\]

其中, RC 电路的 $ \tau = R_{\r{eq}} C $, RL 电路的 $ \tau = L / R_{\r{eq}} $. 
**$ R_{eq} $ 为换路后电路置零, 从储能元件两端看得的无源二端网络的等效电阻.** 

式中<font color=blue>蓝色部分</font>为稳态分量, <font color=red>红色部分</font>为瞬态分量. 对于电容, $ f $ 代表电压; 而电感的 $ f $ 为电流.

$ f(\infty) $, $ f(0^+) $, $ \tau $ 为一阶线性电路全响应的三要素, 只要确定这三个量, 就能确定瞬态响应. 

# 正弦交流电路分析
## 正弦量表示
### 有效值
有效值计算:
\[ I = \sqrt{\dfrac{1}{T} \int_0^T i^2 \,dt } .\]

由于有效值是电流平方的均值再开方, 所以有效值也称**方均根值** (root-mean-square value).

> 对于正弦量, 不妨设 $ i = I_{\rm m} \sin \omega t $, 有效值 $\displaystyle I = \sqrt{\dfrac{1}{T} \int_0^T I_{\rm m}^2 \sin^2 \omega t \,dt } = \dfrac{I_{\rm m}}{\sqrt 2} $.

### 正弦量表达式
\[ i(t) = I_{\r m} \sin(\omega t + \psi) ,\]

$ I_{\rm m} $: 幅值 (瞬时最大值)
$ \omega $: 角频率
$ \omega t + \psi $: 相位角
$ \psi $: 初相位

两个**同频率**正弦量的相位角之差称为它们的**相位差**, 记作 $ \varphi $:
\[ \varphi = (\omega t + \psi_1) - (\omega t + \psi_2) = \psi_1 - \psi_2 .\]

第一个正弦量 $ f_1(t) $ 初相角大于第二个 $ f_2(t) $: $ \psi_1 > \psi_2 $, 则相位差 $ \varphi = \psi_1 - \psi_2 > 0 $, 称 $ f_1 $ **超前**于 $ f_2 $, $ f_2 $ **滞后**于 $ f_1 $. 若 $ \varphi = 0 $, 则称 $ f_1 $, $ f_2 $ **同相**.


## 相量
设有一正弦电压 $ v = V_{\rm m} \sin (\omega t + \psi) $. 根据欧拉公式, 将其写作指数形式:
\[
\begin{align*}
v &= V_{\rm m} \Im e^{j(\omega t + \psi)} \\
  &= \Im \left[ V_{\rm m} e^{j(\omega t + \psi)} \right] \\
  &= \Im \left[ \color{red}{V_{\rm m} e^{j \psi}} e^{j \omega t}  \right]\,,
\end{align*}
\]

记: $ \dot V\!_{\rm m} = \widetilde V\!_{\rm m} = \color{red}{ V_{\rm m} e^{j \psi}} $:
\[ v = \Im\left[ \color{red}{\dot V\!_\r m} e^{j \omega t} \right] \,.\]


通常情况下, 正弦交流电路各电源频率相同, 故同一时刻 $ e^{j \omega t} $ 是一个常量. 所以正弦电压 $ v $ 和 $ \dot V\!_{\r m} $ 一一对应, 也就可以用 $ \dot V\!_{\r m} $ 表示正弦量 $ v $.

所以, **在 $ \omega $ 一定的情况下, 正弦量可以由复数表示, 复数的模等于正弦量的幅值, 辐角等于正弦量的初相位, 这个复数称为幅值相量.** 表示为:
\[ \dot V\!_\r m = V_m e^{j \psi} = V_m \angle \psi \,.\]

同理, 有效值相量 $ \dot{V} = V e^{j \psi} = V \angle \psi $, 其与幅值相量的关系也满足: $ \dot V_{\r m} = \sqrt 2 \dot V $.

> 相量 (复数) 只是正弦量的表示方法, 不等于正弦量. 相量实质上反应了正弦量的两个要素, 幅值和初相位(线性电路中, 角频率一定, 不予考虑). 

### 相量运算
有了相量来表示正弦量, 正弦量的运算就可以归结与相量 (复数) 的运算.

如, $ v_i = \sqrt{2} V_i \sin(\omega t + \psi_i) $:
\[ 
\begin{align*}
  v = \sum_{i = 1}^n v_i &= \sum_{i = 1}^n \left[ \sqrt 2 V_i \sin(\omega t + \psi_i) \right] \\
  &=  \sum_{i = 1}^n \Im\left( \sqrt{2} \dot V\!_i e^{j \omega t} \right) \\
  &= \Im \left( \sqrt{2} \sum_{i = 1}^n \dot V\!_i \cdot e^{j \omega t} \right) \,.
\end{align*}
\]

可以看出, **同频率正弦量之和仍然为同频率的正弦量, 其相量等于这些正弦量对应相量的和.**
\[ v = v_1 + \cdots + v_n \Leftrightarrow \dot V = \dot{V_1} + \cdots + \dot{V_n} \,.\]

## 相量形式的欧姆定律
### 电阻
\[ \dot V = R \dot I \]

可以看出, 电感上, 正弦电压与电流同相. 因此其相量图为:

<center><img src="./pic/resistor_phasor.svg" width=20% /></center>


### 电感
\[ \dot V = j \omega L \dot I = j X_L \dot I \]

> 推导过程如下: 设电流正弦量 $ i = A\sin(\omega t + \psi) $, 则 $ v = L \dd i.t = A \omega L \cos(\omega t + \psi) = A \omega L \sin \left( \omega t + \psi + \dfrac{\pi}{2} \right) $,
> 将其表示为相量:
> $ \dot I = A e^{j \psi} $, 
> $ \dot V = A \omega L e^{j (\psi + \pi / 2)} = A \omega L e^{j \psi} e^{j \frac{\pi}{2}}= j \omega L A e^{j \psi} = j \omega L \dot I $. 
> 记感抗 $ X_L = \omega L $, 则 $ \dot V = j X_L \dot I $.

$ X_L $ 为感抗, $ j X_L $ 称为复感抗.

可以看出, 电感上, 正弦电压超前电流 $ 90^\circ $. 因此其相量图为:

<center><img src="./pic/inductor_phasor.svg" width=20% /></center>

### 电容
\[ \dot V = - \dfrac{j}{\omega C} \dot I = \dfrac{1}{j \omega C} \dot I = - j X_C \dot I \]

> 推导过程: 设电压正弦量 $ v = A \sin (\omega t + \psi) $, 则 $ i = C \dd v.t = A \omega C \cos (\omega t + \psi) = A \omega C \sin \left( \omega t + \psi + \dfrac{\pi}{2} \right) $.
> 表示为相量:
> $ \dot V = A e^{j \psi} $,
> $ \dot I = A \omega C e^{j (\psi + \pi /2)} = A j \omega C e^{j \psi} = j \omega C \dot V $.
> $ \dot V = \dfrac{1}{j \omega C} \dot I = -j \dfrac{1}{\omega C} \dot I $, 记容抗 $ X_C = \dfrac{1}{\omega C} $, 则 $ \dot V = - j X_C \dot I $.

$ X_C $ 为容抗, $ - j X_C $ 称为复容抗. 注意恒等式: $ \dfrac{1}{j} = -j $, 所以复容抗 $ \dot X_C = - j X_C = \dfrac{X_C}{j} $.

可以看出, 电容上, 正弦电流超前电压 $ 90^\circ $. 其相量图:

<center><img src="./pic/capacitor_phasor.svg" width=20% /></center>

### 总结
$ \, $ |电阻 | 电感 | 电容
-|-|-|-
实阻抗| $ R $ | $ \omega L $ | $ \dfrac{1}{\omega C} $ 
复阻抗| $ R + 0i $ | $ j \omega L $ | $ \dfrac{1}{j \omega C} $


## 阻抗
由电阻、电感、电容构成的无源二端网络, 在端口外加正弦电压, 端口电流将是同频率的正弦量. 将阻抗定义为端口电压和电流的相量比:
\[ Z = \dfrac{\dot V}{\dot I} \,.\]

可以得到, 阻抗是一个复数, 其实部是电阻, 虚部是感抗与容抗之差:
\[ Z = R + j X = R + j(X_L - X_C) \,.\]

<center><img src="./pic/impedance.svg" width=30% /></center>

在正弦交流电路中, 正弦量均用相量表示, 电路参数均用复数阻抗表示, 则对交流电路的分析过程和各种定律可照搬自直流电流.


## 功率
交流电功率是电能在交流电路中流动的速率，电压乘以电流的积称为**视在功率**。在交流电系统中，例如电感器和电容器之类的储能装置可能会导致能量流动方向的周期性变化。在一个完整周期内，能量在一个方向上的净流动率称为**有功功率**或实功率，而往返于储能装置与电源间的部分称为**无功功率**或虚功率。

电阻元件恒定对外做功; 而电容和电感作为储能元件, 不会对外做功, 电能只是不断往返于储能元件和电源之间. 所以电阻是有功功率, 电容和电感是无功功率.

### 有功功率
定义瞬时功率在一个周期内的平均值为平均功率. 平均功率定义为有功功率.

设正弦交流电路中的端口电压和电流分别为:
\[ v = \sqrt 2 V \sin(\omega t + \psi_v) \,,\]

\[ i = \sqrt 2 I \sin(\omega t + \psi_i) \,.\]

则瞬时功率 $ p = v \cdot i $, 化简得到:
\[  p = V I \cos \varphi - V I \cos (2 \omega t + \varphi) \,.\]

其中, $ \varphi = \psi_v - \psi_i $ 是电压和电流之间的相位差. 计算平均功率:
\[ P = \dfrac{1}{T} \int_0^T p \,dt = V I \cos \varphi \,.\]

可以看出: 平均功率 (有功功率) 不仅取决于电压和电流的有效值, 还与两者之间的相位差有关. $ \cos \varphi $ 常被称为电路的功率因数.

### 无功功率
对于纯电感:
\[ i = \sqrt 2 I \sin \omega t \, ,\]

\[ v = \sqrt 2 V \sin(\omega t + \pi/2) \,,\]

\[ p = V I \sin 2\omega t \,,\]

\[ P = 0 \,.\]

纯电感不消耗能量, 只有电源和电感元件之间的能量交换. 这种能量交换的规模用无功功率 $ Q $ 来衡量, 定义无功功率为瞬时功率 $ p $ 的幅值 $ Q = V I $. **电感功率为正, 表示其消耗虚功率.**

同理, 对于纯电容: $ Q = - V I $. **电容功率为负, 表示提供虚功率.**

对于普通的含电阻、电容、电感的电路, \[ Q = V I \sin\varphi = V I \sin(\psi_v - \psi_i) \,.\]

### 视在功率
无功功率并不实际传输能量，所以在图中以虚轴表示. 有功功率则表示在实轴上. 视在功率可以表示为: \[ S = P + j Q \,,\]

其模:
\[ |S| = \sqrt{P^2 + Q^2} \,.\]

# 三相交流电
## 对称三相交流电路分析
### Y 型电路
\[ \dot V\!_{\r L} = \sqrt{3} \dot V\!_{\r P} \angle 30^\circ \]

\[ \dot I\!_{\r L} = \dot I\!_{\r P} \]

### △ 型电路
\[ \dot I\!_{\r L} = \sqrt{3} \dot I\!_{\r P} \angle (-30^\circ) \]

\[ \dot V\!_{\r L} = \dot V\!_{\r P} \]

所以对于有效值:
- Y 型电路: $ V_{\r L} = \sqrt{3} V_{\r P} $, $ I_{\r L} = I_{\r P} $
- △ 型电路: $ V_{\r L} = V_{\r P} $, $ I_{\r L} = \sqrt 3 I_{\r P} $

### 功率
三相电路的有功功率等于各相负载有功功率之和:
\[ P = P_1 + P_2 + P_3 = \sum_{k = 1}^3 V_{\r Pk} I_{\r Pk} \cos \varphi_k \,,\]

其中, $ \varphi_k = \varphi_{vk} - \varphi_{ik} $ 为第 $ k $ 相电路的阻抗角. 所以对于对称电路, 各相电压, 电流, 负载均相等, 上式化简为:
\[ P = 3 V_{\r P} I_{\r P} \cos \varphi \,.\]

根据 Y 型和 $ \Delta $ 型电路的相线电压电流特点, 上式等价为:
\[ P = \sqrt 3 V_{\r L} I_{\r L} \cos \varphi \,.\]

同单相交流电处理方法, 无功功率的计算则将 $ \cos\varphi $ 换为 $ \sin\varphi $. 视在功率 $ S = \sqrt{P^2 + Q^2} $.

# 机电能量转换原理
## 变压器
### 一次侧感应电动势瞬时值
\[ e_1 = - N_1 \dfrac{d\phi}{dt} = - N_1 \omega \phi_\r m \cos \omega t \,,\]

\[ E_{1\r m} = N_1 \omega \phi_\r m \,,\]

有效值:
\[ E_1 = \dfrac{E_{1\r m}}{\sqrt 2} = \sqrt 2 \pi f N_1 \phi_\r m = 4.44 f N_1 \phi_\r m \]

## 变换关系
\[ \dfrac{V_1}{V_{20}} \approx \dfrac{E_1}{E_2} = K \,,\]

\[ \dfrac{I_1}{I_2} \approx \dfrac{N_2}{N_1} = \dfrac{1}{K} 
\,,\]

\[ |Z_L'| = K^2 |Z_L| \,.\]

## 运行特征
单相
\[ I_{1\r N} = \dfrac{S_\r N}{U_{\r{1N}}}, I_{2\r N} = \dfrac{S_\r N}{U_{\r{2N}}} \,,\]

三相
\[ I_{1\r N} = \dfrac{S_\r N}{\sqrt 3 U_{\r{1N}}}, I_{2\r N} = \dfrac{S_\r N}{\sqrt 3 U_{\r{2N}}} \,.\]

# 三相异步电动机
## 转动原理
定子产生旋转磁场, 转速为 $ n_0 $, 称为同步转速. 
\[ n_0 = \dfrac{60 f_1}{p} \ \r{r/min} \,,\]

其中, $ f_1 $ 是定子电流频率, $ p $ 是极对数. 我国交流电频率 $ f_1 = 50 \ \r{Hz} $. 故 $ n_0 = 3000 / p $.


旋转磁场使转子转动, 转子转速为 $ n $, 转子的速度始终低于同步转速; 若 $ n = n_0 $, 转子不再切割磁感线, 便不能产生感应电流, 也不会有电磁转矩, 转子转速将下降, 使 $ n < n_0 $.

### 转差率
转差率 $ s $ 是反应异步电动机运行情况的重要参数. 
\[ s = \dfrac{n_0 - n}{n_0} \,.\]

**负载越大, 转速 $ n $ 越小, 从表达式可以看出, 转差率 $ s $ 增大.**

## 转子电路分析
### 转子电路频率
转子绕组中电动势和电流频率 $ f_2 $ 为
\[  f_2 = s f_1 \,.\]

### 转子感应电动势和电流
\[ E_2 = 4.44 f_2 N_2 \phi_\r m = 4.44 s f_1 N_2 \phi_\r m \,.\]

当转速 $ n = 0 $ 时, $ s = 1 $, $ E_2 $ 取得最大值, 记作 $ E_{20} $
\[ E_{20} = 4.44 f_1 N_2 \phi_\r m \,,\]

可见, $ E_2 = s E_{20} $.

转子电流 $ I_2 = \dfrac{s E_{20}}{\sqrt{R_2^2 + (sX_{20})^2}} $, **转速 $ n $ 增大, 转差率 $ s $ 减小, 转子电流 $ I_2 $ 减小.**

## 额定转矩
转子的电磁转矩 $ T $, 电机输出功率 $ P_\r o $ 以及转子转速 $ n $ 之间满足 $ T = 9550 \dfrac{P_\r o \ (\r{kW})}{n \ (\r{rpm})} $.

额定转矩 $ T_\r N $, 额定功率 $ P_\r N  $ 和额定转速亦满足
\[ T_\r N = 9550 \dfrac{P_\r N }{n_\r N} \,. \]

## 过载能力
过载能力 $ \lambda $, 最大转矩 $ T_\max $ 和额定转矩 $ T_\r N $ 之间的关系:
\[ \lambda = \dfrac{T_\max}{T_\r N} \,.\]

## 起动转矩和启动能力
起动转矩记为 $ T_\r{st} $, 起动能力 $ K_\r{st} $ 和额定转矩 $ T_\r N $ 的关系为:
\[ K_\r{st} = \dfrac{T_\r{st}}{T_\r N} \,.\]


## 输入功率与效率
输入功率 $ P_\r i $ 计算方法
\[ P_\r i = \sqrt 3 U_\r N I_\r N \cos \varphi_\r N \,,\]

其中 $ U_\r N $, $ I_\r N $, $ \varphi_\r N $ 从电机铭牌上读得.

电机效率 $ \eta $ 定义为额定输出功率与输入功率之比
\[ \eta = \dfrac{P_\r N}{P_\r i} = \dfrac{P_\r N}{\sqrt 3 U_\r N I_\r N \cos \varphi_\r N} \,.\]

由此也可以推导出额定电流 $ I_\r N = \dfrac{P_\r N}{\sqrt 3 U_\r N \cos \varphi_\r N \eta} $

## 星型-三角形换接起动
\[ I_{\r L \Delta} = 3 I_{\r{LY}} \,,\]

\[ T_\r{st\Delta} = 3 T_\r{stY} \,.\]

## 自耦降压起动
\[ I_\r{st}' = \dfrac{1}{K^2} I_\r{stN} \,.\]

$ I_\r{stN} $ 即前面的 $ I_\r N $.