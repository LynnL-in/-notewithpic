## Page 1

[Diagram Description: Figure 6-13 (a) shows a Bode plot for a lead network. The magnitude plot $L(\omega)$ starts at 0 dB, rises at 20 dB/dec, and levels off at $10\lg a$. The phase plot $\varphi(\omega)$ starts at 0°, rises to a peak $\varphi_m$ at frequency $\omega_m$, and returns to 0°. Figure 6-13 (b) is a graph showing the relationship between the attenuation factor $a$ and the maximum lead angle $\varphi_m$ (in degrees) and $10\lg a$ (in dB).]

**图 6-13 无源超前网络特性**

$$\omega_m = \frac{1}{T\sqrt{a}} \quad (6-20)$$

将式(6-20)代入式(6-19)，得最大超前角

$$\varphi_m = \arctan \frac{a-1}{2\sqrt{a}} = \arcsin \frac{a-1}{a+1} \quad (6-21)$$

式(6-21)表明：最大超前角 $\varphi_m$ 仅与分度系数 $a$ 有关。$a$ 值选得越大，超前网络的微分效应越强。为了保持较高的系统信噪比，实际选用的 $a$ 值一般不超过 20。此外，由图 6-13(a) 可以明显看出 $\omega_m$ 处的对数幅频值

$$L_c(\omega_m) = 20\lg |aG_c(j\omega_m)| = 10\lg a \quad (6-22)$$

$a$ 与 $\varphi_m$ 及 $10\lg a$ 的关系曲线如图 6-13(b) 所示。

设 $\omega_m$ 为频率 $1/(aT)$ 及 $1/T$ 的几何中心，则应有

$$\lg \omega_m = \frac{1}{2} \left( \lg \frac{1}{aT} + \lg \frac{1}{T} \right)$$

解得 $\omega_m = 1/(T\sqrt{a})$，正好与式(6-20)完全相同，故最大超前频率 $\omega_m$ 确是 $1/(aT)$ 和 $1/T$ 的几何中心。

**(2) 无源滞后网络**

无源滞后网络的电路图如图 6-14(a) 所示。如果输入信号源的内阻为零，负载阻抗为无穷大，滞后网络的传递函数为

$$G_c(s) = \frac{1+bTs}{1+Ts} \quad (6-23)$$

式中

$$b = \frac{R_2}{R_1+R_2} < 1, \quad T = (R_1+R_2)C$$

通常，$b$ 称为滞后网络的分度系数，表示滞后深度。

无源滞后网络的对数频率特性如图 6-14(b) 所示。由可见，滞后网络在频率 $1/T$ 至 $1/(bT)$ 之间呈积分效应，而对数幅频特性呈滞后特性。与超前网络类似，最大滞后角 $\varphi_m$

---

## Page 2

发生在最大滞后角频率 $\omega_m$ 处，且 $\omega_m$ 正好是 $1/T$ 与 $1/(bT)$ 的几何中心。计算 $\omega_m$ 及 $\varphi_m$ 的公式分别为

$$\omega_m = \frac{1}{T\sqrt{b}} \quad (6-24)$$

$$\varphi_m = \arcsin \frac{1-b}{1+b} \quad (6-25)$$

图 6-14(b) 还表明，滞后网络对低频有用信号不产生衰减，而对高频噪声有削弱作用，$b$ 值越小，通过网络的噪声电平越低。

[Diagram Description: Figure 6-14 (a) shows a circuit diagram of a passive lag network consisting of a resistor $R_1$ in series with a parallel combination of a resistor $R_2$ and a capacitor $C$. Figure 6-14 (b) shows the Bode plot for the lag network: the magnitude plot $L(\omega)$ starts at 0 dB, drops at -20 dB/dec between $1/T$ and $1/(bT)$, and levels off at $20\lg b$. The phase plot $\varphi(\omega)$ starts at 0°, dips to a minimum $-\varphi_m$, and returns to 0°.]

**图 6-14 无源滞后网络及其特性**

采用无源滞后网络进行串联校正时，主要是利用其高频幅值衰减的特性，以降低系统的开环截止频率，提高系统的相角裕度。因此，力求避免最大滞后角发生在已校正系统开环截止频率 $\omega_c''$ 附近。选择滞后网络参数时，通常使网络的交接频率 $1/(bT)$ 远小于 $\omega_c''$，一般取

$$\frac{1}{bT} = \frac{\omega_c''}{10} \quad (6-26)$$

此时，滞后网络在 $\omega_c''$ 处产生的相角滞后按下式确定：

$$\varphi_c(\omega_c'') = \arctan bT\omega_c'' - \arctan T\omega_c''$$

由两角和的三角函数公式，得

$$\tan \varphi_c(\omega_c'') = \frac{bT\omega_c'' - T\omega_c''}{1+bT^2(\omega_c'')^2}$$

代入式(6-26)及 $b<1$ 关系，上式可化简为

$$\varphi_c(\omega_c'') \approx \arctan [0.1(b-1)] \quad (6-27)$$

$b$ 与 $\varphi_c(\omega_c'')$ 和 $20\lg b$ 的关系曲线如图 6-15 所示。为便于使用，图 6-15 曲线画在对数坐标中。

**(3) 无源滞后-超前网络**

无源滞后-超前网络的电路图如图 6-16(a) 所示，其传递函数

$$G_c(s) = \frac{(1+T_as)(1+T_bs)}{T_aT_bs^2 + (T_a + T_b + T_{ab})s + 1} \quad (6-28)$$

式中

$$T_a = R_1C_1, \quad T_b = R_2C_2, \quad T_{ab} = R_1C_2$$

---

## Page 3

[Diagram Description: Figure 6-15 shows a graph plotting the relationship between the attenuation factor $b$ (on the x-axis, logarithmic scale) and both $20\lg b$ (in dB) and the phase angle $\varphi_c(\omega_c'')$ (in degrees). The curves show how these values change as $b$ varies from 0.01 to 1.0.]

**图 6-15 无源滞后网络关系曲线($1/(bT)=0.1\omega_c''$)**

令式(6-28)的分母二项式有两个不相等的负实根，则式(6-28)可以写为

$$G_c(s) = \frac{(1+T_as)(1+T_bs)}{(1+T_1s)(1+T_2s)} \quad (6-29)$$

比较式(6-28)及(6-29)，可得

$$T_1T_2 = T_aT_b, \quad T_1+T_2 = T_a+T_b+T_{ab}$$

设

$$T_1 > T_a, \quad \frac{T_a}{T_1} = \frac{T_2}{T_b} = \frac{1}{\alpha}$$

其中 $\alpha > 1$，则有

$$T_1 = \alpha T_a, \quad T_2 = \frac{T_b}{\alpha}$$

于是，无源滞后-超前网络的传递函数最后可表示为

$$G_c(s) = \frac{(1+T_as)(1+T_bs)}{(1+\alpha T_as)(1+\frac{T_b}{\alpha}s)} \quad (6-30)$$

其中，$(1+T_as)/(1+\alpha T_as)$ 为网络的滞后部分，$(1+T_bs)/(1+T_bs/\alpha)$ 为网络的超前部分。

无源滞后-超前网络的对数幅频渐近特性如图 6-16(b) 所示，其低频部分和高频部分均起于和终于零分贝水平线。由可见，只要确定 $\omega_a, \omega_b$ 和 $\alpha$，或者确定 $T_a, T_b$ 和 $\alpha$ 三个独立变量，图 6-16(b) 的形状即可确定。

[Diagram Description: Figure 6-16 (a) shows the circuit diagram of a passive lag-lead network. Figure 6-16 (b) shows the asymptotic magnitude Bode plot: it starts at 0 dB, drops at -20 dB/dec starting at $\omega_a$, stays at a constant negative value $-20\lg \alpha$ between $\omega_b$ and $\alpha\omega_b$ (wait, the diagram shows the drop occurs between $\omega_a$ and $\omega_b$, then rises at 20 dB/dec between $\omega_b$ and $\alpha\omega_b$), and returns to 0 dB.]

**图 6-16 无源滞后-超前网络及其特性**