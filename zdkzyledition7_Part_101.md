==Start of PDF==

[Page 293]

[Image: A diagram showing a spring connected to a pulley system with a rubber band, labeled "图 6-44 组合驱动装置示意图". To the right, a block diagram shows $R(s) \rightarrow G_p(s) \rightarrow G_c(s) \rightarrow G_o(s) \rightarrow C(s)$, labeled "图 6-45 组合驱动装置转速控制系统结构图".]

[Image: A more complex block diagram labeled "图 6-46 具有前置滤波器的鲁棒控制系统结构图". It shows $R(s)$ entering a summing junction, followed by $G_p(s)$, then another summing junction with $G_c(s)$, leading to a block $\frac{2}{s+1}$ (output $x_2$) and a block $\frac{5}{s+2}$ (output $x_1 = C(s)$). There is a feedback loop with $K_b$ from $x_1$ and a feedforward/feedback path with $K_a$.]

PID 控制器
$$G_c(s) = \frac{K_p s^2 + K_i s + K_d}{s}$$

$G_p(s)$ 为前置滤波器。设计要求：
(1) 当 $K_a=10, K_b=0$ 时，设计 $G_c(s)$ 和 $G_p(s)$，使系统具有最小节拍响应，即系统在单位阶跃输入作用下，$e_{ss}(\infty)=0, \sigma\% \leqslant 2\%, t_s \leqslant 1s (\Delta=2\%)$;
(2) 若 $G_o(s)$ 的两个极点发生 $\pm 50\%$ 范围摄动，在最坏情况下，被控对象变为
$$G_o(s) = \frac{10}{(s+0.5)(s+1)}$$
试用(1)中的设计结果，对系统性能进行考核，以检验系统的鲁棒性。

6-15 NASA 的宇航员可以在航天飞机中通过控制机械手将卫星回收到航天飞机的货舱中，如图 6-47(a)所示。图中显示了宇航员站在机械臂上工作。该卫星回收系统结构如图 6-47(b)所示。要求：
(1) 当 $T=0.1s$ 时，确定 $K_a$ 的取值，使系统的相角裕度 $\gamma=50^\circ$;
(2) 当 $T=0.5s$ 时，仍采用(1)中确定的 $K_a$，求此时系统的相角裕度 $\gamma_1$;
(3) 当 $T=0.5s$ 时，若要求 $\gamma=50^\circ$，试问 $K_a$ 值应如何改变？

6-16 已知汽车点火系统有一个单位负反馈子系统，其开环传递函数为 $G_c(s)G_o(s)$，其中
$$G_o(s) = \frac{10}{s(s+10)}, \quad G_c(s) = K_1 + \frac{K_2}{s}$$
若已知 $K_2/K_1=0.5$，试确定 $K_1$ 和 $K_2$ 的取值，使系统主极点的阻尼比 $\zeta=0.707$，而且单位阶跃响应的调节时间 $t_s \leqslant 2s (\Delta=5\%)$。

· 293 ·

---

[Page 294]

[Image: (a) A photograph of an astronaut in space working on a robotic arm. (b) A block diagram showing $R(s) \rightarrow K_a \rightarrow \frac{e^{-sT}}{s(s+10)} \rightarrow C(s)$. Labeled "图 6-47 卫星回收控制系统".]

6-17 在核工业中，远程机器人主要用来回收和处理废料，同时也用于核反应堆的监控，清除放射性污染和处理意外事故等。图 6-48 所示为核工厂的遥控机器人示意图，其构成的远程监控系统可以完成某些特定操作的监测任务。若系统的开环传递函数为
$$G_o(s) = \frac{K_a e^{-sT}}{(s+1)(s+3)}$$
要求：
(1) 当 $T=0.5s$ 时，确定 $K_a$ 的合适取值，使系统阶跃响应的超调量小于 30%，并计算所得系统的稳态误差；
(2) 设计校正网络
$$G_c(s) = \frac{s+2}{s+b}$$
以改进(1)中所得系统的性能，使系统的稳态误差小于 12%。

[Image: A diagram showing a robotic arm with a camera, labeled "操作器/手臂", "监视摄像机", "通信". Labeled "图 6-48 核电厂的遥控机器人示意图".]

· 294 ·

---

[Page 295]

6-18 MANUTEC 机器人具有很大的惯性和较长的手臂，其实物如图 6-49(a)所示。机械臂的动力学特性可以表示为
$$G_o(s) = \frac{250}{s(s+2)(s+40)(s+45)}$$
要求选用图 6-49(b)所示控制方案，使系统阶跃响应的超调量小于 20%，上升时间小于 0.5s，调节时间小于 1.2s($\Delta=2\%$)，静态速度误差系数 $K_v \geqslant 10$。试问：采用超前校正网络
$$G_c(s) = 1483.7 \frac{s+3.5}{s+33.75}$$
是否合适？

[Image: (a) A photograph of a MANUTEC industrial robotic arm. (b) A block diagram showing $R(s) \rightarrow G_c(s) \rightarrow \text{机械臂动力特性} (G_o(s)) \rightarrow C(s)$. Labeled "图 6-49 机器人控制".]

6-19 双手协调机器人如图 6-50 所示，两台机械手相互协作，试图将一根长杆插入另一物体。已知单个机器人关节的反馈控制系统为单位反馈控制系统，被控对象为机械臂，其传递函数为
$$G_o(s) = \frac{4}{s(s+0.5)}$$
要求设计一个串联超前-滞后校正网络，使系统在单位斜坡输入时的稳态误差不大于 0.0125，单位阶跃响应的超调量小于 25%，调节时间小于 3s($\Delta=2\%$)，并给出系统校正前后的单位阶跃响应曲线。试问：选用网络
$$G_c(s) = \frac{10(s+2)(s+0.1)}{(s+20)(s+0.01)}$$
是否合适？

6-20 图 6-51 为机器人和视觉系统的示意图，移动机器人利用摄像系统来观测环境信息。已知机器人系统为单位反馈系统，被控对象为机械臂，其传递函数
$$G_o(s) = \frac{1}{(s+1)(0.5s+1)}$$

[Image: (a) A diagram showing two robotic arms holding a rod. (b) A diagram showing a mobile robot, an object, and a computer system labeled "识别子系统", "计算机". Labeled "图 6-50 双手协调机器人示意图" and "图 6-51 机器人和视觉系统示意图".]

· 295 ·

==End of PDF==