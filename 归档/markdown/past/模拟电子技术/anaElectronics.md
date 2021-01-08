<center><font size=7>模拟电子技术</font></center>
[TOC]
$ 
\newcommand{\ve}[1]{\boldsymbol{\mathbf{#1}}}
\newcommand{\unit}[1]{\boldsymbol{\mathbf{\hat{#1}}}}
\newcommand{\mcal}{\mathcal}
\newcommand{\mr}{\mathrm}
\newcommand{\mscr}{\mathscr}
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
\DeclareMathOperator{\tr}{tr} $

# 信号与放大电路 

## 模拟信号与数字信号
一般将时间和数值均连续的信号称为模拟信号, 时间和数值均离散的信号称为数字信号.

<center><img src="./pic/analog&digital.svg" width=60% /></center>
## 信号的频谱

### 时域

对于正弦电压信号, 电压与时间的数学关系可以表达为:

$$
v(t) = V_m \sin(\omega t + \theta).
$$

式中 $ V_m $ 是正弦电压的振幅, $ \omega $ 为角频率, $ \theta $ 为初始相位角. 当 $ \omega = 0 $ 时, $ v(t) $ 为直流电压信号. 

<center><img src="D:./pic/sine_signal.svg" width=40% /></center>
类似的, 还有方波:

<center><img src="./pic/square_wave.svg" width=50% /></center>
方波信号可以展开为傅里叶级数:

$$
    v(t) = \dfrac{V_s}{2} + \dfrac{2V_s}{\pi} \left( \color{red}{\sin \omega_0 t} + \color{blue}{ \dfrac{\sin 3\omega_0 t}{3} + \dfrac{\sin 5\omega_0 t}{5} + \cdots }\right)
$$

红色部分 $ \color{red}{ \dfrac{2 V_s}{\pi} \sin \omega_0 t} $ 为该信号的基波, 其余各项都是高次谐波分量. 

> 为什么使用角频率(速率) ? 
> 角频率 $ \omega $ 与频率 $ f $ 之间的关系为: $ \omega = 2 \pi f $. 使用角频率而不是频率作为变量可以避免出现额外 $ \pi $, 从而能简化公式, 如:
> \[ a = -\omega^2 x ,\]
> 
> 和
> \[ a = - 4 \pi^2 f^2 x .\]

### 频谱图
#### 幅度频谱
通过傅里叶级数, 可以得到信号幅值与角频率关系的图解. 其中包括直流项 $ (\omega = 0) $ 和每一谐波分量在相应角频率处的振幅. 这种信号<u>**各频率分量的振幅随角频率变化的分布**</u>, 称为该信号的**幅度频谱** (简称幅度谱).

<figure align="center"><img src="./pic/frequency_spectrum.svg" width=50% /><figcaption>正弦电压的幅度频谱</figcaption></figure>

#### 相位频谱
与幅度谱类似, 信号<u>**各频率分量的相位随角频率变化的分布**</u>, 称为该信号的**相位频谱**.

<center><img src="./pic/phase_spectrum.svg" width=50% /></center>

> 非周期信号的频谱包含所有可能频率 $ (0 \leqslant \omega < \infty) $ 成分. 随角频率升高, 频谱函数总趋势是衰减的. 由于实际电路处理能力不可能延伸至无穷远, 所以常常选择一个适当的频率 $ \omega_{\rm c} $ (截止频率), 将高于此频率的部分截断, 而信号特性不会发生太大变化. 保留部分的频率范围称为信号的带宽. 

##  等效电路

<center><img src="./pic/equivalent_circuit.svg" width=45%></center>

## 放大电路
### 放大电路的主要性能指标
#### 输入电阻
从输入端看过去的电压. 在输入端外加测试电压 $ v_{\mr t} $, 求得测试电流 $ i_{\mr t} $, $ R_{\mr i} = \dfrac{v_{\mr t}}{i_{\mr t}} $.
#### 输出电阻
从负载端看过去的电压. **信号源置零**, 将负载去掉, 换成测试电压, 求测试电流, $ R_{\mr o} = \dfrac{v_{\mr t}}{i_{\mr t}} $.
#### 增益
电压增益:
\[ A_v = \dfrac{v_{\mr o}}{v_{\mr i}} \]

\[ A_{vs} = \dfrac{v_{\mr o}}{v_{\mr s}} = \dfrac{R_{\mr i}}{R_{\mr i} + R_{\mr s}} A_v \]

\[ A_v = 20 \lg | A_v | \ (\mathrm{dB}) ,\]

电流增益:
\[ A_i = 20 \lg | A_i | \ (\mathrm{dB}) ,\]

功率增益:
\[ A_p = 10 \lg | A_p | \ (\mathrm{dB}) .\]
#### 频率响应与失真
- 频率失真(线性失真)
  - 幅度失真
  - 相位失真
- 非线性失真

# 半导体与二极管
## 半导体原理
半导体的导电性能介于导体和绝缘体之间. 常用的半导体材料有元素半导体 (如 $ \mathrm{Si} $ 和 $ \mathrm{Ge} $) 和化合物半导体 (如 $ \mathrm{GaAs} $).


### 本征半导体
本征半导体是纯净不掺入杂质的半导体晶体. 一般结构由下图表示:

<center><img src="./pic/semiconductor.svg" width=45% /></center>

部分被束缚的价电子在获得足够的热能而挣脱束缚, 成为自由电子, 这叫做**本征激发**. 自由电子产生后, 原位置便出现一个空位, 成为空穴. 显然, 在本征半导体中, 空穴数和自由电子数是恒等的.

在外加电场的条件下, 自由电子产生定向移动就会形成电流. 同时, 电场的能量或其它能量作用下, 邻近价电子 (束缚电子) 可能会填补该空位. 于是位置被填补, 新的空穴产生. 从效果上看, 仿佛是空穴在移动, 如下图. 

<center><img src="./pic/hole_mov.svg" width=40% /></center>

<font color="#3EB0DC"><u>所以我们把空穴虚拟成一种载流子, 它的运动方向与价电子相反, 所以认为其带正电.</u></font> 空穴的移动产生了电流, 称为空穴电流.

> 注意: 由于空穴移动实际上是束缚电子移动, 所以空穴电流本质上是束缚电子产生电流.

于是可以看出, 本征半导体的载流子有两种: 本征激发得到的自由电子以及空穴. 这两种载流子的浓度都很小, 所以本征半导体的导电效果不佳. 不过随温度增加, 其导电性亦会增强.

### 杂质半导体
通过向纯净的半导体中掺入其他元素 (+3 或 +5 价), 可以显著改变半导体的导电性能.

#### P 型半导体
向本征半导体中掺入微量 +3 价元素 (如: $ \mr B $), 因其价电子只有三个, 晶体中产生了空位. 热激发产生的自由电子能填补该空位, 使其成为无法移动的**负离子**, 故称杂质原子为**受主原子**.

在这种半导体中, 由掺杂而引入了大量空穴. 本征激发带来的空穴-电子对只是少数. 故称空穴为**多数载流子**, 自由电子为**少数载流子**. 由于多数载流子带正电, 故称这种半导体为 P 型半导体 (P 即 Positive).

#### N 型半导体
向本征半导体中掺入微量 +5 价元素 (如: $ \mr P $), 这种杂质原子在形成共价键时, 就会多出一个价电子, 这个电子容易受热激发而变为自由电子. 而形成自由电子后, 原位置留下一个不能移动的正离子, 故称掺入的原子为**施主原子**. 

可以看出, 掺入的杂质使半导体中自由电子数目远多于空穴的数目. 所以多数载流子是自由电子, 而少数载流子是空穴. 这种半导体称为 N 型半导体 (N 即 Negative).

<center>

|P 型 | N 型
:-:|:-:
空穴(多) <br> 自由电子-空穴对(少)| 空穴-自由电子对(少) <br> 自由电子(多)
</center>

## PN 结
将半导体两边分别掺入 P 型和 N 型半导体, 得到 PN 结.

<center><img src="./pic/Pn-junction.png" width=70% /></center>

左边 P 区中, 多数载流子为空穴 (+), 受主原子带负电 (-);

右边 N 区中, 多数载流子为电子 (-), 施主原子带正电 (+).

载流子会从浓度高的区域向浓度低的区域扩散. 所以 P 区的空穴向 N 区扩散, N 区的电子向 P 区扩散, 两者在交界处附近**复合** (耗尽). 交界处附近, P 区失去空穴, 留下带负电的杂质离子; N 区失去电子, 留下带正电的杂质离子. 因此交界面附近产生了一个很薄的空间电荷区 (space charge region). 电场 (图中的 E-field) 方向由 N 指向 P, 由于其在内部形成, 故称内电场.

内电场的方向指向 P 区, 因此从 P 区扩散来的空穴 (+) 会受到一个与其扩散方向相反的电场力, 扩散也会被阻碍. P 区中的少数载流子为电子, 在内电场作用下, 电子会更加容易向 N 区漂移.

故可看出内电场的作用: **<font color="#00bfff">阻碍多数载流子的扩散, 有利于少数载流子的漂移</font>**.

多数载流子扩散会使空间电荷区变宽, 少数载流子漂移会使空间电荷区变窄. 两种运动相等时, 空间电荷区便达到平衡.

## PN结/二极管的特性
将 P 区和 N 区各连上导线就形成了最简单的二极管模型. 规定 P 区为二极管正级, N 区为负极. 符号如图所示.

<center><img src="./pic/diode0.svg" width=25% /></center>

PN 结具有如下特性:
当外加正向电压, 即正极电势高于负极电势, 外电场方向和内电场方向相反. 随着外电场的增加, 外电场逐渐克服了内电场, 此时合场强指向 N 区, 多数载流子的扩散效果将大大增强, 此时 PN 结表现为阻值很小的电阻, 称为 PN 结导通.

同理, 当外加反向电压, PN 结表现为一个阻值极大的电阻, 可认为其基本上不导电, 称为 PN 结截止.

### 二极管的 I-V 特性

<center><img src="./pic/diode_i-v.svg" width=50% /></center>

### 二极管等效模型
理想模型: 
- 正偏导通, 视为短路, 管压降为零
- 反偏截止, 视为断路

\[ 
\begin{cases}
    v \geqslant 0 \Rightarrow v = 0\\
    v < 0 \Rightarrow i = 0
\end{cases} 
\]

恒压降模型:
- 正偏电压大于等于 0.7 V 时导通, 管压降恒为 0.7 V
- 电压小于 0.7 V 时截止, 视作断路, 电流为零

\[ 
\begin{cases}
    v \geqslant 0.7 \Rightarrow v = 0.7\\
    v < 0.7 \Rightarrow i = 0
\end{cases} 
\]

# 双极结型三极管 (BJT)
## BJT 原理
懒得写

## BJT 电流分配关系
<center><img src="./pic/BJT.svg" width=50% /></center>

发射极:
\[ I_{\mr E} = I_{\mr{EN}} + I_{\mr{EP}} \approx I_{\mr{EN}} \]

集电极:
\[ I_{\mr C} = I_{\mr{CN}} + I_{\mr{CBO}} \approx = I_{\mr{CN}} \]

基极:
\[ I_{\mr B} = I_{\mr E} - I_{\mr C} \]

### 放大系数
定义共基极直流电流放大系数 $ \alpha $ 为 $ I_{\mr E} $ 转化为 $ I_{\mr{CN}} $ 的能力,
\[ \alpha = \dfrac{I_{\mr{CN}}}{I_{\mr E}} \approx \dfrac{I_{C}}{I_{\mr E}} .\]

显然, $ \alpha < 1 $ 但 $ \alpha $ 接近 $ 1 $, 一般 $ \alpha \geqslant 0.98 $.

定义共射极直流电流放大系数 $ \beta $ 为 \[ \beta \approx \dfrac{I_{\mr C}}{I_{\mr B}}. \]

$ \alpha $, $ \beta $ 间的关系满足: \[ \dfrac{1}{\alpha} - \dfrac{1}{\beta} = 1 ,\]

即: $ \alpha = \dfrac{\beta}{1 + \beta} $, $ \beta = \dfrac{\alpha}{1 - \alpha} $

由此可以推出发射极, 基极, 集电极两两间的关系:
\[ I_{\mr C} = \alpha I_{\mr E} ,\]

\[ I_{\mr C} = \beta I_{\mr B} ,\]

\[ I_{\mr E} = (1 + \beta) I_{\mr B} .\]

可见在发射结正偏, 集电结反偏且 $ \alpha $, $ \beta $ 保持不变时, 输入电流 $ I_{\mr C} $ (或 $ I_{\mr E} $) 正比于输入电流 $ I_{\mr E} $ (或 $ I_{\mr B} $).

## BJT 的 I-V 特性曲线
BJT 可视为二端口网络, 要完整描述其 $ I $-$ V $ 特性, 需选用两组特性曲线, 常用 BJT 的**输入特性曲线**和**输出特性曲线**.

BJT 不同组态时具有不同的端电压和电流, 因此, 它们的 $ I $-$ V $ 特性曲线也就各不相同. 共集电极组态与共射极组态的特性曲线类似, 所以这里着重讨论共射极连接时的 $ I $-$ V $ 特性.

### 共射极连接时的 I-V 特性曲线
#### (1) 输入特性曲线
#### (2) 输出特性
> 注意: 判断正/反偏的本质方法是判断发射结和集电结两极的电势差.
1. 放大区
   **发射结正偏, 集电结反偏.**

   > 厄利效应 (Early effect): 也称基区宽度调制效应. 指当集电极-发射极电压 $ v_{\rm CE} $ 变化, 引起基区有效宽度变化, 从而导致基极电流 $ i_{\rm B} $ 变化的现象. 
   > 
   > 当集电结正偏时, 集电极收集电子的能力减弱, 同时集电结宽度减小, 发射极进入基极的大部分电子被基区复合. 
   >当集电结反偏时, 内电场增强, 集电极收集电子的能力急剧增强; 与此同时, 由于集电结宽度变宽, 基区有效宽度减小, 进一步遏止电子在基区复合. 所以此时小的反偏电压就会使集电极电流 $ i_{\mr C} $ 急剧增大. 当 $ v_{\mr{CE}} $ 增大到 1 V 左右, 集电结电场已经足够强, 发射区到基区的绝大部分电子被收集到集电区. 继续增加 $ v_{\mr{CE}} $, 不会对 $ i_{\mr C} $ 和 $ i_{\mr B} $ 造成明显影响. 此时, $ i_{\mr C} $ 和 $ i_{\mr B} $ 便满足线性关系.
   
2. 饱和区
   **发射结和集电结均正偏**, 此时: $ v_{\mr{CE}} \leqslant v_{\mr{BE}} \Rightarrow v_{\mr C} - v_{\mr E} \leqslant v_{\mr B} - v_{\mr E} \Rightarrow v_{\mr C} \leqslant v_{\mr B} $.

   

3. 截止区
    **发射结处于死区, 集电结反偏.**

# 场效应晶体管 (FET)
## 金属-氧化物-半导体场效应管 (MOSFET)
<center><img src="./pic/MOSFET.png" width=45% /></center>
以 N 沟道增强型场效应管为例, 控制作用主要取决于两个电压:
- 栅源电压: $ V_{\mr{GS}} $ 控制沟道宽度, 当栅源电压大于开启电压时 $ V_{\mr{GS}} > V_{\mr{TN}} $, 沟道出现, MOS 管被导通
- 漏源电压: $ V_{\mr{DS}} $ 使沟道漏极和源极出现电位差, 随 $ V_{\mr{DS}} $ 增大, 漏极端电势越来越大, 这使得原本栅极电场对沟道的开启效应被削弱, 当栅极-漏极电势差 $ V_{\mr{GD}} < V_{\mr{TN}} $, 沟道就被夹断. $ V_{\mr{GD}} = V_{\mr{GS}} - V_{\mr{DS}} < V_{\mr{TN}} $, 所以夹断条件: $ V_{\mr{DS}} > V_{\mr{GS}} - V_{\mr{TN}} $.
<br/>
<br/>
可以这样简单理解: 栅源电压 $ V_{\mr{GS}} $ 使沟道开启; 漏源电压 $ V_{\mr{DS}} $ 削弱 $ V_{\mr{GS}} $; $ V_{\mr{GS}} - V_{\mr{TN}} $ 表示此时开启时的沟道电压, 当削弱的电压 $ V_{\mr DS} $ 大于此时沟道的电压, 沟道就被夹断.

<center><img src="./pic/MOSFET_pitch.svg" width=40% /></center>


# FET 电路分析法
## 静态分析——直流通路分析
求解: $ V_{\mr{GS}} $ (注意 $ I_{\mr G} $ 恒为 $ 0 $), $ I_{\mr D} $, $ V_{\mr{DS}} $

方程:
- 输入回路 KVL
- 输出回路 KVL
- 控制方程 (转移特性): $ I_{\mr D} = K_{\mr n} (V_{\mr{GS}} - V_{\mr{TN}})^2 $

求解完, 验证是否工作在饱和区:
- $ V_{\mr{GS}} > V_{\mr{TN}} $
- $ V_{\mr{DS}} > V_{\mr{GS}} - V_{\mr{TN}} $

## 动态分析——交流通路分析
求解: $ A_{v} $, $ A_{vs} $, $ R_{\mr i} $, $ R_{\mr o} $

画小信号等效模型: 将直流电源置零, 电容视作通路

参数:
- $ r_{\mr{ds}} = \dfrac{1}{\lambda I_{\mr{DQ}}} $, 一般 $ \lambda = 0 $, $ r_{ds} = \infty $, 所在支路直接断开
- $ g_{\mr m} = 2 K_{\mr n} (V_{\mr{GSQ}} - V_{\mr{TN}}) = 2 \sqrt{K_{\mr n} I_{\mr DQ}} $
- $ i_{\mr d} = g_{\mr m} v_{\mr{gs}} $

<center><img src="./pic/MOSFET_eq.svg" width=35% /></center>

增益:
\[ A_v = \dfrac{v_{\mr o}}{v_{\mr i}} \,.\]

\[ A_{vs} = \dfrac{v_{\mr o}}{v_{\mr s}} = \dfrac{v_{\mr o}}{v_{\mr i}} \dfrac{v_{\mr i}}{v_{\mr s}} = A_v \cdot \dfrac{R_{\mr i}}{R_{\mr i} + R_{\mr s}} \,.\]

输入电阻与输出电阻按定义计算.

> 直接写出电压增益:
> FET 输入端和输出端有 $ i_{\mr d} = g_{\mr m} v_{\mr{gs}} $ 的关系, 之间由 $ v_{\mr{gs}} $ 联系起来. 根据定义 $ A_v = \dfrac{v_{\mr o}}{v_{\mr i}} $, 其中, $ v_{\mr o} $ 可用电流 $ g_{\mr m} v_{\mr{gs}} $ 乘电阻求得, $ v_{\mr i} $ 也含 $ v_{\mr{gs}} $, 故 $ v_{\mr{gs}} $ 可以约去. 
>
> 如果 $ v_{\mr{gs}} $ 会出现在分子分母中的每一项, 那么 $ v_{\mr{gs}} $ 也可以预见性地被约去, 在一开始计算电压时, 直接将电流中的 $ v_{\mr{gs}} $ 写成 $ 1 $.

> 直接写出输入电阻:
> 无需画出小信号等效电路, 直接将直流源置零, 电容通路. 根据定义, 在输入端外加测试电压, 求测试电流后作比.

> 直接写出输出电阻:
> 将信号源置零. 根据定义, 从负载端向里看等效电阻. 可以采取: 在负载端加电压源, 求测试电流的方法.
>
> 当 FET 等效出的受控电流源两端的电压 $ v_{\rm ds} $ 恒为栅源控制电压 $ v_{\rm gs} $, 即电势: $ V_{\mr d} = V_{\mr g} $, 则受控源可以等效成一个电阻, 其电导为 $ g_{\mr m} $, 阻值 $ \dfrac{1}{g_{\mr m}} $.

# BJT 电路分析法
## 静态分析——直流通路分析
求解: $ I_{\mr B} $, $ I_{\mr C} $, $ V_{\mr{CE}} $, $ V_{\mr{BE}} $

方程:
- 输入回路 KVL
- 输出回路 KVL
- bce三极电流关系: 
  - $ I_{\mr B} + I_{\mr C} = I_{\mr E} $
  - $ I_{\mr C} = \beta I_{\mr B} $
  - $ I_{\mr E} = (1 + \beta) I_{\mr B} $


## 动态分析——交流通路分析
求解: $ A_{v} $, $ A_{vs} $, $ R_{\mr i} $, $ R_{\mr o} $

画小信号等效模型: 将直流电源置零, 电容视作通路

参数:
- $ r_{\mr{be}} = r_{\mr{bb'}} + (1 + \beta) \dfrac{26\ (\mr{mV})}{I_{\mr{EQ}}\ (\mr{mA})} = r_{\mr{bb'}} + \dfrac{26\ (\mr{mV})}{I_{\mr{BQ}}\ (\mr{mA})} $ 
- $ r_{\mr{bb'}} \approx 200 $ &ndash; $ 300\ \Omega $
</br>
<center><img src="./pic/BJT_eq.svg" width=40% /></center>

# 频率响应
## 单时间常数 RC 电路频率响应
### RC 高通电路
<center><img src="./pic/h.svg" width=30% /></center>

即下限频率 (转折频率) 为 $ f_{\mr L} = \dfrac{1}{2 \pi R C}$.

\[ \dot A_{v\mathrm L} = \dfrac{\dot V_\mathrm o}{\dot V_\mathrm i} = \dfrac{1}{1 - j (f_\mathrm L / f)} \]

\[ |\dot A_{v\mathrm L}| = \dfrac{1}{\sqrt{1 + (f_{\mr L} / f)^2}} \]

\[ \varphi_\mr L = \arctan \dfrac{f_\mr L}{f} \]

可见, 当 $ f \gg f_\mr L $, 增益 $ A \approx 1 $, 相移 $ \varphi \approx 0^{\circ} $.

### RC 低通电路
<center><img src="./pic/l.svg" width=30% /></center>

即上限频率 为 $ f_{\mr H} = \dfrac{1}{2 \pi R C}$.

\[ \dot A_{v\mathrm H} = \dfrac{\dot V_\mathrm o}{\dot V_\mathrm i} = \dfrac{1}{1 + j (f / f_\mr H)} \]

\[ |\dot A_{v\mathrm H}| = \dfrac{1}{\sqrt{1 + (f / f_{\mr H})^2}} \]

\[ \varphi_\mr H = -\arctan \dfrac{f}{f_\mr H} \]

可见, 当 $ f \ll f_\mr H $, 增益 $ A \approx 1 $, 相移 $ \varphi \approx 0^{\circ} $.

### 全频域响应
<center><img src="./pic/lh.png" width=60% /></center>
<center><img src="./pic/bode.png" width=80% /></center>




