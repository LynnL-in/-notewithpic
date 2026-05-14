在上述中，若 $|z^{-1}| < 1$，则无穷级数是收敛的，利用等比级数和公式，可得 $1(t)$ 的 $z$ 变换的闭合形式为
$$E(z) = \frac{1}{1-z^{-1}} = \frac{z}{z-1}$$
因为 $|z^{-1}| = |e^{-sT}| = e^{-\sigma T}$，式中 $\sigma = \text{Re}s$，所以条件 $|z^{-1}| < 1$ 意味着条件 $\sigma > 0$。这也是单位阶跃函数进行拉氏变换的条件。本例结果与例 7-3 一致。

**例 7-6** 设
$$e(t) = \delta_T(t) = \sum_{n=0}^{\infty} \delta(t-nT)$$
试求理想脉冲序列 $\delta_T(t)$ 的 $z$ 变换。
**解** 因为 $T$ 为采样周期，故
$$e^*(t) = \delta_T(t) = \sum_{n=0}^{\infty} \delta(t-nT)$$
由拉氏变换知
$$E^*(s) = \sum_{n=0}^{\infty} e^{-nsT}$$
因此
$$E(z) = \sum_{n=0}^{\infty} z^{-n} = 1 + z^{-1} + z^{-2} + \cdots$$
将上式写成闭合形式，得 $\delta_T(t)$ 的 $z$ 变换为
$$E(z) = \frac{1}{1-z^{-1}} = \frac{z}{z-1}, \quad |z^{-1}| < 1$$
从例 7-5 和例 7-6 可见，相同的 $z$ 变换 $E(z)$ 对应于相同的采样函数 $e^*(t)$，但是不一定对应于相同的连续函数 $e(t)$，这是利用 $z$ 变换法分析离散系统时特别要注意的一个问题。

**(2) 部分分式法**
利用部分分式法求 $z$ 变换时，先求出已知连续时间函数 $e(t)$ 的拉氏变换 $E(s)$，然后将有理分式函数 $E(s)$ 展成部分分式之和的形式，使每一部分分式对应简单的时间函数，其相应的 $z$ 变换是已知的，于是可方便地求出 $E(s)$ 对应的 $z$ 变换 $E(z)$。

**例 7-7** 设 $e(t) = \sin \omega t$，试求其 $E(z)$。
**解** 对 $e(t) = \sin \omega t$ 取拉氏变换，得
$$E(s) = \frac{\omega}{s^2 + \omega^2}$$
将上式展开为部分分式
$$E(s) = \frac{1}{2j} \left( \frac{1}{s-j\omega} - \frac{1}{s+j\omega} \right)$$
根据指数函数的 $z$ 变换表达式，可以得到
$$E(z) = \frac{1}{2j} \left( \frac{z}{z-e^{j\omega T}} - \frac{z}{z-e^{-j\omega T}} \right) = \frac{1}{2j} \left[ \frac{z(e^{j\omega T} - e^{-j\omega T})}{z^2 - z(e^{j\omega T} + e^{-j\omega T}) + 1} \right]$$
化简后得
$$E(z) = \frac{z \sin \omega T}{z^2 - 2z \cos \omega T + 1}$$
常用时间函数的 $z$ 变换表如表 7-2 所示。由表可见，这些函数的 $z$ 变换都是 $z$ 的有理分式，且分母多项式的次数大于或等于分子多项式的次数。值得指出，表中各 $z$ 变换有理分式中，分母 $z$ 多项式的最高次数与相应传递函数分母 $s$ 多项式的最高次数相等。

### 表 7-2 $z$ 变换表

| 序号 | 拉氏变换 $E(s)$ | 时间函数 $e(t)$ | $z$ 变换 $E(z)$ |
| :--- | :--- | :--- | :--- |
| 1 | $e^{-nsT}$ | $\delta(t-nT)$ | $z^{-n}$ |
| 2 | $1$ | $\delta(t)$ | $1$ |
| 3 | $\frac{1}{s}$ | $1(t)$ | $\frac{z}{z-1}$ |
| 4 | $\frac{1}{s^2}$ | $t$ | $\frac{Tz}{(z-1)^2}$ |
| 5 | $\frac{1}{s^3}$ | $\frac{t^2}{2!}$ | $\frac{T^2z(z+1)}{2(z-1)^3}$ |
| 6 | $\frac{1}{s^4}$ | $\frac{t^3}{3!}$ | $\frac{T^3z(z^2+4z+1)}{6(z-1)^4}$ |
| 7 | $\frac{1}{s-(1/T)\ln a}$ | $a^{t/T}(a^t)$ | $\frac{z}{z-a}$ |
| 8 | $\frac{1}{s+a}$ | $e^{-at}$ | $\frac{z}{z-e^{-aT}}$ |
| 9 | $\frac{1}{(s+a)^2}$ | $te^{-at}$ | $\frac{Tze^{-aT}}{(z-e^{-aT})^2}$ |
| 10 | $\frac{1}{(s+a)^3}$ | $\frac{1}{2}t^2e^{-at}$ | $\frac{T^2ze^{-aT}}{2(z-e^{-aT})^2} + \frac{T^2ze^{-2aT}}{(z-e^{-aT})^3}$ |
| 11 | $\frac{a}{s(s+a)}$ | $1-e^{-at}$ | $\frac{(1-e^{-aT})z}{(z-1)(z-e^{-aT})}$ |
| 12 | $\frac{a}{s^2(s+a)}$ | $t-\frac{1}{a}(1-e^{-at})$ | $\frac{Tz}{(z-1)^2} - \frac{(1-e^{-aT})z}{a(z-1)(z-e^{-aT})}$ |
| 13 | $\frac{1}{(s+a)(s+b)(s+c)}$ | $\frac{e^{-at}}{(b-a)(c-a)} + \frac{e^{-bt}}{(a-b)(c-b)} + \frac{e^{-ct}}{(a-c)(b-c)}$ | $\frac{z}{(b-a)(c-a)(z-e^{-aT})} + \frac{z}{(a-b)(c-b)(z-e^{-bT})} + \frac{z}{(a-c)(b-c)(z-e^{-cT})}$ |

*(续表)*

| 序号 | 拉氏变换 $E(s)$ | 时间函数 $e(t)$ | $z$ 变换 $E(z)$ |
| :--- | :--- | :--- | :--- |
| 14 | $\frac{s+d}{(s+a)(s+b)(s+c)}$ | $\frac{(d-a)e^{-at}}{(b-a)(c-a)} + \frac{(d-b)e^{-bt}}{(a-b)(c-b)} + \frac{(d-c)e^{-ct}}{(a-c)(b-c)}$ | $\frac{(d-a)z}{(b-a)(c-a)(z-e^{-aT})} + \frac{(d-b)z}{(a-b)(c-b)(z-e^{-bT})} + \frac{(d-c)z}{(a-c)(b-c)(z-e^{-cT})}$ |
| 15 | $\frac{abc}{s(s+a)(s+b)(s+c)}$ | $1 - \frac{bc e^{-at}}{(b-a)(c-a)} - \frac{ca e^{-bt}}{(c-b)(a-b)} - \frac{ab e^{-ct}}{(a-c)(b-c)}$ | $\frac{z}{z-1} - \frac{bcz}{(b-a)(c-a)(z-e^{-aT})} - \frac{caz}{(c-b)(a-b)(z-e^{-bT})} - \frac{abz}{(a-c)(b-c)(z-e^{-cT})}$ |
| 16 | $\frac{\omega}{s^2+\omega^2}$ | $\sin \omega t$ | $\frac{z \sin \omega T}{z^2-2z \cos \omega T + 1}$ |
| 17 | $\frac{s}{s^2+\omega^2}$ | $\cos \omega t$ | $\frac{z(z-\cos \omega T)}{z^2-2z \cos \omega T + 1}$ |
| 18 | $\frac{\omega}{s^2-\omega^2}$ | $\sinh \omega t$ | $\frac{z \sinh \omega T}{z^2-2z \cosh \omega T + 1}$ |
| 19 | $\frac{s}{s^2-\omega^2}$ | $\cosh \omega t$ | $\frac{z(z-\cosh \omega T)}{z^2-2z \cosh \omega T + 1}$ |
| 20 | $\frac{\omega^2}{s(s^2+\omega^2)}$ | $1-\cos \omega t$ | $\frac{z}{z-1} - \frac{z(z-\cos \omega T)}{z^2-2z \cos \omega T + 1}$ |
| 21 | $\frac{\omega}{(s+a)^2+\omega^2}$ | $e^{-at} \sin \omega t$ | $\frac{ze^{-aT} \sin \omega T}{z^2-2ze^{-aT} \cos \omega T + e^{-2aT}}$ |
| 22 | $\frac{s+a}{(s+a)^2+\omega^2}$ | $e^{-at} \cos \omega t$ | $\frac{z^2-ze^{-aT} \cos \omega T}{z^2-2ze^{-aT} \cos \omega T + e^{-2aT}}$ |
| 23 | $\frac{b-a}{(s+a)(s+b)}$ | $e^{-at}-e^{-bt}$ | $\frac{z}{z-e^{-aT}} - \frac{z}{z-e^{-bT}}$ |
| 24 | $\frac{a^2b^2}{s^2(s+a)(s+b)}$ | $abt-(a+b)-\frac{b^2}{a-b}e^{-at}+\frac{a^2}{a-b}e^{-bt}$ | $\frac{abTz}{(z-1)^2} - \frac{(a+b)z}{z-1} - \frac{b^2z}{(a-b)(z-e^{-aT})} + \frac{a^2z}{(a-b)(z-e^{-bT})}$ |

### 3. $z$ 变换性质
$z$ 变换有一些基本定理，可以使 $z$ 变换的应用变得简单和方便，其内容在许多方面与拉氏变换的基本定理有相似之处。

**(1) 线性定理**
若 $E_1(z) = \mathcal{Z}[e_1(t)]$，$E_2(z) = \mathcal{Z}[e_2(t)]$，$a$ 为常数，则
$$\mathcal{Z}[e_1(t) \pm e_2(t)] = E_1(z) \pm E_2(z) \quad (7-26)$$