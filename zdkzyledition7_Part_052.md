(1) 当功率放大器增益 $K_a=20$，输入 $\theta_d(t)$ 为单位阶跃信号时，确定系统的单位阶跃响应 $\theta(t)$；
(2) 当 $\theta_d(t)=0$，$n(t)=1(t)$ 时，确定负载对系统的影响；
(3) 当 $n(t)=0$，$\theta_d(t)=t$，$t>0$ 时，确定系统的稳态误差 $e_{ss}(\infty)$。

[Diagram Description: Figure (a) shows a robotic gripper with a control knob, potentiometer, power amplifier, and DC motor. Figure (b) shows the control system model for the gripper, illustrating the feedback loop with the potentiometer, power amplifier, and DC motor. Figure (c) shows the block diagram of the gripper control system, with input $\theta_d(s)$, a gain $K_i$, a summing junction, a power amplifier gain $K_a$, a motor transfer function $\frac{K_m}{R_f}$, a plant transfer function $\frac{1}{s(Js+f)}$, and a feedback gain $K_f$ returning to the summing junction.]

图 3-68 机器人手爪控制系统

3-25 1984 年 2 月 7 日，美国宇航员利用手持喷气推进装置，完成了人类历史上的首次太空行走，如图 3-69(a)所示。宇航员机动控制系统结构图如图 3-69(b)所示，其中喷气控制器可用增益 $K_2$ 表示，$K_3$ 为速度反馈增益。若将宇航员以及他手臂上的装置一并考虑，系统总的转动惯量 $J=25N \cdot m \cdot s^2/rad$。要求：
(1) 当输入为单位斜坡 $r(t)=tm \cdot s^{-1}$ 时，确定速度反馈增益 $K_3$ 的取值，使系统稳态误差 $e_{ss}(\infty)<0.01m$；
(2) 采用(1)中求得的 $K_3$，确定 $K_1K_2$ 的取值，使系统超调量 $\sigma\% \le 10\%$。

3-26 在喷气式战斗机的自动驾驶仪中，配置有横滚角控制系统，其结构如图 3-70 所示。要求：
(1) 确定闭环传递函数 $\theta_c(s)/\theta_d(s)$；
(2) 当 $K_1$ 分别等于 0.7，3.0 和 6.0 时，确定闭环系统的特征根；
(3) 在(2)所给的条件下，应用主导极点概念，确定各二阶近似系统，估计有系统的超调量和峰值时间；
(4) 绘出原有系统的实际单位阶跃响应曲线，并与(3)中的近似结果进行比较。

3-27 打磨机器人能够按照预先设定的路径(输入指令)对加工的工件进行打磨抛光。在实践中，机器人自身的偏差、机械加工误差以及工具的磨损等，都会导致打磨加工误差。若利用力反馈修正机器人的运动路径，可以消除这些误差，提高抛光精度，但是，又可能使接触稳定性问题变得难以解决。

---

[Diagram Description: Figure (a) shows an astronaut performing a spacewalk. Figure (b) shows the block diagram of the astronaut maneuvering control system, with input $R(s)$, a summing junction, a gain $K_1$, a block for the jet controller $K_2$, a block for the dynamics $\frac{1}{Js}$, a block for velocity $\frac{1}{s}$, and a feedback loop with gain $K_3$.]

图 3-69 宇航员机动控制系统

[Diagram Description: Figure 3-70 shows the block diagram of the aircraft roll angle control system, with input $\theta_d(s)$, a summing junction, a controller block $\frac{K_1}{s+10}$, a plant block $\frac{11.4}{s(s+1.4)}$, and a feedback loop with a gyro gain $K_g=1$.]

图 3-70 飞机横滚角控制系统结构图

例如，在引入腕力传感器构成力反馈的同时，就带来了新的稳定性问题。
打磨机器人的结构如图 3-71 所示。若可调增益 $K_1$ 及 $K_2$ 均大于零，试确定能保证系统稳定性的 $K_1$ 和 $K_2$ 的取值范围。

3-28 一种新型电动轮椅装有一种非常实用的速度控制系统，能使颈部以下有残障的人士自行驾驶这种电动轮椅。该系统在头盔上以 90°间隔安装了四个速度传感器，用来指示前、后、左、右四个方向。头盔传感系统的综合输出与头部运动的幅度成正比。图 3-72 给出了该控制系统的结构图，其中时间常数 $T_1=0.5s, T_3=1s, T_4=0.25s$。要求：
(1) 确定使系统稳定的 $K$ 的取值($K=K_1K_2K_3$)；
(2) 确定增益 $K$ 的取值，使系统单位阶跃响应的调节时间等于 4s($\Delta=2\%$)，并计算此时系统的特征根。

---

[Diagram Description: Figure 3-71 shows the block diagram of the grinding robot, with input $X_d(s)$, a controller $K_1$, a plant $\frac{1}{s(s+1)}$, and a feedback loop. Below it is a force control loop with input $F_d(s)$, a controller $K_2$, a plant $\frac{-2}{s+2}$, and a force sensor gain of 1.]

图 3-71 打磨机器人结构图

[Diagram Description: Figure 3-72 shows the block diagram of the electric wheelchair control system, with input "Expected Speed", a summing junction, a block for "Sensor on Helmet" $\frac{K_1}{T_1s+1}$, an amplifier $K_2$, a "Wheel Dynamics Model" $\frac{K_3}{(T_3s+1)(T_4s+1)}$, and a feedback loop.]

图 3-72 电动轮椅控制系统结构图

3-29 设垂直起飞飞机如图 3-73(a)所示，起飞时飞机的四个发动机同时工作。垂直起飞飞机的高度控制系统结构如图 3-73(b)所示。要求：
(1) 当 $K_1=1$ 时，判断系统是否稳定；
(2) 确定使系统稳定的 $K_1$ 的取值范围。

3-30 火星自主漫游车的导向控制系统如图 3-74 所示。该系统在漫游车的前后部都装有一个导向轮，其反馈通道传递函数为
$$H(s)=1+K_s s$$
要求：
(1) 确定使系统稳定的 $K_s$ 值范围；
(2) 当 $s_3=-5$ 为该系统的一个闭环特征根时，试计算 $K_s$ 的取值，并计算另外两个闭环特征根；
(3) 应用(2)求出的 $K_s$ 值，确定系统的单位阶跃响应。

3-31 一种采用电磁力驱动的磁悬浮列车的构造如图 3-75(a)所示，其运行速度可达 480km/h，载客量为 400 人。但是，磁悬浮列车的正常运行需要在车体与轨道之间保持 0.635cm 的气隙。设间隙控制系统结构如图 3-75(b)所示。若控制器取为
$$G_c(s)=\frac{K_a(s+2)}{s+12}$$
式中，$K_a$ 为控制器增益。要求：
(1) 确定使系统稳定的 $K_a$ 值范围；
(2) 可否确定 $K_a$ 的合适取值，使系统对单位阶跃输入的稳态跟踪误差为零；
(3) 取控制器增益 $K_a=2$，确定系统的单位阶跃响应。