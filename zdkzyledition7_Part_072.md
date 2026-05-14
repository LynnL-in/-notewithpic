## Page 1

$$L_a(\omega) = \begin{cases} 0, & \omega < \frac{1}{T} \\ -20\lg \omega T, & \omega > \frac{1}{T} \end{cases} \quad (5-43)$$

惯性环节的对数幅频渐近特性曲线如图 5-15 所示，低频部分是零分贝线，高频部分是斜率为 $-20\text{dB/dec}$ 的直线，两条直线交于 $\omega = \frac{1}{T}$ 处，称频率 $\frac{1}{T}$ 为惯性环节的交接频率。用渐近特性近似表示对数幅频特性存在误差

$$\Delta L(\omega) = L(\omega) - L_a(\omega) \quad (5-44)$$

误差曲线如图 5-16 所示。在交接频率处误差最大，约为 $-3\text{dB}$。根据误差曲线，可修正渐近特性曲线获得准确曲线。

**[图 5-15 惯性环节的对数幅频渐近特性曲线]**
(描述：该图显示了一个对数幅频特性图。横轴为 $\omega T$，纵轴为 $L_a(\omega)/\text{dB}$。图中有一条折线，在 $\omega T < 1$ 时为 $0\text{dB}$ 水平线，在 $\omega T > 1$ 时为斜率为 $-20\text{dB/dec}$ 的下降直线，两条线在 $\omega T = 1$ 处相交。)

**[图 5-16 惯性环节的误差曲线]**
(描述：该图显示了误差 $\Delta L(\omega)/\text{dB}$ 随 $\omega T$ 变化的曲线。横轴为 $\omega T$ (从 0.1 到 10)，纵轴为 $\Delta L(\omega)/\text{dB}$ (从 -5 到 -1)。曲线在 $\omega T = 1$ 处达到最小值 $-3\text{dB}$，在两侧趋近于 0。)

由于非最小相位惯性环节的对数幅频特性与惯性环节相同，故其对数幅频渐近特性亦相同。根据一阶微分环节和非最小相位一阶微分环节的对数幅频特性相等，且与惯性环节对数幅频特性互为倒数的特点，可知一阶微分环节和非最小相位一阶微分环节与惯性环节的对数幅频渐近特性曲线以 $0\text{dB}$ 线互为镜像。

振荡环节的对数幅频特性为

$$L(\omega) = -20\lg \sqrt{\left(1 - \frac{\omega^2}{\omega_n^2}\right)^2 + 4\zeta^2 \frac{\omega^2}{\omega_n^2}} \quad (5-45)$$

当 $\omega \ll \omega_n$ 时，$L(\omega) \approx 0$，低频渐近线为 $0\text{dB}$ 线。而当 $\omega \gg \omega_n$ 时，$L(\omega) = -40\lg \frac{\omega}{\omega_n}$，高频渐近线为过 $(\omega_n, 0)$ 点，斜率为 $-40\text{dB/dec}$ 的直线。振荡环节的交接频率为 $\omega_n$，对数幅频渐近特性为

$$L_a(\omega) = \begin{cases} 0, & \omega < \omega_n \\ -40\lg \frac{\omega}{\omega_n}, & \omega > \omega_n \end{cases} \quad (5-46)$$

由于 $L_a(\omega)$ 与阻尼比 $\zeta$ 无关，用渐近线近似表示对数幅频曲线存在误差，误差的大小不仅和 $\omega$ 有关，而且也和 $\zeta$ 有关，误差曲线 $\Delta L(\omega, \zeta)$ 为一曲线簇，如图 5-17 所示。根据误差曲线可以修正渐近特性曲线而获得准确曲线。

· 206 ·

---

## Page 2

**[图 5-17 振荡环节的误差曲线]**
(描述：该图显示了不同阻尼比 $\zeta$ 下的误差曲线簇。横轴为 $\omega/\omega_n$，纵轴为 $\Delta L(\omega, \zeta)/\text{dB}$。曲线簇覆盖了 $\zeta = 0.05, 0.10, 0.15, 0.25, 0.30, 0.40, 0.50, 0.60, 0.80, 1.0$ 等不同情况，在 $\omega/\omega_n = 1$ 附近有显著的峰值或谷值变化。)

根据对数幅频特性定义还可知，非最小相位振荡环节与振荡环节的对数幅频渐近特性相同，二阶微分环节和非最小相位二阶微分环节与振荡环节的对数幅频渐近特性曲线关于 $0\text{dB}$ 线对称。

这里还应指出，半对数坐标中的直线方程为

$$k = \frac{L_a(\omega_2) - L_a(\omega_1)}{\lg \omega_2 - \lg \omega_1} \quad (5-47)$$

其中 $[\omega_1, L_a(\omega_1)]$ 和 $[\omega_2, L_a(\omega_2)]$ 为直线上的两点，$k (\text{dB/dec})$ 为直线斜率。

### 3. 开环幅相特性曲线

根据系统开环特性的表达式，可以通过取点、计算和作图等方法绘制系统开环幅相特性曲线。这里着重介绍结合工程需要，绘制概略开环幅相特性曲线的方法。

概略开环幅相特性曲线应反映开环频率特性的三个重要因素：
1) 开环幅相特性曲线的起点 ($\omega = 0+$) 和终点 ($\omega = \infty$)。
2) 开环幅相特性曲线与实轴的交点。设 $\omega = \omega_x$ 时，$G(j\omega)H(j\omega)$ 的虚部为

$$\text{Im}[G(j\omega_x)H(j\omega_x)] = 0 \quad (5-48)$$

或

$$\phi(\omega_x) = \angle G(j\omega_x)H(j\omega_x) = k\pi; \quad k = 0, \pm 1, \pm 2, \cdots \quad (5-49)$$

称 $\omega_x$ 为穿越频率，而开环幅相特性曲线与实轴交点的坐标值为

$$\text{Re}[G(j\omega_x)H(j\omega_x)] = G(j\omega_x)H(j\omega_x) \quad (5-50)$$

3) 开环幅相特性曲线的变化范围 (象限、单调性)。开环系统典型环节分解和典型环节幅相特性曲线的特点是绘制概略开环幅相特性曲线的基础，下面结合具体的系统加以介绍。

例 5-1 某 0 型单位反馈系统

· 207 ·

---

## Page 3

$$G(s) = \frac{K}{(T_1s + 1)(T_2s + 1)}; \quad K, T_1, T_2 > 0$$

试概略绘制系统开环幅相特性曲线。

解：由于惯性环节的角度变化为 $0^\circ \sim -90^\circ$，故该系统开环幅相特性曲线
起点：$A(0) = K, \quad \phi(0) = 0^\circ$
终点：$A(\infty) = 0, \quad \phi(\infty) = 2 \times (-90^\circ) = -180^\circ$
系统开环频率特性

$$G(j\omega) = \frac{K[1 - T_1T_2\omega^2 - j(T_1 + T_2)\omega]}{(1 + T_1^2\omega^2)(1 + T_2^2\omega^2)}$$

令 $\text{Im}G(j\omega) = 0$，得 $\omega_x = 0$，即系统开环幅相特性曲线除在 $\omega = 0$ 处外与实轴无交点。
由于惯性环节单调地从 $0^\circ$ 变化至 $-90^\circ$，故该系统概略幅相特性曲线的变化范围为第 IV 象限和第 III 象限，系统概略开环幅相曲线如图 5-18 实线所示。
若取 $K < 0$，由于非最小相位比例环节的相角恒为 $-180^\circ$，故此时系统概略幅相特性曲线由原曲线绕原点顺时针旋转 $180^\circ$ 而得，如图 5-18 中虚线所示。

**[图 5-18 例 5-1 系统概略开环幅相特性曲线 (MATLAB)]**
(描述：该图为 Nyquist 图。横轴为 Real Axis，纵轴为 Imaginary Axis。实线表示 $K > 0$ 的情况，曲线从实轴上的 $(K, 0)$ 点出发，经过第四象限和第三象限，最终趋向于原点 $(0, 0)$，且在 $\omega \to \infty$ 时切向趋近于负虚轴。虚线表示 $K < 0$ 的情况，曲线关于原点对称，位于第一和第二象限。)

例 5-2 设系统开环传递函数为

$$G(s)H(s) = \frac{K}{s(T_1s + 1)(T_2s + 1)}; \quad K, T_1, T_2 > 0$$

试绘制系统概略开环幅相特性曲线。

解：系统开环频率特性

$$G(j\omega)H(j\omega) = \frac{K(1 - jT_1\omega)(1 - jT_2\omega)(-j)}{\omega(1 + T_1^2\omega^2)(1 + T_2^2\omega^2)} = \frac{K[-(T_1 + T_2)\omega + j(-1 + T_1T_2\omega^2)]}{\omega(1 + T_1^2\omega^2)(1 + T_2^2\omega^2)}$$

· 208 ·