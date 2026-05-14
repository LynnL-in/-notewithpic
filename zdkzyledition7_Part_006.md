==Start of PDF==

[Page 1]

**图 1-7 电机速度复合控制系统**
*(Diagram description: A block diagram showing a control system. An input $u_0$ enters a summing junction, where a feedback signal $u_f$ is subtracted to produce an error signal $u_e$. This signal goes into a "Voltage Amplifier" and a "Power Amplifier". The output of the power amplifier goes to a "Motor". The motor output $n$ is connected to a "Tachogenerator", which feeds back to the summing junction as $u_f$. The "Voltage Amplifier" also has a feedback loop through "Resistor R".)*

### 1-2 自动控制系统示例

#### 1. 函数记录仪

函数记录仪是一种通用的自动记录仪，它可以在直角坐标上自动描绘两个电量的函数关系。同时，记录仪还带有走纸机构，用以描绘一个电量对时间的函数关系。

函数记录仪通常由衰减器、测量元件、放大元件、伺服电动机-测速发电机组、齿轮系及绳轮等组成，采用负反馈控制原理工作，其原理如图 1-8 所示。系统的输入是待记录电压，被控对象是记录笔，其位移即为被控量。系统的任务是控制记录笔位移，在记录纸上描绘出待记录的电压曲线。

**图 1-8 函数记录仪原理示意图**
*(Diagram description: A schematic showing a bridge circuit with resistors $R_Q$ and $R_M$. A pen is attached to the slider of potentiometer $R_M$. An input voltage $u_r$ is compared with the feedback voltage $u_p$ from the bridge to produce an error voltage $\Delta u$. This signal passes through an amplifier to drive a servo motor/tachogenerator unit, which uses a gear train and pulley system to move the pen and the potentiometer slider.)*

在图 1-8 中，测量元件是由电位器 $R_Q$ 和 $R_M$ 组成的桥式测量电路，记录笔就固定在电位器 $R_M$ 的滑臂上，因此，测量电路的输出电压 $u_p$ 与记录笔位移成正比。当有慢变的输入电压 $u_r$ 时，在放大元件入口得到偏差电压 $\Delta u = u_r - u_p$，经放大后驱动伺服电动机，并通过齿轮系及绳轮带动记录笔移动，同时偏差电压减小。当偏差电压 $\Delta u = 0$ 时，电动机停止转动，记录笔也静止不动。此时，$u_p = u_r$，表明记录笔位移与输入电压相对应。如

· 8 ·

---

[Page 2]

果输入电压随时间连续变化，记录笔便描绘出随时间连续变化的相应曲线。函数记录仪方块图如图 1-9 所示，图中测速发电机反馈与电动机速度成正比的电压，用以增加阻尼，改善系统性能。

**图 1-9 函数记录仪方块图**
*(Diagram description: A block diagram showing the input $u_r$ and feedback $u_p$ entering a summing junction to produce $\Delta u$. This goes to an "Amplifier/Converter", then to a "Servo Motor", which drives a "Gear Train/Pulley" to move the "Recording Pen". A "Tachogenerator" is connected to the motor and feeds back to the amplifier. A "Measuring Circuit" block provides the $u_p$ feedback.)*

#### 2. 飞机-自动驾驶仪系统

飞机自动驾驶仪是一种能保持或改变飞机飞行状态的自动装置。它可以稳定飞行的姿态、高度和航迹；可以操纵飞机爬高、下滑和转弯。飞机与自动驾驶仪组成的自动控制系统称为飞机-自动驾驶仪系统。

如同飞行员操纵飞机一样，自动驾驶仪控制飞机飞行是通过控制飞机的三个操纵面（升降舵、方向舵、副翼）的偏转，改变舵面的气动力特性，以形成围绕飞机质心的旋转转矩，从而改变飞机的飞行姿态和轨迹。现以比例式自动驾驶仪稳定飞机俯仰角为例，说明其工作原理。图 1-10 为飞机-自动驾驶仪系统稳定俯仰角的原理示意图。图中，垂直陀螺仪为测量元件用以测量飞机的俯仰角，当飞机以给定俯仰角水平飞行时，陀螺仪电位器没有电压输出。

如果飞机受到扰动，使俯仰角向下偏离期望值，陀螺仪电位器输出与俯仰角偏差成正比的信号，经放大器放大后驱动舵机，一方面推动升降舵向上偏转，产生使飞机抬头的转矩，以减小俯仰角偏差；同时还带动反馈电位器滑臂，输出与舵角成正比的电压并反馈到输入端。随着俯仰角偏差的减小，陀螺仪电位器输出信号越来越小，舵角也随之减小，直到俯仰角回到期望值，这时，舵面也恢复到原来状态。

**图 1-10 飞机-自动驾驶仪系统原理图**
*(Diagram description: A schematic showing a vertical gyroscope, an amplifier, a servo motor (舵机), and the aircraft's elevator. A feedback potentiometer is linked to the servo motor.)*

图 1-11 是飞机-自动驾驶仪系统稳定俯仰角的系统方块图。图中，飞机是被控对象，俯仰角是被控量，放大器、舵机、垂直陀螺仪、反馈电位器等是控制装置，即自动驾驶仪。输入量是给定的常值俯仰角，控制系统的任务就是在任何扰动（如阵风或气流冲击）作用下，始终保持飞机以给定俯仰角飞行。

#### 3. 电阻炉温度微型计算机控制系统

用于工业生产中炉温控制的微型计算机控制系统，具有精度高、功能强、经济性

· 9 ·

---

[Page 3]

好、无噪声、显示醒目、读数直观、打印存档方便、操作简单、灵活性和适应性好等一系列优点。用微型计算机控制系统代替模拟控制系统是今后工业过程控制的发展方向。图 1-12 为某工厂电阻炉温度微型计算机控制系统原理示意图。图中，电阻丝通过晶闸管主电路加热，炉温期望值用计算机键盘预先设置，炉温实际值由热电偶检测，并转换成电压，经放大、滤波后，由 A/D 变换器将模拟量变换为数字量送入计算机，在计算机中与所设置的温度期望值比较后产生偏差信号，计算机便根据预定的控制算法（即控制规律）计算出相应的控制量，再经 D/A 变换器变换成电流，通过触发器控制晶闸管导通，从而改变电阻丝中电流大小，达到控制炉温的目的。该系统既有精确的温度控制功能，还有实时屏幕显示和打印功能，以及超温、极值和电阻丝、热电偶损坏报警等功能。

**图 1-11 飞机俯仰角控制系统方块图**
*(Diagram description: A block diagram showing a "Setting Device" ($\theta_0$) as input, a summing junction, an "Amplifier", "Servo Motor" (舵机), and "Aircraft" (飞机). The output is $\theta$. A "Vertical Gyroscope" and "Feedback Potentiometer" form a feedback loop. A "Disturbance" (扰动) input affects the aircraft.)*

**图 1-12 电阻炉温度微型计算机控制系统方块图**
*(Diagram description: A block diagram showing a "Thermocouple" (热电偶) and "Electric Furnace" (电炉). The thermocouple signal goes through "Amplifier/Filter" to an "A/D Converter", then to a "Single-board Computer" (单板计算机). The computer output goes to a "D/A Converter", then to a "Trigger" (触发器), which controls the "Thyristor" (晶闸管) circuit connected to the "Resistance Wire" (电阻丝) in the furnace.)*

#### 4. 锅炉液位控制系统

锅炉是电厂和化工工厂常见的生产蒸汽的设备。为了保证锅炉正常运行，需要维持锅炉液位为正常标准值。锅炉液位过低，易烧干锅而发生严重事故；锅炉液位过高，则易使蒸汽带水并有溢出危险。因此，必须通过调节器严格控制锅炉液位的高低，以保证锅炉正常安全运行。常见的锅炉液位控制系统示意图如图 1-13 所示。

当蒸汽的耗气量与锅炉进水量相等时，液位保持为正常标准值。当锅炉的给水量不变，而蒸汽负荷突然增加或减少时，液位就会下降或上升；或者，当蒸汽负荷不变，而

· 10 ·

==End of PDF==