==Start of PDF==

[Page 1]

$$+ \left( \frac{\partial^2 f}{\partial x_2^2} \right)_{x_{10}, x_{20}} (x_2 - x_{20})^2 + \cdots$$

略去二阶以上导数项，并令 $\Delta y = y - f(x_{10}, x_{20})$, $\Delta x_1 = x_1 - x_{10}$, $\Delta x_2 = x_2 - x_{20}$，可得增量线性化方程

$$\Delta y = \left( \frac{\partial f}{\partial x_1} \right)_{x_{10}, x_{20}} \Delta x_1 + \left( \frac{\partial f}{\partial x_2} \right)_{x_{10}, x_{20}} \Delta x_2 = K_1 \Delta x_1 + K_2 \Delta x_2$$

式中，$K_1 = (\partial f / \partial x_1)_{x_{10}, x_{20}}$; $K_2 = (\partial f / \partial x_2)_{x_{10}, x_{20}}$。

这种小偏差线性化对于控制系统大多数工作状态是可行的。事实上，自动控制系统在正常情况下都处于一个稳定的工作状态，即平衡状态，这时被控量与期望值保持一致，控制系统也不进行控制动作。一旦被控量偏离期望值产生偏差时，控制系统便开始控制动作，以便减小或消除这个偏差，因此，控制系统中的偏差一般不会很大，只是“小偏差”。在建立控制系统的数学模型时，通常是将系统的稳定工作状态作为起始状态，仅仅研究小偏差的运动情况，也就是只研究相对于平衡状态下，系统入量和输出量的运动特性，这正是增量线性化方程所描述的系统特性。

例 2-7 设铁心线圈电路如图 2-7(a)所示，其磁通 $\phi$ 与线圈中电流 $i$ 之间关系如图 2-7(b)所示。试列写以 $u_r$ 为输入量，$i$ 为输出量的电路微分方程。

解 设铁心线圈磁通变化时产生的感应电势为

$$u_\phi = K_1 \frac{d\phi(i)}{dt}$$

[Diagram Description: Figure 2-7(a) shows a circuit diagram with a voltage source $u_r$ connected in series with a resistor $R$ and an iron-core coil. Figure 2-7(b) shows a graph of magnetic flux $\phi$ versus current $i$, with a curve passing through the origin and a tangent line at point $(i_0, \phi_0)$ showing $\Delta \phi$ and $\Delta i$.]

图 2-7 铁心线圈电路及其特性

根据法拉第定律写出电路微分方程

$$u_r = K_1 \frac{d\phi(i)}{dt} + Ri = K_1 \frac{d\phi(i)}{di} \frac{di}{dt} + Ri \quad (2-33)$$

式中，$d\phi(i)/di$ 是线圈中电流 $i$ 的非线性函数，因此，式(2-33)是一个非线性微分方程。

在工程应用中，如果电路的电压和电流只在某平衡点 $(u_0, i_0)$ 附近作微小变化，则可设 $u_r$ 相对于 $u_0$ 的增量是 $\Delta u_r$，$i$ 相对于 $i_0$ 的增量是 $\Delta i$，并设 $\phi(i)$ 在 $i_0$ 的邻域内连续可导，这样可将 $\phi(i)$ 在 $i_0$ 附近用泰勒级数展开为

$$\phi(i) = \phi(i_0) + \left( \frac{d\phi(i)}{di} \right)_{i_0} \Delta i + \frac{1}{2!} \left( \frac{d^2\phi(i)}{di^2} \right)_{i_0} (\Delta i)^2 + \cdots$$

当 $\Delta i$ 足够小时，略去高阶导数项，可得

$$\phi(i) - \phi(i_0) = \left( \frac{d\phi(i)}{di} \right)_{i_0} \Delta i = K \Delta i$$

式中，$K = (d\phi(i)/di)_{i_0}$。令 $\Delta \phi = \phi(i) - \phi(i_0)$，便得到磁通 $\phi$ 与电流 $i$ 之

• 32 •

[Page 2]

间的增量线性化方程为

$$\Delta \phi = K \Delta i \quad (2-34)$$

由式(2-34)可求得 $d\phi(i)/di = K$，代入式(2-33)，有

$$K_1 K \frac{di}{dt} + Ri = u_r \quad (2-35)$$

式(2-35)便是铁心线圈电路在平衡点 $(u_0, i_0)$ 的增量线性化微分方程，若平衡点变动时，$K$ 值亦相应改变。

**6. 运动的模态**

在数学上，线性微分方程的解由输入作用下的特解和齐次微分方程的通解组成。通解由微分方程的特征根所决定，它代表自由运动。如果 $n$ 阶微分方程的特征根是 $\lambda_1, \lambda_2, \cdots, \lambda_n$ 且无重根，则把函数 $e^{\lambda_1 t}, e^{\lambda_2 t}, \cdots, e^{\lambda_n t}$ 称为该微分方程所描述运动的模态，也叫振型。每一种模态代表一种类型的运动形态，齐次微分方程的通解则是它们的线性组合，即

$$y_0(t) = c_1 e^{\lambda_1 t} + c_2 e^{\lambda_2 t} + \cdots + c_n e^{\lambda_n t}$$

式中，系数 $c_1, c_2, \cdots, c_n$ 是由初始条件决定的常数。

如果特征根中有多个重根，则模态会具有形如 $te^{\lambda t}, t^2 e^{\lambda t}, \cdots$ 的函数；如果特征根中有共轭复根 $\lambda = \sigma \pm j\omega$，则其共轭模态 $e^{(\sigma + j\omega)t}$ 与 $e^{(\sigma - j\omega)t}$ 可写成实函数模态 $e^{\sigma t} \sin \omega t$ 与 $e^{\sigma t} \cos \omega t$。

在例 2-6 中，微分方程的特征根 $\lambda = -0.5 \pm j0.866$，故其共轭模态 $e^{(-0.5 + j0.866)t}$ 与 $e^{(-0.5 - j0.866)t}$，或 $e^{-0.5t} \sin 0.866t$ 与 $e^{-0.5t} \cos 0.866t$，则微分方程的齐次通解为

$$u_0(t) = c_1 e^{-0.5t} \sin 0.866t + c_2 e^{-0.5t} \cos 0.866t$$

由给定初始条件 $u_0(0) = 0.1\text{V}, i(0) = 0.1\text{A}$ 可求得 $c_1 = 0.173, c_2 = 0.1$，故得

$$u_0(t) = 0.173 e^{-0.5t} \sin 0.866t + 0.1 e^{-0.5t} \cos 0.866t$$

这个结果与例 2-6 中 $u_0(t)$ 的零输入分量 $0.2 e^{-0.5t} \sin(0.866t + 30^\circ)$ 是一致的。

**2-2 控制系统的复域数学模型**

控制系统的微分方程是在时间域描述动态性能的数学模型，在给定外作用及初始条件下，求解微分方程可以得到系统的输出响应。这种方法比较直观，特别是借助由于计算机可以迅速而准确地求得结果。但是如果系统的结构改变或某个参数变化时，就要重新列写并求解微分方程，不便于系统进行分析和设计。

用拉氏变换法求解线性系统的微分方程时，可以得到控制系统在复数域中的数学模型——传递函数。传递函数不仅可以表征系统的动态性能，而且可以用来研究系统的结构或参数变化对系统性能的影响。经典控制理论中广泛应用的频率法和根轨迹法，就是以传递函数为基础建立起来的，传递函数是经典控制理论中最基本和最重要的概念。

• 33 •

[Page 3]

**1. 传递函数的定义和性质**

**(1) 传递函数的定义**

线性定常系统的传递函数，定义为零初始条件下，系统输出量的拉氏变换与输入量的拉氏变换之比。

设线性定常系统由下述 $n$ 阶线性常微分方程描述：

$$a_0 \frac{d^n c(t)}{dt^n} + a_1 \frac{d^{n-1} c(t)}{dt^{n-1}} + \cdots + a_{n-1} \frac{d c(t)}{dt} + a_n c(t)$$
$$= b_0 \frac{d^m r(t)}{dt^m} + b_1 \frac{d^{m-1} r(t)}{dt^{m-1}} + \cdots + b_{m-1} \frac{d r(t)}{dt} + b_m r(t) \quad (2-36)$$

式中，$c(t)$ 是系统输出量；$r(t)$ 是系统输入量；$a_i (i = 1, 2, \cdots, n)$ 和 $b_j (j = 1, 2, \cdots, m)$ 是与系统结构和参数有关的常系数。设 $r(t)$ 和 $c(t)$ 及其各阶导数在 $t=0$ 时的值均为零，即零初始条件，则对上式中各项分别求拉氏变换，并令 $C(s) = \mathscr{L}[c(t)]$, $R(s) = \mathscr{L}[r(t)]$，可得 $s$ 的代数方程为

$$\left[ a_0 s^n + a_1 s^{n-1} + \cdots + a_{n-1} s + a_n \right] C(s) = \left[ b_0 s^m + b_1 s^{m-1} + \cdots + b_{m-1} s + b_m \right] R(s)$$

于是，由定义得系统传递函数

$$G(s) = \frac{C(s)}{R(s)} = \frac{b_0 s^m + b_1 s^{m-1} + \cdots + b_{m-1} s + b_m}{a_0 s^n + a_1 s^{n-1} + \cdots + a_{n-1} s + a_n} = \frac{M(s)}{N(s)} \quad (2-37)$$

式中

$$M(s) = b_0 s^m + b_1 s^{m-1} + \cdots + b_{m-1} s + b_m$$
$$N(s) = a_0 s^n + a_1 s^{n-1} + \cdots + a_{n-1} s + a_n$$

例 2-8 试求例 2-1 RLC 无源网络的传递函数 $U_o(s)/U_i(s)$。

解 RLC 网络的微分方程用式(2-1)表示为

$$LC \frac{d^2 u_o(t)}{dt^2} + RC \frac{d u_o(t)}{dt} + u_o(t) = u_i(t)$$

在零初始条件下，对上述方程中各项求拉氏变换，并令 $U_o(s) = \mathscr{L}[u_o(t)]$, $U_i(s) = \mathscr{L}[u_i(t)]$，可得 $s$ 的代数方程为 $(LCs^2 + RCs + 1)U_o(s) = U_i(s)$，由传递函数定义，网络传递函数为

$$G(s) = \frac{U_o(s)}{U_i(s)} = \frac{1}{LCs^2 + RCs + 1} \quad (2-38)$$

**(2) 传递函数性质**

1) 传递函数是复变量 $s$ 的有理分式函数，具有复变函数的所有性质；$m \le n$，且所有系数均为实数。

2) 传递函数是一种系统参数表示输出量与输入量之间关系的表达式，它只取决于系统或元件的结构和参数，而与输入量的形式无关，也不反映系统内部的任何信息。

[Diagram Description: A block diagram showing an input $R(s)$ entering a block labeled $G(s)$, which outputs $C(s)$.]

图 2-8 传递函数的图示

因此，可以用图 2-8 的方块图表示一个具有传递函数 $G(s)$ 的线性系统。图中表明，系统输入量与输出量的因果关系可以用传递函数联系起来。

3) 传递函数与微分方程有相通性。传递函数分子多

• 34 •

==End of PDF==