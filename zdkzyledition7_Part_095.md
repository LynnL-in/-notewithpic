==Start of PDF==

### Page 1

考虑到 $\omega_a < \omega_b = 2\text{rad/s}$，故可取 $-\arctan(175/\omega_a) \approx -90^\circ$。因为要求 $\gamma' = 45^\circ$，所以上式可简化为
$$\arctan \frac{3.5}{\omega_a} = 77.3^\circ$$
从求得 $\omega_a = 0.78\text{rad/s}$。这样，已校正系统 $-20\text{dB/dec}$ 斜率的中频区宽度 $H = 6/0.78 = 7.69$，满足在期望特性校正法中的中频区宽度近似关系
$$H \ge \frac{1 + \sin \gamma'}{1 - \sin \gamma'} = \frac{1 + \sin 45^\circ}{1 - \sin 45^\circ} = 5.83$$
于是，校正网络和已校正系统的传递函数分别为
$$G_c(s) = \frac{(1 + 1.28s)(1 + 0.5s)}{(1 + 64s)(1 + 0.01s)}$$
$$G_c(s)G_o(s) = \frac{180(1 + 1.28s)}{s(1 + 0.167s)(1 + 64s)(1 + 0.01s)}$$
其对数幅频特性 $L_c(\omega)$ 和 $L'(\omega)$ 已分别表示在图 6-23 之中。

最后，用计算的方法验算已校正系统的相角裕度和幅值裕度指标，求得 $\gamma' = 45.5^\circ$，$h'(\text{dB}) = 27\text{dB}$，完全满足指标要求。

#### 6-4 前馈校正

当系统性能指标要求为时域特征量时，为了改善控制系统的性能，除了采用串联校正方式外，还可以配置前置滤波器形成组合前馈校正方式，以获得某些改善系统性能的特殊功能。

**1. 前置滤波组合校正**

为了改善系统性能，在系统中常引入形如 $G_c(s) = (s+z)/(s+p)$ 的串联校正网络，以改变系统的闭环极点。但是，$G_c(s)$ 同时也会在系统闭环传递函数 $\Phi(s)$ 中增加一个新的零点。这个新增的零点可能会严重影响闭环系统的动态性能。此时，可考虑在系统的输入端串接一个前置滤波器，以消除新增闭环零点的不利影响。

**例 6-6** 设带有前置滤波器的控制系统如图 6-24 所示。图中，被控对象为 $G_o(s) = \frac{1}{s}$，串联校正网络为 PI 控制器，$G_c(s) = K_1 + \frac{K_2}{s} = \frac{K_1s + K_2}{s}$，$G_p(s)$ 为前置滤波器。系统的设计要求为：
(1) 系统阻尼比 $\zeta_d = \frac{1}{\sqrt{2}} = 0.707$；
(2) 阶跃响应的超调量 $\sigma\% \le 5\%$；
(3) 阶跃响应的调节时间 $t_s \le 0.6\text{s} (\Delta = 2\%)$。
试设计 $K_1, K_2$ 及 $G_p(s)$。

**解** 图 6-24 系统的闭环传递函数为

---

### Page 2

[Diagram Description: Figure 6-24 shows a block diagram of a control system with a feedforward filter. The input $R(s)$ enters a block $G_p(s)$ (the feedforward filter). The output of this block goes to a summing junction (positive input). The output of the summing junction goes to a controller $G_c(s)$, then to the plant $G_o(s)$, resulting in the output $C(s)$. A feedback loop returns $C(s)$ to the negative input of the summing junction.]

**图 6-24 前置滤波器的控制系统结构图**

$$\Phi(s) = \frac{(K_1s + K_2)G_p(s)}{s^2 + K_1s + K_2}$$

闭环系统特征方程为
$$s^2 + K_1s + K_2 = s^2 + 2\zeta_d\omega_n s + \omega_n^2 = 0$$
根据系统对阻尼比和调节时间的要求，令 $\zeta_d = 0.707$，且由
$$t_s = \frac{4.4}{\zeta_d\omega_n} < 0.6 \quad (\Delta = 2\%)$$
求得 $\zeta_d\omega_n \ge 7.33$。现取 $\zeta_d\omega_n = 8$，故 $\omega_n = 8\sqrt{2}$。于是求出 PI 控制器参数
$$K_1 = 2\zeta_d\omega_n = 16, \quad K_2 = \omega_n^2 = 128$$
若不引入前置滤波器，相当于 $G_p(s) = 1$，则系统的闭环传递函数为
$$\Phi(s) = \frac{16(s + 8)}{s^2 + 16s + 128} = \frac{\omega_n^2}{z} \cdot \frac{s + z}{s^2 + 2\zeta_d\omega_n s + \omega_n^2}$$
上式表明，此时系统有零点的二阶系统。根据 $\zeta_d = 1/\sqrt{2}$，$\omega_n = 8\sqrt{2}$，$z = 8$ 以及(3-42)
$$c(t) = 1 + re^{-\zeta_d\omega_n t} \sin(\omega_d\sqrt{1-\zeta_d^2}t + \psi)$$
再由(3-43)，式(3-44)及(3-46)，可得
$$r = \frac{\sqrt{z^2 - 2\zeta_d\omega_n z + \omega_n^2}}{z\sqrt{1-\zeta_d^2}} = 1.41$$
$$\beta_d = \arctan \frac{\sqrt{1-\zeta_d^2}}{\zeta_d} = \frac{\pi}{4}$$
$$\psi = -\pi + \arctan \left( \frac{\omega_n\sqrt{1-\zeta_d^2}}{z - \zeta_d\omega_n} \right) + \arctan \left( \frac{\sqrt{1-\zeta_d^2}}{\zeta_d} \right) = -\frac{\pi}{4}$$
于是，无前置滤波器时，系统的动态性能可由图 3-23 及式(3-45)，式(3-47)及(3-49)得
$$t_r = \frac{0.75}{\omega_n} = 0.07\text{s} \quad \left( \frac{z}{\zeta_d\omega_n} = 1, \omega_n t_r = 0.75 \right)$$
$$t_p = \frac{\beta_d - \psi}{\omega_n\sqrt{1-\zeta_d^2}} = 0.2\text{s}$$
$$\sigma\% = r\sqrt{1-\zeta_d^2}e^{-\zeta_d\omega_n t_p} \times 100\% = 20.0\%$$
$$t_s = \frac{4 + \ln r}{\zeta_d\omega_n} = 0.54\text{s} \quad (\Delta = 2\%)$$

---

### Page 3

显然，由于新增零点的影响，超调量无法满足设计指标要求。
考虑采用前置滤波器 $G_p(s)$ 来对消闭环传递函数 $\Phi(s)$ 中的零点，并同时保持系统原有的直流增益即 $\Phi(0)$ 不变，为此取
$$G_p(s) = \frac{8}{s+8}$$
因而闭环传递函数变成
$$\Phi(s) = \frac{128}{s^2 + 16s + 128}$$
此时，系统属无零点的二阶系统。由于
$$\beta = \arccos \zeta = \frac{\pi}{4}, \quad \omega_d = \omega_n\sqrt{1-\zeta^2} = 8$$
根据式(3-19)、式(3-20)、式(3-21)，可以算出系统的动态性能指标为
$$t_r = \frac{\pi - \beta}{\omega_d} = 0.29\text{s}, \quad t_p = \frac{\pi}{\omega_d} = 0.39\text{s}$$
$$\sigma\% = 100e^{-\pi\zeta/\sqrt{1-\zeta^2}}\% = 4.3\%, \quad t_s = \frac{4.4}{\zeta_d\omega_n} = 0.55\text{s} \quad (\Delta = 2\%)$$
结果表明：系统设计指标要求全部满足。

MATLAB 验证：
无前置滤波器时，$\Phi(s) = \frac{16(s+8)}{s^2 + 16s + 128}$，单位阶跃响应如图 6-25 所示，测得 $\sigma\% = 21\%$, $t_p = 0.2\text{s}$, $t_s = 0.44\text{s} (\Delta = 2\%)$
有前置滤波器时，$\Phi(s) = \frac{128}{s^2 + 16s + 128}$，单位阶跃响应如图 6-26 所示，测得 $\sigma\% = 4\%$, $t_p = 0.4\text{s}$, $t_s = 0.52\text{s} (\Delta = 2\%)$

[Diagram Description: Figure 6-25 shows a step response graph with Amplitude on the y-axis (0 to 1.4) and Time/sec on the x-axis (0 to 0.7). The curve rises sharply, overshoots to about 1.25, and settles around 1.0.]
**图 6-25 无前置滤波器时系统的单位阶跃响应(MATLAB)**

[Diagram Description: Figure 6-26 shows a step response graph with Amplitude on the y-axis (0 to 1.4) and Time/sec on the x-axis (0 to 0.7). The curve rises smoothly, reaches a peak slightly above 1.0, and settles at 1.0.]
**图 6-26 有前置滤波器时系统的单位阶跃响应(MATLAB)**

MATLAB 文本如下：
K1=16;K2=128;Gc=tf([K1 K2],[1 0]);

==End of PDF==