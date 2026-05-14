## Page 299

间有摩擦力，故由一套专门的同步电动机通过减速器带动凸轮旋转，使检流计指针周期性地上下运动，每隔 $T$ 秒与电位器接触一次，每次接触时间为 $\tau$。其中，$T$ 称为采样周期，$\tau$ 称为采样持续时间。当炉温连续变化时，电位器的输出是一串宽度为 $\tau$ 的脉冲电压信号 $e^*(t)$，如图 7-2(a)所示。$e^*$ 经放大器、电动机及减速器去控制阀门开度 $\varphi$，以改变加热气体的进气量，使炉温趋于给定值。炉温的给定值，由给定电位器给出。

[Diagram Description: Figure 7-1 shows the principle of a furnace temperature sampling control system. It includes a "Given Potentiometer" connected to a "Temperature Measuring Resistor" ($\theta$) which monitors the "Heated Gas". The output goes to a "Detector" connected to a "Cam" driven by a "Motor and Reducer". The cam interacts with a "Potentiometer" which outputs $e^*$ to an "Amplifier" that controls the motor/reducer.]

[Diagram Description: Figure 7-2 shows the output voltage of the potentiometer. (a) Pulse output sequence: A series of pulses with width $\tau$ occurring at intervals of $T, 2T, 3T, 4T$. (b) Pulse output sequence: A series of pulses with width $\tau$ occurring at intervals of $T, 2T, 3T, 4T$ but with negative polarity.]

在炉温控制过程中，如果采用连续控制方式，则无法解决控制精度与动态性能之间的矛盾。炉温调节是一个大惯性过程，当加大开环增益以提高系统的控制精度时，由于系统的灵敏度相应提高，在炉温低于给定值的情况下，电动机将迅速增大阀门开度，给炉子供应更多的加热气体，但因炉温上升缓慢，在炉温升到给定值时，电动机已将阀门的开度开得更大了，从而炉温继续上升，结果造成反向调节，引起炉温振荡性调节过程；而在炉温高于给定值情况下，具有类似的调节过程。如果对炉温进行采样控制，只有当检流计的与电位器接触时，电动机才在采样信号下产生旋转运动，进行炉温调节；而在检流计与电位器脱开时，电动机就停止不动，保持一定的阀门开度，等待炉温缓慢变化。在采样控制情况下，电动机时转时停，所以调节过程中超调现象大为减小，甚至在采用较大开环增益下，不但能保证系统稳定，而且能使炉温调节过程无超调。

---

## Page 300

由例 7-1 可见，在采样系统中不仅有模拟部件，还有脉冲部件。通常，测量元件、执行元件和被控对象是模拟元件，其输入和输出是连续信号，即时间和幅值上都连续的信号，称为模拟信号；而控制器的脉冲元件，其输入和输出为脉冲序列，即时间上离散而幅值上连续的信号，称为离散模拟信号。为了使两种信号在系统中能相互传递，在连续信号和脉冲序列之间要用采样器，而在脉冲序列和连续信号之间要用保持器，以实现两种信号的转换。采样器和保持器，是采样控制系统中的两个特殊环节。

**(1) 采样和复现**

在采样控制系统中，把连续信号转变为脉冲序列的过程称为采样过程，简称采样。实现采样的装置称为采样器，或称采样开关。用 $T$ 表示采样周期，单位为 s; $f_s=1/T$ 表示采样频率，单位为 $\text{s}^{-1}$; $\omega_s=2\pi/T$ 表示采样角频率，单位为 $\text{rad/s}$。在实际应用中，采样开关多为电子开关，闭合时间极短，采样持续时间 $\tau$ 远小于采样周期 $T$，也远小于系统连续部分的最大时间常数。为了简化系统的分析，可认为 $\tau$ 趋于零，即把采样器的输出近似看成一串矩形脉冲面积的理想脉冲 $e^*(t)$，如图 7-2(b)所示。

在采样控制系统中，把脉冲序列转变为连续信号的过程称为信号复现过程。实现复现过程的装置称为保持器。采用保持器不仅因为需要实现两种信号之间的转换，也是因为采样器输出的脉冲信号 $e^*(t)$，如果不经滤波器将其恢复成连续信号，则 $e^*(t)$ 中的高频分量相当于系统中的连续部分加入了噪声，不但影响控制质量，严重时会加剧机械部件的磨损。因此，需要在采样器后串联一个信号复现滤波器，以使脉冲信号 $e^*(t)$ 复原成连续信号，再加到系统的连续部分。最简单的复现滤波器由保持器实现，可把脉冲信号 $e^*(t)$ 复现为阶梯信号 $e_h(t)$，如图 7-3 所示。由图可见，当采样频率足够高时，$e_h(t)$ 接近于连续信号。

[Diagram Description: Figure 7-3 shows the input and output signals of a holder. It shows a pulse sequence $e^*(t)$ being converted into a staircase signal $e_h(t)$ by a "Signal Reconstruction Filter (Holder)".]

**(2) 采样系统的典型结构图**

根据采样器在系统中所处的位置不同，可以构成各种采样系统。如果采样器位于系统闭合回路之外，或者系统本身不存在闭合回路，则称为开环采样系统；如果采样器位于系统闭合回路之内，则称为闭环采样系统。在各种采样控制系统中，得到最多的是误差采样控制的闭环采样系统，其典型结构如图 7-4 所示。图中，$S$ 为理想采样开关，其采样瞬时的脉冲幅值，等于相应采样瞬时误差信号 $e(t)$ 的幅值，且采样持续时间 $\tau$ 趋于零；$G_h(s)$ 为保持器的传递函数；$G_0(s)$ 为被控对象的传递函数；$H(s)$ 为测量变送反馈元件的传递函数。

由图 7-4 可见，采样开关 $S$ 的输出 $e^*(t)$ 的幅值，与其输入 $e(t)$ 的幅值之间存在线性关系。当采样开关和系统其余部分的传递函数都具有线性特性时，这样的系统就称为线性采样系统。

---

## Page 301

[Diagram Description: Figure 7-4 shows the typical structure of a sampling system. It consists of a feedback loop: $r(t)$ enters a summing junction, producing error $e(t)$. $e(t)$ goes through a sampler $S$ to become $e^*(t)$. $e^*(t)$ passes through a holder $G_h(s)$ and a plant $G_0(s)$ to produce output $c(t)$. $c(t)$ is fed back through $H(s)$ to the summing junction as $b(t)$.]

**2. 数字控制系统**

数字控制系统是一种以数字计算机为控制器去控制具有连续工作状态的被控对象的闭环控制系统。因此，数字控制系统包括工作于离散状态下的数字计算机和工作于连续状态下的被控对象大部分。由于数字控制系统具有一系列的优越性，所以在军事、航空及工业过程控制中，得到了广泛的应用。

例 7-2 图 7-5 是小口径高炮高精度数字伺服系统原理图。

[Diagram Description: Figure 7-5 shows the principle of a small-caliber anti-aircraft gun high-precision digital servo system. It includes:
- Inputs: "Coarse $\theta_e$ display", "Medium $\theta_e$ display", "Fine $\theta_e$ display".
- Digital Signal Generator and Error Display.
- A computer system with "2x8255A" and "D/A" converters.
- A "Digital Computer" block.
- An "Analog Filter" leading to a "PWM Amplifier".
- A "Servo Motor", "Tachogenerator (TG)", and "Reducer" driving the "Load".
- A "Multi-channel Rotary Transformer" providing feedback.
- A "Passive Correction Network" in the loop.]

现代的高炮伺服系统，已由数字系统取代了原来模拟系统的模式，使系统获得了高速、高精度、无超调的特性，其性能大大超过了原有的高炮伺服系统。如美国多管火炮反导系统“密集阵”、“守门员”等，均采用了数字伺服系统。

本例系统采用 MCS-96 系列单片机作为数字控制器，并结合 PWM(脉宽调制)直流伺服...