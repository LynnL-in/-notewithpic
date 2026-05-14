代入 $T=0.1$，可知在 $\zeta=1$ 时，必有 $\omega_n = \sqrt{10}K = 5\text{rad/s}$，解得开环增益 $K=2.5(\text{rad/s})^2$。因为 $\omega_n^2 = 1/(T_1T_2)$，而在 $\zeta=1$ 时，$T_1=T_2$，所以 $T_1=T_2=0.2\text{s}$，从而由式(3-26)算得调节时间 $t_s = 4.75T_1 = 0.95\text{s}$，满足指标要求。

根据 $\zeta=1$ 和 $\omega_n=5\text{rad/s}$，利用式(3-24)算得
$$t_r = \frac{1+1.5\zeta+\zeta^2}{\omega_n} = 0.70\text{s}$$

**5. 二阶系统的单位斜坡响应**

当输入信号为单位斜坡函数时，由式(3-11)知，系统输出量的拉氏变换式为
$$C(s) = \frac{\omega_n^2}{s^2(s^2+2\zeta\omega_n s + \omega_n^2)} = \frac{1}{s^2} - \frac{\omega_n}{s} + \frac{\omega_n(s+\zeta\omega_n) + (2\zeta^2-1)}{s^2+2\zeta\omega_n s + \omega_n^2}$$
对上式取拉氏反变换，可得不同 $\zeta$ 值下的二阶系统的单位斜坡响应。

(1) 欠阻尼单位斜坡响应
$$c(t) = t - \frac{2\zeta}{\omega_n} + \frac{1}{\omega_n\sqrt{1-\zeta^2}}e^{-\zeta\omega_n t}\sin(\omega_d t + 2\beta), \quad t \ge 0 \quad (3-27)$$
上式表明，欠阻尼二阶系统的单位斜坡响应由稳态分量 $c_{ss}(\infty)=t-2\zeta/\omega_n$ 和瞬态分量
$$c_{tt} = \frac{e^{-\zeta\omega_n t}}{\omega_d}\sin(\omega_d t + 2\beta)$$
组成。在 3-6 节将要指出，对于图 3-8 所示的单位反馈系统，误差响应为 $e(t)=r(t)-c(t)$。当时间 $t$ 趋于无穷时，误差响应 $e(t)$ 的稳态值为稳态误差，以 $e_{ss}(\infty)$ 标志。对于单位斜坡响应[式(3-27)]，其稳态误差为
$$e_{ss}(\infty) = t - c_{ss}(\infty) = \frac{2\zeta}{\omega_n} \quad (3-28)$$
误差响应为
$$e(t) = \frac{2\zeta}{\omega_n} - \frac{1}{\omega_d}e^{-\zeta\omega_n t}\sin(\omega_d t + 2\beta) \quad (3-29)$$
将上式对 $t$ 求导并令其为零，得误差响应的峰值时间
$$t_p = \frac{\pi-\beta}{\omega_d} \quad (3-30)$$
它正好等于单位阶跃响应的上升时间。将式(3-30)代入式(3-29)，得误差响应的峰值
$$e(t_p) = \frac{2\zeta}{\omega_n}\left(1 + \frac{1}{2\zeta}e^{-\zeta\omega_n t_p}\right)$$
从而误差响应的最大偏离量可表示为
$$e_m = e(t_p) - e_{ss}(\infty) = \frac{1}{\omega_n}e^{-\zeta\omega_n t_p} \quad (3-31)$$
若令 $D$ 表示误差响应对其稳态值的偏差，则由于

---

$$e(t) = \frac{2\zeta}{\omega_n}\left[1 - \frac{1}{2\zeta\sqrt{1-\zeta^2}}e^{-\zeta\omega_n t}\sin(\omega_d t + 2\beta)\right]$$
因此 $D$ 由下式限定：
$$D = \left| \frac{1}{2\zeta\sqrt{1-\zeta^2}}e^{-\zeta\omega_n t}\sin(\omega_d t + 2\beta) \right| \leqslant \frac{1}{2\zeta\sqrt{1-\zeta^2}}e^{-\zeta\omega_n t}$$
当取 $\zeta \leqslant 0.8$ 时，上式可进一步表示为 $D \leqslant 1.04e^{-\zeta\omega_n t}$。取 5%误差带，可得响应调节时间的近似表达式
$$t_s = \frac{3}{\zeta\omega_n} \quad (3-32)$$

稳态误差、峰值时间、最大偏离量和调节时间，表示了欠阻尼二阶系统的单位斜坡响应性能。图 3-18 给出了几种 $\zeta$ 值下的无因次误差响应曲线。由图及性能计算公式可以明显看出：减小系统的阻尼比 $\zeta$，可以减小系统的稳态误差和峰值时间，但是最大偏离量增大，调节时间会加长，从而使动态性能恶化。

[图 3-18 二阶系统单位斜坡误差响应曲线：横坐标为 $\omega_n t$，纵坐标为 $\omega_n e(t)$。图中展示了 $\zeta=1.0$（平滑下降至0.4）、$\zeta=0.5$（震荡衰减至0.4）、$\zeta=0.2$（大幅震荡衰减至0.4）的三条曲线。]

(2) 临界阻尼单位斜坡响应
由于 $\zeta=1$，故单位斜坡响应可表示为
$$c(t) = t - \frac{2}{\omega_n} + \frac{2}{\omega_n}\left(1 + \frac{1}{2}\omega_n t\right)e^{-\omega_n t}, \quad t \ge 0 \quad (3-33)$$
由上式可见，稳态误差
$$e_{ss}(\infty) = \frac{2}{\omega_n} \quad (3-34)$$
而误差响应
$$e(t) = \frac{2}{\omega_n}\left[1 - \left(1 + \frac{1}{2}\omega_n t\right)e^{-\omega_n t}\right], \quad t \ge 0 \quad (3-35)$$
若取 5%误差带，则利用数值解法可以求出误差响应的调节时间近似为
$$t_s = \frac{4.1}{\omega_n} \quad (3-36)$$

(3) 过阻尼单位斜坡响应
在 $\zeta > 1$ 时，输出量的拉氏变换式可写为
$$C(s) = \frac{1}{s^2} - \frac{\frac{2\zeta}{\omega_n}}{s} + \frac{\frac{2\zeta}{\omega_n}(s+\zeta\omega_n) + (2\zeta^2-1)}{\left[s+\omega_n(\zeta-\sqrt{\zeta^2-1})\right]\left[s+\omega_n(\zeta+\sqrt{\zeta^2-1})\right]}$$

---

所以得
$$c(t) = t - \frac{2\zeta}{\omega_n} + \frac{2\zeta^2-1+2\zeta\sqrt{\zeta^2-1}}{2\omega_n\sqrt{\zeta^2-1}}e^{-(\zeta-\sqrt{\zeta^2-1})\omega_n t}$$
$$- \frac{2\zeta^2-1-2\zeta\sqrt{\zeta^2-1}}{2\omega_n\sqrt{\zeta^2-1}}e^{-(\zeta+\sqrt{\zeta^2-1})\omega_n t}, \quad t \ge 0 \quad (3-37)$$
显然，稳态误差
$$e_{ss}(\infty) = \frac{2\zeta}{\omega_n} \quad (3-38)$$
误差响应
$$e(t) = \frac{2\zeta}{\omega_n} \left[ 1 - \frac{2\zeta^2-1+2\zeta\sqrt{\zeta^2-1}}{4\zeta\sqrt{\zeta^2-1}}e^{-(\zeta-\sqrt{\zeta^2-1})\omega_n t} \right.$$
$$\left. + \frac{2\zeta^2-1-2\zeta\sqrt{\zeta^2-1}}{4\zeta\sqrt{\zeta^2-1}}e^{-(\zeta+\sqrt{\zeta^2-1})\omega_n t} \right] \quad (3-38)$$

一般来说，在单位斜坡输入信号作用下，过阻尼二阶系统的动态性能指标只能用计算机求得。

例 3-3 控制系统如图 3-19 所示。图中，输入信号 $\theta_i(t)=t$，放大器增益 $K_a$ 分别取为 13.5，200 和 1500。试分别写出系统的误差响应表达式，并估算其性能指标。

[图 3-19 控制系统结构图：输入 $\theta_i(s)$ 经过加法器（输出 $\theta_e(s)$），进入传递函数 $5K_a / s(s+34.5)$，输出 $\theta_o(s)$，并反馈回加法器。]

解 由图知，系统开环传递函数为
$$G(s) = \frac{5K_a}{s(s+34.5)} = \frac{\omega_n^2}{s(s+2\zeta\omega_n)}$$
因而，$\zeta=17.25/\sqrt{5K_a}$，$\omega_n=\sqrt{5K_a}$。
当 $K_a=13.5$ 时，算得 $\zeta=2.1$，$\omega_n=8.2\text{rad/s}$，属过阻尼二阶系统。由式(3-38)可得
$$\theta_e(t) = 0.51(1-e^{-2.08t} + 0.004e^{-32.4t}) \approx 0.51(1-e^{-2.08t})$$
此时，系统等效为一阶系统，其等效时间常数 $T=0.48\text{s}$。因而性能指标：$t_r=1.06\text{s}, t_s=1.44\text{s}, \theta_{ess}(\infty)=0.51\text{rad}$。
当 $K_a=200$ 时，算得 $\zeta=0.55$，$\omega_n=31.6\text{rad/s}$，属于欠阻尼二阶系统。由式(3-29)可得
$$\theta_e(t) = 0.035 - 0.038e^{-17.4t}\sin(26.4t+113^\circ)$$
于是，由式(3-30)~(3-32)和式(3-28)算出性能指标为：$t_p=0.08\text{s}, \theta_{em}=0.008\text{rad}, t_s=0.17\text{s}, \theta_{ess}(\infty)=0.035\text{rad}$。
当 $K_a=1500$ 时，算得 $\zeta=0.2$ 和 $\omega_n=86.6\text{rad/s}$，仍属于欠阻尼二阶系统，其误差响应
$$\theta_e(t) = 0.0046 - 0.012e^{-17.3t}\sin(84.9t+157^\circ)$$
性能指标为：$t_p=0.02\text{s}, \theta_{em}=0.008\text{rad}, t_s=0.17\text{s}, \theta_{ess}(\infty)=0.0046\text{rad}$。