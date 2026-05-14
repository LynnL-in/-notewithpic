## Page 1

[Image: A graph titled "图 4-21 零点相对位置与超调量关系曲线" (Figure 4-21 Relationship curve between zero point relative position and overshoot). The x-axis is labeled $z_1/\omega_n$ and the y-axis is labeled $\sigma\%$. Curves are plotted for different damping ratios $\zeta = 0.25, 0.5, 0.707$. An inset diagram shows the complex s-plane with a pole at $-\zeta\omega_n \pm j\omega_n\sqrt{1-\zeta^2}$ and a zero at $-z_1$.]

过渡过程被平缓。实数极点越接近坐标原点，意味着滤波器的时间常数越大，上述这种作用便越强。

闭环系统零、极点位置对时间响应性能的影响，可以归纳为以下几点：

1) 稳定性。如果闭环极点全部位于 $s$ 左半平面，则系统一定是稳定的，即稳定性只与闭环极点位置有关，而与闭环零点位置无关。

2) 运动形式。如果闭环系统无零点，且闭环极点均为实数极点，则时间响应一定是单调的；如果闭环极点均为复数极点，则时间响应一般是振荡的。

3) 超调量。超调量主要取决于闭环复数主导极点的衰减率 $\sigma_1/\omega_d = \zeta/\sqrt{1-\zeta^2}$，并与其他闭环零、极点接近坐标原点的程度有关。

4) 调节时间。调节时间主要取决于最靠近虚轴的闭环复数极点的实部绝对值 $\sigma_1 = \zeta\omega_n$；如果实数极点距虚轴最近，并且它附近没有实数零点，则调节时间主要取决于该实数极点的模值。

5) 实数零、极点影响。零点减小系统阻尼，使峰值时间提前，超调量增大；极点增大系统阻尼，使峰值时间滞后，超调量减小。它们的作用，随着其本身接近坐标原点的程度而加强。

6) 偶极子及其处理。如果零、极点之间的距离比它们本身的模值小一个数量级，则它们就构成了偶极子。远离原点的偶极子，其影响可略；接近原点的偶极子，其影响必须考虑。

7) 主导极点。在 $s$ 平面上，最靠近虚轴而附近又无闭环零点的一些闭环极点，对系统性能影响最大，称为主导极点。凡比主导极点的实部大 $3 \sim 6$ 倍以上的其他闭环零、极点，其影响均可忽略。

· 176 ·

---

## Page 2

### 4-5 控制系统复域设计

#### 例 4-7 自动平衡秤系统。

自动平衡能自动完成称重操作，其示意图如图 4-22 所示。称重时，由下面一个电动反馈环节控制其自动平衡，图 4-22 中所示为无重物时的平衡状态。图中，$x$ 是砝码 $W_c$ 离极轴的距离；待称重物 $W$ 将放置在离极轴 $l_w=5\text{cm}$ 处；重物一方还有一个黏性阻尼器，其到极轴的距离 $l_i=20\text{cm}$。平衡系统的有关参数如下：

[Image: A diagram showing an automatic balance scale. A beam is pivoted at a central axis. On the left side, a viscous damper is attached at distance $l_i$. On the right side, a weight $W$ is at distance $l_w$, and a sliding weight $W_c$ is at distance $x$. A DC motor drives the position $x$ via a lead screw. Labels include $K_i$, $E_{bb}$, $K_f$, $K_s$.]

**图 4-22 自动平衡秤示意图**

极轴惯量 $J=0.05\text{kg} \cdot \text{m} \cdot \text{s}^2$，
黏性阻尼器的阻尼系数 $f=10\sqrt{3}\text{kg} \cdot \text{m} \cdot \text{s}/\text{rad}$，
导引螺杆增益 $K_s=1/(4000\pi)\text{m}/\text{rad}$，
砝码 $W_c$ 的质量依需要的称重范围而定，本例 $W_c=2\text{kg}$。
电池电压 $E_{bb}=24\text{V}$，
反馈电位计增益 $K_f=400\text{V}/\text{m}$，
输入电位计增益 $K_i=4800\text{V}/\text{m}$，

要求完成以下设计工作：
1) 建立系统的模型与信号流图。
2) 在根轨迹图上确定根轨迹增益 $K^*$ 的取值。
3) 确定系统的主导极点。
设计后的系统达到以下性能指标要求：
1) 阶跃输入下：$K_p=\infty$，$e_{ss}(\infty)=0$。
2) 欠阻尼响应：$\zeta=0.5$。
3) 调节时间：$t_s < 2\text{s} (\Delta=2\%)$。

**解** 首先建立平衡运动方程。设系统略偏平衡状态，偏角为
$$\theta = \frac{y}{l_i}$$
因 $J\frac{d^2\theta}{dt^2} = \Sigma \text{扭矩}$，故平衡秤关于极轴的扭矩方程为

· 177 ·

---

## Page 3

$$J\frac{d^2\theta}{dt^2} = l_w W - x W_c - fl_i^2 \frac{d\theta}{dt}$$

电机输入电压
$$v_m(t) = K_i y - K_f x$$
电机的传递函数
$$\frac{\Theta_m(s)}{V_m(s)} = \frac{K_m}{s(T_m s + 1)}$$

式中，$\Theta_m$ 为输出轴转角；$K_m$ 为电机传递系数；$T_m$ 为电机机电时间常数，与系统时间常数相比，可略去不计。

根据上述方程可画出系统信号流图，如图 4-23 所示。由信号流图可见，从物体质量 $W(s)$ 到测量值 $X(s)$ 的前向通路中，在节点测量高度 $Y(s)$ 之前有一个积分环节，因此该系统为 I 型系统，在阶跃输入作用下，能实现稳态位置误差系数 $K_p=\infty$ 及稳态误差 $e_{ss}(\infty)=0$ 的要求。应用梅森增益公式，可得系统闭环传递函数为
$$\frac{X(s)}{W(s)} = \frac{l_w l_i K_i K_m K_s / (Js^3)}{1 + fl_i^2 / (Js) + K_m K_s K_f / (Js^3) + l_i K_m K_s W_c / (Js^3) + fl_i^2 K_m K_s K_f / (Js^2)}$$

[Image: A signal flow diagram (Figure 4-23). Nodes include $W(s)$, $l_w$, $l_i$, $Y(s)$, $V_m(s)$, $\Theta_m(s)$, $X(s)$. Feedback loops include $-fl_i$, $-K_f$, and $-W_c$.]

**图 4-23 自动平衡系统信号流图**

式中，分子对应于从 $W$ 到 $X$ 的前向通路总增益；分母的第二项对应于 $L_1$ 回路增益，第三项对应于 $L_2$ 回路增益，第四项对应于 $L_3$ 回路增益，第五项对应于两个不接触的回路 $L_1$ 与 $L_2$ 增益乘积。于是，闭环传递函数可化为
$$\frac{X(s)}{W(s)} = \frac{(l_w l_i K_i K_m K_s)}{s(Js + fl_i^2) + (s + K_f K_m K_s) + W_c l_i K_m K_s}$$

当重物 $W$ 放在自动平衡秤上时，$W(s)=|W|/s$，系统的稳态增益为
$$\lim_{t \to \infty} \left[ \frac{x(t)}{|W|} \right] = \lim_{s \to 0} \left[ \frac{X(s)}{W(s)} \right] = \frac{l_w}{W_c} = 2.5\text{cm}/\text{kg}$$

为了绘制电机传递函数(含放大器附加增益)$K_m$ 变化时系统的根轨迹，可将各有关参数代入闭环传递函数的分母，于是系统特征方程
$$0.05s(s + 8\sqrt{3}) \left( s + \frac{K_m}{10\pi} \right) + \frac{4.8}{10\pi} K_m = 0$$
即
$$s(s + 8\sqrt{3}) \left( s + \frac{K_m}{10\pi} \right) + \frac{96}{10\pi} K_m = 0$$
为将 $K_m$ 化为乘积因子，将上式展开

· 178 ·