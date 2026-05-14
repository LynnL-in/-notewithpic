==Start of PDF==

[Page 215]

解 开环传递函数的典型环节分解为

$$G(s)H(s) = \frac{-10\left(1-\frac{s}{2}\right)}{s^2\left(s+1\right)\left(\frac{s^2}{20^2}+\frac{1}{2}\frac{s}{20}+1\right)}$$

开环系统由六个典型环节串联而成：非最小相位比例环节、两个积分环节、非最小相位一阶微分环节、惯性环节和振荡环节。

1) 确定各交接频率 $\omega_i, i=1, 2, 3$ 及斜率变化值。
非最小相位一阶微分环节：$\omega_2=2$，斜率增加 $20\text{dB/dec}$
惯性环节：$\omega_1=1$，斜率减小 $20\text{dB/dec}$
振荡环节：$\omega_3=20$，斜率减小 $40\text{dB/dec}$
最小交接频率 $\omega_{\min}=\omega_1=1$。

2) 绘制低频段($\omega < \omega_{\min}$)渐近特性曲线。因为 $\nu=2$，则低频渐近线斜率 $k=-40\text{dB/dec}$，
按方法二得直线上一点 $(\omega_0, L_a(\omega_0))=(1, 20\text{dB})$。

3) 绘制频段 $\omega \ge \omega_{\min}$ 渐近特性曲线。
$$\omega_{\min} \le \omega < \omega_2, \quad k=-60\text{dB/dec}$$
$$\omega_2 \le \omega < \omega_3, \quad k=-40\text{dB/dec}$$
$$\omega \ge \omega_3, \quad k=-80\text{dB/dec}$$

系统开环对数幅频渐近特性曲线如图 5-24 所示。

[Diagram Description: Figure 5-24 shows a Bode magnitude plot. The horizontal axis is $\omega$ (rad/s) on a logarithmic scale from $10^{-1}$ to $10^2$. The vertical axis is $L(\omega)$ in dB from -80 to 80. A line starts at $\omega=1$ with a slope of -40dB/dec, changes to -60dB/dec at $\omega=1$, then to -40dB/dec at $\omega=2$, and finally to -80dB/dec at $\omega=20$.]

图 5-24 例 5-6 系统开环对数幅频渐近特性曲线(MATLAB)

开环对数相频特性曲线的绘制，一般由典型环节分解下的相频特性表达式，取若干

· 215 ·

[Page 216]

个频率点，列表计算各点的相角并标注在对数坐标图中，最后将各点光滑连接，即可得开环对数相频特性曲线。具体计算相角时应注意别象限。例如在例 5-6 中

$$\varphi(\omega) = \angle \frac{1}{1-\frac{\omega^2}{400}+j\frac{\omega}{40}} = \begin{cases} -\arctan \frac{\frac{\omega}{40}}{1-\frac{\omega^2}{400}}, & 0 < \omega < 20 \\ 180^\circ - \arctan \frac{\frac{\omega}{40}}{\frac{\omega^2}{400}-1}, & \omega > 20 \end{cases}$$

5. 延迟环节和延迟系统

输出量经恒定延时后不失真地复现输入量变化的环节称为延迟环节。含有延迟环节的系统称为延迟系统。化工、电力系统多为延迟系统。延迟环节的输入输出的时域表达式为

$$c(t)=l(t-\tau)r(t-\tau) \quad (5-58)$$

式中，$\tau$ 为延迟时间，应用拉氏变换的实数位移定理，可得延迟环节的传递函数

$$G(s)=\frac{C(s)}{R(s)}=e^{-\tau s} \quad (5-59)$$

延迟环节的频率特性为

$$G(j\omega)=e^{-j\tau\omega}=1 \cdot \angle(-57.3\tau\omega) \quad (5-60)$$

[Diagram Description: Figure 5-25 shows a block diagram with $R(s)$ entering a block $e^{-0.5s}$ to produce $C(s)$. Below it, a complex plane diagram shows a unit circle with a vector $OA$ at an angle $\theta$ representing the frequency response of the delay system.]

图 5-25 延迟系统及其开环相频特性曲线

由式(5-60)可知，延迟环节相频特性曲线为单位圆。当系统存在延迟现象，即开环系统表现为延迟环节和线性环节的串联形式时，延迟环节对系统开环频率特性的影响是造成了相频特性的明显变化，如图 5-25 所示。

当线性环节 $G(s)=\frac{10}{1+s}$ 与延迟环节 $e^{-0.5s}$ 串联后，系统开环幅相特性曲线为螺旋线。图中以$(5, j0)$为圆心，半径为 5 的半圆为惯性环节的幅相特性曲线，任取频率点 $\omega$，设惯性环节的频率特性点为 $A$，则延迟系统的幅相特性线的 $B$ 点位于以$|OA|$为半径，距 $A$ 点圆心角$\theta=57.3 \times 0.5\omega$ 的圆弧处。

6. 传递函数的频域确定

由前可知，稳定系统的频率响应为与输入同频率的正弦信号，且其幅值和相位的变化为频率的函数，因此可以运用频率响应实验确定稳定系统的数学模型。

(1) 频率响应实验
频率响应实验原理如图 5-26 所示。首先选择信号源输出的正弦信号的幅值，以使

· 216 ·

[Page 217]

系统处于非饱和状态。在一定频率范围内，改变输入正弦信号的频率，记录各频率点处系统输出信号的波形。由稳态段的输入输出信号的幅值和相位绘制对数频特性曲线。

[Diagram Description: Figure 5-26 shows a block diagram: Signal Source -> Object -> Recorder. The input is $A\sin\omega t$.]

图 5-26 频率响应实验原理方块图

(2) 传递函数确定
从低频段起，将实验所得的对数幅频特性曲线用斜率为 $0\text{dB/dec}, \pm 20\text{dB/dec}, \pm 40\text{dB/dec}, \cdots$ 直线分段近似，获得对数幅频渐近特性曲线。

由对数幅频渐近特性曲线可以确定最小相位条件下系统的传递函数，这是对数幅频渐近特性曲线绘制的逆问题，下面举例说明其方法和步骤。

例 5-7 图 5-27 为由频率响应实验获得的某最小相位系统的开环对数幅频特性和对数幅频渐近特性曲线，试确定系统传递函数。

[Diagram Description: Figure 5-27 shows a Bode magnitude plot. The horizontal axis is $\omega$ (log scale), vertical is $L(\omega)$ in dB. The plot shows a line with slope 20dB/dec up to $\omega_1$, then 0dB/dec up to $\omega_2$, then -40dB/dec.]

图 5-27 系统开环对数幅频特性曲线

解 1) 确定系统积分或微分环节的个数。因为对数幅频渐近特性曲线的低频渐近线的斜率为 $-20\nu\text{dB/dec}$，而由图 5-27 知低频渐近线斜率为 $+20\text{dB/dec}$，故 $\nu=-1$，系统含有一个微分环节。

2) 确定系统传递函数结构形式。由于对数幅频渐近特性曲线为分段折线，其各转折点对应的频率为所含一阶环节或二阶环节的交接频率，每个交接频率处斜率的变化取决于环节的种类。本例中共有两个交接频率：

$\omega=\omega_1$ 处，斜率变化 $-20\text{dB/dec}$，对应惯性环节。
$\omega=\omega_2$ 处，斜率变化 $-40\text{dB/dec}$，可以对应振荡环节也可以为重惯性环节，本例中，对数幅频特性在 $\omega_2$ 附近存在谐振现象，故应为振荡环节。因此所测系统应具有下述传递函数：

$$G(s) = \frac{Ks}{\left(1+\frac{s}{\omega_1}\right)\left(\frac{s^2}{\omega_2^2}+2\zeta\frac{s}{\omega_2}+1\right)}$$

其中参数 $\omega_1, \omega_2, \zeta$ 及 $K$ 待定。

3) 由给定条件确定传递函数参数。低频渐近线的方程为

$$L_a(\omega)=20\lg\frac{K}{\omega^\nu}=20\lg K - 20\nu\lg\omega$$

由给定点 $(\omega, L_a(\omega))=(1, 0)$ 及 $\nu=-1$ 得 $K=1$。

根据直线方程式(5-47)

$$L_a(\omega_a)-L_a(\omega_b)=k(\lg\omega_a-\lg\omega_b)$$

· 217 ·

==End of PDF==