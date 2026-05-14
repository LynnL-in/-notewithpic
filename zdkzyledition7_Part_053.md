## Page 1

[Image: A photograph of a Moller 400 vertical take-off aircraft.]

(a) 垂直起飞飞机

[Diagram: A block diagram showing a feedback control loop. The input $R(s)$ enters a summing junction. The output of the junction goes to a block $\frac{K_1(4s^2+2s+1)}{s}$, then to a block $\frac{1}{s^2(s^2+s+4)}$, resulting in output $H(s)$. A feedback path returns $H(s)$ to the negative input of the summing junction.]

(b) 控制系统结构图

图 3-73 垂直起飞飞机高度控制系统

[Diagram: A block diagram showing a feedback control loop. The input $R(s)$ (labeled "转向指令") enters a summing junction. The output goes to a block $\frac{10}{s+10}$, then to a block $\frac{1}{s^2}$, resulting in output $C(s)$ (labeled "漫游方向"). A feedback path with block $H(s)$ returns the signal to the negative input of the summing junction.]

图 3-74 火星漫游车导向控制系统结构图

[Image: A diagram showing a Maglev train (labeled "车体") above a T-shaped rail (labeled "T形导轨"). An electromagnet (labeled "电磁铁") is shown between the train and the rail, with a gap (labeled "气隙").]

(a) 磁悬浮列车

[Diagram: A block diagram showing a feedback control loop. The input $R(s)$ (labeled "预期间隙") enters a summing junction. The output goes to a controller block $G_c(s)$, then to a plant block $\frac{s-4}{(s+2)^2}$ (labeled "车体与悬浮线圈 $G_0(s)$"), resulting in output $C(s)$ (labeled "气隙"). A feedback path returns the signal to the negative input of the summing junction.]

(b) 间隙控制系统结构图

图 3-75 磁悬浮列车控制系统

· 149 ·

---

## Page 2

# 第四章 线性系统的根轨迹

## 4-1 根轨迹的基本概念

根轨迹是分析和设计线性定常控制系统的图解方法，使用十分简便，特别在进行多回路系统的分析时，应用根轨迹法比用其他方法更为方便，因此在工程实践中获得了广泛应用。本节主要介绍根轨迹的基本概念，根轨迹与系统性能之间的关系，并从闭环零、极点与开环零、极点之间的关系推导出根轨迹方程，然后将向量形式的根轨迹方程转化为常用的相角条件和模值条件形式，最后应用这些条件绘制简单系统的根轨迹。

### 1. 根轨迹概念

根轨迹简称根迹，它是开环系统某一部分从零变到无穷时，闭环系统特征方程的根在 $s$ 平面上变化的轨迹。

当闭环系统没有零点与极点相消时，闭环特征方程的根就是闭环传递函数的极点，我们常称之为闭环极点。因此，从已知的开环零、极点位置及某一变化的参数来求取闭环极点的分布，实际上就是解闭环特征方程的求根问题。当特征方程的阶数高于四阶时，除了应用 MATLAB 软件包，求根过程是比较复杂的。如果要研究系统参数变化对闭环特征方程的影响，就需要进行大量的反复计算，同时还不能直观看出影响趋势。因此对于高阶系统的求根问题，解析法就显得很不方便。1948 年，W. R. 伊文思在“控制系统的图解分析”一文中，提出了根轨迹法。当开环增益或其他参数改变时，其全部数值对应的闭环极点均可在根轨迹图上简便地确定。因为系统的稳定性由系统闭环极点唯一确定，而系统的稳态性能和动态性能又与闭环零、极点在 $s$ 平面上的位置密切相关，所以根轨迹图不仅可以直接给出闭环系统时间响应的全部信息，而且可以指明开环零、极点应该怎样变化才能满足给定的闭环系统的性能要求。除此之外，用根轨迹法求解高阶方程的根，比用其他近似法简便。

为了具体说明根轨迹的概念，设控制系统如图 4-1 所示，其闭环传递函数为
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{2K}{s^2 + 2s + 2K}$$

[Diagram: A block diagram showing a feedback control loop. Input $R(s)$ enters a summing junction. The output goes to a block $\frac{K}{s(0.5s+1)}$, then to output $C(s)$. A feedback path returns $C(s)$ to the negative input of the summing junction.]

图 4-1 控制系统结构图

于是，特征方程可写为
$$s^2 + 2s + 2K = 0$$

显然，特征方程的根是
$$s_1 = -1 + \sqrt{1 - 2K}$$
$$s_2 = -1 - \sqrt{1 - 2K}$$

如果令开环增益 $K$ 从零变到无穷，可

· 150 ·

---

## Page 3

以用解析的方法求出闭环极点的全部数值，将这些数值标注在 $s$ 平面上，并连成光滑的粗实线，如图 4-2 所示。图上，粗实线就称为系统的根轨迹，根轨迹上的箭头表示随着 $K$ 值的增加，根轨迹的变化趋势，而标注的数值则代表与闭环极点位置相应的开环增益 $K$ 的数值。

### 2. 根轨迹与系统性能

有了根轨迹图，可以立即分析系统的各种性能。
下面以图 4-2 为例进行说明。

(1) 稳定性
当开环增益从零变到无穷时，图 4-2 上的根轨迹不会越过虚轴进入右半 $s$ 平面，因此图 4-1 系统对所有的 $K$ 值都是稳定的，这与我们在第 3-5 节所得到的结论完全相同。如果分析高阶系统的根轨迹，那么根轨迹有可能越过虚轴进入 $s$ 右半平面，此时根轨迹与虚轴交点处的 $K$ 值，就是临界开环增益。

(2) 稳态性能
由图 4-2 可见，开环系统在坐标原点有一个极点，所以系统属 I 型系统，因而根轨迹上的 $K$ 值就是静态速度误差系数。如果给定系统的稳态误差要求，则由根轨迹图可以确定闭环极点位置的容许范围。在一般情况下，根轨迹图上标注出来的参数不是开环增益，而是所谓根轨迹增益。下面将指出，开环增益和根轨迹增益之间，仅相差一个比例常数，很容易进行换算。对于其他参数变化的根轨迹图，情况是类似的。

(3) 动态性能
由图 4-2 可见，当 $0 < K < 0.5$ 时，所有闭环极点位于实轴上，系统为过阻尼系统，单位阶跃响应应为非周期过程；当 $K = 0.5$ 时，闭环两个实数极点重合，系统为临界阻尼系统，单位阶跃响应仍为非周期过程，但响应速度较 $0 < K < 0.5$ 情况为快；当 $K > 0.5$ 时，闭环极点为复数极点，系统为欠阻尼系统，单位阶跃响应为阻尼振荡过程，且超调量将随 $K$ 值的增大而加大，但调节时间的变化不会显著。

上述分析表明，根轨迹与系统性能之间有着比较密切的联系。然而，对于高阶系统，用解析的方法绘制系统的根轨迹，显然是不适用的。我们希望有简便的图解方法，可以根据已知的开环传递函数迅速绘出闭环系统的根轨迹。为此，需要研究闭环零、极点与开环零、极点之间的关系。

### 3. 闭环零、极点与开环零、极点之间的关系

由于开环零、极点是已知的，建立开环零、极点与闭环零、极点之间的关系，有助于闭环系统根轨迹的绘制，并由此导出根轨迹方程。

[Diagram: A plot on the complex $s$-plane. The horizontal axis is the real axis ($\sigma$), and the vertical axis is the imaginary axis ($j\omega$). Two poles are marked with 'x' at $s = -1 \pm j\sqrt{2K-1}$ for $K > 0.5$, and at $s = -1 \pm \sqrt{1-2K}$ for $K < 0.5$. The trajectory is a vertical line at $\sigma = -1$. Arrows indicate the direction of increasing $K$.]

图 4-2 $\frac{C(s)}{R(s)} = \frac{2K}{s^2 + 2s + 2K}$ 的根轨迹图

· 151 ·