中半径为无穷大的1/4圆。

当 $G(s)H(s)$ 在虚轴上有极点时，为避开开环极点，在图5-30(a)所选闭合曲线 $\Gamma$ 的基础上加以扩展，构成图5-30(b)所示的闭合曲线 $\Gamma$。

1) 开环系统含有积分环节时，在原点附近，取 $s=\varepsilon e^{j\theta}$ ($\varepsilon$ 为正无穷小量，$\theta \in [-90^\circ, +90^\circ]$)，即圆心为原点、半径为无穷小的半圆。

2) 开环系统含有等幅振荡环节时，在 $\pm j\omega_n$ 附近，取 $s=\pm j\omega_n + \varepsilon e^{j\theta}$ ($\varepsilon$ 为正无穷小量，$\theta \in [-90^\circ, +90^\circ]$)，即圆心为 $\pm j\omega_n$、半径为无穷小的半圆。

按上述 $\Gamma$ 曲线，函数 $F(s)$ 位于 $s$ 右半平面的极点即开环传递函数 $G(s)H(s)$ 位于 $s$ 右半平面的极点数 $P$ 应不包括 $G(s)H(s)$ 位于 $s$ 平面虚轴上的极点。

(4) $G(s)H(s)$ 闭合曲线的绘制

由图5-30知，$s$ 平面闭合曲线 $\Gamma$ 关于实轴对称，鉴于 $G(s)H(s)$ 为实系数有理分式函数，故闭合曲线 $\Gamma_{GH}$ 亦关于实轴对称，因此只需绘制 $\Gamma_{GH}$ 在 $\text{Im}s > 0, s \in \Gamma$ 对应的曲线段，即 $G(s)H(s)$ 的半闭合曲线，称为奈奎斯特曲线，仍记为 $\Gamma_{GH}$。

1) 若 $G(s)H(s)$ 无虚轴上极点
$\Gamma_{GH}$ 在 $s=j\omega, \omega \in [0, +\infty)$ 时，对应开环相特性曲线。
$\Gamma_{GH}$ 在 $s=\infty e^{j\theta}, \theta \in [0^\circ, +90^\circ]$ 时，对应原点($n>m$时)或($K^*, j0$)点($n=m$时)，$K^*$ 为系统开环根轨迹增益。

2) 若 $G(s)H(s)$ 有虚轴极点。当开环系统含有积分环节时，设
$$G(s)H(s) = \frac{1}{s^\nu} G_1(s); \quad \nu > 0, \quad |G_1(j0)| \neq \infty \quad (5-67)$$
有
$$A(0_+) = \infty, \quad \varphi(0_+) = \angle G(j0_+)H(j0_+) = \nu \times (-90^\circ) + \angle G_1(j0_+) \quad (5-68)$$
于是在原点附近，闭合曲线 $\Gamma$ 为 $s=\varepsilon e^{j\theta}, \theta \in [0^\circ, +90^\circ]$，且有 $G_1(\varepsilon e^{j\theta}) \approx G_1(j0)$，故
$$G(s)H(s)|_{s=\varepsilon e^{j\theta}} \approx \infty e^{j\left[ \nu \times (-\theta) + \angle G_1(j0) \right]} = \infty e^{j[\nu \times (-\theta) + \angle G_1(j0)]} \quad (5-69)$$
对应的曲线为从 $G_1(j0)$ 点起，半径为 $\infty$、圆心角为 $\nu \times (-\theta)$ 的圆弧，即可从 $G(j0_+)H(j0_+)$ 点起逆时针作半径无穷大、圆心角为 $\nu \times 90^\circ$ 的圆弧，如图5-31(a)中虚线所示。

当开环系统含有等幅振荡环节时，设
$$G(s)H(s) = \frac{1}{(s^2 + \omega_n^2)^\nu} G_1(s); \quad \nu > 0, \quad |G_1(\pm j\omega_n)| \neq \infty \quad (5-70)$$
考虑 $s$ 在 $j\omega_n$ 附近沿 $\Gamma$ 运动时，$\Gamma_{GH}$ 的变化为
$$s = j\omega_n + \varepsilon e^{j\theta}; \quad \theta \in [-90^\circ, +90^\circ] \quad (5-71)$$
因为 $\varepsilon$ 为正无穷小，所以(5-70)可写为
$$G(s)H(s) = \frac{1}{(2j\omega_n \varepsilon e^{j\theta} + \varepsilon^2 e^{j2\theta})^\nu} G_1(j\omega_n + \varepsilon e^{j\theta}) \approx \frac{e^{-j(\theta + 90^\circ)\nu}}{(2\omega_n \varepsilon)^\nu} G(j\omega_n) \quad (5-72)$$

---

**[图5-31 $F(s)$ 平面的半闭合曲线]**
(a) 开环系统有积分环节：显示了一个从 $G(j0_+)H(j0_+)$ 出发，经过一个半径为无穷大的圆弧，到达 $G(j\infty)H(j\infty)$ 的轨迹。
(b) 开环系统有等幅振荡环节：显示了在 $G(j\omega_n-)H(j\omega_n-)$ 和 $G(j\omega_n+)H(j\omega_n+)$ 之间，通过一个半径为无穷大的圆弧连接。

故有
$$\varphi(s) = \begin{cases} \angle G(j\omega_n), & \theta = -90^\circ, \text{即} s = j\omega_{n-} \\ \angle G(j\omega_n) - (\theta + 90^\circ)\nu, & \theta \in (-90^\circ, +90^\circ) \\ \angle G(j\omega_n) - \nu \times 180^\circ, & \theta = 90^\circ, \text{即} s = j\omega_{n+} \end{cases} \quad (5-73)$$
因此，$s$ 沿 $\Gamma$ 在 $j\omega_n$ 附近运动时，对应的 $\Gamma_{GH}$ 闭合曲线为半径无穷大，圆心角等于 $\nu \times 180^\circ$ 的圆弧，即从 $G(j\omega_n-)H(j\omega_n-)$ 点起以半径为无穷大顺时针 $\nu \times 180^\circ$ 的圆弧至 $G(j\omega_n+)H(j\omega_n+)$ 点，如图5-31(b)中虚线所示。上述分析表明，半闭合曲线 $\Gamma_{GH}$ 由开环相特性曲线和根据开环极点所补的无穷大半径的虚线圆弧两部分组成。

(5) 闭合曲线 $\Gamma_F$ 包围原点圈数 $R$ 的计算
根据半闭合曲线 $\Gamma_{GH}$ 可获得 $\Gamma_F$ 包围原点的圈数 $R$。设 $N$ 为 $\Gamma_{GH}$ 穿越 $(-1, j0)$ 点左侧负实轴的次数，$N_+$ 表示正穿越的次数(从上向下穿越)，$N_-$ 表示负穿越的次数(从下向上穿越)，则
$$R = 2N = 2(N_+ - N_-) \quad (5-74)$$
在图5-32中，虚线为按系统型次 $\nu$ 或等幅振荡节数 $\nu_1$ 补作的圆弧，点 $A, B$ 为奈氏曲线与负实轴的交点，穿越负实轴($-\infty, -1$)段的方向，分别有：
[图(a)] $A$ 点位于 $(-1, j0)$ 点左侧，$\Gamma_{GH}$ 从下向上穿越，为一次负穿越。故 $N_-=1, N_+=0, R=-2$。
[图(b)] $A$ 点位于 $(-1, j0)$ 点的右侧，$N_+=N_-=0, R=0$。
[图(c)] $A, B$ 点均位于 $(-1, j0)$ 点左侧，而在 $A$ 点处 $\Gamma_{GH}$ 从下向上穿越，为一次负穿越；$B$ 点处 $\Gamma_{GH}$ 从上向下穿越，为一次正穿越，故 $N_+=N_-=1, R=0$。
[图(d)] $A, B$ 点均位于 $(-1, j0)$ 点左侧，$A$ 点处 $\Gamma_{GH}$ 从下向上穿越，为一次负穿越；$B$ 点处 $\Gamma_{GH}$ 从上向下运动至轴并停止，为半次正穿越，故 $N_-=1, N_+=\frac{1}{2}, R=-1$。
[图(e)] $A, B$ 点均位于 $(-1, j0)$ 点左侧，$A$ 点对应 $\omega=0$，随 $\omega$ 增大，$\Gamma_{GH}$ 离开负实轴，为半次负穿越，而 $B$ 点处为一次负穿越，故 $N_-=\frac{3}{2}, N_+=0, R=-3$。

---

**[图5-32 系统开环半闭合曲线 $\Gamma_{GH}$ 与 $\Gamma_F$ 包围原点的圈数 $R$]**
(a) $R=-2$
(b) $R=0$
(c) $R=0$
(d) $R=-1$
(e) $R=-3$

$\Gamma_F$ 包围原点的圈数 $R$ 等于 $\Gamma_{GH}$ 包围 $(-1, j0)$ 点的圈数。计算 $R$ 的过程中应注意正确判断 $\Gamma_{GH}$ 穿越 $(-1, j0)$ 点左侧负实轴时的方向、半次穿越和虚线圆弧所产生的穿越次数。

2. 奈奎斯特稳定性判据(奈氏判据)
设闭合曲线 $\Gamma$ 如图5-30所示，在已知开环系统右半平面的极点(不包括虚轴上的极点)和半闭合曲线 $\Gamma_{GH}$ 的情况下，根据幅角原理和闭环稳定性条件，可得下述奈氏判据。

奈氏判据 反馈控制系统稳定的充分必要条件是半闭合曲线 $\Gamma_{GH}$ 不穿过 $(-1, j0)$ 点且逆时针包围临界点 $(-1, j0)$ 的圈数 $R$ 等于开环传递函数的正实部极点数 $P$。
由幅角原理可知，闭合曲线 $\Gamma$ 包围函数 $F(s)=1+G(s)H(s)$ 的零点数即闭环反馈控制系统正实部极点数为
$$Z = P - R = P - 2N \quad (5-75)$$
当 $P \neq R$ 时，$Z \neq 0$，系统闭环不稳定。而当半闭合曲线 $\Gamma_{GH}$ 穿过 $(-1, j0)$ 点时，说明存在 $s=\pm j\omega_n$，使得
$$G(\pm j\omega_n)H(\pm j\omega_n) = -1 \quad (5-76)$$
即系统闭环特征方程存在共轭虚根，则系统可能临界稳定。计算 $\Gamma_{GH}$ 的穿越次数 $N$ 时，应注意不计及 $\Gamma_{GH}$ 穿过 $(-1, j0)$ 点的次数。

例5-8 已知单位反馈系统开环相特性曲线($K=10, P=0, \nu=1$)如图5-33所示，试确定系统闭环稳定时 $K$ 值的范围。
解 由图所示，开环相特性曲线与负实轴有三个交点，设交点处穿越频率分别为 $\omega_1, \omega_2, \omega_3$，系统开环传递函数形如
$$G(s) = \frac{K}{s^\nu} G_1(s)$$
由题设条件 $\nu=1, \lim_{s \to 0} G_1(s)=1$，和
$$G(j\omega_i) = \frac{K}{j\omega_i} G_1(j\omega_i); \quad i=1, 2, 3$$
当 $K=10$ 时
$$G(j\omega_1) = -2, \quad G(j\omega_2) = -1.5, \quad G(j\omega_3) = -0.5$$

**[图5-33 例5-8 系统 $K=10$ 时开环相特性曲线]**