## Page 86

[Diagram Description: A graph showing the unit step response $c(t)$ of an underdamped second-order system. The x-axis represents $\omega_n t$ and the y-axis represents $c(t)$. The curve starts at 0, rises above 1, oscillates, and settles at $c_{ss} = 1$. Two exponential decay curves, $1 \pm \frac{e^{-\zeta \omega_n t}}{\sqrt{1-\zeta^2}}$, act as envelopes for the oscillation. Key points marked include the peak time, overshoot, and the settling time.]

**图 3-13 欠阻尼二阶系统 $c(t)$ 的一对包络线**

若选取误差带 $\Delta=0.02$，则有
$$t_s = \frac{4.4}{\zeta \omega_n} = \frac{4.4}{\sigma} \quad (3-23)$$

上式表明，调节时间与闭环极点的实部数值成反比。闭环极点距虚轴的距离越远，系统的调节时间越短。由于阻尼比主要根据对系统超调量的要求来确定，所以调节时间主要由自然频率决定。若能保持阻尼比不变而加大自然频率值，则可以在不改变超调量的情况下缩短调节时间。

从上述各项动态性能指标的计算式可以看出，各指标之间是有矛盾的。比方说，上升时间和超调量，即响应速度和阻尼程度，不能同时达到满意的结果。这是因为在如图 3-8 所示的二阶系统中，$\omega_n = \sqrt{K/T_m}$ 及 $\zeta = 1/2\sqrt{T_m K}$，其中机电时间常数 $T_m$ 是一个不可调的确定参数。当增大开环增益 $K$ 时，可以加大自然频率 $\omega_n$，提高了系统的响应速度，但同时减小了阻尼比 $\zeta$，使得系统的阻尼程度减小。因此，对于既要增强系统的阻尼程度，又要使系统具有较高响应速度的二阶控制系统设计，需要采取合理的折中方案或补偿方案，才能达到设计的目的。

**例 3-1** 设系统结构图如图 3-14 所示，若要求系统具有性能指标 $\sigma_p=0.2, t_p=1\text{s}$，试确定系统参数 $K$ 和 $\tau$，并计算单位阶跃响应的特征量 $t_r$ 和 $t_s$。

[Diagram Description: A block diagram showing a unity feedback system. The forward path contains a block with transfer function $\frac{K}{s(s+1)}$ and a feedback path containing a block with transfer function $1+\tau s$. The input is $R(s)$ and the output is $C(s)$.]

**图 3-14 控制系统结构图**

**解** 由图 3-14 知，系统闭环传递函数为
$$\frac{C(s)}{R(s)} = \frac{K}{s^2 + (1+K\tau)s + K}$$
与传递函数标准式(3-11)相比，可得

---

## Page 87

$$\omega_n = \sqrt{K}, \quad \zeta = \frac{1+K\tau}{2\sqrt{K}}$$

由 $\zeta$ 与 $\sigma\%$ 的关系式(3-21)，解得
$$\zeta = \frac{\ln(1/\sigma_p)}{\sqrt{\pi^2 + \left(\ln\frac{1}{\sigma_p}\right)^2}} = 0.46$$

再由峰值时间计算式(3-20)，算出
$$\omega_n = \frac{\pi}{t_p\sqrt{1-\zeta^2}} = 3.54\text{rad/s}$$

从而解得
$$K = \omega_n^2 = 12.53(\text{rad/s})^2, \quad \tau = \frac{2\zeta\omega_n - 1}{K} = 0.18\text{s}$$

由于
$$\beta = \arccos\zeta = 1.09\text{rad}, \quad \omega_d = \omega_n\sqrt{1-\zeta^2} = 3.14\text{rad/s}$$

故由式(3-19)和式(3-22)计算得
$$t_r = \frac{\pi-\beta}{\omega_d} = 0.65\text{s}, \quad t_s = \frac{3.5}{\zeta\omega_n} = 2.15\text{s}$$

若取误差带 $\Delta=0.02$，则调节时间为
$$t_s = \frac{4.4}{\zeta\omega_n} = 2.70\text{s}$$

### 4. 过阻尼二阶系统的动态过程分析

由于过阻尼系统响应缓慢，故通常不希望采用过阻尼系统。但是，这并不排除在某些情况下，例如在低增益、大惯性的温度控制系统中，需要采用过阻尼系统。此外，在有些不允许时间响应出现超调，而又希望响应速度较快的情况下，例如在指示仪表系统和记录仪表系统中，需要采用临界阻尼系统。特别是，有些高阶系统的时间响应往往可用过阻尼二阶系统的时间响应来近似，因此研究过阻尼二阶系统的动态过程分析，有较大的工程意义。

当阻尼比 $\zeta>1$，且初始条件为零时，二阶系统的单位阶跃响应如式(3-17)所示。显然，在动态性能指标中，只有上升时间和调节时间才有意义。然而，式(3-17)是一个超越方程，无法根据各动态性能指标的定义求出其准确计算公式。目前工程上采用的方法，仍然是利用数值解法求出不同 $\zeta$ 值下的无因次时间，然后制成曲线以供查用；或者，利用曲线拟合合法给出近似计算公式。

(1) 上升时间 $t_r$ 的计算
根据上升时间的第一种定义方法，参照式(3-16)和式(3-17)，可得无因次上升时间 $\omega_n t_r$ 与阻尼比 $\zeta$ 的关系曲线，如图 3-15 所示。图中曲线可用下式近似描述：

---

## Page 88

$$t_r = \frac{1+1.5\zeta+\zeta^2}{\omega_n} \quad (3-24)$$

(2) 调节时间 $t_s$ 的计算
根据式(3-17)，令 $T_1/T_2$ 为不同值，可以画出相应的无因次调节时间 $t_s/T_1$，如图 3-16 所示。图中阻尼比 $\zeta$ 为参变量。由于
$$s^2 + 2\zeta\omega_n s + \omega_n^2 = (s+1/T_1)(s+1/T_2)$$
因而 $\zeta$ 与自变量 $T_1/T_2$ 的关系式为
$$\zeta = \frac{1+T_1/T_2}{2\sqrt{T_1/T_2}} \quad (3-25)$$

[Diagram Description: Figure 3-15 shows a graph of $\omega_n t_r$ vs $\zeta$. The curve starts at approximately 3 for $\zeta=1$ and increases linearly to about 13 at $\zeta=3$. Figure 3-16 shows a graph of $t_s/T_1$ vs $T_1/T_2$ for different values of $\zeta$ (1.1, 1.2, 1.3, 1.4, 1.5, 1.6, 1.7, 1.8, 1.9, 2.0, 2.1, 2.2). The curves show the settling time characteristics for an overdamped second-order system.]

**图 3-15 过阻尼二阶系统 $\omega_n t_r$ 与 $\zeta$ 的关系曲线**
**图 3-16 过阻尼二阶系统的调节时间特性**

当 $\zeta>1$ 时，由已知的 $T_1$ 及 $T_2$ 值在图 3-16 上可以查出相应的 $t_s$；若 $T_1 \ge 4T_2$，即过阻尼二阶系统第二个闭环极点的数值比第一个闭环极点的数值大四倍以上时，系统可等效为具有 $-1/T_1$ 闭环极点的一阶系统，此时 $t_s=3T_1$，相对误差不超过 10%。当 $\zeta=1$ 时，由图 3-16 可见，临界阻尼系统的调节时间
$$t_s = 4.75T_1, \quad \zeta=1 \quad (3-26)$$

[Diagram Description: Figure 3-17 shows a block diagram of an angular follow-up system. The input is $\Theta_i(s)$, the output is $\Theta_o(s)$. The forward path contains a block $\frac{K}{s(Ts+1)}$.]

**图 3-17 角度随动系统结构图**

**例 3-2** 设角度随动系统如图 3-17 所示，中 $K$ 为开环增益，$T=0.1\text{s}$ 为伺服电动机时间常数。若要求系统的单位阶跃响应无超调，且调节时间 $t_s < 1\text{s}$，问 $K$ 应取多大？此时系统的上升时间 $t_r$ 等于多少？

**解** 根据题意并考虑有尽快的响应速度，应取阻尼比 $\zeta=1$。由图 3-17 得闭环特征方程为
$$s^2 + \frac{1}{T}s + \frac{K}{T} = 0$$