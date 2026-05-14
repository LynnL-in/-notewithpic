==Start of PDF==

### Page 1

[Diagram Description: Figure (a) shows a block diagram for a Mars rover steering control system. It consists of a "Steering Throttle" input leading to a "Power Transmission and Control System" block, which outputs "Right Wheel Torque" and "Left Wheel Torque" to a "Rover" block, resulting in a "Speed Difference of Two Wheels" and finally the "Rover Direction" $C(s)$. Figure (b) shows a structural block diagram: an input $R(s)$ (Expected Direction) enters a summing junction, followed by a controller $G_c(s) = \frac{s+a}{s+1}$, then a power transmission and rover system $G_0(s) = \frac{K_1}{s(s+2)(s+5)}$, resulting in output $C(s)$.]

**图 3-57 火星漫游车转向控制系统**

**解** 由图 3-57(b) 可知，闭环特征方程为
$$1 + G_c(s)G_0(s) = 0$$
即
$$1 + \frac{K_1(s+a)}{s(s+1)(s+2)(s+5)} = 0$$
于是有
$$s^4 + 8s^3 + 17s^2 + (10 + K_1)s + aK_1 = 0$$
为了确定 $K_1$ 和 $a$ 的稳定区域，建立如下劳斯表：

| | | | |
| :--- | :--- | :--- | :--- |
| $s^4$ | $1$ | $17$ | $aK_1$ |
| $s^3$ | $8$ | $10 + K_1$ | |
| $s^2$ | $\frac{126 - K_1}{8}$ | $aK_1$ | |
| $s^1$ | $\frac{1260 + (116 - 64a)K_1 - K_1^2}{126 - K_1}$ | | |
| $s^0$ | $aK_1$ | | |

由劳斯稳定性判据知，使火星漫游车闭环稳定的充分必要条件为
$$K_1 < 126$$
$$aK_1 > 0$$
$$1260 + (116 - 64a)K_1 - K_1^2 > 0$$
当 $K_1 > 0$ 时，漫游车系统的稳定区域如图 3-58 所示。
由于设计指标要求系统在斜坡输入时的稳态误差不大于输入指令幅度的 24%，故需要对 $K_1$ 与 $a$ 的取值关系加以约束。令 $r(t) = At$，其中 $A$ 为指令斜率，系统的稳态误差为
$$e_{ss}(\infty) = \frac{A}{K_v}$$

• 140 •

---

### Page 2

[Diagram Description: Figure 3-58 is a graph showing the "Mars Rover Stability Region". The x-axis represents $K_1$ (ranging from 0 to 150) and the y-axis represents $a$ (ranging from 0 to 4.0). A curve starts at $a \approx 3.6$ when $K_1=0$, decreases to $a \approx 0.6$ at $K_1=70$, and continues to decrease as $K_1$ approaches 126. The region below the curve is labeled "Stable Region". A point is marked "Selected $K_1$ and $a$ values".]

**图 3-58 火星漫游车稳定区域**

式中，静态速度误差系数
$$K_v = \lim_{s \to 0} s G_c(s) G_0(s) = \frac{aK_1}{10}$$
于是
$$e_{ss}(\infty) = \frac{10A}{aK_1}$$
若取 $aK_1 = 42$，则 $e_{ss}(\infty)$ 等于 $A$ 的 23.8%，正好满足指标要求。因此，在图 3-58 的稳定区域中，在 $K_1 < 126$ 的限制条件下，可任取满足 $aK_1 = 42$ 的 $a$ 与 $K_1$ 值。例如：$K_1 = 70, a = 0.6$；或者 $K_1 = 50, a = 0.84$ 等参数组合。待选参数取值范围：$K_1 = 15 \sim 100, a = 0.42 \sim 2.8$。

**习 题**

**3-1** 设某高阶系统可用下列一阶微分方程近似描述：
$$T\dot{c}(t) + c(t) = \tau\dot{r}(t) + r(t)$$
式中，$1 > T - \tau > 0$。试证明系统的动态性能指标为
$$t_r = 2.2T, \quad t_s = \left(3 + \ln\frac{T - \tau}{T}\right)T \quad (\Delta = 5\%)$$

**3-2** 设备系统的微分方程如下：
(1) $0.2\dot{c}(t) = 2r(t)$；
(2) $0.04\ddot{c}(t) + 0.24\dot{c}(t) + c(t) = r(t)$。
试求系统的单位脉冲响应 $c(t)$ 和单位阶跃响应 $c(t)$。已知全部初始条件为零。

**3-3** 已知各系统的脉冲响应，试求系统的闭环传递函数 $\Phi(s)$。
(1) $c(t) = 0.0125e^{-1.25t}$；

• 141 •

---

### Page 3

(2) $c(t) = 5t + 10\sin(4t + 45^\circ)$；
(3) $c(t) = 0.1(1 - e^{-t/3})$。

**3-4** 已知二阶系统的单位阶跃响应为
$$c(t) = 10 - 12.5e^{-1.2t} \sin(1.6t + 53.1^\circ)$$
试求系统的超调量 $\sigma\%$、峰值时间 $t_p$ 和调节时间 $t_s$。

**3-5** 设单位反馈系统的开环传递函数为
$$G(s) = \frac{0.4s + 1}{s(s + 0.6)}$$
试求系统在单位阶跃输入下的动态性能。

**3-6** 已知控制系统的单位阶跃响应为
$$c(t) = 1 + 0.2e^{-60t} - 1.2e^{-10t}$$
试确定系统的阻尼比 $\zeta$ 和自然频率 $\omega_n$。

**3-7** 设图 3-59 是简化的飞行控制系统结构图，试选择参数 $K_1$ 和 $K_s$，使系统的 $\omega_n = 6, \zeta = 1$。

[Diagram Description: Figure 3-59 shows a block diagram. Input $R(s)$ goes to a summing junction, then to gain $K_1$, then to a plant $\frac{25}{s(s+0.8)}$, outputting $C(s)$. A feedback loop from $C(s)$ goes through gain $K_s$ back to the summing junction.]

**图 3-59 飞行控制系统结构图**

**3-8** 试分别求出图 3-60(a)~(c) 各系统的自然频率和阻尼比，并列表比较其动态性能。

[Diagram Description: Figure 3-60 shows three block diagrams: (a) Proportional control: $R(s)$ to summing junction, then $\frac{1}{s^2}$, output $C(s)$, with unity feedback. (b) Proportional-Derivative control: $R(s)$ to summing junction, then $(1+s)$ and $\frac{1}{s^2}$ in series, output $C(s)$, with unity feedback. (c) Velocity feedback control: $R(s)$ to summing junction, then $\frac{1}{s^2}$, output $C(s)$, with a feedback loop from the output of the integrator $s$ back to the summing junction.]

**图 3-60 控制系统结构图**

**3-9** 设控制系统如图 3-61 所示。要求：
(1) 取 $\eta_1 = 0, \eta_2 = 0.1$，计算测速反馈校正系统的超调量、调节时间和速度误差；
(2) 取 $\eta_1 = 0.1, \eta_2 = 0$，计算比例-微分校正系统的超调量、调节时间和速度误差。

[Diagram Description: Figure 3-61 shows a block diagram. Input $R(s)$ goes to a summing junction, then to a block $\frac{10}{s(s+1)}$, output $C(s)$. There is a feedback loop from $C(s)$ through a block $\tau_1 s$ and a feedforward block $\tau_2 s$ acting on the input.]

**图 3-61 控制系统结构图**

**3-10** 图 3-62 所示控制系统有 (a) 和 (b) 两种不同的结构方案，其中 $T > 0$ 不可变。要求：
(1) 在这两种方案中，应如何调整 $K_1, K_2$ 和 $K_3$，才能使系统获得较好的动态性能？
(2) 比较说明两种结构方案的特点。

• 142 •

==End of PDF==