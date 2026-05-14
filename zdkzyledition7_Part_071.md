频特性为

$$A(\omega) = \frac{1}{(1+T^2\omega^2)^{\frac{1}{2}}}, \quad \varphi(\omega) = \arctan T\omega \quad (5-29)$$

由式(5-28)和式(5-29)可知，最小相位惯性环节和非最小相位的惯性环节，其幅频特性相同，相频特性符号相反，幅频曲线关于实轴对称；对数相频曲线相同，对数幅频曲线关于 $0^\circ$ 线对称。上述特点对于振荡环节和非最小相位(或不稳定)振荡环节、一阶微分环节和非最小相位一阶微分环节、二阶微分环节和非最小相位二阶微分环节均适用。

(2) 传递函数互为倒数的典型环节

最小相位典型环节中，积分环节和微分环节、惯性环节和一阶微分环节、振荡环节和二阶微分环节的传递函数互为倒数，即有下述关系成立：

$$G_1(s) = 1/G_2(s) \quad (5-30)$$

设 $G_1(j\omega) = A_1(\omega)e^{j\varphi_1(\omega)}$，则

$$\begin{cases} \varphi_2(\omega) = -\varphi_1(\omega) \\ L_2(\omega) = 20\lg A_2(\omega) = 20\lg \frac{1}{A_1(\omega)} = -L_1(\omega) \end{cases} \quad (5-31)$$

由此可知，传递函数互为倒数的典型环节，对数幅频曲线关于 $0\text{dB}$ 线对称，对数相频曲线关于 $0^\circ$ 线对称。在非最小相位环节中，同样存在传递函数互为倒数的典型环节，其对数频率特性曲线的对称性亦成立。

(3) 振荡环节和二阶微分环节

振荡环节的传递函数为

$$G(s) = \frac{1}{(s/\omega_n)^2 + 2\zeta(s/\omega_n) + 1}; \quad \omega_n > 0, \ 0 < \zeta < 1 \quad (5-32)$$

振荡环节的频率特性

$$A(\omega) = \frac{1}{\sqrt{\left(1-\frac{\omega^2}{\omega_n^2}\right)^2 + 4\zeta^2\frac{\omega^2}{\omega_n^2}}} \quad (5-33)$$

$$\varphi(\omega) = -\arctan \frac{2\zeta\frac{\omega}{\omega_n}}{1-\frac{\omega^2}{\omega_n^2}} = \begin{cases} -\arctan \frac{2\zeta\frac{\omega}{\omega_n}}{1-\frac{\omega^2}{\omega_n^2}}, & \omega \le \omega_n \\ 180^\circ - \arctan \frac{2\zeta\frac{\omega}{\omega_n}}{\frac{\omega^2}{\omega_n^2}-1}, & \omega > \omega_n \end{cases} \quad (5-34)$$

显然，$\varphi(0)=0^\circ$，$\varphi(\infty)=-180^\circ$，故相频特性曲线从 $0^\circ$ 单调减至 $-180^\circ$。当 $\omega=\omega_n$ 时，

---

$\varphi(\omega_n)=-90^\circ$，由式(5-33)得 $A(\omega_n) = \frac{1}{2\zeta}$，表明振荡环节与虚轴的交点为 $-j\frac{1}{2\zeta}$。

由式(5-33)可得 $A(0)=1, A(\infty)=0$。为分析 $A(\omega)$ 的极值，求 $A(\omega)$ 的极值，即令

$$\frac{dA(\omega)}{d\omega} = \frac{-\left[2\omega\left(1-\frac{\omega^2}{\omega_n^2}\right) + 4\zeta^2\frac{\omega}{\omega_n^2}\right]}{\left[\left(1-\frac{\omega^2}{\omega_n^2}\right)^2 + 4\zeta^2\frac{\omega^2}{\omega_n^2}\right]^{\frac{3}{2}}} = 0 \quad (5-35)$$

得谐振频率

$$\omega_r = \omega_n\sqrt{1-2\zeta^2}, \quad 0 < \zeta < \sqrt{2}/2 \quad (5-36)$$

将 $\omega_r$ 代入式(5-33)，求得谐振峰值

$$M_r = A(\omega_r) = \frac{1}{2\zeta\sqrt{1-\zeta^2}}, \quad 0 < \zeta < \sqrt{2}/2 \quad (5-37)$$

因为 $\zeta = \frac{\sqrt{2}}{2}$ 时 $M_r=1$，当 $0 < \zeta < \frac{\sqrt{2}}{2}$ 时

$$\frac{dM_r}{d\zeta} = \frac{-(1-2\zeta^2)}{\zeta^2(1-\zeta^2)^{\frac{3}{2}}} < 0 \quad (5-38)$$

可见 $M_r$ 均为阻尼比 $\zeta$ 的减函数($0 < \zeta < \frac{\sqrt{2}}{2}$)。当 $0 < \zeta < \frac{\sqrt{2}}{2}$，且 $\omega \in (0, \omega_r)$ 时，$A(\omega)$ 单调增；$\omega \in (\omega_r, \infty)$ 时，$A(\omega)$ 单调减。而当 $\frac{\sqrt{2}}{2} < \zeta < 1$ 时，$A(\omega)$ 单调减。不同阻尼比 $\zeta$ 情况中，振荡环节的幅相特性曲线和对数频率特性曲线分别如图 5-12 和图 5-13 所示，其中 $u = \frac{\omega}{\omega_n}$。

二阶微分环节的传递函数为振荡环节传递函数的倒数，按对称性可得二阶微分环节的对数频率曲线，并有

$$\begin{cases} A(0) = 1 \\ \varphi(0) = 0^\circ \end{cases} \quad \begin{cases} A(\omega_n) = 2\zeta \\ \varphi(\omega_n) = 90^\circ \end{cases} \quad \begin{cases} A(\infty) = \infty \\ \varphi(\infty) = 180^\circ \end{cases}$$

当阻尼比 $\frac{\sqrt{2}}{2} < \zeta < 1$ 时，$A(\omega)$ 从 1 单调增至 $\infty$；当阻尼比 $0 < \zeta < \frac{\sqrt{2}}{2}$，且 $\omega \in (0, \omega_r)$ 时，$A(\omega)$ 从 1 单调减至

$$\begin{cases} A(\omega_r) = 2\zeta\sqrt{1-\zeta^2} < 1 \\ \omega_r = \omega_n\sqrt{1-2\zeta^2} \end{cases} \quad (5-39)$$

而在 $\omega \in (\omega_r, \infty)$ 时，$A(\omega)$ 单调增，二阶微分环节的概略幅相特性曲线如图 5-14 所示。

---

**图 5-12 振荡环节的幅相特性曲线**
该图显示了在复平面（实轴与虚轴）上，不同阻尼比 $\zeta$（$\zeta=0.4, 0.6, 0.8$）对应的振荡环节频率响应轨迹。曲线从点 $(1, 0)$ 出发，随着频率 $u = \omega/\omega_n$ 的增加，轨迹向原点靠近。

**图 5-13 振荡环节的对数频率特性曲线**
该图包含两个子图：
1. 上图为对数幅频特性曲线 $L(\omega)$ (单位 dB) 随 $\omega/\omega_n$ 的变化，展示了不同 $\zeta$ 值（0.1, 0.2, 0.3, 0.5, 0.7, 1.0）下的谐振峰值。
2. 下图为相频特性曲线 $\varphi(\omega)$ (单位 度) 随 $\omega/\omega_n$ 的变化，所有曲线均从 $0^\circ$ 降至 $-180^\circ$，在 $\omega/\omega_n=1$ 处经过 $-90^\circ$。

**图 5-14 二阶微分环节的概略幅相特性曲线**
该图展示了在复平面上，当 $0 < \zeta < \frac{\sqrt{2}}{2}$ 时，二阶微分环节的频率响应轨迹。曲线从点 $(1, 0)$ 出发，先向内凹陷至点 $A(\omega_r)$，随后向外延伸至无穷远，相角最终趋于 $180^\circ$。

非最小相位的二阶微分环节和不稳定振荡环节的频率特性曲线可按前述(1)中结论以及二阶微分环节和振荡环节的频率特性曲线加以确定。

(4) 对数频率渐近特性曲线

在控制工程中，为简化惯性环节、一阶微分环节、振荡环节和二阶微分环节的对数频率特性曲线的作图，常用低频和高频渐近线近似表示对数幅频曲线，称之为对数幅频渐近特性曲线。

对于惯性环节，对数频率特性为

$$L(\omega) = -20\lg\sqrt{1+\omega^2T^2} \quad (5-40)$$

当 $\omega \ll \frac{1}{T}$ 时，$\omega^2T^2 \approx 0$，有

$$L(\omega) \approx -20\lg 1 = 0 \quad (5-41)$$

当 $\omega \gg \frac{1}{T}$ 时，$\omega^2T^2 \gg 1$，有

$$L(\omega) \approx -20\lg \omega T \quad (5-42)$$

因此惯性环节的对数幅频渐近特性为