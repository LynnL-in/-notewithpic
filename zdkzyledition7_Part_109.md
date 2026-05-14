## Page 1

$$\mathcal{Z}[ae(t)] = aE(z) \quad (7-27)$$

其中，$E(z) = \mathcal{Z}[e(t)]$。

**证明** 由 $z$ 变换定义
$$\mathcal{Z}[e_1(t) \pm e_2(t)] = \sum_{n=0}^{\infty} [e_1(nT) \pm e_2(nT)]z^{-n} = \sum_{n=0}^{\infty} e_1(nT)z^{-n} \pm \sum_{n=0}^{\infty} e_2(nT)z^{-n} = E_1(z) \pm E_2(z)$$

以及
$$\mathcal{Z}[ae(t)] = a \sum_{n=0}^{\infty} e(nT)z^{-n} = aE(z)$$

式(7-26)和式(7-27)表明，$z$ 变换是一种线性变换，其变换过程满足齐次性与均匀性。

(2) 实数位移定理
实数位移又称平移定理。实数位移的含义，是指整个采样序列在时间轴上左右平移若干采样周期，其中向左平移为超前，向右平移为滞后。实数位移定理如下：

如果函数 $e(t)$ 是可拉氏变换的，其 $z$ 变换为 $E(z)$，则有
$$\mathcal{Z}[e(t-kT)] = z^{-k}E(z) \quad (7-28)$$

以及
$$\mathcal{Z}[e(t+kT)] = z^k \left[ E(z) - \sum_{n=0}^{k-1} e(nT)z^{-n} \right] \quad (7-29)$$

其中 $k$ 为正整数。

**证明** 由 $z$ 变换定义
$$\mathcal{Z}[e(t-kT)] = \sum_{n=0}^{\infty} e(nT-kT)z^{-n} = z^{-k} \sum_{n=0}^{\infty} e(n-k)T z^{-(n-k)}$$

令 $m=n-k$，则有
$$\mathcal{Z}[e(t-kT)] = z^{-k} \sum_{m=-k}^{\infty} e(mT)z^{-m}$$

由于 $z$ 变换的单边性，当 $m<0$ 时，有 $e(mT)=0$，所以上式可写为
$$\mathcal{Z}[e(t-kT)] = z^{-k} \sum_{m=0}^{\infty} e(mT)z^{-m}$$

再令 $m=n$，立即证得式(7-28)。

为了证明式(7-29)，取 $k=1$，得
$$\mathcal{Z}[e(t+T)] = \sum_{n=0}^{\infty} e(nT+T)z^{-n} = z \sum_{n=0}^{\infty} e(n+1)T z^{-(n+1)}$$

令 $m=n+1$，上式可写为
$$\mathcal{Z}[e(t+T)] = z \sum_{m=1}^{\infty} e(mT)z^{-m} = z \left[ \sum_{m=0}^{\infty} e(mT)z^{-m} - e(0) \right] = z[E(z)-e(0)]$$

取 $k=2$，同理得
$$\mathcal{Z}[e(t+2T)] = z^2 \sum_{m=2}^{\infty} e(mT)z^{-m} = z^2 \left[ \sum_{m=0}^{\infty} e(mT)z^{-m} - e(0) - z^{-1}e(T) \right] = z^2 \left[ E(z) - \sum_{n=0}^{1} e(nT)z^{-n} \right]$$

取 $k=k$ 时，必有
$$\mathcal{Z}[e(t+kT)] = z^k \left[ E(z) - \sum_{n=0}^{k-1} e(nT)z^{-n} \right]$$

---

## Page 2

在实数位移定理中，式(7-28)称为滞后定理；式(7-29)称为超前定理。显然可见，算子 $z$ 有明确的物理意义：$z^{-k}$ 代表时域中的滞后环节，它将采样信号滞后 $k$ 个采样周期；同理，$z^k$ 代表超前环节，它将采样信号超前 $k$ 个采样周期。但是，$z^k$ 仅用于运算，在物理系统中并不存在。

实数位移定理是一个重要定理，其作用相当于拉氏变换中的微分和积分定理。应用实数位移定理，可将描述离散系统的差分方程转换为 $z$ 域的代数方程。有关差分方程的概念将在下节介绍。

**例 7-8** 试用实数位移定理计算滞后一个采样周期的指数函数 $e^{-a(t-T)}$ 的 $z$ 变换，其中 $a$ 为常数。

**解** 由式(7-28)
$$\mathcal{Z}[e^{-a(t-T)}] = z^{-1} \mathcal{Z}[e^{-at}] = z^{-1} \cdot \frac{z}{z-e^{-aT}} = \frac{1}{z-e^{-aT}}$$

(3) 复数位移定理
如果函数 $e(t)$ 是可拉氏变换的，其 $z$ 变换为 $E(z)$，则有
$$\mathcal{Z}[e^{\pm at}e(t)] = E(ze^{\mp aT}) \quad (7-30)$$

**证明** 由 $z$ 变换定义
$$\mathcal{Z}[e^{\pm at}e(t)] = \sum_{n=0}^{\infty} e^{\pm anT}e(nT)z^{-n} = \sum_{n=0}^{\infty} e(nT)(ze^{\mp aT})^{-n}$$

令
$$z_1 = ze^{\mp aT}$$

则有
$$\mathcal{Z}[e^{\pm at}e(t)] = \sum_{n=0}^{\infty} e(nT)z_1^{-n} = E(ze^{\mp aT})$$

复数位移定理是仿照拉氏变换的复数位移导出的，其含义是函数 $e^*(t)$ 乘以指数序列 $e^{\pm anT}$ 的 $z$ 变换，就等于在 $e^*(t)$ 的 $z$ 变换表达式 $E(z)$ 中，以 $ze^{\mp aT}$ 取代原算子 $z$。

**例 7-9** 试用复数位移定理计算函数 $te^{-aT}$ 的 $z$ 变换。

**解** 令 $e(t)=t$，由表 7-2 知
$$E(z) = \mathcal{Z}[t] = \frac{Tz}{(z-1)^2}$$

根据复数位移定理(7-30)，有
$$E(ze^{aT}) = \mathcal{Z}[te^{-at}] = \frac{T(ze^{aT})}{(ze^{aT}-1)^2} = \frac{Tze^{-aT}}{(z-e^{-aT})^2}$$

(4) 终值定理
如果函数 $e(t)$ 的 $z$ 变换为 $E(z)$，函数序列 $e(nT)$ 为有限值($n=0,1,2,\cdots$)，且极限 $\lim_{n \to \infty} e(nT)$ 存在，则函数序列的终值
$$\lim_{n \to \infty} e(nT) = \lim_{z \to 1} (z-1)E(z) \quad (7-31)$$

---

## Page 3

**证明** 由 $z$ 变换线性定理，有
$$\mathcal{Z}[e(t+T)] - \mathcal{Z}[e(t)] = \sum_{n=0}^{\infty} \{e[(n+1)T] - e(nT)\}z^{-n}$$

由平移定理
$$\mathcal{Z}[e(t+T)] = zE(z) - ze(0)$$

于是
$$(z-1)E(z) - ze(0) = \sum_{n=0}^{\infty} \{e[(n+1)T] - e(nT)\}z^{-n}$$

上式两边取 $z \to 1$ 的极限，得
$$\lim_{z \to 1} (z-1)E(z) - e(0) = \lim_{z \to 1} \sum_{n=0}^{\infty} \{e[(n+1)T] - e(nT)\}z^{-n} = \sum_{n=0}^{\infty} \{e[(n+1)T] - e(nT)\}$$

当取 $n=N$ 为有限项时，上式右端可写为
$$\sum_{n=0}^{N} \{e[(n+1)T] - e(nT)\} = e[(N+1)T] - e(0)$$

令 $N \to \infty$，有
$$\sum_{n=0}^{\infty} \{e[(n+1)T] - e(nT)\} = \lim_{N \to \infty} \{e[(N+1)T] - e(0)\} = \lim_{n \to \infty} e(nT) - e(0)$$

所以
$$\lim_{n \to \infty} e(nT) = \lim_{z \to 1} (z-1)E(z)$$

$z$ 变换的终值定理形式亦可表示为
$$e_{ss}(\infty) = \lim_{n \to \infty} e(nT) = \lim_{z \to 1} (1-z^{-1})E(z) \quad (7-32)$$

读者不妨自行论证。在离散系统分析中，常采用终值定理求系统输出序列的终值误差，或称稳态误差。

**例 7-10** 设 $z$ 变换函数为
$$E(z) = \frac{0.792z^2}{(z-1)(z^2 - 0.416z + 0.208)}$$

试利用终值定理确定 $e(nT)$ 的终值。

**解** 由终值定理(7-31)得
$$e_{ss}(\infty) = \lim_{z \to 1} (z-1) \cdot \frac{0.792z^2}{(z-1)(z^2 - 0.416z + 0.208)}$$
$$= \lim_{z \to 1} \frac{0.792z^2}{z^2 - 0.416z + 0.208} = 1$$

(5) 卷积定理
设 $x(nT)$ 和 $y(nT)$ 为两个采样函数，其离散卷积为
$$x(nT) * y(nT) = \sum_{k=0}^{n} x(kT)y[(n-k)T] \quad (7-33)$$

则由卷积定理，若
$$g(nT) = x(nT) * y(nT)$$