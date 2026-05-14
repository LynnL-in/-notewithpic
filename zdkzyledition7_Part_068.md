## Page 1

[Image Description: A diagram labeled "图 4-48 智能汽车-高速公路系统". Part (a) shows a schematic of an automated highway system with cars communicating with ground controllers and network controllers. Part (b) shows a block diagram of the vehicle spacing control system with a feedback loop involving a transfer function $\frac{1}{(s+3)(s+7)}$, a gain $K_a$, a feedback gain $K_i$, and an integrator $\frac{1}{s}$.]

**图 4-48 智能汽车-高速公路系统**

---

## Page 2

# 第五章 线性系统的频域分析法

控制系统中的信号可以表示为不同频率正弦信号的合成。控制系统的频率特性反映正弦信号作用下系统响应的性能。应用频率特性研究系统的经典方法为频域分析法。频域分析法具有以下特点：

1) 控制系统及其元件的频率特性可以运用分析法和实验方法获得，并可用多种形式的曲线表示，因而系统分析和控制器设计可以应用图解法进行。
2) 频率特性物理意义明确。对于一阶系统和二阶系统，频域性能指标和时域性能指标有确定的对应关系；对于高阶系统，可建立近似的对应关系。
3) 控制系统的频域设计可以兼顾动态响应和噪声抑制两方面的要求。
4) 频域分析法不仅适用于线性定常系统，还可以推广应用于某些非线性控制系统。

本章介绍频率特性的基本概念和频率特性曲线的绘制方法，研究频域稳定性判据和频域性能指标的估算。控制系统的频域综合问题，将在第六章介绍。

## 5-1 频率特性

### 1. 频率特性的基本概念

首先以图 5-1 所示的 RC 滤波网络为例，建立频率特性的基本概念。设电容 $C$ 的初始电压为 $u_{00}$，输入信号为正弦信号
$$u_i = A \sin \omega t \quad (5-1)$$
记录网络的输入、输出信号。当输出响应 $u_o$ 呈稳态时，记录曲线如图 5-2 所示。

由图 5-2 可见，RC 网络的稳态输出信号仍为正弦信号，频率与输入信号的频率相同，幅值较输入信号有一定衰减，其相位存在一定延迟。

[Image Description: Figure 5-1 shows an RC circuit with a resistor R in series and a capacitor C in parallel with the output. Figure 5-2 shows two sine wave graphs: the top one labeled $u_i$ with period $2\pi/\omega$, and the bottom one labeled $u_o$ with a phase shift $\varphi$ and period $2\pi/\omega$.]

**图 5-1 RC 滤波网络**
**图 5-2 RC 网络的输入和稳态输出信号**

RC 网络的输入和输出的关系可由以下微分方程描述：
$$T \frac{du_o}{dt} + u_o = u_i \quad (5-2)$$

* 195 *

---

## Page 3

式中，$T=RC$，为时间常数。取拉氏变换并代入初始条件 $u_o(0)=u_{00}$，得
$$U_o(s) = \frac{1}{Ts+1} [U_i(s) + Tu_{00}] = \frac{1}{Ts+1} \left( \frac{A\omega}{s^2 + \omega^2} + Tu_{00} \right) \quad (5-3)$$

再由拉氏反变换求得
$$u_o(t) = \left( u_{00} + \frac{A\omega T}{1+T^2\omega^2} \right) e^{-\frac{t}{T}} + \frac{A}{\sqrt{1+T^2\omega^2}} \sin(\omega t - \arctan \omega T) \quad (5-4)$$

式中第一项，由于 $T>0$，将随时间增大而趋于零，为输出的瞬态分量；而第二项正弦信号为输出的稳态分量
$$u_{os}(t) = \frac{A}{\sqrt{1+T^2\omega^2}} \sin(\omega t - \arctan \omega T)$$
$$= A \cdot A(\omega) \sin(\omega t + \varphi(\omega)) \quad (5-5)$$

在式(5-5)中，$A(\omega) = \frac{1}{\sqrt{1+T^2\omega^2}}$，$\varphi(\omega) = -\arctan \omega T$，分别反映 RC 网络在正弦信号作用下，输出稳态分量的幅值和相位的变化，称为幅值比和相位差，且皆为输入正弦信号频率 $\omega$ 的函数。

注意到 RC 网络的传递函数为
$$G(s) = \frac{1}{Ts+1} \quad (5-6)$$

取 $s=j\omega$，则有
$$G(j\omega) = G(s)|_{s=j\omega} = \frac{1}{\sqrt{1+T^2\omega^2}} e^{-j\arctan \omega T} \quad (5-7)$$

比较式(5-5)和式(5-7)可知，$A(\omega)$ 和 $\varphi(\omega)$ 分别为 $G(j\omega)$ 的幅值 $|G(j\omega)|$ 和相角 $\angle G(j\omega)$。这一结论非常重要，反映了 $A(\omega)$ 和 $\varphi(\omega)$ 与系统数学模型的本质关系，具有普遍性。

设有稳定的线性定常系统，其传递函数为
$$G(s) = \frac{\sum_{i=0}^m b_i s^{m-i}}{\sum_{i=0}^n a_i s^{n-i}} = \frac{B(s)}{A(s)} \quad (5-8)$$

系统输入为谐波信号
$$r(t) = A \sin(\omega t + \varphi)$$
$$R(s) = \frac{A(\omega \cos \varphi + s \sin \varphi)}{s^2 + \omega^2} \quad (5-10)$$

由于系统稳定，输出响应稳态分量的拉氏变换
$$C_s(s) = \frac{1}{s+j\omega} [(s+j\omega)R(s)G(s)]|_{s=-j\omega} + \frac{1}{s-j\omega} [(s-j\omega)R(s)G(s)]|_{s=j\omega} \quad (5-11)$$
$$= \frac{A \cos \varphi - j \sin \varphi}{-2j} G(-j\omega) + \frac{A \cos \varphi + j \sin \varphi}{2j} G(j\omega)$$

* 196 *