## Page 80

[Diagram Description: Figure 3-7, Position Control System Block Diagram. The diagram shows a feedback control loop. The input $\Theta_i(s)$ enters a summing junction. The output of the summing junction is multiplied by $K_s$, then $K_a$, then a block $\frac{1}{L_as+R_a}$, then $C_m$, then $\frac{1}{Js^2+fs}$, and finally $\frac{1}{i}$ to produce the output $\Theta_o(s)$. A feedback path from the output $\Theta_o(s)$ goes through a block $C_e$ back to the summing junction.]

**图 3-7 位置控制系统结构图**

式中，$L_a$ 和 $R_a$ 分别为电动机电枢绕组的电感和电阻；$C_m$ 为电动机的转矩系数；$C_e$ 为与电动机反电势有关的比例系数；$K_s$ 为桥式电位器传递函数；$K_a$ 为放大器增益；$i$ 为减速器速比；$J$ 和 $f$ 分别为折算到电动机轴上的总转动惯量和总黏性摩擦系数。如果略去电枢电感 $L_a$，且令
$$K_1 = K_s K_a C_m / i R_a, \quad F = f + C_m C_e / R_a$$
其中，$K_1$ 称为增益；$F$ 称为阻尼系数。那么在不考虑负载力矩的情况下，位置控制系统的开环传递函数可以简化为
$$G(s) = \frac{K}{s(T_m s + 1)} \quad (3-8)$$
其中，$K = K_1 / F$，称为开环增益；$T_m = J/F$，称为机电时间常数。相应的闭环传递函数是
$$\Phi(s) = \frac{\Theta_o(s)}{\Theta_i(s)} = \frac{K}{T_m s^2 + s + K} \quad (3-9)$$
显然，上述系统闭环传递函数对应如下二阶运动微分方程：
$$T_m \frac{d^2 \theta_o(t)}{dt^2} + \frac{d \theta_o(t)}{dt} + K \theta_o(t) = K \theta_i(t) \quad (3-10)$$
所以图 3-6 所示位置控制系统在简化情况下是一个二阶系统。
为了使研究的结果具有普遍的意义，可将式(3-9)表示为标准形式：
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{\omega_n^2}{s^2 + 2\zeta \omega_n s + \omega_n^2} \quad (3-11)$$

[Diagram Description: Figure 3-8, Standard Second-Order System Block Diagram. A summing junction takes input $R(s)$ and subtracts a feedback signal to produce $E(s)$. $E(s)$ is multiplied by $\frac{\omega_n^2}{s(s+2\zeta\omega_n)}$ to produce output $C(s)$. The output $C(s)$ is fed back to the summing junction.]

**图 3-8 标准形式的二阶系统结构图**

相应的结构图如图 3-8 所示。图中
$$\omega_n = \sqrt{\frac{K}{T_m}} \text{——自然频率(或无阻尼振荡频率)}$$
$$\zeta = \frac{1}{2\sqrt{T_m K}} \text{——阻尼比(或相对阻尼系数)}$$
令式(3-11)的分母多项式为零，二阶系统的特征方程
$$s^2 + 2\zeta \omega_n s + \omega_n^2 = 0 \quad (3-12)$$
其两个根(闭环极点)为
$$s_{1,2} = -\zeta \omega_n \pm \omega_n \sqrt{\zeta^2 - 1} \quad (3-13)$$
显然，二阶系统的时间响应取决于 $\zeta$ 和 $\omega_n$ 这两个参数。下面将根据式(3-11)这一数学

---

## Page 81

模型，研究二阶系统时间响应及动态性能指标的求法。应当指出，对于结构和功用不同的二阶系统，$\zeta$ 和 $\omega_n$ 的物理含义是不同的。

**2. 二阶系统的单位阶跃响应**

式(3-13)表明，二阶系统特征根的性质取决于 $\zeta$ 值的大小。若 $\zeta < 0$，则二阶系统具有两个正实部的特征根，其单位阶跃响应为
$$c(t) = 1 - \frac{e^{-\zeta \omega_n t}}{\sqrt{1-\zeta^2}} \sin(\omega_n \sqrt{1-\zeta^2} t + \beta); \quad -1 < \zeta < 0, \quad t > 0$$
式中，$\beta = \arctan(\sqrt{1-\zeta^2}/\zeta)$。或者
$$c(t) = 1 + \frac{e^{-(\zeta + \sqrt{\zeta^2-1})\omega_n t}}{2\sqrt{\zeta^2-1}(\zeta + \sqrt{\zeta^2-1})} - \frac{e^{-(\zeta - \sqrt{\zeta^2-1})\omega_n t}}{2\sqrt{\zeta^2-1}(\zeta - \sqrt{\zeta^2-1})}; \quad \zeta < -1, \quad t > 0$$
由于阻尼比 $\zeta$ 为负，指数因子具有正幂指数，因此系统的动态过程为发散正弦振荡或单调发散的形式，从而表明 $\zeta < 0$ 的二阶系统是不稳定的。如果 $\zeta = 0$，则特征方程有一对纯虚根，$s_{1,2} = \pm j\omega_n$，对应于 $s$ 平面轴上一对共轭极点，可以算出系统的阶跃响应为等幅振荡，此时系统相当于无阻尼情况。如果 $0 < \zeta < 1$，则特征方程有一对具有负实部的共轭复根，$s_{1,2} = -\zeta \omega_n \pm j\omega_n \sqrt{1-\zeta^2}$，对应于 $s$ 平面左半部的共轭复数极点，相应的阶跃响应为衰减振荡过程，此时系统处于欠阻尼情况。如果 $\zeta = 1$，则特征方程具有两个相等的负实根，$s_{1,2} = -\omega_n$，对应于 $s$ 平面负实轴上的两个相等极点，相应的阶跃响应非周期地趋于稳态输出，此时系统处于临界阻尼情况。如果 $\zeta > 1$，则特征方程具有两个不相等的负实根，$s_{1,2} = -\zeta \omega_n \pm \omega_n \sqrt{\zeta^2 - 1}$，对应于 $s$ 平面负实轴上的两个不等实极点，相应的单位阶跃响应也是非周期地趋于稳态输出，但响应速度比临界阻尼情况缓慢，因此称为过阻尼情况。上述各种情况的闭环极点分布，如图 3-9 所示。

[Diagram Description: Figure 3-9, Distribution of closed-loop poles of second-order systems. Six sub-figures (a) through (f) show the complex $s$-plane with axes $j$ (imaginary) and $\sigma$ (real).
(a) $\zeta < -1$: Two poles on the positive real axis.
(b) $-1 < \zeta < 0$: Two complex conjugate poles in the right half-plane.
(c) $\zeta = 0$: Two purely imaginary poles on the $j$ axis.
(d) $0 < \zeta < 1$: Two complex conjugate poles in the left half-plane.
(e) $\zeta = 1$: Two identical poles on the negative real axis at $-\omega_n$.
(f) $\zeta > 1$: Two distinct poles on the negative real axis.]

**图 3-9 二阶系统的闭环极点分布**

---

## Page 82

由此可见，$\zeta$ 值的大小决定了系统的阻尼程度。对于图 3-6 所示的位置控制系统，有
$$\zeta = \frac{1}{2\sqrt{T_m K}} = \frac{F}{2\sqrt{J K_1}}$$
式中，$F_c = 2\sqrt{J K_1}$ 为 $\zeta = 1$ 时的阻尼系数。所以，$\zeta$ 是阻尼系数 $F$ 与临界阻尼系数 $F_c$ 之比，故称为阻尼比或相对阻尼系数。
下面分别研究欠阻尼、临界阻尼、过阻尼二阶系统的单位阶跃响应。
(1) 欠阻尼($0 < \zeta < 1$)二阶系统的单位阶跃响应
若令 $\sigma = \zeta \omega_n, \omega_d = \omega_n \sqrt{1-\zeta^2}$，则有
$$s_{1,2} = -\sigma \pm j\omega_d$$
式中，$\sigma$ 称为衰减系数，$\omega_d$ 叫做阻尼振荡频率。
当 $R(s) = 1/s$ 时，由式(3-11)得
$$C(s) = \frac{\omega_n^2}{s^2 + 2\zeta \omega_n s + \omega_n^2} \cdot \frac{1}{s} = \frac{1}{s} - \frac{s + \zeta \omega_n}{(s + \zeta \omega_n)^2 + \omega_d^2} - \frac{\zeta \omega_n}{(s + \zeta \omega_n)^2 + \omega_d^2}$$
对上式取拉氏反变换，求得单位阶跃响应为
$$c(t) = 1 - e^{-\zeta \omega_n t} \left[ \cos \omega_d t + \frac{\zeta}{\sqrt{1-\zeta^2}} \sin \omega_d t \right]$$
$$= 1 - \frac{1}{\sqrt{1-\zeta^2}} e^{-\zeta \omega_n t} (\sqrt{1-\zeta^2} \cos \omega_d t + \zeta \sin \omega_d t) \quad (3-14)$$
$$= 1 - \frac{1}{\sqrt{1-\zeta^2}} e^{-\zeta \omega_n t} \sin(\omega_d t + \beta), \quad t \ge 0$$
式中，$\beta = \arctan(\sqrt{1-\zeta^2}/\zeta)$，或者 $\beta = \arccos \zeta$。
式(3-14)表明，欠阻尼二阶系统的单位阶跃响应由两部分组成：稳态分量为 1，表明系统在单位阶跃函数作用下不存在稳态位置误差；瞬态分量为阻尼正弦振荡项，其振荡频率为 $\omega_d$，故称为阻尼振荡频率。由于瞬态分量衰减的快慢程度取决于包络线 $1 \pm e^{-\zeta \omega_n t} / \sqrt{1-\zeta^2}$ 收敛的速度，当 $\zeta$ 一定时，包络线的收敛速度又取决于指数函数 $e^{-\zeta \omega_n t}$ 的幂，所以 $\sigma = \zeta \omega_n$ 称为衰减系数。
若 $\zeta = 0$，则二阶系统无阻尼时的单位阶跃响应为
$$c(t) = 1 - \cos \omega_n t, \quad t \ge 0 \quad (3-15)$$
这是一条平均值为 1 的正、余弦形式的等幅振荡，其振荡频率为 $\omega_n$，故可称为无阻尼振荡频率。由图 3-6 位置控制系统可知，$\omega_n$ 由系统本身的结构参数 $K$ 和 $T_m$ 或 $K_1$ 和 $J$ 确定，故 $\omega_n$ 常称为自然频率。
应当指出，实际的控制系统通常有一定的阻尼比，因此不可能通过实验方法测得 $\omega_n$，而只能测得 $\omega_d$，其值小于自然频率 $\omega_n$。只有在 $\zeta = 0$ 时，才有 $\omega_d = \omega_n$。当阻尼比 $\zeta$ 增大时，阻尼振荡频率 $\omega_d$ 将减小。如果 $\zeta > 1$，$\omega_d$ 将不存在，系统的响应不再出现振荡。但是，为了便于分析和叙述，$\sigma$ 和 $\omega_d$ 的符号和名称在 $\zeta > 1$ 时仍将沿用下去。