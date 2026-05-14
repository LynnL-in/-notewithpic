期信号的频谱不同，非周期信号的频谱为连续谱，单个方波的幅值谱特性如图 5-45 所示。

[图 5-45 描述：该图包含两个部分。图 (a) 显示了一个以原点为中心、宽度为 $\tau$、幅值为 $A$ 的矩形脉冲信号 $f(t)$。图 (b) 显示了其对应的幅值谱特性 $|F(j\omega)|$，其形状为一个以 $\omega=0$ 为中心的 sinc 函数的绝对值，峰值为 $A\tau$，且在 $\omega = \pm \frac{2\pi}{\tau}, \pm \frac{4\pi}{\tau}, \dots$ 处过零点。]

图 5-45 频域特性

由图 5-45 可知，当控制输入信号频谱特性具有收敛形式时，可按跟踪要求选定常数 $\varepsilon$，若 $\omega > \omega_b$ 时，$|F(j\omega)| < \varepsilon$，从而确定系统所需要的带宽频率 $\omega_b$。

综上所述，系统的分析应区分输入信号的性质、位置，根据其频谱或谱密度以及相应的传递函数选择合适带宽，而系统的设计则主要围绕带宽来进行。为了设计合适的系统带宽，需要确定系统的闭环频率特性。

### 3. 确定闭环频率特性的方法

工程上常用 MATLAB 方法获得闭环频率特性：在已知系统开环传递函数条件下，直接调用命令 `feedback` 和 `bode`，可立即得到闭环对数幅频和相频曲线，然后可判读出系统谐振频率 $\omega_r$、谐振峰值 $M_r$ (dB) 及带宽频率 $\omega_b$。

### 4. 闭环系统频域指标和时域指标的转换

系统时域指标物理意义明确、直观，但不能直接应用于频域的分析和综合。闭环系统频域指标 $\omega_b$ 虽然能反映系统的跟踪速度和抗干扰能力，但由于需要通过闭环频率特性加以确定，在校正元件的形式和参数尚需确定时显得较为不便。鉴于系统开环频域指标相角裕度 $\gamma$ 和截止频率 $\omega_c$ 可以利用已知的开环对数频率特性曲线确定，且由前面分析知，$\gamma$ 和 $\omega_c$ 的大小在很大程度上决定了系统的性能，因此工程上常用 $\gamma$ 和 $\omega_c$ 来估算系统的时域性能指标。

#### (1) 闭环指标和开环频域指标的关系

系统开环指标截止频率 $\omega_c$ 与闭环指标带宽频率 $\omega_b$ 有着密切的关系。如果两个系统的稳定程度相仿，则 $\omega_c$ 大的系统，$\omega_b$ 也大；$\omega_c$ 小的系统，$\omega_b$ 也小。因此 $\omega_c$ 和系统响应速度存在正比关系，$\omega_c$ 可用来衡量系统的响应速度。鉴于闭环振荡性指标谐振峰值 $M_r$ 和开环指标相角裕度 $\gamma$ 都能表征系统的稳定程度，故下面建立 $M_r$ 和 $\gamma$ 的近似关系：

设系统开环相频特性可以表示为
$$\varphi(\omega) = -180^\circ + \gamma(\omega) \quad (5-100)$$
其中 $\gamma(\omega)$ 表示相角相对于 $-180^\circ$ 的相移。因此开环频率特性可以表示为
$$G(j\omega) = A(\omega)e^{-j[180^\circ - \gamma(\omega)]} = A(\omega)[-\cos\gamma(\omega) - j\sin\gamma(\omega)] \quad (5-101)$$
闭环幅频特性
$$M(\omega) = \left| \frac{G(j\omega)}{1 + G(j\omega)} \right| = \frac{A(\omega)}{\left[ 1 + A^2(\omega) - 2A(\omega)\cos\gamma(\omega) \right]^{\frac{1}{2}}} \quad (5-102)$$
$$= \frac{1}{\left[ \frac{1}{A(\omega)} - \cos\gamma(\omega) \right]^2 + \sin^2\gamma(\omega)} \quad (5-102)$$

一般情况下，在 $M(\omega)$ 的极大值附近，$\gamma(\omega)$ 变化较小，且使 $M(\omega)$ 为极值的谐振频率 $\omega_r$ 常位于 $\omega_c$ 附近，即有
$$\cos\gamma(\omega_r) \approx \cos\gamma(\omega_c) = \cos\gamma \quad (5-103)$$
由式 (5-102) 可知，令 $\frac{dM(\omega)}{d A(\omega)} = 0$，得 $A(\omega) = \frac{1}{\cos\gamma(\omega)}$，相应的 $M(\omega)$ 为极值，谐振峰值为
$$M_r = M(\omega_r) \approx \frac{1}{|\sin\gamma(\omega_r)|} \approx \frac{1}{\sin\gamma} \quad (5-104)$$

由于 $\cos\gamma(\omega_r) \le 1$，故在闭环幅频特性的峰值处对应的开环幅值 $A(\omega_r) > 1$，而 $A(\omega_c) = 1$，显然 $\omega_r \le \omega_c$。因此随着相角裕度 $\gamma$ 的减小，$\omega_c - \omega_r$ 减小，当 $\gamma = 0$ 时，$\omega_r = \omega_c$。由此可知，$\gamma$ 较小时，式 (5-104) 的近似程度较高。控制系统的设计中，一般先根据控制要求提出闭环频域指标 $\omega_b$ 和 $M_r$，再由式 (5-104) 确定相角裕度 $\gamma$ 和选择合适的截止频率 $\omega_c$，然后根据 $\gamma$ 和 $\omega_c$ 选择校正网络的结构并确定参数。

#### (2) 开环频域指标和时域指标的关系

对于典型二阶系统，第三章已建立了时域指标超调量 $\sigma\%$ 和调节时间 $t_s$ 与阻尼比 $\zeta$ 的关系式。而欲确定 $\gamma$ 和 $\omega_c$ 与 $\sigma\%$ 和 $t_s$ 的关系，只需确定 $\gamma$ 和 $\omega_c$ 关于 $\zeta$ 的计算公式。因为典型二阶系统的开环频率特性为
$$G(j\omega) = \frac{\omega_n^2}{j\omega(j\omega + 2\zeta\omega_n)} = \frac{\omega_n^2}{\omega\sqrt{\omega^2 + 4\zeta^2\omega_n^2}} \angle -90^\circ - \arctan\frac{\omega}{2\zeta\omega_n}$$
由 $\omega_c$ 定义及式 (5-85) 求得
$$\frac{\omega_c}{\omega_n} = (\sqrt{4\zeta^4 + 1} - 2\zeta^2)^{\frac{1}{2}} \quad (5-105)$$
由式 (5-86) 求出相角裕度
$$\gamma = 180^\circ + \angle[G(j\omega_c)] = 180^\circ - 90^\circ - \arctan\frac{\omega_c}{2\zeta\omega_n}$$
$$= \arctan\frac{2\zeta\omega_n}{\omega_c} = \arctan\left[ 2\zeta(\sqrt{4\zeta^4 + 1} - 2\zeta^2)^{-\frac{1}{2}} \right] \quad (5-106)$$

上述表明，典型二阶系统的相角裕度 $\gamma$ 与阻尼比 $\zeta$ 存在一一对应关系，图 5-46 是根据式 (5-106) 绘制的 $\gamma-\zeta$ 曲线。由图 5-46 可知，$\gamma$ 为 $\zeta$ 的增函数。

[图 5-46 描述：该图为 $\gamma-\zeta$ 曲线图。横坐标为相角裕度 $\gamma$ (单位为度，从 $0^\circ$ 到 $70^\circ$)，纵坐标为阻尼比 $\zeta$ (从 $0$ 到 $0.9$)。曲线从原点出发，随着 $\gamma$ 的增大，$\zeta$ 单调递增。]

当选定 $\gamma$ 后，可由 $\gamma-\zeta$ 曲线确定 $\zeta$，再由 $\zeta$ 确定 $\sigma\%$ 和 $t_s$。

**例 5-15** 设一单位反馈系统的开环传递函数
$$G(s) = \frac{K}{s(Ts + 1)}$$
若已知单位速度信号输入下的稳态误差 $e_{ss}(\infty) = 1/9$，相角裕度 $\gamma = 60^\circ$，试确定时域指标 $\sigma\%$ 和 $t_s$。

**解** 因为该系统为 I 型系统，单位速度输入下的稳态误差为 $1/K$，由题设条件得 $K=9$。由 $\gamma=60^\circ$，查图 5-46 得阻尼比 $\zeta = 0.62$，因此超调量
$$\sigma\% = e^{-\pi\zeta/\sqrt{1-\zeta^2}} \times 100\% = 7.5\%$$
由于
$$K/T = \omega_n^2, \quad 1/T = 2\zeta\omega_n, \quad \omega_n = 2K\zeta = 11.16$$
调节时间
$$t_s = \frac{3.5}{\zeta\omega_n} = 0.506 \quad (\Delta = 5\%)$$
如果采用 MATLAB 仿真方法，可得系统的时域指标为
$$\sigma\% = 8.29\%, \quad t_s = 0.47 (\Delta = 5\%)$$
表明对于典型的无零点二阶系统，时域指标的估算结果是较准确的。

#### (3) 高阶系统的时域指标的估算

对于具有一对共轭复数闭环极点的线性定常高阶系统，阶跃动态响应与频率响应之间通常存在下列关系：

1) $M_r$ 值表征了相对稳定性。如果 $M_r$ 的值在 $1.0 < M_r < 1.4 (0\text{dB} < M_r < 3\text{dB})$ 范围内，这相当于有效阻尼比在 $0.4 < \zeta < 0.7$ 范围内，则通常可以获得满意的动态性能。当 $M_r$ 的值大于 1.5 时，阶跃动态响应可能呈现出若干次过调。

2) 谐振频率 $\omega_r$ 的大小表征了动态响应的速度。$\omega_r$ 的值越大，时间响应便越快。换句话说，上升时间随 $\omega_r$ 成反比变化。在开环频率响应中，动态响应中的阻尼自然频率 $\omega_n$ 将位于截止频率 $\omega_c$ 与穿越频率 $\omega_c$ 之间的某一位上。

3) 对于弱阻尼系统，谐振频率 $\omega_r$ 与阶跃动态响应中的阻尼自然频率 $\omega_n$ 很接近。

如果高阶系统可以用标准二阶系统近似，或者说可以用一对共轭复数闭环极点近似，则可以利用上述三条关系，将高阶系统的阶跃动态响应与频率响应联系起来。

对于一般高阶系统，开环频域指标和时域指标不存在解析关系。通过对大量系统的 $M_r$ 和 $\omega_b$ 的研究，并借助于式 (5-104)，归纳为下述两个近似估算公式：