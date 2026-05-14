==Start of PDF==

### Page 1

[Diagram: A schematic diagram of a boiler water level control system. It shows a boiler drum connected to a steam pipe at the top and a water pipe at the bottom. An economizer is connected to the water pipe. A transmitter is connected to the boiler drum, which sends a signal to a controller. The controller is connected to a gas source and a control valve on the water pipe.]

**图 1-13 锅炉液位控制系统示意图**

给水管道水压发生变化时，引起锅炉液位发生变化。不论出现哪种情况，只要实际液位高度与正常给定液位之间出现了偏差，调节器均应立即进行控制，去开大或关小给水阀门，使液位恢复到给定值。

图 1-14 是锅炉液位控制系统方块图。图中，锅炉为被控对象，其输出为被控参数液位，作用于锅炉上的扰动是指给水压力变化或蒸汽负荷变化等产生的内外扰动；测量变送器为差压变送器，用来测量锅炉液位，并转变为一定的信号输至调节器；调节器是锅炉液位控制系统中的控制器，有电动、气动等形式，在调节器内将测量液位与给定液位进行比较，得出偏差值，然后根据偏差情况按一定的控制律(如比例(P)、比例-积分(PI)、比例-积分-微分(PID)等)发出相应的输出信号去推动调节阀动作；调节阀在控制系统中起执行元件作用，根据控制信号对锅炉的进水量进行调节，阀门的运动取决于阀门的特性，有的阀门与输入信号成正比变化，有的阀门与输入信号呈某种曲线关系变化。大多数调节阀为气动薄膜调节阀，若采用电动调节器，则调节器与气动调节阀之间应有电气转换器。气动调节阀的气动阀门分为气开与气关两种。气开指当调节器输出增加时，阀门开大；气关指当调节器输出增加时，阀门反而关小。为了安全生产，蒸汽锅炉的给水调节阀一般采用气关阀，一旦发生断气现象，阀门保持打开位置，以保证汽鼓不被烧干损坏。

[Diagram: A block diagram of the boiler water level control system. It shows a "给定值" (Set point) entering a summation point (+/-), which then goes to a "调节器" (Controller). The output of the controller goes to a "调节阀" (Control valve), then to "水" (Water), then to "锅炉" (Boiler). The output of the boiler is the "被控参数" (Controlled parameter). A feedback loop goes from the output back to a "测量变送器" (Measurement transmitter), which then feeds back to the summation point. An "扰动" (Disturbance) input enters the "锅炉" block.]

**图 1-14 锅炉液位控制系统方块图**

· 11 ·

---

### Page 2

**5. 转速控制系统**

发动机转速控制系统的原理如图 1-15 所示，图中展示了发动机瓦特式速度调节器的基本原理。允许进入发动机内的燃料数量，可由希望的发动机转速与实际的发动机转速之差进行调整。

[Diagram: A schematic diagram of an engine speed control system. It shows a centrifugal governor connected to a fuel control valve. The governor is driven by the engine. The fuel control valve regulates fuel flow to the engine, which drives a load.]

**图 1-15 转速控制系统原理图**

该系统的工作过程陈述如下：转速调节器的调节原理是当发动机工作于希望的转速时，高压油将不进入动力油缸的任何一侧。如果由于扰动，使得实际转速下降到低于希望值，则转速调节器的离心力下降，导致控制阀向下移动，从而对发动机的燃料供应增多，使发动机的转速增大，直致希望的转速时为止。另一方面，如果发动机的转速增大，以至于超过了希望的转速，则转速调节器的离心力增大，从而导致控制阀向上移动。这样会减少燃料供应，导致发动机的转速减慢，直至希望的转速时为止。

在这个转速控制系统中，被控对象是发动机，而被控变量是发动机的转速。希望转速与实际转速之间的差形成误差信号，作用对象(发动机)的控制信号(燃料的数量)为驱动信号，对被控变量起干扰作用的外部输入量称为扰动量。不能预测的负载变化就是一种扰动量。

**6. 磁盘驱动读取系统**

磁盘驱动器广泛用于各类计算机中，是控制工程的一个重要应用实例。考察图 1-16 所示的磁盘驱动器结构示意图可知，磁盘驱动器读取装置的目标是将磁头准确定位，以便正确读取磁盘上磁道的信息，因此需要进行精确控制的变量是安装在滑动簧片上的磁头位置。磁盘旋转速度为 1800~7200r/min，磁头位置精度要求为 1μm，且磁头由磁道 a 移动到磁道 b 的时间小于 50ms。

· 12 ·

---

### Page 3

[Diagram: A schematic diagram of a disk drive structure. It shows a disk, a magnetic head on a slider, a support arm, and an actuator motor.]

**图 1-16 磁盘驱动器结构示意图**

图 1-17 给出了该系统的初步方案，其闭环系统利用电机驱动磁头到达预期的位置。

[Diagram: A block diagram of the disk drive control system. It shows "预期磁头位置" (Expected head position) entering a summation point, then to a "控制装置" (Control device), then to "执行电机和臂" (Actuator motor and arm), resulting in "实际磁头位置" (Actual head position). A feedback loop goes from the output through a "传感器" (Sensor) back to the summation point.]

**图 1-17 磁盘驱动读取系统初步方案**

**1-3 自动控制系统的分类**

自动控制系统有多种分类方法。例如，按控制方式可分为开环控制、反馈控制、复合控制等；按元件类型可分为机械系统、电气系统、机电系统、液压系统、气动系统、生物系统等；按系统功用可分为温度控制系统、压力控制系统、位置控制系统等；按系统性能可分为线性系统和非线性系统、连续系统和离散系统、定常系统和时变系统、确定性系统和不确定性系统等；按输入量变化规律又可分为恒值控制系统、随动系统和程序控制系统等。为了全面反映自动控制系统的特点，常常将上述各种分类方法组合应用。

**1. 线性连续控制系统**

这类系统可以用线性微分方程描述，其一般形式为

$$a_n \frac{d^n}{dt^n}c(t) + a_{n-1} \frac{d^{n-1}}{dt^{n-1}}c(t) + \dots + a_1 \frac{d}{dt}c(t) + a_0 c(t)$$
$$= b_m \frac{d^m}{dt^m}r(t) + b_{m-1} \frac{d^{m-1}}{dt^{m-1}}r(t) + \dots + b_1 \frac{d}{dt}r(t) + b_0 r(t)$$

式中，$c(t)$是被控量；$r(t)$是系统输入量。系数 $a_0, a_1, \dots, a_n, b_0, b_1, \dots, b_m$ 是常数时，称为定常系统；系数 $a_0, a_1, \dots, a_n, b_0, b_1, \dots, b_m$ 随时间变化时，称为时变系统。线性定常连续系统按其输入量的变化规律又可分为恒值控制系统、随动系统和程序控制

· 13 ·

==End of PDF==