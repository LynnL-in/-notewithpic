设
$$G(j\omega) = \frac{a(\omega) + jb(\omega)}{c(\omega) + jd(\omega)} = |G(j\omega)|e^{j\angle G(j\omega)} \quad (5-12)$$
因为 $G(s)$ 的分子和分母多项式为实系数，故式(5-12)中的 $a(\omega)$ 和 $c(\omega)$ 为关于 $\omega$ 的偶次幂实系数多项式，$b(\omega)$ 和 $d(\omega)$ 为关于 $\omega$ 的奇次幂实系数多项式，即 $a(\omega)$ 和 $c(\omega)$ 为 $\omega$ 的偶函数，$b(\omega)$ 和 $d(\omega)$ 为 $\omega$ 的奇函数。鉴于
$$|G(j\omega)| = \sqrt{\frac{b^2(\omega) + a^2(\omega)}{c^2(\omega) + d^2(\omega)}} \quad (5-13)$$
$$\angle G(j\omega) = \arctan \frac{b(\omega)c(\omega) - a(\omega)d(\omega)}{a(\omega)c(\omega) + d(\omega)b(\omega)} \quad (5-14)$$
因而
$$G(-j\omega) = \frac{a(\omega) - jb(\omega)}{c(\omega) - jd(\omega)} = |G(j\omega)|e^{-j\angle G(j\omega)} \quad (5-15)$$
再由式(5-11)得
$$C_s(s) = \frac{A|G(j\omega)|e^{-j(\phi + \angle G(j\omega))}}{s + j\omega} + \frac{A|G(j\omega)|e^{j(\phi + \angle G(j\omega))}}{s - j\omega}$$
$$c_s(t) = A|G(j\omega)| \left[ \frac{e^{j(\omega t + \phi + \angle G(j\omega))} - e^{-j(\omega t + \phi + \angle G(j\omega))}}{2j} \right] \quad (5-16)$$
$$= A|G(j\omega)| \sin(\omega t + \phi + \angle G(j\omega))$$
式(5-16)与式(5-5)相比较，得
$$\begin{cases} A(\omega) = |G(j\omega)| \\ \phi(\omega) = \angle G(j\omega) \end{cases} \quad (5-17)$$
式(5-16)表明，对于稳定的线性定常系统，由谐波输入产生的输出稳态分量仍然是与输入同频率的谐波函数，而幅值和相位的变化是频率 $\omega$ 的函数，且与系统数学模型相关。为此，定义谐波输入下，输出响应中与输入同频率的谐波分量与谐波输入的幅值之比 $A(\omega)$ 为幅频特性，相位之差 $\phi(\omega)$ 为相频特性，并称其指数表达式
$$G(j\omega) = A(\omega)e^{j\phi(\omega)} \quad (5-18)$$
为系统的频率特性。

上述频率特性的定义既可以适用于稳定系统，也可适用于不稳定系统。稳定系统的频率特性可以用实验方法确定，即在系统的输入端施加不同频率的正弦信号，然后测量系统输出的稳态响应，再根据幅值比和相位差作出系统的频率特性曲线。频率特性也是系统数学模型的一种表达形式。RC 滤波网络的频率特性曲线如图 5-3 所示。

对于不稳定系统，输出响应分量中含有由系统传递函数的不稳定极点产生的呈发散或振荡发散的分量，所以不稳定系统的频率特性不能通过实验方法确定。

线性定常系统的传递函数为零初始条件下，输出和输入的拉氏变换之比
$$G(s) = \frac{C(s)}{R(s)}$$
• 197 •

---

[图 5-3 RC 网络的幅频特性和相频特性曲线(MATLAB)]
(a) 幅频特性：横坐标为 $\omega T$ (0 到 5.0)，纵坐标为 $1/\sqrt{1+\omega^2 T^2}$ (0 到 1.0)。曲线从 (0, 1) 开始，随 $\omega T$ 增大单调下降。
(b) 相频特性：横坐标为 $\omega T$ (0 到 5.0)，纵坐标为 $-\arctan \omega T$ (0 到 -100)。曲线从 (0, 0) 开始，随 $\omega T$ 增大单调下降，趋近于 -90。

上式的反变换式为
$$g(t) = \frac{1}{2\pi j} \int_{\sigma - j\infty}^{\sigma + j\infty} G(s)e^{st} ds$$
式中，$\sigma$ 位于 $G(s)$ 的收敛域。若系统稳定，则 $\sigma$ 可以取为零。如果 $r(t)$ 的傅氏变换存在，可令 $s=j\omega$
$$g(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} G(j\omega)e^{j\omega t} d\omega = \frac{1}{2\pi} \int_{-\infty}^{\infty} \frac{C(j\omega)}{R(j\omega)}e^{j\omega t} d\omega$$
因而
$$G(j\omega) = \left. \frac{C(j\omega)}{R(j\omega)} \right|_{s=j\omega} \quad (5-19)$$

[图 5-4 频率特性、传递函数和微分方程三种系统描述之间的关系]
图示为一个循环流程图：
- 微分方程 $\xrightarrow{s=j\omega}$ 频率特性
- 微分方程 $\xrightarrow{L}$ 传递函数
- 传递函数 $\xrightarrow{s=j\omega}$ 频率特性
- 频率特性 $\xrightarrow{s=j\omega}$ 传递函数
- 传递函数 $\xrightarrow{L^{-1}}$ 微分方程
- 系统位于中心。

由此可知，稳定系统的频率特性等于输出和输入的傅氏变换之比，而这正是频率特性的物理意义。频率特性与微分方程和传递函数一样，也表征了系统的运动规律，成为系统频域分析的理论依据。系统三种描述方法的关系可用图 5-4 说明。

### 2. 频率特性的几何表示法
在工程分析和设计中，通常把线性系统的频率特性画成曲线，再运用图解法进行研究。常用的频率特性曲线有以下三种：

(1) 幅相频率特性曲线
它又简称为幅相曲线或极坐标图。以横轴为实轴、纵轴为虚轴，构成复数平面。对于任一给定的频率 $\omega$，频率特性值为复数。若将频率特性表示为实数和虚数的形式，则实部为实轴坐标值，虚部为虚轴坐标值。若将频率特性表示为复指数形式，则为复平面上的向量，而向量的长度为频率特性的幅值，向量与实轴正方向的夹角等于频率特性的相位。由于幅频特性为 $\omega$ 的偶函数，相频特性为 $\omega$ 的奇函数，则 $\omega$ 从零变化至 $+\infty$ 和 $\omega$ 从零变化至 $-\infty$ 的幅相曲线关于实轴对称，因此一般只绘制 $\omega$ 从零变化至 $+\infty$ 的幅相曲线。在系统幅相曲线中，频率 $\omega$ 为参变量，一般用小箭头表示 $\omega$ 增大时幅相曲线的变化方向。

• 198 •

---

对于 RC 网络
$$G(j\omega) = \frac{1}{1 + jT\omega} = \frac{1 - jT\omega}{1 + (T\omega)^2}$$
故有
$$\left[ \text{Re}G(j\omega) - \frac{1}{2} \right]^2 + \text{Im}^2 G(j\omega) = \left( \frac{1}{2} \right)^2$$
表明 RC 网络的幅相曲线是以 $(\frac{1}{2}, j0)$ 为圆心，半径为 $\frac{1}{2}$ 的半圆，如图 5-5 所示。

[图 5-5 RC 网络的幅相曲线]
图示为复平面，横轴为 $\text{Re}G(j\omega)$，纵轴为 $\text{Im}G(j\omega)$。圆心在 $(0.5, 0)$，圆弧从原点 $(0,0)$ 出发，经过第四象限，终点在 $(1,0)$。$\omega=0$ 处在 $(1,0)$，$\omega=\infty$ 处在 $(0,0)$。

(2) 对数频率特性曲线
它又称为伯德曲线或伯德图。对数频率特性曲线由对数幅频曲线和对数相频曲线组成，是工程中广泛使用的一组曲线。
对数幅频曲线的横坐标按 $\lg\omega$ 度量，单位为弧度/秒(rad/s)，对数幅频曲线的纵坐标按
$$L(\omega) = 20\lg |G(j\omega)| = 20\lg A(\omega) \quad (5-20)$$
线性分度，单位是分贝(dB)。对数相频曲线的纵坐标按 $\phi(\omega)$ 线性分度，单位为度(°)。由此构成的坐标系称为半对数坐标系。

对数分度和线性分度如图 5-6 所示，在线性分度中，当变量增大或减小 1 时，坐标间距变化一个单位长度；而在对数分度中，当变量增大或减小 10 倍，称为十倍频程(dec)，坐标间距变化一个单位长度。设对数分度中的单位长度为 $l$，$\omega$ 的某个十倍频程的左端点为 $\omega_0$，则坐标点相对于左端点的距离为表 5-1 所示值乘以 $l$。

[图 5-6 对数分度与线性分度]
(a) 对数分度：横轴标有 1, 2, 4, 6, 8, 10, 20, 40, 60, 80, 100。标注了“一倍频程”和“十倍频程”。
(b) 线性分度：横轴标有 0, 1, 2, 3, 4, 5, 6, 7。

表 5-1 十倍频程中的对数分度

| $\omega/\omega_0$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $\lg(\omega/\omega_0)$ | 0 | 0.301 | 0.477 | 0.602 | 0.699 | 0.788 | 0.845 | 0.903 | 0.954 | 1 |

• 199 •