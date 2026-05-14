幅值变化: $A(0_+)=\infty, \quad A(\infty)=0$
相角变化: $\angle\left(\dfrac{1}{j\omega}\right): -90^\circ \sim -90^\circ$

$\angle\left(\dfrac{1}{1+jT_1\omega}\right): 0^\circ \sim -90^\circ$

$\angle\left(\dfrac{1}{1+jT_2\omega}\right): 0^\circ \sim -90^\circ$

$\angle K: 0^\circ \sim 0^\circ$
$\varphi(\omega): -90^\circ \sim -270^\circ$

起点处: $\text{Re}[G(j0_+)H(j0_+)]=-K(T_1+T_2)$
$\text{Im}[G(j0_+)H(j0_+)]=-\infty$

与实轴的交点: 令 $\text{Im}[G(j\omega)H(j\omega)]=0$, 得 $\omega_x=\dfrac{1}{\sqrt{T_1T_2}}$, 于是

$$G(j\omega_x)H(j\omega_x)=\text{Re}[G(j\omega_x)H(j\omega_x)]=-\dfrac{KT_1T_2}{T_1+T_2}$$

由此做系统概略开环相特性曲线，如图 5-19 中曲线①所示。图中虚线为开环幅相特性的低频渐近线。由于开环幅相特性曲线用于系统分析时不需要准确知道渐近线的位置，故一般根据 $\varphi(0_+)$ 取渐近线为坐标轴，图中曲线②为相应的概略开环幅相特性曲线。

**[Diagram Description: Figure 5-19]**
The figure shows a Nyquist Diagram with a coordinate system where the horizontal axis is "Real Axis" and the vertical axis is "Imaginary Axis".
- The Real Axis ranges from -3.0 to 0.
- The Imaginary Axis ranges from -6.0 to 0.
- Curve ① starts from the negative imaginary axis (approaching $-\infty$) and curves towards the left, crossing the real axis at $-\dfrac{KT_1T_2}{T_1+T_2}$ and ending at the origin.
- A vertical dashed line is drawn at $\text{Real Axis} = -K(T_1+T_2)$.
- Curve ② is a simpler, smoother curve starting from the negative imaginary axis and ending at the origin.
- The label "图 5-19 例 5-2 系统概略开环相特性曲线" is at the bottom.

---
. 209 .

例 5-2 中系统型次即开环传递函数中积分环节个数 $v=1$, 若分别取 $v=2, 3$ 和 $4$, 则根据积分环节的相角，可将图 5-19 曲线分别绕原点旋转 $-90^\circ, -180^\circ$ 和 $-270^\circ$, 即可得相应的概略开环幅相特性曲线，如图 5-20 所示。

**[Diagram Description: Figure 5-20]**
The figure shows a Nyquist Diagram with four curves labeled $v=1, v=2, v=3, v=4$.
- The $v=1$ curve is in the third quadrant.
- The $v=2$ curve is in the second and third quadrants.
- The $v=3$ curve is in the first and second quadrants.
- The $v=4$ curve is in the first and fourth quadrants.
- The label "图 5-20 $v=1, 2, 3, 4$ 时系统概略开环幅相特性曲线(MATLAB)" is at the bottom.

例 5-3 已知单位反馈系统开环传递函数为
$$G(s)=\dfrac{K(\tau s+1)}{s(T_1s+1)(T_2s+1)}; \quad K, T_1, T_2, \tau > 0$$
试绘制系统概略开环幅相特性曲线。
解 系统开环频率特性为
$$G(j\omega)=\dfrac{-jK\left[1-T_1T_2\omega^2+T_1\tau\omega^2+T_2\tau\omega^2+j\omega(\tau-T_1-T_2-T_1T_2\tau\omega^2)\right]}{\omega(1+T_1^2\omega^2)(1+T_2^2\omega^2)}$$
开环幅相曲线的起点 $G(j0_+)=\infty\angle(-90^\circ)$, 终点 $G(\infty)=0\angle(-180^\circ)$。
与实轴的交点: 当 $\tau < \dfrac{T_1T_2}{T_1+T_2}$ 时，得
$$\omega_x=\dfrac{1}{\sqrt{T_1T_2-T_1\tau-T_2\tau}}$$
$$G(j\omega_x)=-\dfrac{K(T_1+T_2)(T_1T_2-T_1\tau-T_2\tau+\tau^2)}{(T_1T_2-T_1\tau-T_2\tau+T_1^2)(T_1T_2-T_1\tau-T_2\tau+T_2^2)}$$
变化范围:
$\tau > \dfrac{T_1T_2}{T_1+T_2}$ 时，开环相特性曲线位于第 III 象限或第 IV 与第 III 象限;
$\tau < \dfrac{T_1T_2}{T_1+T_2}$ 时，开环相特性曲线位于第 III 象限与第 II 象限。
概略开环幅相特性曲线如图 5-21 所示。

. 210 .

应该指出，由于开环传递函数具有一阶微分环节，系统开环幅相特性曲线有凹凸现象，因为绘制的是概略幅相特性曲线，故这一现象无须准确反映。
例 5-4 已知系统开环传递函数为
$$G(s)H(s)=\dfrac{K(-\tau s+1)}{s(Ts+1)}; \quad K, \tau, T > 0$$
试概略绘制系统概略开环幅相特性曲线。
解 系统开环频率特性为
$$G(j\omega)H(j\omega)=\dfrac{K[-(T+\tau)\omega-j(1-T\tau\omega^2)]}{\omega(1+T^2\omega^2)}$$
开环幅相特性曲线的起点: $A(0_+)=\infty, \quad \varphi(0_+)=-90^\circ$
开环幅相特性曲线的终点: $A(\infty)=0, \quad \varphi(\infty)=-270^\circ$
与实轴的交点: 令虚部为零，解得
$$\omega_x=\dfrac{1}{\sqrt{T\tau}}, \quad G(j\omega_x)H(j\omega_x)=-K\tau$$
因为 $\varphi(\omega)$ 从 $-90^\circ$ 单调减至 $-270^\circ$，故幅相特性曲线在第 III 与第 II 象限间变化。
概略开环幅相特性曲线如图 5-22 所示。

**[Diagram Description: Figure 5-21 and 5-22]**
- Figure 5-21: A Nyquist diagram showing two curves. One curve is labeled with $\tau < \frac{T_1T_2}{T_1+T_2}$ and the other with $\tau > \frac{T_1T_2}{T_1+T_2}$.
- Figure 5-22: A Nyquist diagram showing a curve starting from the negative imaginary axis, passing through the point $-K\tau$ on the real axis, and ending at the origin.
- Labels: "图 5-21 例 5-3 系统概略开环幅相特性曲线(MATLAB)" and "图 5-22 例 5-4 系统概略开环幅相特性曲线(MATLAB)".

在例 5-4 中，系统含有非最小相位一阶微分环节，称开环传递函数含有非最小相位环节的系统为非最小相位系统，而开环传递函数全部由最小相位环节构成的系统为最小相位系统。比较例 5-2、例 5-3 和例 5-4 可知，非最小相位环节的存在对将来的系统频率特性产生一定的影响，故在控制系统分析中必须加以重视。
例 5-5 设系统开环传递函数为
$$G(s)H(s)=\dfrac{K}{s(Ts+1)(s^2/\omega_n^2+1)}; \quad K, T > 0$$
试绘制系统概略开环幅相特性曲线。

. 211 .