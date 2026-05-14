(Page 143)

[Diagram 3-62: Control System Block Diagrams]
(a) Tachometer Feedback Control: A block diagram showing $R(s)$ entering a summing junction, followed by a block $K_1$, then a summing junction leading to a block $\frac{K_2}{s(Ts+1)}$ which outputs $C(s)$. A feedback loop from $C(s)$ goes through a block $K_3s$ back to the first summing junction.
(b) Proportional-Derivative Control: A block diagram showing $R(s)$ entering a summing junction, followed by a block $K_1$, then a summing junction leading to a block $\frac{K_2}{s(Ts+1)}$ which outputs $C(s)$. A feedback loop from $C(s)$ goes through a block $K_3s$ back to the second summing junction (before the $K_2$ block).

**3-11** The characteristic equation of a system is:
$$3s^4 + 10s^3 + 5s^2 + s + 2 = 0$$
Use the Routh-Hurwitz stability criterion to determine the stability of the system.

**3-12** Determine the number of roots in the right half of the $s$-plane and on the imaginary axis for systems with the following characteristic equations:
(1) $s^5 + 3s^4 + 12s^3 + 24s^2 + 32s + 48 = 0$;
(2) $s^6 + 4s^5 - 4s^4 + 4s^3 - 7s^2 - 8s + 10 = 0$;
(3) $s^5 + 3s^4 + 12s^3 + 20s^2 + 35s + 25 = 0$.

**3-13** For a unity feedback system with the open-loop transfer function:
$$G(s) = \frac{K(0.5s + 1)}{s(s + 1)(0.05s^2 + s + 1)}$$
Determine the range of $K$ for which the system is stable.

**3-14** For the control system shown in Figure 3-63, use the Routh-Hurwitz stability criterion to determine the range of the feedback parameter $\tau$ for which the system is stable.

[Diagram 3-63: Control System Block Diagram]
A block diagram showing $R(s)$ entering a summing junction, followed by a block $(1 + \frac{1}{s})$, then a summing junction leading to a block $\frac{10}{s(s+1)}$ which outputs $C(s)$. A feedback loop from $C(s)$ goes through a block $\tau s$ back to the second summing junction.

**3-15** For unity feedback systems with the following open-loop transfer functions:
(1) $G(s) = \frac{100}{(0.1s + 1)(s + 5)}$;
(2) $G(s) = \frac{50}{s(0.1s + 1)(s + 5)}$;
(3) $G(s) = \frac{10(2s + 1)}{s^2(s^2 + 6s + 100)}$.
Determine the steady-state error when the input is $r(t) = 2t$ and $r(t) = 2 + 2t + t^2$, respectively.

**3-16** For unity feedback systems with the following open-loop transfer functions:
(1) $G(s) = \frac{50}{(0.1s + 1)(2s + 1)}$;
(2) $G(s) = \frac{K}{s(s^2 + 4s + 200)}$;
(3) $G(s) = \frac{10(2s + 1)(4s + 1)}{s^2(s^2 + 2s + 10)}$.
Determine the position error constant $K_p$, velocity error constant $K_v$, and acceleration error constant $K_a$.

**3-17** For a unity feedback system with open-loop transfer function $G(s) = 1/(Ts)$. Use the dynamic error method to find the steady-state error when the input signal is $r(t) = t^2/2$ and $r(t) = \sin 2t$.

---
(Page 144)

**3-18** For the control system shown in Figure 3-64, where $G(s) = K_p + \frac{K}{s}$ and $F(s) = \frac{1}{Js}$.
Given that $r(t)$ and disturbances $n_1(t)$ and $n_2(t)$ are unit step functions. Determine:
(1) The steady-state error under the action of $r(t)$;
(2) The steady-state error under the action of $n_1(t)$;
(3) The steady-state error under the action of $n_1(t)$ and $n_2(t)$ simultaneously.

[Diagram 3-64: Control System Block Diagram]
A block diagram showing $R(s)$ entering a summing junction, followed by $G(s)$, then a summing junction with input $N_1(s)$, followed by $F(s)$, then a summing junction with input $N_2(s)$, outputting $C(s)$. The feedback loop from $C(s)$ returns to the first summing junction.

**3-19** The general form of a closed-loop transfer function is:
$$\Phi(s) = \frac{G(s)}{1 + G(s)H(s)} = \frac{b_m s^m + b_{m-1} s^{m-1} + \dots + b_1 s + b_0}{s^n + a_{n-1} s^{n-1} + \dots + a_1 s + a_0}$$
Define error $e(t) = r(t) - c(t)$. Prove:
(1) For a step input, the sufficient condition for zero steady-state error is: $b_0 = a_0$, $b_i = 0 (i = 1, 2, \dots, m)$;
(2) For a ramp input, the sufficient condition for zero steady-state error is: $b_0 = a_0$, $b_1 = a_1$, $b_i = 0 (i = 2, 3, \dots, m)$.

**3-20** The differential equations for a servo system are:
$$T_1 \frac{d^2c(t)}{dt^2} + \frac{dc(t)}{dt} = K_2 u(t), \quad u(t) = K_1 [r(t) - b(t)]$$
$$T_2 \frac{db(t)}{dt} + b(t) = c(t)$$
where $T_1, T_2, K_2$ are positive constants. If $r(t) = 1 + t$, and the steady-state error for $r(t)$ is not greater than a positive constant $\alpha$, what conditions must $K_1$ satisfy? Assume all initial conditions are zero.

**3-21** Robot applications use feedback control for each joint. Changes in load and robot arm extension cause different effects on the robot. For example, a mechanical gripper carrying a load can cause the robot to deviate. Given the robot joint orientation control system shown in Figure 3-65, where the load disturbance $N(s) = 1/s$. Requirements:

[Diagram 3-65: Robot Joint Orientation Control System Block Diagram]
A block diagram showing $R(s)$ (expected joint angle) entering a summing junction, followed by a controller $K_1$, then a summing junction with input $N(s)$ (load disturbance), followed by a block $\frac{K_2}{s(Ts+1)}$, outputting $C(s)$ (actual joint angle). A feedback loop from $C(s)$ goes through a block $K_3 + K_4s$ back to the first summing junction.

(1) When $R(s) = 0$, determine the effect of $N(s)$ on $C(s)$ and point out methods to reduce this effect;
(2) When $N(s) = 0, R(s) = \frac{1}{s}$, calculate the steady-state error of the system output, and point out methods to reduce this steady-state error.

---
(Page 145)

**3-22** In the paper roll process of a paper mill, the tension between the unwinding roll and the winding roll is controlled by the tension control system shown in Figure 3-66 to keep the tension $F$ constant. As the paper thickness changes, the tension $F$ on the paper will change, so the motor speed $\omega(t)$ must be adjusted. If the motor speed $\omega(t)$ is not controlled, the line speed $v_0(t)$ will drop as the paper is continuously transferred from the unwinding roll to the winding roll, thereby reducing the tension $F$ of the paper.

[Diagram 3-66: Paper Roll Tension Control System Principle]
A diagram showing an unwinding roll connected to a motor, a winding roll connected to a motor, and a tension sensor (spring-loaded roller) in between. The sensor output goes to a linear deviation converter, then a rectifier/amplifier, which controls the motor.

In the tension control system, three rollers and a spring-loaded tension meter are used to measure the tension of the paper. Let the spring constant be $K_y$, where $y$ is the distance from the spring equilibrium position, then the tension can be expressed as $2F = K_y y$, where $F$ is the vertical component of the tension increment. In addition, assuming the linear deviation converter, rectifier, and amplifier are combined, it can be expressed as $e_0 = -K_2 y$; the motor transfer function is $K_m$, time constant $T_m = L_a/R_a$, and the motor speed is twice the angular velocity, i.e., $v_0(t) = 2\omega(t)$. Thus, the motor's equation of motion is:
$$E_0(s) = \frac{1}{K_m} [T_m s \Omega(s) + \Omega(s)] + K_3 \Delta F(s)$$
where $K_3$ is the tension disturbance coefficient; $\Delta F$ is the tension increment. Complete the following:
(1) Draw the tension control system block diagram, including the tension disturbance $\Delta F(s)$ and the winding roll speed disturbance $\Delta V_1(s)$;
(2) When the input is a unit step disturbance $\Delta V_1(s) = 1/s$, determine the steady-state error of the tension.

**3-23** Modern ship navigation control systems are shown in Figure 3-67. $N(s)$ represents continuous wind disturbance, given $N(s) = 1/s$. In the figure, the gain $K_1 = 5$ or $K_1 = 30$. Under the following conditions, determine the steady-state effect of the wind on the ship's navigation:

[Diagram 3-67: Ship Navigation Control System Block Diagram]
A block diagram showing $R(s)$ (rudder input) entering a summing junction, followed by $K_1$, then a summing junction with input $N(s)$, followed by $\frac{100}{s^2 + 10s + 100}$, outputting $C(s)$ (ship's deviation from preset course). A unity feedback loop returns from $C(s)$ to the first summing junction.

(1) Assuming the rudder input $R(s) = 0$, the system has no other disturbances or adjustments;
(2) Prove that the rudder can steer the ship back to the course after a deviation.

**3-24** A common robot gripper is shown in Figure 3-68(a), which is driven by a DC motor to change the angle between the two gripper fingers. The gripper control system is shown in Figure 3-68(b), and the corresponding block diagram is shown in Figure 3-68(c). In the figure, $K_m = 30, R_f = 1\Omega, K_f = K_i = 1, J = 0.1, f = 1$. Requirements: