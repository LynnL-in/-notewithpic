续表

| 原方框图 | 等效方框图 | 等效运算关系 |
| :--- | :--- | :--- |
| ![Diagram 1](https://i.imgur.com/y1y1y1.png) | ![Diagram 2](https://i.imgur.com/y2y2y2.png) | (3) 反馈等效<br>$C(s) = \frac{G_1(s)R(s)}{1 \mp G_1(s)G_2(s)}$ |
| ![Diagram 3](https://i.imgur.com/y3y3y3.png) | ![Diagram 4](https://i.imgur.com/y4y4y4.png) | (4) 等效单位反馈<br>$\frac{C(s)}{R(s)} = \frac{1}{G_2(s)} \frac{G_1(s)G_2(s)}{1 + G_1(s)G_2(s)}$ |
| ![Diagram 5](https://i.imgur.com/y5y5y5.png) | ![Diagram 6](https://i.imgur.com/y6y6y6.png) | (5) 比较点前移<br>$C(s) = R(s)G(s) \pm Q(s)$<br>$= \left[ R(s) \pm \frac{Q(s)}{G(s)} \right] G(s)$ |
| ![Diagram 7](https://i.imgur.com/y7y7y7.png) | ![Diagram 8](https://i.imgur.com/y8y8y8.png) | (6) 比较点后移<br>$C(s) = [R(s) \pm Q(s)]G(s)$<br>$= R(s)G(s) \pm Q(s)G(s)$ |
| ![Diagram 9](https://i.imgur.com/y9y9y9.png) | ![Diagram 10](https://i.imgur.com/y10y10.png) | (7) 引出点前移<br>$C(s) = R(s)G(s)$ |
| ![Diagram 11](https://i.imgur.com/y11y11.png) | ![Diagram 12](https://i.imgur.com/y12y12.png) | (8) 引出点后移<br>$R(s) = R(s)G(s) \frac{1}{G(s)}$<br>$C(s) = R(s)G(s)$ |
| ![Diagram 13](https://i.imgur.com/y13y13.png) | ![Diagram 14](https://i.imgur.com/y14y14.png) | (9) 交换或合并比较点<br>$C(s) = E_1(s) \pm R_1(s)$<br>$= R_1(s) \pm R_2(s) \pm R_3(s)$<br>$= R_1(s) \pm R_2(s) \pm R_3(s)$ |
| ![Diagram 15](https://i.imgur.com/y15y15.png) | ![Diagram 16](https://i.imgur.com/y16y16.png) | (10) 交换比较点或引出点<br>(一般不采用)<br>$C(s) = R_1(s) - R_2(s)$ |
| ![Diagram 17](https://i.imgur.com/y17y17.png) | ![Diagram 18](https://i.imgur.com/y18y18.png) | (11) 负号在支路上移动<br>$E(s) = R(s) - H(s)C(s)$<br>$= R(s) + H(s) \times (-1)C(s)$ |

• 50 •

---

例 2-11 试简化图 2-27 系统结构图，并求系统传递函数 $C(s)/R(s)$。

[Diagram Description: A block diagram showing $R(s)$ entering a summing junction, then through $G_1(s)$, $G_2(s)$, $G_3(s)$, $G_4(s)$ to $C(s)$. There is a feedback loop from the output of $G_2(s)$ through $H_2(s)$ back to the summing junction before $G_2(s)$. There is another feedback loop from the output of $G_4(s)$ through $H_3(s)$ back to the input of $G_3(s)$. There is a third feedback loop from the output of $G_4(s)$ through $H_1(s)$ back to the main input summing junction.]

图 2-27 例 2-11 系统结构图

解 在图 2-27 中，若不移动比较点或引出点就无法进行方框的等效运算。为此，首先应用表 2-1 的规则(8)，将 $G_3(s)$ 与 $G_4(s)$ 两方框之间的引出点后移到 $G_4(s)$ 方框的输出端（注意，不宜前移），如图 2-28(a)所示。其次，将 $G_3(s)$，$G_4(s)$ 和 $H_3(s)$ 组成的内反馈回路简化，其等效传递函数为
$$G_{34}(s) = \frac{G_3(s)G_4(s)}{1 + G_3(s)G_4(s)H_3(s)}$$
如图 2-28(b)所示。然后，再将 $G_2(s)$，$G_{34}(s)$，$H_2(s)$ 和 $1/G_4(s)$ 组成的内反馈回路简化，其等效传递函数为

[Diagram Description: (a) shows the block diagram after moving the take-off point. (b) shows the diagram after simplifying the $G_{34}$ loop. (c) shows the diagram after simplifying the $G_{23}$ loop.]

图 2-28 例 2-11 系统结构简化

• 51 •

---

$$G_{23}(s) = \frac{G_2(s)G_3(s)G_4(s)}{1 + G_3(s)G_4(s)H_3(s) + G_2(s)G_3(s)H_2(s)}$$
如图 2-28(c)所示。最后，将 $G_1(s)$，$G_{23}(s)$ 和 $H_1(s)$ 组成的反馈回路简化便求得系统的传递函数
$$\Phi(s) = \frac{C(s)}{R(s)} = \frac{G_1(s)G_2(s)G_3(s)G_4(s)}{1 + G_3(s)G_4(s)H_3(s) + G_2(s)G_3(s)H_2(s) + G_1(s)G_2(s)G_3(s)G_4(s)H_1(s)}$$
本例还有其他变换方法，例如，可以先将 $G_4(s)$ 后的引出点前移到 $G_4(s)$ 方框的输入端，或者将比较点移动到同一点再加以合并，读者不妨一试。

在进行结构图等效变换时，变换前后应注意保持信号的等效性。例如，图 2-27 中 $H_2(s)$ 的输入信号是 $G_3(s)$ 的输出，当将该引出点后移时，$H_2(s)$ 的输入信号变为 $G_4(s)$ 的输出信号了。为保持 $H_2(s)$ 的输入信号不变，应将 $G_4(s)$ 的输出信号乘以 $1/G_4(s)$ 便可还原为 $G_3(s)$ 的输出信号，故有图 2-28(a)的系统结构图。又例如，若将 $G_2(s)$ 输入端的比较点按规则(6)后移到 $G_2(s)$ 的输出端，虽然 $G_2(s)$ 的输入信号减少了一项（来自 $H_2(s)$ 的输出信号），由于在 $G_2(s)$ 的输出信号中补入了来自 $H_2(s)G_2(s)$ 的输出信号，故保持了 $G_2(s)$ 的输出信号在变换前后的等效性，而且回路 $G_2(s)G_3(s)H_2(s)$ 的乘积保持不变。

例 2-12 试简化图 2-29 系统结构图，并求传递函数 $C(s)/R(s)$。

[Diagram Description: A block diagram showing $R(s)$ entering a summing junction, then $G_1(s)$ and $G_2(s)$ in parallel paths, then another summing junction, then $G_3(s)$, $H(s)$, $G_4(s)$, and $G_5(s)$ in a complex configuration.]

图 2-29 例 2-12 系统结构图

解 为简化图 2-29 的系统结构图，必须移动引出点或比较点。首先将 $G_4(s)$ 与 $G_3(s)$ 前的两个比较点分别移到 $G_4(s)$ 及 $G_3(s)$ 之后，并用表 2-1 中的规则(6)可得到图 2-30(a)。其次，将 $H(s)$ 后的引出点前移到 $H(s)$ 之前，并用规则(7)得到图 2-30(b)，为便于观察，可改画成图 2-30(c)。最后，将比较点合并为两个，得到图 2-30(d)；并用规则(1)~(3)求得传递函数

[Diagram Description: (a) shows the diagram after moving the $G_3$ and $G_4$ summing junctions.]

图 2-30(a) 后移 $G_3(s)$ 及 $G_4(s)$ 的比较点

• 52 •