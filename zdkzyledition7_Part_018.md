## Page 1

$$G(s) = \frac{\Delta H(s)}{\Delta U(s)} = \frac{K}{Ts+1}e^{-\tau s} \quad (2-61)$$

该式与单容水槽传递函数[式(2-57)]相比，多了一个延迟因子 $e^{-\tau s}$。

**双容水槽** 图 2-20 是两个串联单容水槽构成的双容水槽。其输入量为调节阀 1 产生的阀门开度变化 $\Delta u$，而输出量为第二个水槽的液位增量 $\Delta h_2$。

[Diagram Description: Figure 2-20 shows a schematic of a two-tank system. A flow $Q_i + \Delta Q_i$ enters the first tank (level $h_1 + \Delta h_1$), which then flows out as $Q_{10} + \Delta Q_1$ into the second tank (level $h_2 + \Delta h_2$), and finally exits as $Q_{20} + \Delta Q_2$.]

图 2-20 双容水槽原理图

在水流量增量、水槽液位增量及液阻之间，经平衡点线性化后，可以导出如下关系式：

$$\Delta Q_i - \Delta Q_1 = C_2 \frac{d\Delta h_2}{dt} \quad (2-62)$$
$$\Delta Q_1 = \frac{\Delta h_1}{R_1}, \quad \Delta Q_2 = \frac{\Delta h_2}{R_2} \quad (2-63)$$
$$\Delta Q_1 - \Delta Q_2 = C_1 \frac{d\Delta h_1}{dt} \quad (2-64)$$
$$\Delta Q_i = K_u \Delta u \quad (2-65)$$

式中，$C_1$ 和 $C_2$ 为两液槽的容量系数；$R_1$ 和 $R_2$ 为两液槽的液阻。将式(2-63)代入(2-62)，得

$$\frac{\Delta h_1}{R_1} - \frac{\Delta h_2}{R_2} = C_2 \frac{d\Delta h_2}{dt}$$

故有

$$\Delta h_1 = R_1 \left( C_2 \frac{d\Delta h_2}{dt} + \frac{\Delta h_2}{R_2} \right) \quad (2-66)$$
$$\frac{d\Delta h_1}{dt} = R_1 C_2 \frac{d^2\Delta h_2}{dt^2} + \frac{R_1}{R_2} \frac{d\Delta h_2}{dt} \quad (2-67)$$

将式(2-65)及式(2-63)代入(2-64)，得

$$C_1 \frac{d\Delta h_1}{dt} + \frac{\Delta h_1}{R_1} = K_u \Delta u$$

分别将式(2-66)和式(2-67)代入上式，整理后可得双容水槽的微分方程

---

## Page 2

$$T_1 T_2 \frac{d^2\Delta h_2}{dt^2} + (T_1 + T_2) \frac{d\Delta h_2}{dt} + \Delta h_2 = K \Delta u \quad (2-68)$$

式中，$T_1 = R_1 C_1$ 为第一个水槽的时间常数；$T_2 = R_2 C_2$ 为第二个水槽的时间常数；$K$ 为双容水槽的传递系数。

在零初始条件下，对式(2-68)进行拉氏变换，得双容水槽的传递函数

$$G(s) = \frac{\Delta H_2(s)}{\Delta U(s)} = \frac{K}{T_1 T_2 s^2 + (T_1 + T_2)s + 1} \quad (2-69)$$

若双容水槽调节阀 1 开度变化所引起的流入水量变化还存在纯延迟，则其传递函数不难导出为

$$G(s) = \frac{K}{T_1 T_2 s^2 + (T_1 + T_2)s + 1} e^{-\tau s} \quad (2-70)$$

### 2-3 控制系统的结构图与信号流图

控制系统的结构图和信号流图都是描述系统各元部件之间信号传递关系的数学图形，它们表示了系统中各变量之间的因果关系以及对各变量所进行的运算，是控制理论中描述复杂系统的一种简便方法。与结构图相比，信号流图符号简单，更便于绘制和应用，特别在系统的计算机仿真研究以及状态空间分析设计中，信号流图可以直接给出计算机模拟真程序和系统的状态方程描述，更显示出其优越性。但是，信号流图只适用于线性系统，而结构图也可用于非线性系统。

#### 1. 系统结构图的组成和绘制

控制系统的结构图是由许多对信号进行单向运算的方框和一些信号流向线组成，它包含如下四种基本单元：

**信号线** 信号线是带有箭头的直线，箭头表示信号的流向，在直线旁标记信号的时间函数或象函数，如图 2-21(a)所示。

**引出点(或测量点)** 引出点表示信号引出或测量的位置，从同一位置引出的信号在数值和性质方面完全相同，如图 2-21(b)所示。

**比较点(或综合点)** 比较点表示对两个以上的信号进行加减运算，“+”号表示相加，“-”号表示相减，“+”号可省略不写，如图 2-21(c)所示。

**方框(或环节)** 方框表示对信号进行的数学变换，方框中写入元部件或系统的传递函数，如图 2-21(d)所示。显然，方框的输出变量等于方框的输入变量与传递函数的乘积。

[Diagram Description: Figure 2-21 shows the basic components of a block diagram: (a) Signal line with arrow, (b) Take-off point, (c) Summing point with inputs and output, (d) Block representing a transfer function G(s) with input U(s) and output C(s).]

图 2-21 结构图的基本组成单元

---

## Page 3

积，即

$$C(s) = G(s)U(s)$$

因此，方框可视为单向运算的算子。

绘制系统结构图时，首先考虑负载效应分别列写系统各元部件的微分方程或传递函数，并将它们用方框表示；然后，根据各元部件的信号流向，用信号线依次将各方框连接便得到系统的结构图。因此，系统结构图实质上是系统原理图与数学方程两者的结合，既补充了原理图所缺少的定量描述，又避免了纯数学的抽象运算。从结构图上可以用方框进行数学运算，也可以直观了解各元部件的相互关系及其在系统中所起的作用；更重要的是，从系统结构图可以方便地求得系统的传递函数。所以，系统结构图也是控制系统的一种数学模型。

要指出的是，虽然系统结构图是从系统元部件的数学模型得到的，但结构图中的方框与实际的元部件并非是一一对应的。一个实际元部件可以用一个方框或几个方框表示；而一个方框也可以代表几个元部件或是一个子系统，或是一个大的复杂系统。

下面举例说明系统结构图的绘制方法。

**例 2-10** 图 2-22 是一个电压测量装置，也是一个反馈控制系统。$e_1$ 是待测量电压，$e_2$ 是指示的电压测量值。如果 $e_2$ 不同于 $e_1$，就产生误差电压 $e = e_1 - e_2$，经调制、放大以后，驱动两相伺服电动机运转，并带动测量指针移动，直至 $e_2 = e_1$。这时指针指示的电压值即是待测量的电压值。试绘制该系统的结构图。

[Diagram Description: Figure 2-22 shows a schematic of a voltage measurement device. It includes a comparison circuit, a modulator, an amplifier, a two-phase servo motor (SM), and a mechanical linkage to a ruler/pointer.]

图 2-22 电压测量装置原理图

**解** 系统由比较电路、机械调制器、放大器、两相伺服电动机及指针机构组成。首先，考虑负载效应分别列写各元部件的运动方程，并在零初始条件下进行拉氏变换，于是有

比较电路：$E(s) = E_1(s) - E_2(s)$
调制器：$U_-(s) = E(s)$
放大器：$U_a(s) = K_a E(s)$
两相伺服电动机：$M_m = -C_\omega \Theta_m(s) + M_s, \quad M_s = C_u U_a(s)$
$M_m = J_m s^2 \Theta_m(s) + f_m s \Theta_m(s)$

式中，$M_m$ 是电动机转矩；$M_s$ 是电动机堵转转矩；$U_a(s)$ 是控制电压；$\Theta_m(s)$ 是电动机角位移；$J_m$ 和 $f_m$ 分别是折算到电动机上的总转动惯量及总黏性摩擦系数。