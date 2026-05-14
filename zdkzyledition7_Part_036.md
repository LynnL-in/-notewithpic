设二阶系统运动方程为
$$a_0\ddot{c}(t) + a_1\dot{c}(t) + a_2c(t) = b_2r(t)$$
对上式取拉氏变换，并考虑初始条件，可得
$$C(s) = \frac{b_2}{a_0s^2 + a_1s + a_2}R(s) + \frac{a_0[c(0)s + \dot{c}(0)] + a_1c(0)}{a_0s^2 + a_1s + a_2}$$
若 $a_2=b_2$，则上式可写为标准形式：
$$C(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}R(s) + \frac{c(0)(s + 2\zeta\omega_n) + \dot{c}(0)}{s^2 + 2\zeta\omega_n s + \omega_n^2} \quad (3-55)$$
式中，$\omega_n = \sqrt{a_2/a_0}$， $2\zeta\omega_n = a_1/a_0$。对上式取拉氏变换，得
$$c(t) = c_1(t) + c_2(t)$$
式中，$c_1(t)$为零初始条件响应分量；$c_2(t)$为非零初始条件响应分量。当 $0 < \zeta < 1$ 时，有
$$c_2(t) = \sqrt{c^2(0) + \left[ \frac{c(0)\zeta\omega_n + \dot{c}(0)}{\omega_n\sqrt{1-\zeta^2}} \right]^2} e^{-\zeta\omega_n t} \sin(\omega_d t + \theta), \quad t \ge 0 \quad (3-56)$$
式中
$$\theta = \arctan \frac{\omega_n\sqrt{1-\zeta^2}}{\dot{c}(0)/c(0) + \zeta\omega_n}$$
若 $\zeta=0$，则有
$$c_2(t) = \sqrt{c^2(0) + [\dot{c}(0)/\omega_n]^2} \sin(\omega_n t + \theta_1), \quad t \ge 0 \quad (3-57)$$
式中
$$\theta_1 = \arctan \frac{\omega_n}{\dot{c}(0)/c(0)}$$
由式(3-56)及式(3-57)可见，欠阻尼二阶系统的非零初始条件响应分量 $c_2(t)$，为阻尼正弦振荡过程。其初始幅值及相位与初始条件有关，振荡性与阻尼比$\zeta$有关，$\zeta$值越大，振荡性越弱；反之，$\zeta$值越小，振荡性越强。响应分量衰减速率取决于乘积$\zeta\omega_n$。当$\zeta=0$时，$c_2(t)$为不衰减等幅振荡，幅值与初始条件有关。

由上述分析可以看出，关于响应分量 $c_2(t)$ 所得各项结论与分析响应分量 $c_1(t)$ 所得的相应结论一致。因此，若仅限于分析系统自身固有特性，可不考虑非零初始条件对响应过程的影响。

### 3-4 高阶系统的时域分析

在控制工程中，几乎所有的控制系统都是高阶系统，即用高阶微分方程描述的系统。对于不能用一、二阶系统近似的高阶系统来说，其动态性能指标的确定是比较复杂的。工程上常采用闭环主极点的概念对高阶系统进行近似分析，或直接应用 MATLAB 软件进行高阶系统分析。

---

#### 1. 三阶系统的单位阶跃响应

下面在 $s$ 左半平面具有一对共轭复数极点和一个实极点的分布模式为例，分析三阶系统的单位阶跃响应。其闭环传递函数的一般形式为
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{\omega_n^2 s_0}{(s + s_0)(s^2 + 2\zeta\omega_n s + \omega_n^2)} \quad (3-58)$$
式中，$-s_0$ 为三阶系统的闭环实数极点。当输入为单位阶跃函数，且 $0 < \zeta < 1$ 时，输出量的拉氏变换为
$$C(s) = \frac{1}{s} + \frac{A}{s + s_0} + \frac{B}{s + \zeta\omega_n - j\omega_n\sqrt{1-\zeta^2}} + \frac{C}{s + \zeta\omega_n + j\omega_n\sqrt{1-\zeta^2}}$$
式中
$$A = \frac{-\omega_n^2}{s_0^2 - 2\zeta\omega_n s_0 + \omega_n^2}$$
$$B = \frac{s_0(2\zeta\omega_n - s_0) - js_0(2\zeta^2\omega_n - \zeta s_0 - \omega_n)/\sqrt{1-\zeta^2}}{2[(2\zeta^2\omega_n - \zeta s_0 - \omega_n)^2 + (2\zeta\omega_n - s_0)^2(1-\zeta^2)]}$$
$$C = \frac{s_0(2\zeta\omega_n - s_0) + js_0(2\zeta^2\omega_n - \zeta s_0 - \omega_n)/\sqrt{1-\zeta^2}}{2[(2\zeta^2\omega_n - \zeta s_0 - \omega_n)^2 + (2\zeta\omega_n - s_0)^2(1-\zeta^2)]}$$
对上式取拉氏变换，且令 $b=s_0/(\zeta\omega_n)$，则有
$$c(t) = 1 + Ae^{-s_0t} + 2\text{Re}B \cdot e^{-\zeta\omega_n t} \cos\omega_n\sqrt{1-\zeta^2}t - 2\text{Im}B \cdot e^{-\zeta\omega_n t} \sin\omega_n\sqrt{1-\zeta^2}t, \quad t \ge 0$$
式中 $A = -\frac{1}{b\zeta^2(b-2)+1}$， $\text{Re}B = \frac{b\zeta^2(b-2)}{2[b\zeta^2(b-2)+1]}$， $\text{Im}B = \frac{b\zeta^2(b-2)+1}{2[b\zeta^2(b-2)+1]\sqrt{1-\zeta^2}}$
将上述系数代入 $c(t)$ 表达式，经整理得式(3-58)所示三阶系统在 $0 < \zeta < 1$ 时的单位阶跃响应：
$$c(t) = 1 - \frac{1}{b\zeta^2(b-2)+1}e^{-s_0t} - \frac{e^{-\zeta\omega_n t}}{b\zeta^2(b-2)+1} \left[ b\zeta^2(b-2)\cos\omega_n\sqrt{1-\zeta^2}t + \frac{b\zeta^2(b-2)+1}{\sqrt{1-\zeta^2}}\sin\omega_n\sqrt{1-\zeta^2}t \right], \quad t \ge 0 \quad (3-59)$$
当 $\zeta=0.5, b>1$ 时，三阶系统的单位阶跃响应曲线如图 3-26 所示。在式(3-59)中，由于
$$b\zeta^2(b-2)+1 = \zeta^2(b-1)^2 + (1-\zeta^2) > 0$$
所以，不论闭环实数极点在共轭复数极点的左边或右边，即 $b$ 不论大于 1 或是小于 1，$e^{-s_0t}$ 项的系数总是负数。因此，实数极点 $s = -s_0$ 可使单位阶跃响应的超调量下降，并使调节时间增加。

由图 3-26 可见，当系统阻尼比 $\zeta$ 不变时，随着实数极点向虚轴方向移动，即随着 $b$ 值的下降，响应的超调量不断下降，而峰值时间、上升时间和调节时间则不断加长。当 $b<1$ 时，即闭环实数极点的数值小于或等于闭环复数极点的实部数值时，三阶系统将表现出明显的过阻尼特性。

---

**图 3-26 说明：** 该图展示了三阶系统单位阶跃响应曲线（$\zeta=0.5$）。横坐标为 $\omega_n t$，纵坐标为 $c(t)$。图中绘制了多条曲线，分别对应 $b=\infty, b=4, b=2, b=1$ 的情况。曲线显示随着 $b$ 值的减小，响应的超调量逐渐减小，但上升时间变长。

**图 3-27 说明：** 该图展示了控制系统结构图。输入信号 $R(s)$ 进入一个求和点，输出信号 $C(s)$ 经过反馈环节 $H(s)$ 后反馈回求和点。前向通道包含传递函数 $G(s)$。

#### 2. 高阶系统的单位阶跃响应

研究图 3-27 所示系统，其闭环传递函数为
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{G(s)}{1+G(s)H(s)} \quad (3-60)$$
在一般情况下，$G(s)$ 和 $H(s)$ 都是 $s$ 的多项式之比，故式(3-60)可以写为
$$\Phi(s) = \frac{M(s)}{D(s)} = \frac{b_0s^m + b_1s^{m-1} + \dots + b_{m-1}s + b_m}{a_0s^n + a_1s^{n-1} + \dots + a_{n-1}s + a_n}, \quad m < n \quad (3-61)$$
利用 MATLAB 软件可以方便地求出式(3-61)所示高阶系统的单位阶跃响应，即先建立其高阶系统模型，再直接调用 `step` 命令即可。一般命令语句如下：
`sys=tf([b0 b1 b2 b3 ... bm], [a0 a1 a2 a3 ... an]);` % 高阶系统建模
`step(sys);` % 计算单位阶跃响应

其中，$b_0, b_1, b_2, b_3, \dots, b_m$ 表示式(3-61)对应的分子多项式系数；$a_0, a_1, a_2, a_3, \dots, a_n$ 表示式(3-61)对应的分母多项式系数。

当采用解析法求解高阶系统的单位阶跃响应时，应将式(3-61)的分子多项式和分母多项式进行因式分解，再进行拉氏变换。这种分解方法，可采用高次方程的近似求根法，也可以使用 MATLAB 中的 `tf2zp` 命令。因此，式(3-61)必定可以表示为如下因式的乘积形式：
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{M(s)}{D(s)} = \frac{K\prod_{i=1}^{m}(s-z_i)}{\prod_{i=1}^{n}(s-s_i)} \quad (3-62)$$
式中，$K=b_0/a_0$；$z_i$ 为 $M(s)=0$ 之根，称为闭环零点；$s_i$ 为 $D(s)=0$ 之根，称为闭环极点。