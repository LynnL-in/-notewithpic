贝，即 $0.707|\Phi(j0)|(\text{dB})$ 时，对应的频率称为带宽频率，记为 $\omega_b$。即当 $\omega > \omega_b$ 时
$$20\lg|\Phi(j\omega)| < 20\lg|\Phi(j0)| - 3 \quad (5-88)$$
而频率范围$(0, \omega_b)$称为系统的带宽，如图 5-43 所示。带宽定义表明，对高于带宽频率的正弦输入信号，系统输出将呈现较大的衰减。对于 I 型和 II 型以上的开环系统，由于 $|\Phi(j0)|=1$, $20\lg|\Phi(j0)|=0$, 故
$$20\lg|\Phi(j\omega)| < -3 (\text{dB}), \omega > \omega_b \quad (5-89)$$
带宽是频域中一项非常重要的性能指标。对于一阶和二阶系统，带宽频率和系统参数具有解析关系。

设一阶系统的闭环传递函数为
$$\Phi(s) = \frac{1}{Ts+1}$$
因为开环系统为 I 型，$\Phi(j0)=1$，按带宽定义
$$20\lg|\Phi(j\omega_b)| = 20\lg\frac{1}{\sqrt{1+T^2\omega_b^2}} = 20\lg\frac{1}{\sqrt{2}}$$
可求得带宽频率
$$\omega_b = \frac{1}{T} \quad (5-90)$$

对于二阶系统，闭环传递函数为
$$\Phi(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$$
系统幅频特性
$$|\Phi(j\omega)| = \frac{1}{\sqrt{\left(1-\frac{\omega^2}{\omega_n^2}\right)^2 + 4\zeta^2\frac{\omega^2}{\omega_n^2}}}$$
因为 $|\Phi(j0)|=1$，由带宽定义
$$\sqrt{\left(1-\frac{\omega_b^2}{\omega_n^2}\right)^2 + 4\zeta^2\frac{\omega_b^2}{\omega_n^2}} = \sqrt{2}$$
于是
$$\omega_b = \omega_n \left[ (1-2\zeta^2) + \sqrt{(1-2\zeta^2)^2 + 1} \right]^{\frac{1}{2}} \quad (5-91)$$
由式(5-90)知，一阶系统的带宽频率和时间常数 $T$ 成反比。由式(5-91)知，二阶系统的带宽频率和自然频率 $\omega_n$ 成正比。令 $A = \left(\frac{\omega_b}{\omega_n}\right)^2$，由于
$$\frac{dA}{d\zeta} = \frac{-4\zeta}{\sqrt{(1-2\zeta^2)^2+1}} \left[ \sqrt{(1-2\zeta^2)^2+1} + (1-2\zeta^2) \right] < 0$$
· 233 ·

$A$ 为 $\zeta$ 的减函数，故 $\omega_b$ 为 $\zeta$ 的减函数，即 $\omega_b$ 与阻尼比 $\zeta$ 成反比。根据第三章中一阶系统和二阶系统上升时间和调节时间与参数的关系可知，系统的单位阶跃响应的速度和带宽成正比。对于任意阶次的控制系统，这一关系仍然成立。

设两个控制系统存在以下关系：
$$\Phi_1(s) = \Phi_2\left(\frac{s}{\lambda}\right) \quad (5-92)$$
其中 $\lambda$ 为任意正数。两个系统的闭环频率特性亦有
$$\Phi_1(j\omega) = \Phi_2\left(j\frac{\omega}{\lambda}\right)$$
当对数幅频特性 $20\lg|\Phi_1(j\omega)|$ 和 $20\lg|\Phi_2(j\frac{\omega}{\lambda})|$ 的横坐标分别为 $\omega$ 和 $\frac{\omega}{\lambda}$ 时，其对数幅频特性曲线具有相同的形状，按带宽定义可得
$$\omega_{b1} = \lambda\omega_{b2}$$
即系统 $\Phi_1(s)$ 的带宽频率为系统 $\Phi_2(s)$ 带宽频率的 $\lambda$ 倍。设两个系统的单位阶跃响应分别为 $c_1(t)$ 和 $c_2(t)$，按拉氏变换，有
$$\frac{1}{s}\Phi_1(s) = \int_0^\infty c_1(t)e^{-st}dt = \frac{1}{\lambda} \cdot \frac{1}{\frac{s}{\lambda}} \Phi_2\left(\frac{s}{\lambda}\right) = \int_0^\infty c_2(\lambda t)e^{-st}dt$$
即得
$$c_1(t) = c_2(\lambda t) \quad (5-93)$$
由时域性能指标可知，系统 $\Phi_1(s)$ 的上升时间和过渡过程时间为 $\Phi_2(s)$ 的 $1/\lambda$ 倍。即当系统的带宽扩大 $\lambda$ 倍，系统的响应速度则加快 $\lambda$ 倍。鉴于系统复现输入信号的能力取决于系统的幅频特性和相频特性，对于输入端信号，带宽大，则跟踪控制信号的能力强；而在另一方面，抑制输入端高频干扰的能力则弱，因此系统带宽的选择在设计中应折中考虑，不能一味求大。

**2. 系统带宽与信号频谱的关系**

受环境变化，元器件老化，电源波动和传感器、执行器非线性因素的影响，系统的输入和输出端不可避免地存在扰动和噪声，因此控制系统带宽的选择需综合考虑各种输入信号的频率范围及其对系统性能的影响，即使使系统对控制输入信号具有良好的跟踪能力和对扰动输入信号具有较强的抑制能力。从误差的角度来看，就是使各种输入信号所产生的误差尽可能地小。因此很有必要分析信号的频域分布及其对误差的影响。

(1) 周期信号的频谱
设 $f(t)$ 为周期函数，其周期为 $T$，可用下式描述：
$$f(t) = f(t+lT); \quad l=0, \pm 1, \cdots \quad (5-94)$$
若 $f(t)$ 在区间 $[0, T]$ 内有界，且仅有有限个极值，即满足狄利克雷条件，则 $f(t)$ 可展开为傅里叶级数
$$f(t) = \sum_{k=-\infty}^{\infty} c_k e^{j\frac{2\pi k}{T}t} \quad (5-95)$$
· 234 ·

其中 $c_k$ 为复数，称为傅里叶系数，
$$c_k = \frac{1}{T} \int_0^T f(t) e^{-j\frac{2\pi k}{T}t} dt = \frac{A_k}{2} e^{jB_k} \quad (5-96)$$
且有
$$c_0 = \frac{A_0}{2}, \quad c_{-k} = \overline{c_k} = \frac{A_k}{2} e^{-jB_k}$$
代入式(5-95)可得
$$f(t) = \frac{A_0}{2} + \sum_{k=1}^{\infty} A_k \cos\left(\frac{2\pi k}{T}t + B_k\right) \quad (5-97)$$
复数表达式中的 $A_k$ 和 $B_k$ 表示 $f(t)$ 的第 $k$ 次谐波分量的幅值和相位，称系数 $c_k$ 的集合为周期信号的频谱。频谱可以有不同的表示形式，有时只列出复系数的幅值谱。对于图 5-44(a)所示的矩形波序列，其基波频率和复系数的幅值分别为
$$\Omega = \frac{2\pi}{T}, \quad |c_k| = \frac{A\tau}{T} \left| \frac{\sin\frac{\pi k\tau}{T}}{\frac{\pi k\tau}{T}} \right|$$
幅值谱如图 5-44(b)所示。

**图 5-44 矩形波及其幅值谱**
*   **(a) 矩形波**：显示一个周期为 $T$ 的矩形波信号，脉冲宽度为 $\tau$，幅值为 $A$。波形在 $[-T, -T/2]$ 之间为 0，在 $[-T/2, -T/2+\tau]$ 之间为 $A$，在 $[-T/2+\tau, T/2]$ 之间为 0，在 $[T/2, T/2+\tau]$ 之间为 $A$。
*   **(b) 幅值谱**：显示离散的幅值谱线，横坐标为频率 $\omega$，纵坐标为 $|c_k|$。谱线分布在 $0, \pm\Omega, \pm 2\Omega, \dots$ 等位置，其包络线为 $\text{sinc}$ 函数形状，在 $\omega=0$ 处达到最大值 $A\tau/T$。

由图 5-44 可知，周期信号的幅值谱为一簇谱线，随 $k$ 增大，即 $\omega = \frac{2\pi}{T}k$ 的增大，幅值谱的包络线衰减。若系统的控制输入为矩形波时，系统的跟踪能力取决于带宽覆盖矩形波频谱的范围，带宽大则处于较高频率范围的谱线衰减小，故失真小。

(2) 非周期函数的频谱
非周期函数可以看做是周期 $T \to \infty$ 的周期函数。若 $f(t)$ 为绝对可积函数，则 $f(t)$ 可以表示为傅里叶积分
$$f(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} F(j\omega) e^{j\omega t} d\omega \quad (5-98)$$
$$F(j\omega) = \int_{-\infty}^{\infty} f(t) e^{-j\omega t} dt \quad (5-99)$$
$f(t)$ 和 $F(j\omega)$ 构成傅氏变换对，而 $F(j\omega)$ 表示 $f(t)$ 谐波的分布特性，也简称为频谱。与周
· 235 ·