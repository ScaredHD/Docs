<center><font size=7>物理</font></center>
[TOC]
$ 
\newcommand{\ve}[1]{\boldsymbol{\mathbf{#1}}}
\newcommand{\unit}[1]{\boldsymbol{\mathbf{\hat{#1}}}}
\newcommand{\mcal}{\mathcal}
\newcommand{\mscr}{\mathscr}
\newcommand{\mr}{\mathrm}
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

# 热力学
## 热力学系统状态
### 平衡态
平衡态是指在没有外界影响时, 系统的宏观性质不随时间的变化而变化的**宏观状态**. 对于气体, 只有在平衡态时, 才能用一组状态参量 $ (p, V, T) $ 来描述其性质; 而非平衡态下, 压强、体积及温度等参数都在随时间不断变化. 

当系统在宏观上处于平衡状态时, 组成系统的大量微观粒子仍处于不断的运动中, 只是大量微观粒子运动的平均效果不变而已. 由此热力学的平衡态时一种动态平衡, 常称热动平衡.

### 热平衡
两个处于平衡态的热力学系统相互接触, 由于其冷热程度不同, 它们之间会发生能量交换. 能量交换一段时间后, 两个系统会达到共同的平衡态, 称为热平衡.

> 热平衡定律 (热力学第零定律): 若 $ A $, $ B $, $ C $ 是三个热力学系统, $ A $ 与 $ C $, $ B $ 与 $ C $ 分别处于热平衡态. 则 $ A $ 和 $ B $ 必然彼此处于热平衡态.

### 热力学温标
摄氏温度 $ t \ (^\circ\mathrm{C}) $ 与热力学温标 $ T\ (\mathrm K) $ 之间的换算关系如下:
$$
T = t + 273.15.
$$

## 理想气体
### 物态方程
对于理想气体, 设 $ m $ 为气体质量, $ M $ 为该气体的摩尔质量. 则有:
$$
  p V = \dfrac{m}{M} R T .
$$

又因为物质的量 $ \nu = m / M $, 所以还可以写成下面的形式: 
$$
p V = \nu R T .
$$

经推导, 亦可表达为:
$$
p = n k T .
$$

其中 $ n $ 为单位体积内分子数 (气体密度), $ k = 1.38 \times 10^{-23}\ \mathrm{J \cdot K^{-1}} $, 被称为玻尔兹曼常数. $ R = 8.31 \ \mathrm{J/(mol\cdot K)} $ 是描述 $ 1 \ \mathrm{mol} $ 气体行为的普适常量.

> 理想气体满足上述物态方程, 反过来, 满足上述方程的气体就是理想气体.


## 理想气体的压强公式
理想气体对容器壁的压强是**大量**分子对器壁持续碰撞后的平均效果.
> 注意: 必须有**大量**分子.
### 压强计算公式
设气体单位体积分子数量 (即气体密度) 为 $ n $, 气体质量为 $ m $, 气体分子速度的平方均值为 $ \overline{v^2} $, 则气体对器壁的压强可以表示为: 
$$
  p = \dfrac{1}{3} n m \overline{v^2} .
$$

若用 $ \overline{\varepsilon_{\mathrm t}} $ 表示每个气体分子的平均平动动能, 则可推导出: 
$$
  p = \dfrac{2}{3} n \overline{\varepsilon_{\mathrm t}} .
$$

### 理想气体温度的围观意义
单个气体分子的平均平动动能可以由下式计算:
$$
  \overline{\varepsilon_{\mathrm t}} = \dfrac{1}{2} m \overline{v^2} .
$$

结合 $ p = n k T $ 与 $ p = \dfrac{2}{3} n \overline{\varepsilon_{\mathrm t}} $, 可得: 
$$
  \overline{\varepsilon_{\mathrm t}} = \dfrac{3}{2} k T .
$$

> 道尔顿分压定律: 有 $ m $ 种不同的理想气体共同密封在一个容器中, 处于平衡状态, 则混合气体的压强等于各组成气体的分压强之和 
> $$
>  p = p_1 + p_2 + \cdots + p_m .
> $$

## 能量均分定理
### 自由度
分子种类 | 平动自由度 | 转动自由度 | 总自由度
:-:|:-:|:-:|:-:
单原子分子 | 3 | 0 | 3
刚性双原子分子 | 3 | 2 | 5
刚性多原子分子 | 3 | 3 | 6

在平衡态下, 气体分子每一个自由度上的平均动能相等, 都等于 $ \dfrac{kT}{2} $. 也就是说, 分子的平均总动能被均分到每个自由度上.

双原子分子和多原子分子还具有振动产生的势能, 每一个自由度的平均势能也为 $ \dfrac{kT}{2} $. 所以自由度为 $ i $ 的双原子分子, 产生的平均动能: $ \dfrac{ikT}{2} $, 平均势能 $ \dfrac{ikT}{2} $, 平均总能量 $ i k T $.

### 内能
系统总能量为气体的内能, 是组成系统的**所有分子动能和势能之和**. 理想气体分子间无相互作用力, 势能为零. 故对于理想气体: **<font color="#00bfff">气体内能即所有分子动能总和</font>**.

设理想气体分子数 $ N $, 每个分子平均总动能 $ \overline \varepsilon = \dfrac{i k T}{2} $, 所以总动能 $ E = N \overline \varepsilon = \dfrac{i N k T}{2} $. 
由于 $ k = \dfrac{R}{N_\mathrm{A}} $, $ \nu = \dfrac{N}{N_\mathrm{A}} $, 化简上式, 得到理想气体的内能公式:
\[ E = \dfrac{i \nu R T}{2} \,.\]

定义 $ 1 \ \mathrm{mol} $ 理想气体内能为摩尔内能: $ E_\mathrm{m} = iRT/2 $.



## 麦克斯韦速率分布律
### 速率分布函数
记分子总数为 $ N $, 在速率区间 $ (v, v + dv) $ 中的分子数为 $ dN $, 则记 $ f(v) = \dfrac{dN}{N\,dv} $ 为速率分布函数. 类比概率分布函数, $ f(v)\, dv = dN / N $ 记录了速率落在 $ (v, v + dv) $ 中的分子占总数的比例 (即一分子处于这段速率的概率).

通过概率论知识, 容易类比得到下面的性质:
\[ \int_{0}^{\infty} f(v) \,dv = 1 \,.\]

### 最概然速率
粒子处于该速率的概率最大,
\[ v_\mathrm{p} = \sqrt{\dfrac{2kT}{m}} = \sqrt{\dfrac{2RT}{M}} \approx 1.41\sqrt{\dfrac{RT}{M}} \,.\]

### 平均速率
期望 (均值) $\displaystyle E(X) = \int_{\R} x f(x) \,dx $, 所以气体分子运动的平均速率:
\[ \overline v = \int_{0}^{\infty} v f(v) \,dv \,,\]

\[ \overline v = \sqrt{\dfrac{8RT}{\pi M}} \approx 1.6 \sqrt{\dfrac{RT}{M}} \,.\]

### 方均根速率
$\displaystyle E(X^2) = \int_{\R} x^2 f(x) \,dx $, 所以:
\[ \overline{v^2} = \int_0^\infty v^2 f(v)\, dv \,,\]

\[ \overline{v^2} = \sqrt{\dfrac{3RT}{M}} \approx 1.73\sqrt{\dfrac{RT}{M}} \,.\]

# 振动
## 简谐振动
弹簧振子系统由质量为 $ m $, 弹性系数 $ k $ 的弹簧构成. 该运动满足微分方程:
\[ \DD 2.x.t + \omega^2 x = 0 \,.\]

具有这种特征的振动, 称为简谐振动. 可以证明: **合外力为线性恢复力的振动为简谐振动.**

其中: $ \omega^2 = k / m $, 即: $ \omega = \sqrt{\dfrac{k}{m}} $.

该方程的通解为:
\[ x = A \cos(\omega t + \varphi_0) \,.\]

其中:
$ A $: 振幅, 物体离开平衡位置的最大距离
$ \omega $: 角频率, 表征物体振动快慢
$ \omega t + \varphi_0 $: 相位
$ \varphi_0 $: 初相(角)

角频率 $ \omega\ (\mathrm{s}^{-1})$, 周期 $ T\ (\mathrm{s}) $, 频率 $ f\ (\mathrm{s}^{-1}) $ 之间的转化:
\[ \omega = 2 \pi f \,,\]

\[ \omega T = 2 \pi \,,\]

\[ f = \dfrac{1}{T} \,.\]

只要清楚三者的量纲, 就容易记忆.

### 速度和加速度
\[ v = \dd x.t = -A\omega \sin(\omega t + \varphi_0) = A\omega \cos\left(\omega t + \varphi_0 + \dfrac{\pi}{2}\right) \,,\]

\[ a = \DD 2.x.t = -A \omega^2 \cos(\omega t + \varphi_0) = A\omega \cos (\omega t + \varphi_0 + \pi) \,.\]

比较 $ a $ 和 $ x $ 的表达式:
\[ a = - \omega^2 x \,.\]

### 初始条件
当 $ t = 0 $ 时, 物体的初始位置 $ x_0 = A \cos \varphi_0 $, 初始速度 $ v_0 = -A\omega \sin \varphi_0 $. 联立解得:
\[ A = \sqrt{x_0^2 + \dfrac{v_0^2}{\omega^2}} \qquad \tan \varphi_0 = - \dfrac{v_0}{\omega x_0} \,.\]

## 旋转矢量法
懒得写

## 单摆
小角度摆动下, 满足简谐振动:
\[ \omega = \sqrt{\dfrac{g}{l}} \,,\]

\[ T = 2\pi \sqrt{\dfrac{l}{g}} \,.\]

> 数值上 $ g \approx 9.87 $ &ndash; $ 9.83 $, 而 $ \pi^2 \approx 9.8696 $. 如果把 $ g $ 和 $ \pi^2 $ 看作近似相等. 则单摆周期公式可简化:
> \[ T = 2 \pi \sqrt{\dfrac{l}{g}} = 2 \pi \sqrt{\dfrac{l}{\pi^2}} = 2 \sqrt{l} \,.\]

## 简谐振动能量
以弹簧振子为例, 任意时刻其动能和势能分别为: 
\[ E_{\mathrm k} = \dfrac{1}{2}mv^2 = \dfrac{1}{2} m \omega^2 A^2 \sin^2 (\omega t + \varphi_0) \,,\]

\[ E_{\mathrm p} = \dfrac{1}{2} k x^2 = \dfrac{1}{2} k A^2 \cos^2 (\omega t + \varphi_0) \]. 

因此总机械能为:
\[ E = E_{\mathrm k} + E_{\mathrm k} = \dfrac{1}{2} m \omega^2 A^2 = \dfrac{1}{2} k A^2 \,.\]

## 简谐振动的合成
两个同方向, 同频率的简谐振动:
\[ x_1 = A_1 \cos (\omega t + \varphi_{10}) \,,\]

\[ x_2 = A_2 \cos (\omega t + \varphi_{20}) \,.\]

合成得到:
\[ x = x_1 + x_2 = A \cos (\omega t + \varphi_0) \,,\]

其中,
\[ A = \sqrt{A_1^2 + A_2^2 + 2 A_1 A_2 \cos(\varphi_{20} - \varphi_{10})} \,,\]

\[ \varphi_0 = \dfrac{A_1 \sin\varphi_{10} + A_2 \sin \varphi_{20}}{A_1 \cos\varphi_{10} + A_2 \cos \varphi_{20}} \,.\]

上式容易通过旋转矢量法证明.

# 简谐波
横波: 质元振动方向于波传播方向垂直. 如: 绳波
纵波: 质元振动方向于波传播方向平行. 如: 弹簧
## 平面简谐波函数
原点 $ O $ 处的振动方程 \[ y(0, t) = A \cos (\omega t + \varphi_0 ) \,,\]

考察 $ x $ 轴上任意一点 $ P $ 的振动. $ P $ 坐标为 $ x $, 波沿正向传播, 所以 $ O $ 点的振动状态经 $ \Delta t = \dfrac{x}{u} $ 时间传到 $ P $ 处, 即: $ t $ 时刻 $ P $ 点的振动状态与 $ O $ 点在 $ t - \Delta t $ 时刻的振动状态相同:
\[ y(x, t) = y(0, t - \Delta t) = A \cos \left[ \omega \left( t - \dfrac{x}{u} \right) + \varphi_0 \right] \,.\]

若波沿负向传播, $ P $ 的振动超前于 $ O $ 点, 即: $ P $ 在 $ t $ 时刻的振动状态和 $ O $ 在 $ t + \Delta t $ 时刻振动状态一致:
\[ y(x, t) = y(0, t + \Delta t) = A \cos \left[ \omega \left( t + \dfrac{x}{u} \right) + \varphi_0 \right] \,.\]

## 各参数关系
波长: $ \lambda $, 波速: $ u $, 周期: $ T $, 角频率: $ \omega $, 频率: $ f $

\[ \lambda = uT \,, \]

\[ \omega = \dfrac{2 \pi}{T} = 2 \pi f \,, \]

\[ u = \lambda f \,.\]

定义角波数 $ k $ 为 $ 2 \pi $ 空间内含有的完整波的个数:
\[ k = \dfrac{2 \pi}{\lambda} = \dfrac{\omega}{u} \,.\]

用角波数重写波函数:
\[ 
  \begin{align*}  
    y(x, t)  &= \color{red}{A \cos \left[ \omega \left( t + \dfrac{x}{u} \right) + \varphi_0 \right]} \\
    &= A \cos \left( \omega t + \dfrac{\omega}{u} x + \varphi_0 \right) \\
    &= A \cos \left( \omega t + \dfrac{\omega T}{u T} x + \varphi_0 \right) \\
    &= \color{red}{A \cos \left( \omega t + \dfrac{2 \pi}{\lambda} x + \varphi_0 \right)} \\
    &= \color{red}{A \cos \left( \omega t + k x + \varphi_0 \right)}
  \end{align*}  
\]

## 相位差
同一时刻 $ t $, 波线上坐标分别为 $ x_1 $ 和 $ x_2 $ 的两个质元, 它们的相位之差:
\[ \Delta \varphi = \dfrac{2\pi}{\lambda} (x_2 - x_1) = \dfrac{2 \pi}{\lambda} \Delta x \,.\]

> $ y_1(x_1, t) = A \cos\left[ \omega\left( t - \dfrac{x_1}{u} \right) + \varphi \right] = A \cos \left( \omega t - \dfrac{x_1 \omega}{u} + \varphi \right) = A \cos \varphi_1 $,
> $ y_2(x_2, t) = A \cos \left( \omega t - \dfrac{x_2 \omega}{u} + \varphi \right) = A \cos \varphi_2 $.
> $ \Delta \varphi = \varphi_1 - \varphi_2 = -\dfrac{\omega}{u}(x_1 - x_2) = \dfrac{2\pi}{\lambda} (x_2 - x_1)  $.

## 波的干涉
两列波在同一点叠加, 当两波相位差恒定, 根据同频率简谐振动的合成, 合成振幅 $ A $ 满足:
\[ A = \sqrt{A_1^2 + A_2^2 + 2 A_1 A_2 \cos \Delta \varphi} \,.\]

空间中, 任意一点振动强度与振幅平方成正比, $ I \propto A^2 $, 于是:
\[ I = I_1 + I_2 + 2\sqrt{I_1 I_2} \cos \Delta \varphi \,.\]

### 相位差
下面计算两波在一点处干涉的相位差,  

两波在 $ P $ 的振动分别为:
\[ y_1 = A_1 \cos \left[ \omega \left( t - \dfrac{r_1}{u} \right) + \varphi_{01}  \right] = A_1 \cos \left( \omega  t - \dfrac{2\pi}{\lambda} r_1 + \varphi_{01}  \right) = A_1 \cos \left( \omega  t - k r_1 + \varphi_{01}  \right)  \,,\]

\[ y_2 =  A_2 \cos \left( \omega  t - \dfrac{2\pi}{\lambda} r_2 + \varphi_{02}  \right) = A_2 \cos \left( \omega  t - k r_2 + \varphi_{02}  \right)  \,.\]

记 $ \varphi_1 =  - k r_1 + \varphi_{01} $, $ \varphi_2 =  - k r_2 + \varphi_{02} $, 于是:
\[ y_1 = A_1 \cos (\omega t + \varphi_1) \,,\]

\[ y_2 = A_2 \cos (\omega t + \varphi_2) \,.\]

\[ \Delta \varphi = \varphi_1 - \varphi_2 = -k (r_1 - r_2) + (\varphi_{01} - \varphi_{02}) = - \dfrac{2 \pi}{\lambda} \Delta r + \Delta \varphi \,.\]

### 干涉状态的判断
当 $ \Delta \varphi = k \cdot 2\pi $ 时, 即: 两波在 $ P $ 发生相长干涉, 叠加波的强度最大.


# 光的干涉
## 相干条件
振动方向相同, 振动频率相同, 初相位差稳定, 光波的叠加为相干叠加, 发生光的干涉.

## 光程
定义光程 $ L = n l $, 等于光在介质中通过的集合路径 $ l $ 与该介质折射率 $ n $ 的乘积. 光程表示光在介质中通过真实路程所需时间内, 在真空中所能传播的路程.

### 相位差
光路上两点的相位差, 只与真空波长 $ \lambda $ 和两点之间路程对应总光程差有关:
\[ \color{red}{\Delta \varphi = \dfrac{2 \pi}{\lambda} \Delta L} \,.\]

> 原介质折射率为 $ n $, 光传播路程 $ l $. 
> 在原光路中加入宽度为 $ e $, 折射率为 $ n' $ 的介质, 光程差变为: $ n (l - e) + n' e = n l + (n' - n) e $.
> 插入新介质前后光程差变化量为 $ (n' - n) e $. 当原介质为空气时: $ \Delta L = (n' - 1) e $.

从两个光源 $ S_1 $, $ S_2 $ 发出的相干光在一点 $ P $ 发生干涉. 第一束光从 $ S_1 $ 传播到 $ P $, 相位滞后了 $ \Delta \varphi_1 $, 所以第一束光在 $ P $ 的振动相位为 $ \varphi_1 = \varphi_{01} - \Delta \varphi_1 = \varphi_{01} - \dfrac{2 \pi}{\lambda} L_1 $. 同理: $ \varphi_2 = \varphi_{02} - \dfrac{2 \pi}{\lambda} L_2 $.

相位差为: \[ \Delta \varphi = \varphi_1 - \varphi_2 = \varphi_{01} - \varphi_{02} - \dfrac{2 \pi}{\lambda} (L_1 - L_2) = -\dfrac{2 \pi}{\lambda} \Delta L + \Delta \varphi \,.\]

## 杨氏双缝干涉
<center><img src="./pic/double-slit.svg" width=60% /></center>
空气介质中, 光程差为:
\[ \Delta L = (l_1 + r_1) - (l_2 + r_2) \,,\]

时常有 $ l_1 = l_2 $, 所以:
\[ \Delta L = r_1 - r_2 \,\]

作过一个双缝向另一条光线作垂线, 光程差可作近似处理:
\[ \Delta L = r_2 - r_1 = d \sin\theta  \,,\]

其中, $ \sin \theta $ 也可作近似处理:
\[ \sin \theta = \dfrac{x}{D} \,,\]

最终:
\[ \Delta L = d \dfrac{x}{D} \,.\]

### 明暗纹公式
光程差为半波长的偶数倍时, 即 $ \Delta L = 2 k \dfrac{\lambda}{2} = k \lambda $, 接收屏上得到明条纹, 所以 $ d\dfrac{x}{D} = k \lambda $:
\[ x = k \dfrac{D}{d} \lambda \,,\]

同理暗条纹位置:
\[ x = \dfrac{2k - 1}{2} \dfrac{D}{d} \lambda \,.\]

相邻两明条纹或暗条纹中心距离:
\[ \Delta x = \dfrac{D}{d} \lambda \,.\]

> 从 $ \Delta L = \delta = d \dfrac{x}{D} $ 可以看出: 若原光程差 $ \delta $ 变化 $ \Delta \delta $, 明/暗条纹也会在屏上移动 $ \Delta x = \Delta \delta $.

## 等倾干涉
<center><img src="./pic/Interference_of_a_parallel_plate.png" width=30% /></center>

当光从光疏射入光密时, 反射光会发生 $ \pi $ 的相位跃变, 所以有时要附加 $ \dfrac{\lambda}{2} $ 的光程差. 记从上到下三层的折射率分别为 $ n_1 $, $ n_2 $, $ n_3 $:
- 当 $ n_1 < n_2 < n_3 $ 或 $ n_1 > n_2 > n_3 $, 前者上下两个表面的反射光同时附加半波长的光程差, 而后者两反射都不附加, 所以最终反射情况完全相同, 无附加光程差:
\[ \Delta L = 2 d \sqrt{n_2^2 - n_1^2 \sin^2 i} \,.\]
- 当 $ n_1 < n_2 > n_3 $ 或 $ n_1 > n_2 < n_3 $, 两个反射面反射情况相反 (一个面附加, 另一个不附加), 所以最后要附加 $ \dfrac{\lambda}{2} $ 的光程差:
\[ \Delta L = 2 d \sqrt{n_2^2 - n_1^2 \sin^2 i} + \dfrac{\lambda}{2} \,.\]

透射光道理相同.

### 明暗环公式
同双缝干涉, 当光程差等于半波长的偶数倍时明环, 奇数倍则是暗环.

## 等厚干涉
通常时平行光垂直照射劈尖, 即左图. 取等倾干涉中入射角 $ i = 0 $, 即得到
\[ \Delta L = 2 d \sqrt{n_2^2 - n_1^2 \sin^2 i} = 2 d n_2 \,.\]
<center><img src="./pic/Equal_thickness_interference.png" width=70% /></center>
光程差 \[ \Delta L = 2 n e + \dfrac{\lambda}{2} \,, \] 

其中 $ e $ 为入射点的劈尖厚度.

同双缝干涉, 当光程差等于半波长的偶数倍时明纹, 奇数倍则是暗纹.

相邻两个明纹或暗纹的光程差为一个波长, $ 2 n e_k + \dfrac{\lambda}{2} = k \lambda $, $ 2 n e_{k + 1} + \dfrac{\lambda}{2} = (k + 1) \lambda $, 容易计算得, 相邻两明纹或暗纹对应的膜厚之差:
\[ \Delta e = \dfrac{\lambda}{2n} \,.\]

所以相邻明纹或暗纹**在表面上的间距**为 ($ \theta $ 为薄膜倾角):
\[ \Delta l = \dfrac{\Delta e}{\sin \theta} \approx \dfrac{\Delta e}{\theta} = \dfrac{\lambda}{2 n \theta} \,.\]

### 测量表面平整度
<center><img src="./pic/surface_test.svg" width=60% /></center>
亮纹处代表的深度一致, 可类比等高线. 如图, 若测试表面有凹坑, 深度为 $ \delta $, 就会导致凹坑处深度增加, 与右方某一条亮纹对应深度一样, 亮纹就会局部左移. 同理凸起就会使条纹向右偏.

将虚线圈中的部分放大, 有几何关系:
\[ \tan \theta \approx \theta = \dfrac{\delta}{b} \,. \]

因为 $ \Delta l = \dfrac{\lambda}{2 n e} $, $ \theta = \dfrac{\lambda}{2 n \Delta l} $, 代入即可求出凹坑深度:
\[ \delta = b \theta = \dfrac{b\lambda}{2 n \Delta l} \,.\]

可以看出, 从干涉图样中可以检查表面平整度.

# 狭义相对论
## 洛伦兹变换
$ S $ 系中点 $ (x, y, z, t) $, $ S' $ 系中点 $ (x', y', z', t') $. $ S' $ 系相对 $ S $ 的速度为 $ v $.
\[ 
  \begin{cases}
    x' = \dfrac{x-vt}{\sqrt{ 1- \dfrac{v^2}{c^2}}} \\
    y' = y \\
    z' = z \\
    t' = \dfrac{t - \dfrac{v}{c^2} x}{\sqrt{1-\dfrac{v^2}{c^2}}  }
  \end{cases}  
\]

记 $ \beta = \dfrac{v}{c} $, 由 $ S' $ 到 $ S $ 的逆变换为
\[ 
  \begin{cases}
    x = \dfrac{x'+vt}{\sqrt{ 1- \beta^2}} \\
    y = y' \\
    z = z' \\
    t = \dfrac{t' + \dfrac{\beta}{c} x}{\sqrt{1-\dfrac{v^2}{c^2}}  }
  \end{cases}  
\]

## 相对论效应
### 尺缩
相对与物体静止的系中观测到的物体长度称为固有长度, 记作 $ l_0 $. 则相对物体速度为 $ v = \beta c $ 的系中, 观测到的物体长度会变短:
\[ l = l_0 \sqrt{1-\beta^2} \]

### 钟慢
相对与物体静止的系中观测到的事件持续时间为固有时, 记作 $ \Delta t_0 $. 则相对于物体速度为 $ v = \beta c $ 的系中, 观测到的时间间隔会变长:
\[ \Delta t = \dfrac{\Delta t_0}{\sqrt{1 - \beta^2}} \]


## 质量, 动量, 能量关系
### 质量
相对与物体静止的系中观测到的物体质量称为静质量, 记作 $ m_0 $. 则相对于物体速度为 $ v = \beta c $ 的系中, 观测到的质量会变轻:
\[ m = \dfrac{m_0}{\sqrt{1 - \beta^2}} \]

### 动量
\[ \ve p = \dfrac{m_0}{\sqrt{1 - \beta^2}} \ve v \]

### 能量
观测到速度为 $ v $ 的物体, 其质量为 $ m $, 动能
\[ 
  \begin{align*}  
    E_{\mathrm k} &= m c^2 - m_0 c^2 \\
    &= \dfrac{m_0}{\sqrt{1 - \beta^2}}c^2 - m_0 c^2
  \end{align*}
\]

总能量
\[ 
    E = E_{\mathrm k} + m_0 c^2 = m c^2
\]

### 动质能关系
\[ E^2 = p^2 c^2 + m_0^2 c^{4} \]

对于一些微观粒子, 如光子和中微子, 其静质量为 $ 0 $. 于是有
\[ E = p c \]

# 量子物理基础
## 光子
每一个光子的能量为 \[ E = h \nu \]

由于 $ c = \lambda \nu $,
\[ E = \dfrac{h c}{\lambda} \]

光子静质量为 $ 0 $, 故动量
\[ p = \dfrac{E}{c} = \dfrac{h \nu}{c} = \dfrac{h}{\lambda} \]

## 光电效应
### 电子的最大初动能与截止电压
\[ e U_{\mathrm a} = \dfrac{1}{2} m v_{\mathrm m}^2 \]

### 爱因斯坦光电效应方程
\[ \dfrac{1}{2} m v_{\mathrm m}^2 = h \nu - W_0 = h \nu - h \nu_0 \]

其中, $ \nu_0 $ 被称为截止频率 (红限), $ W_0 $ 叫做逸出功.

## 康普顿散射
### 散射公式
\[ \lambda - \lambda_0 = \dfrac{h}{m_{\mathrm e} c} (1 - \cos \varphi) = \lambda_{\mathrm C} (1 - \cos \varphi) \]

## 玻尔氢原子模型
### 里德伯方程
\[ \dfrac{1}{\lambda} = R \left( \dfrac{1}{m^2} - \dfrac{1}{n^2} \right) \]

当 $ m $ 取不同值时, 得到不同谱线系.

### 跃迁理论
氢原子基态能量 $ E_1 = -13.6 \ \mathrm{eV} $, 第 $ n $ 能级轨道能量
\[ E_n = \dfrac{E_1}{n^2} \,,\]

如果第 $ x $ 能级的能量为 $ E_x $, 则该能级为
\[ x = \sqrt{\dfrac{E_1}{E_x}} \,.\]

电子从能级间跃迁, 放出的光波长由里德伯方程计算.

# 波粒二象性
## 物质波
### 德布罗意关系
\[ \nu = \dfrac{E}{h} = \dfrac{mc^2}{h} \]

\[ \lambda = \dfrac{h}{p} = \dfrac{h}{m v} \]

## 不确定原理
\[ \Delta x \Delta p_x \geqslant h \geqslant \dfrac{\hbar}{2} \]









