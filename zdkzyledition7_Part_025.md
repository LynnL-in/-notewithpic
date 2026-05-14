## Page 65

$$G(s) = \frac{K_m}{s(Js + f)(Ls + R)}$$

假定簧片是完全刚性的，不会出现明显的弯曲，则磁盘驱动读取系统的模型如图 2-46(b) 所示。

[Diagram Description: Figure 2-46(a) shows a block diagram of a disk drive reading system. It consists of a "Controller/Amplifier" block, followed by an "Actuator and Read Arm" block (labeled "DC Motor and Arm"), which outputs to the "Actual Head Position". A feedback loop goes from the "Actual Head Position" through a "Sensor (Head and Track)" block back to the input, where it is subtracted from the "Desired Head Position" to form an error signal.]

[Diagram Description: Figure 2-46(b) shows the simplified block diagram. The input $R(s)$ is summed with a negative feedback signal to produce $E(s)$. $E(s)$ goes through an amplifier $K_a$ to produce $V(s)$. $V(s)$ enters the plant $G(s) = \frac{K_m}{s(Js+f)(Ls+R)}$, producing output $C(s)$. $C(s)$ is fed back through a sensor block $H(s) = 1$.]

**图 2-46 磁盘驱动读取系统**

磁盘驱动读取系统的典型参数如表 2-3 所示。由表 2-3 可得

$$G(s) = \frac{5000}{s(s+20)(s+1000)} \quad (2-89)$$

上式还可以改写为

$$G(s) = \frac{K_m / (fR)}{s(T_L s + 1)(Ts + 1)} \quad (2-90)$$

其中，$T_L = J/f = 50\text{ms}$；$T = L/R = 1\text{ms}$。由于 $T \ll T_L$，常常略去 $T$，可得

**表 2-3 磁盘驱动读取系统典型参数**

| 参数 | 符号 | 典型值 |
| :--- | :--- | :--- |
| 手臂与磁头的转动惯量 | $J$ | $1\text{N}\cdot\text{m}\cdot\text{s}^2/\text{rad}$ |
| 摩擦系数 | $f$ | $20\text{N}\cdot\text{m}\cdot\text{s}/\text{rad}$ |
| 放大器增益 | $K_a$ | $10 \sim 1000$ |
| 电枢电阻 | $R$ | $1\Omega$ |
| 电机传递系数 | $K_m$ | $5\text{N}\cdot\text{m}/\text{A}$ |
| 电枢电感 | $L$ | $1\text{mH}$ |

· 65 ·

---

## Page 66

$$G(s) \approx \frac{K_m / (fR)}{s(T_L s + 1)} = \frac{0.25}{s(0.05s + 1)} = \frac{5}{s(s + 20)}$$

利用 $G(s)$ 的二阶近似表示，该磁盘驱动读取系统的闭环传递函数为

$$\frac{C(s)}{R(s)} = \frac{K_a G(s)}{1 + K_a G(s)} = \frac{5K_a}{s^2 + 20s + 5K_a} \quad (2-91)$$

当取 $K_a = 40$ 时，有 $C(s) = \frac{200}{s^2 + 20s + 200} R(s)$，若令 $R(s) = 1/s$，使用 MATLAB 的函数 step，可得该系统的阶跃响应曲线，如图 2-47 所示。

[Diagram Description: Figure 2-47 shows a Step Response plot. The x-axis is "Time/sec" from 0 to 1.0. The y-axis is "Amplitude" from 0 to 1.2. The curve starts at 0, rises to a peak of approximately 1.1 at 0.25s, oscillates, and settles at 1.0.]

**图 2-47 磁盘驱动读取系统的阶跃响应(MATLAB)**

MATLAB 文本：
G=zpk([ ],[0 -20 -1000],5000);Ka=40;sys=feedback(Ka*G,1);
t=0:0.01:1;step(sys,t);grid;axis([0,1,0,1.2])

**习 题**

2-1 在图 1-21 的液位自动控制系统中，设容器截面积为 $F$，希望液位为 $c_0$。若液位高度变化率与液体流量差 $Q_1 - Q_2$ 成正比，试列写以液位为输出量的微分方程。

2-2 设机械系统如图 2-48 所示，其中 $x_i$ 是输入位移，$x_o$ 是输出位移。试分别列写各系的微分方程。

[Diagram Description: Figure 2-48 shows three mechanical systems. (a) A mass $m$ connected to a damper $f_1$ above and $f_2$ below. (b) A spring $K_1$ and damper $f$ in parallel, connected to a spring $K_2$. (c) A spring $K_1$ and damper $f$ in series, connected to a spring $K_2$.]

**图 2-48 机械系统原理图**

· 66 ·

---

## Page 67

[Diagram Description: Figure 2-49(a) shows an electrical network with input $u_i$ and output $u_o$. It consists of a capacitor $C_1$ in parallel with resistor $R_1$, followed by a resistor $R_2$ in parallel with capacitor $C_2$. Figure 2-49(b) shows a mechanical system with a mass $m$ and dampers/springs.]

**图 2-49 电网络与机械系统原理图**

[Diagram Description: Figure 2-50 shows two passive electrical networks. (a) A circuit with $U_i$ input, $R_1$ in parallel with $C$, and $R_2$ in parallel with $U_o$. (b) A circuit with $U_i$ input, $R_1$ in series with $C_1$, and $R$ in parallel with $C_2$ at the output $U_o$.]

**图 2-50 无源网络电路图**

2-5 设初始条件均为零，试用拉氏变换法求解下列微分方程，并概略绘制 $x(t)$ 曲线，指出各方程的模态：
(1) $2\dot{x}(t) + x(t) = t$；
(2) $\ddot{x}(t) + \dot{x}(t) + x(t) = \delta(t)$；
(3) $\ddot{x}(t) + 2\dot{x}(t) + x(t) = 1(t)$。

2-6 在液压系统管道中，设通过阀门的流量 $Q$ 满足如下流量方程：
$$Q = K\sqrt{P}$$
式中，$K$ 为比例常数；$P$ 为阀门前后的压差。若流量 $Q$ 与压差 $P$ 在其平衡点 $(Q_0, P_0)$ 附近做微小变化，试导出线性化流量方程。

2-7 设弹簧特性由下式描述：
$$F = 12.65y^{1.1}$$
其中，$F$ 是弹力；$y$ 是变形位移。若弹簧在变形位移 $0.25$ 附近做微小变化，试推导 $\Delta F$ 的线性化方程。

2-8 设晶闸管三相桥式全控整流电路的输入量为控制角 $\alpha$，输出量为空载整流电压 $e_d$，其间的关系为 $e_d = E_{d_0} \cos \alpha$，式中 $E_{d_0}$ 是整流电压的理想空载值，试推导其线性化方程。

2-9 若某系统在阶跃输入 $r(t) = 1(t)$ 时，初始条件下的输出响应 $c(t) = 1 - e^{-2t} + e^{-t}$，试求系统的传递函数和脉冲响应。

2-10 设系统传递函数为
$$\frac{C(s)}{R(s)} = \frac{2}{s^2 + 3s + 2}$$

· 67 ·