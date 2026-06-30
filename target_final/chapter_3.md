# 第 3 章

# 目标与均衡器设计

## 3.1 引言

在硬盘驱动器的信号处理系统中，维特比检测器 (Viterbi detector) [15] 与 PR 均衡器 (partial-response equalizer) 配合使用。PR 均衡器是一种线性滤波器 (linear filter)，其作用是将信道的总响应整形为所需的响应形式，即所谓的目标 (target)。然后，维特比检测器对均衡器的输出数据进行最大似然 (ML: maximum-likelihood) 序列检测 (sequence detection)，以计算出发送端发送的输入数据序列。这两个步骤合称为"部分响应最大似然 (PRML: partial-response maximum-likelihood)" 技术，被认为是当今硬盘驱动器信号处理系统的核心。

水平记录 (longitudinal recording) 系统中公认的 PR 目标以多项式 (polynomial) 形式给出：

$$
H(D) = (1 - D)(1 + D)^n \tag{3.1}
$$

其中 $n$ 是正整数，$D$ 是延迟算子 (delay operator)。从式 (3.1) 可以看出，该目标的频率响应在零频率和奈奎斯特频率 (Nyquist frequency) 处具有频谱零点 (spectral null)，这是因为分别存在 $(1 - D)$ 和 $(1 + D)$ 项。而垂直记录 (perpendicular recording) 系统的读回信号具有直流 (d.c.) 分量，因此 $(1 - D)$ 项对于垂直记录系统并非必需。因此，垂直记录系统中公认的 PR 目标以如下多项式形式给出：

$$
H(D) = (1 + D)^n \tag{3.2}
$$

表 3.1 显示了水平记录和垂直记录系统中公认的 PR 目标。图 3.1 比较了各种目标的频率响应与 ND = 2 和 2.5 时信道的频率响应。从图 3.1 可以看出，当信道的 ND 值增大时，所使用的目标应具有更多的抽头（$n$ 更大），以使频率响应与信道的频率响应尽可能一致。然而，所使用的目标不应有不必要的过多抽头，因为这将增加维特比检测器的复杂度 (complexity)，这将在第 4 章中进一步说明。

从式 (3.1) 和 (3.2) 可以观察到，PR 目标的每个抽头系数都是整数。但如果 PRML 系统允许使用系数为实数的目标，则此类目标可以显著提高系统整体性能，特别是在高 ND 条件下。这种目标通常称为"广义部分响应 (GPR: generalized partial-response) 目标"，可以通过多种方法求得，例如 [41, 42, 43, 44, 45, 46]。

**表 3.1: 硬盘驱动器中公认的 PR 目标示例**

| PR 目标 | $n = 1$ | $n = 2$ | $n = 3$ |
|---------|---------|---------|---------|
| 水平记录系统 | PR4 [1 0 -1] $1 - D^2$ | EPR4 [1 1 -1 -1] $1 + D - D^2 - D^3$ | EEPR4 [1 2 0 -2 -1] $1 + 2D - 2D^3 - D^4$ |
| 垂直记录系统 | PR1 [1 1] $1 + D$ | PR2 [1 2 1] $1 + 2D + D^2$ | EPR2 [1 3 3 1] $1 + 3D + 3D^2 + D^3$ |

![](../source_final/images/chapter_3/4c0fe7a4cfbe5976b9efd997d1cc229c8740fcbe3d9078664b588eb033134a83.jpg)  
(a) 归一化频率 (fT)

![](../source_final/images/chapter_3/6e8605f0f90bccaaa7ad6f02fdedf099ad580809482239d6776649fa2c7dbdc1.jpg)  
(b) 归一化频率 (fT)  
图 3.1: 各种目标的频率响应：(a) 水平记录 (b) 垂直记录

目标设计方法有多种，例如：

1) **使目标响应在时域和频域上与信道的转变响应或双比特响应形状一致**

   此方法求取在各 ND 下，目标响应形状与信道的转变响应或双比特响应一致的目标，包括时域和频域。例如，在垂直记录系统中，与双比特响应 [43] 在时域上一致的目标有 [1 −4 1]、[1 −2 −2 1] 和 [1 0 −8 0 1] 等。此外，某些目标可能不与信道响应在时域上一致，而更倾向于在频域上与信道响应一致。在实际应用中，频域上的一致性比时域上的一致性更为重要，因为它有助于了解噪声增强 (noise enhancement) 的相关特性。

2) **使均衡器输出端的总噪声功率最小**

   此方法假设系统设计者已知信道的特性，以便利用信道来计算均衡器的传递函数。然后计算均衡器输出端的总噪声功率，当得到数学形式的噪声功率表达式后，利用微分 (differentiation) 技术求出使总噪声功率最小的目标系数。此方法的详细内容可参阅 [41]。

3) **使维特比检测器输出端的有效 SNR 最大**

   上述各种目标设计方法并不能保证维特比检测器输出端的误码率 (BER: bit error-rate) 最小。文献 [19, 42] 提出了求取"最优目标 (optimal target)"的方法，使维特比检测器输出端的有效 SNR 最大，换言之，使维特比检测器输出端测得的系统 BER 最小。感兴趣的读者可以在 [19, 42] 中找到更多详细信息。

4) **使均衡器输出信号与期望信号（即所需目标信号）之间的均方误差 (MSE: mean-squared error) 最小**

   研究发现，此方法简单且适合实际应用 [19]。此外，所得目标的性能接近最优目标。这种目标设计方法称为"最小均方误差 (MMSE: minimum mean-squared error)" 方法，以下将详细介绍此方法的具体内容。

## 3.2 MMSE 目标设计方法

采用 MMSE 方法 [19] 进行目标设计时，根据设计过程中施加的约束条件 (constraint) 不同，可以得到多种形式的目标。考虑图 3.2 所示的系统模型，其中均衡器试图使其输出数据 $y_k$ 尽可能接近期望数据 $r_k$，同时避免噪声放大。假设均衡器有 $N = 2K + 1$ 个抽头，且中心抽头位于 $k = 0$ 时刻。因此，均衡器可以在 D 域中表示为如下数学形式：

![](../source_final/images/chapter_3/5befc6f4c9136b6afc946ce43c534dd7bfb154cab4ec0913ffa5eb4d9688f821.jpg)  
图 3.2: MMSE 目标设计系统模型

$$
F(D) = \sum_{k=-K}^{K} f_k D^k \tag{3.3}
$$

其中 $D$ 是 $T$ 单位延迟算子。类似地，具有 $L$ 个抽头的目标可以表示为 D 域函数：

$$
H(D) = \sum_{k=0}^{L-1} h_k D^k \tag{3.4}
$$

其中 $f_k$ 和 $h_k$ 分别是均衡器和目标各抽头的实系数。MMSE 目标设计方法的目标是同时计算 $F(D)$ 和 $H(D)$ 的系数，使均衡器输出 $y_k$ 与目标输出 $r_k$ 之间的 MSE 最小。换句话说，选择系数 $f_k$ 和 $h_k$ 使得下式最小：

$$
E[w_k^2] = E[\{ (s_k * f_k) - (a_k * h_k) \}^2] \tag{3.5}
$$

其中 $w_k = y_k - r_k$ 是目标设计产生的误差，$*$ 是卷积算子 (convolution operator)，$E[\cdot]$ 是期望算子 (expectation operator)。

定义列向量 $\mathbf{H} = [h_0, h_1, \cdots, h_{L-1}]^{\mathrm{T}}$ 和 $\mathbf{F} = [f_{-K}, \cdots, f_0, \cdots, f_K]^{\mathrm{T}}$，其中 $h_k$ 和 $f_k$ 分别是 $H(D)$ 和 $F(D)$ 的系数，$[\cdot]^{\mathrm{T}}$ 表示转置矩阵 (transpose matrix)。本章取 $K = 10$（均衡器共 21 个抽头）。设 $\mathbf{R}$ 为数据 $s_k$ 的 $N \times N$ 自相关矩阵 (auto-correlation matrix)，$\mathbf{A}$ 为数据 $a_k$ 的 $L \times L$ 自相关矩阵，$\mathbf{P}$ 为数据 $s_k$ 和 $a_k$ 之间的 $N \times L$ 互相关矩阵 (cross-correlation matrix)。这三个矩阵的元素 $(i, j)$（第 $i$ 行第 $j$ 列）分别为：

$$
\begin{array}{rcl}
\mathbf{R}(i, j) &=& E\left[\sum_{k=0}^{S-1} s_{k+K-i} s_{k+K-j}\right], \quad -K \le i, j \le K \tag{3.6}
\end{array}
$$

$$
\mathbf{A}(i, j) = E\left[\sum_{k=0}^{S-1} a_{k-i} a_{k-j}\right], \quad 0 \leq i, j \leq L-1 \tag{3.7}
$$

$$
\mathbf{P}(i, j) = E\left[\sum_{k=0}^{S-1} s_{k+K-i} a_{k-j}\right], \quad -K \leq i \leq K, \quad 0 \leq j \leq L-1 \tag{3.8}
$$

其中 $S$ 是输入数据序列 $\{a_k\}$ 的长度（即比特数）。

根据上述定义的变量，式 (3.5) 可以写成矩阵形式：

$$
E[w^2] = \mathbf{F}^{\mathrm{T}} \mathbf{R} \mathbf{F} + \mathbf{H}^{\mathrm{T}} \mathbf{A} \mathbf{H} - 2 \mathbf{F}^{\mathrm{T}} \mathbf{P} \mathbf{H} \tag{3.9}
$$

在使 $E[w^2]$ 相对于 $\mathbf{F}$ 和 $\mathbf{H}$ 最小化的过程中，必须施加约束条件，以避免得到 $\mathbf{F} = \mathbf{0}$ 和 $\mathbf{H} = \mathbf{0}$ 的平凡解。下面介绍计算 $\mathbf{F}$ 和 $\mathbf{H}$ 时使用的几种有趣约束条件。

### 3.2.1 首项系数约束 $(h_0 = 1)$

首项系数约束 (monic constraint) 要求目标的第一个抽头系数等于 1，即 $h_0 = 1$ [19]。定义 $L \times 1$ 的列向量 $\mathbf{I}$，其中第一个元素为 1，其余元素为 0，即 $\mathbf{I} = [1, 0, \cdots, 0]^{\mathrm{T}}$。因此，首项系数约束可以写成矩阵形式 $\mathbf{I}^{\mathrm{T}} \mathbf{H} = 1$。

采用此约束的 MMSE 目标设计过程，即是在始终保持 $\mathbf{I}^{\mathrm{T}} \mathbf{H} = 1$ 的条件下使式 (3.9) 中的 MSE 最小化。也就是说，该过程将使下式最小：

$$
E[w^2] = \mathbf{F}^{\mathrm{T}} \mathbf{R} \mathbf{F} + \mathbf{H}^{\mathrm{T}} \mathbf{A} \mathbf{H} - 2 \mathbf{F}^{\mathrm{T}} \mathbf{P} \mathbf{H} - 2\lambda(\mathbf{I}^{\mathrm{T}} \mathbf{H} - 1) \tag{3.10}
$$

其中 $\lambda$ 是拉格朗日乘子 (Lagrange multiplier)，为标量 (scalar)。使式 (3.10) 最小化的方法是对式 (3.10) 分别关于 $\mathbf{F}$、$\mathbf{H}$ 和 $\lambda$ 求偏导，结果如下（详见附录 C）：

$$
\frac{\partial(E[w^2])}{\partial \mathbf{F}} = 2\mathbf{R}\mathbf{F} - 2\mathbf{P}\mathbf{H} \tag{3.11}
$$

$$
\frac{\partial(E[w^2])}{\partial \mathbf{H}} = 2\mathbf{A}\mathbf{H} - 2\mathbf{P}^{\mathrm{T}}\mathbf{F} - 2\lambda\mathbf{I} \tag{3.12}
$$

$$
\frac{\partial(E[w^2])}{\partial \lambda} = -2\mathbf{I}^{\mathrm{T}}\mathbf{H} + 2 \tag{3.13}
$$

令式 (3.11)-(3.13) 的所有偏导结果为零。令式 (3.11) 等于零，可得：

$$
\begin{array}{rcl}
2\mathbf{R}\mathbf{F} - 2\mathbf{P}\mathbf{H} &=& 0 \\
\mathbf{R}\mathbf{F} &=& \mathbf{P}\mathbf{H} \\
\mathbf{F} &=& \mathbf{R}^{-1}\mathbf{P}\mathbf{H} \tag{3.14}
\end{array}
$$

令式 (3.12) 等于零，可得：

$$
\begin{array}{rlr}
2\mathbf{A}\mathbf{H} - 2\mathbf{P}^{\mathrm{T}}\mathbf{F} - 2\lambda\mathbf{I} &=& 0 \\
\mathbf{A}\mathbf{H} - \mathbf{P}^{\mathrm{T}}\mathbf{F} &=& \lambda\mathbf{I} \tag{3.15}
\end{array}
$$

将式 (3.14) 中的 $\mathbf{F}$ 代入式 (3.15)，可得：

$$
\begin{array}{rlrl}
\mathbf{A}\mathbf{H} - \mathbf{P}^{\mathrm{T}}(\mathbf{R}^{-1}\mathbf{P}\mathbf{H}) &=& \lambda\mathbf{I} \\
(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})\mathbf{H} &=& \lambda\mathbf{I} \\
\mathbf{H} &=& \lambda(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I} \tag{3.16}
\end{array}
$$

类似地，令式 (3.13) 等于零，可得：

$$
\begin{array}{rlr}
-2\mathbf{I}^{\mathrm{T}}\mathbf{H} + 2 &=& 0 \\
\mathbf{I}^{\mathrm{T}}\mathbf{H} &=& 1 \tag{3.17}
\end{array}
$$

将式 (3.16) 中的 $\mathbf{H}$ 代入式 (3.17)，可得：

$$
\begin{array}{rcl}
\mathbf{I}^{\mathrm{T}} \lambda(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I} &=& 1 \\
\lambda &=& \dfrac{1}{\mathbf{I}^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I}} \tag{3.18}
\end{array}
$$

综上所述，首项系数约束 $(h_0 = 1)$ 下的目标和均衡器设计步骤如下：

1) 确定目标和均衡器的抽头数（$L$ 和 $N$ 的值），即构造向量 $\mathbf{F}$ 和 $\mathbf{H}$。
2) 根据式 (3.6)-(3.8) 计算矩阵 $\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$。
3) 构造 $L \times 1$ 向量 $\mathbf{I} = [1, 0, \cdots, 0]^{\mathrm{T}}$。
4) 根据式 (3.18) 计算拉格朗日乘子 $\lambda$，即：

$$
\lambda = \frac{1}{\mathbf{I}^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I}} \tag{3.19}
$$

5) 根据式 (3.16) 计算目标 $\mathbf{H}$，即：

$$
\mathbf{H} = \lambda(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I} \tag{3.20}
$$

6) 根据式 (3.14) 计算均衡器 $\mathbf{F}$，即：

$$
\mathbf{F} = \mathbf{R}^{-1}\mathbf{P}\mathbf{H} \tag{3.21}
$$

由式 (3.19) 得到的 $\lambda$ 即为该约束下的 MMSE 值。这可以通过将式 (3.20)-(3.21) 中的 $\mathbf{F}$ 和 $\mathbf{H}$ 代入式 (3.9) 来证明：

$$
\begin{array}{rcl}
E[w^2] &=& (\mathbf{R}^{-1}\mathbf{P}\mathbf{H})^{\mathrm{T}}\mathbf{R}(\mathbf{R}^{-1}\mathbf{P}\mathbf{H}) + \mathbf{H}^{\mathrm{T}}\mathbf{A}\mathbf{H} - 2(\mathbf{R}^{-1}\mathbf{P}\mathbf{H})^{\mathrm{T}}\mathbf{P}\mathbf{H} \\
&=& \mathbf{H}^{\mathrm{T}}\mathbf{P}^{\mathrm{T}}(\mathbf{R}^{-1})^{\mathrm{T}}\mathbf{P}\mathbf{H} + \mathbf{H}^{\mathrm{T}}\mathbf{A}\mathbf{H} - 2\mathbf{H}^{\mathrm{T}}\mathbf{P}^{\mathrm{T}}(\mathbf{R}^{-1})^{\mathrm{T}}\mathbf{P}\mathbf{H} \\
&=& \mathbf{H}^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})\mathbf{H} \\
&=& \lambda^2\{[\mathbf{I}^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}]^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I}\} \\
&=& \lambda^2\{\mathbf{I}^{\mathrm{T}}(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}\mathbf{I}\} \\
&=& \lambda \tag{3.22}
\end{array}
$$

式 (3.22) 的推导利用了 $\mathbf{R}$ 和 $\mathbf{A}$ 是对称自相关矩阵这一事实。此外，$\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$ 还是 Toeplitz 矩阵，因此 $(\mathbf{R}^{-1})^{\mathrm{T}} = \mathbf{R}^{-1}$ 且 $[(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}]^{\mathrm{T}} = (\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})^{-1}$。

### 3.2.2 $h_1 = 1$ 约束

$h_1 = 1$ 约束要求目标的第二个抽头系数等于 1，即 $h_1 = 1$ [19]，其余抽头系数可以为任意值。此约束的目的是用于比较各种目标的性能。定义 $L \times 1$ 的列向量 $\mathbf{J}$，其中第二个元素为 1，其余元素为 0，即 $\mathbf{J} = [0, 1, 0, \cdots, 0]^{\mathrm{T}}$。因此，$h_1 = 1$ 约束可以写成矩阵形式 $\mathbf{J}^{\mathrm{T}}\mathbf{H} = 1$。

采用此约束的目标设计过程与首项系数约束完全相同，只需将式 (3.10) 中的最后一项 $2\lambda(\mathbf{I}^{\mathrm{T}}\mathbf{H} - 1)$ 替换为 $2\lambda(\mathbf{J}^{\mathrm{T}}\mathbf{H} - 1)$。因此，结果与式 (3.19)-(3.21) 相同，只需将向量 $\mathbf{I}$ 替换为向量 $\mathbf{J}$。

### 3.2.3 单位能量约束 $(\mathbf{H}^{\mathrm{T}}\mathbf{H} = 1)$

单位能量约束 (unit energy) 可以写成矩阵形式 $\mathbf{H}^{\mathrm{T}}\mathbf{H} = 1$，即要求目标的能量等于 1 [19, 46]。

采用此约束的目标设计过程，是在始终保持 $\mathbf{H}^{\mathrm{T}}\mathbf{H} = 1$ 的条件下使式 (3.9) 中的 MSE 最小化。也就是说，该过程将使下式最小：

$$
E[w^2] = \mathbf{F}^{\mathrm{T}}\mathbf{R}\mathbf{F} + \mathbf{H}^{\mathrm{T}}\mathbf{A}\mathbf{H} - 2\mathbf{F}^{\mathrm{T}}\mathbf{P}\mathbf{H} - 2\lambda(\mathbf{H}^{\mathrm{T}}\mathbf{H} - 1) \tag{3.23}
$$

可以通过分别对 $\mathbf{F}$、$\mathbf{H}$ 和 $\lambda$ 求偏导并令所有偏导为零来实现。按此步骤进行，可以发现目标和均衡器可以通过解以下方程得到：

$$
(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})\mathbf{H} = \lambda\mathbf{H} \tag{3.24}
$$

该方程的求解类似于"特征值问题 (eigenvalue problem)" [12, 25]。可以证明，式 (3.24) 中的 $\lambda$ 就是 MMSE 值。因此，从式 (3.24) 可知，$\lambda$ 实际上是矩阵 $(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})$ 的最小特征值 (minimum eigenvalue)，$\mathbf{H}$ 是对应于最小特征值的归一化特征向量 (normalized eigenvector)，$\mathbf{F}$ 与式 (3.21) 相同。

### 3.2.4 固定目标约束

对于固定目标约束 (fixed target)，目标从一开始就已确定。系统需要的是适合该给定目标的均衡器 $\mathbf{F}$，可由式 (3.21) 求得，即：

$$
\mathbf{F} = \mathbf{R}^{-1}\mathbf{P}\mathbf{G} \tag{3.25}
$$

可以保证得到的 MSE 值等于式 (3.9) 中的值。

这种目标设计方法非常实用。因为在实际应用中，硬盘驱动器的信号处理芯片是为特定目标设计的。用户必须调整均衡器各抽头系数以匹配给定的目标，使得均衡器输出信号的形状与期望信号一致，从而帮助维特比检测器更容易地工作。相反，如果通过试错法 (trial and error) 调整均衡器各抽头系数，将非常耗时，且得到的均衡器往往与给定的目标不匹配。

> **注意**：在根据式 (3.20) 和 (3.21) 求解目标 $\mathbf{H}$ 和均衡器 $\mathbf{F}$ 时，第一步应计算矩阵 $\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$。这三个矩阵在实际中可以很容易地求得：根据图 3.2 的目标设计模型，向系统输入一个扇区 (sector) 即 4096 比特的输入数据序列 $\{a_k\}$，将其写入记录介质（即用户明确知道 $\{a_k\}$ 是什么），然后让读头从记录介质读取数据，将得到的读回信号经过低通滤波器和采样器，得到数据序列 $\{s_k\}$。在实际中，用户也可以知道 $\{s_k\}$ 是什么。因此，获得 $\{a_k\}$ 和 $\{s_k\}$ 后，使用 MATLAB [13] 或 SCILAB [14] 程序计算矩阵 $\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$。可以看出，MMSE 目标设计方法在实际中比其他目标设计方法更易实现。

## 3.3 实验结果

本节将使用图 3.2 所示的模型，比较采用不同目标的系统性能，针对垂直记录系统。根据图 3.2，来自读头的读回信号可以表示为如下数学形式 [40]：

$$
p(t) = \sum_{k=0}^{S-1} b_k g(t - kT + \Delta t_k) + n(t) \tag{3.26}
$$

其中 $b_k = (a_k - a_{k-1})/2$ 是转变比特（$b_k = \pm 1$ 对应正或负的转变，$b_k = 0$ 表示无转变）；$a_k \in \pm 1$ 是第 $k$ 个输入数据比特，共 4096 比特（1 个扇区）；$g(t)$ 是垂直记录系统的转变脉冲信号，如式 (1.2) 所示；$\Delta t$ 是介质抖动噪声 (media jitter noise)；$n(t)$ 是加性高斯白噪声 (AWGN)，双边功率谱密度为 $N_0/2$。在本书中，介质抖动噪声被建模为 "随机转变偏移 (random transition shift)"，具有高斯概率密度函数 (Gaussian probability density function)，均值为零，方差为 $|b_k|\sigma_j^2$（即 $\Delta t_k \sim \mathcal{N}(0, |b_k|\sigma_j^2)$），且限制不超过 $T/2$，其中 $\sigma_j$ 以比特单元 $T$ 的百分比表示，$|b_k|$ 是 $b_k$ 的绝对值。

读回信号 $p(t)$ 经过 7 阶巴特沃斯 (Butterworth) 低通滤波器，然后以 $1/T$ 的速率采样（即每个采样点间隔 1 个比特单元）。此处假设读回信号与采样时钟之间为完美同步 (perfect synchronization)。然后，数据序列 $\{s_k\}$ 被送入均衡器，将信号整形为系统所需的目标响应，维特比检测器对 $\{y_k\}$ 进行解码，找出最可能的序列 $\{a_k\}$。

实验中，"电子 SNR"（简称 SNR）定义为：

$$
\mathrm{SNR} = 10 \log_{10} \left( \frac{V_p^2}{\sigma^2} \right) \quad \text{(dB)} \tag{3.27}
$$

其中 $V_p = g(\infty) = 1$ 是孤立转变脉冲在 $t = \infty$ 处的幅度，$\sigma_n^2 = N_0/(2T)$ 是噪声 $n(t)$ 的功率。每个 BER 数据点通过使用多个扇区的数据计算，直到总错误数不少于 1000 比特。所使用的目标和均衡器针对各 ND 值分别进行了优化设计，目标 BER 水平为 $\mathrm{BER} = 10^{-5}$。

### 示例 3.1

本例演示根据式 (3.19)-(3.21) 计算目标和均衡器的步骤。考虑图 3.2 所示的垂直记录系统模型，ND = 1.5，SNR = 20 dB。给定输入数据序列 $\{a_k\} = \{1, 1, 1, -1, 1, -1\}$，以及相应的均衡器输入数据序列 $\{s_k\} = \{-0.5337, -0.0662, 0.8821, 0.8122, 0.3219, 0.0260\}$。求取 3 抽头 GPR 目标和 5 抽头均衡器，约束条件如下：

a) 首项系数约束 $h_0 = 1$
b) $h_1 = 1$ 约束
c) 单位能量约束
d) 固定目标约束，给定 $H(D) = 1 + 2D + D^2$

**解**：求取目标和均衡器的第一步是根据式 (3.6)-(3.8) 计算矩阵 $\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$，其中 $S = 6$、$K = 2$、$L = 3$。计算结果如下：

矩阵 $\mathbf{R}$：
$$
\mathbf{R} = \left[\begin{array}{ccccc}
0.3052 & 0.1926 & -0.0549 & -0.1440 & -0.0868 \\
0.1926 & 0.3052 & 0.1926 & -0.0549 & -0.1440 \\
-0.0549 & 0.1926 & 0.3052 & 0.1926 & -0.0549 \\
-0.1440 & -0.0549 & 0.1926 & 0.3052 & 0.1926 \\
-0.0868 & -0.1440 & -0.0549 & 0.1926 & 0.3052
\end{array}\right]
$$

矩阵 $\mathbf{A}$：
$$
\mathbf{A} = \left[\begin{array}{rrr}
1.0000 & -0.2000 & 0.5000 \\
-0.2000 & 1.0000 & -0.2000 \\
0.5000 & -0.2000 & 1.0000
\end{array}\right]
$$

矩阵 $\mathbf{P}$：
$$
\mathbf{P} = \left[\begin{array}{rrr}
0.4976 & 0.3867 & 0.1740 \\
0.2664 & 0.4976 & 0.3867 \\
-0.0390 & 0.2664 & 0.4976 \\
-0.1983 & -0.0390 & 0.2664 \\
-0.0994 & -0.1983 & -0.0390
\end{array}\right]
$$

下面以矩阵 $\mathbf{A}$ 的部分元素 $(i,j)$ 计算为例进行说明。由 $\mathbf{A}(i,j) = E[\sum_{k=0}^{5} a_{k-i}a_{k-j}], 0 \leq i,j \leq 2$，且输入数据序列 $\{a_k\} = \{a_0, a_1, a_2, a_3, a_4, a_5\} = \{1, 1, 1, -1, 1, -1\}$，可得：

$$
\begin{array}{lll}
\mathbf{A}(0,0) &=& E[\sum_{k=0}^{5} a_k a_k] \\
&=& E[a_0 a_0 + a_1 a_1 + a_2 a_2 + a_3 a_3 + a_4 a_4 + a_5 a_5] \\
&=& \frac{1}{6}[(1)(1) + (1)(1) + (1)(1) + (-1)(-1) + (1)(1) + (-1)(-1)] \\
&=& 1
\end{array}
$$

$$
\begin{array}{lll}
\mathbf{A}(0,1) &=& E[\sum_{k=0}^{5} a_k a_{k-1}] \\
&=& E[a_1 a_0 + a_2 a_1 + a_3 a_2 + a_4 a_3 + a_5 a_4] \\
&=& \frac{1}{5}[(1)(1) + (1)(1) + (-1)(1) + (1)(-1) + (-1)(1)] \\
&=& -0.2
\end{array}
$$

$$
\begin{array}{lcl}
\mathbf{A}(0,2) &=& E[\sum_{k=0}^{5} a_k a_{k-2}] \\
&=& E[a_2 a_0 + a_3 a_1 + a_4 a_2 + a_5 a_3] \\
&=& \frac{1}{4}[(1)(1) + (-1)(1) + (1)(1) + (-1)(-1)] \\
&=& 0.5
\end{array}
$$

其他矩阵元素可类似计算。得到矩阵 $\mathbf{R}$、$\mathbf{A}$ 和 $\mathbf{P}$ 后，由题意知 $\mathbf{H} = [h_0, h_1, h_2]^{\mathrm{T}}$、$\mathbf{F} = [f_{-2}, f_{-1}, f_0, f_1, f_2]^{\mathrm{T}}$。因此，目标和均衡器可根据式 (3.19)-(3.21) 按不同约束条件计算如下：

a) **首项系数约束 $h_0 = 1$**：$\mathbf{I} = [1, 0, 0]^{\mathrm{T}}$，$\lambda = -0.0837$，
   $\mathbf{H} = [1, 0.1754, -0.8587]^{\mathrm{T}}$，
   $\mathbf{F} = [1.0936, -0.0722, -0.9953, -0.2400, -0.0805]^{\mathrm{T}}$

b) **$h_1 = 1$ 约束**：$\mathbf{J} = [0, 1, 0]^{\mathrm{T}}$，$\lambda = -2.2814$，
   $\mathbf{H} = [4.7796, 1, -1.6613]^{\mathrm{T}}$，
   $\mathbf{F} = [7.0507, 1.8111, -4.6115, 3.0835, -1.9107]^{\mathrm{T}}$

c) **单位能量约束**：矩阵 $(\mathbf{A} - \mathbf{P}^{\mathrm{T}}\mathbf{R}^{-1}\mathbf{P})$ 的特征值为 $\{1.5182, -0.0476, -1.0211\}$，
   $\mathbf{H} = [0.3843, 0.7335, 0.5607]^{\mathrm{T}}$，
   $\mathbf{F} = [1.7138, 1.1288, 0.0256, 1.5285, -0.6140]^{\mathrm{T}}$

d) **固定目标约束**：$\mathbf{H} = [1, 2, 1]^{\mathrm{T}}$，
   $\mathbf{F} = [4.2431, 2.6064, 0.1106, 3.1983, -1.3164]^{\mathrm{T}}$

在本实验中，比较以下 5 种不同目标的系统性能：

1) PR1 目标：$H(D) = 1 + D$ 或表示为 [1, 1]
2) PR2 目标：$H(D) = 1 + 2D + D^2$ 或表示为 [1, 2, 1]
3) 首项系数约束 $h_0 = 1$ 的 GPR 目标
4) $h_1 = 1$ 约束的 GPR 目标
5) 单位能量约束的 GPR 目标

图 3.3 比较了 ND = 2 时各种目标的系统性能，采用 3 抽头的 GPR 目标。本例中，首项系数约束目标为 $1 + 1.15D + 0.48D^2$，$h_1 = 1$ 约束目标为 $0.55 + D + 0.55D^2$，单位能量约束目标为 $0.45 + 0.77D + 0.45D^2$。从图 3.3 可以看出，总体而言 GPR 目标的系统性能优于 PR 目标，且首项系数约束目标的性能最佳，尤其是在高 ND 条件下。

![](../source_final/images/chapter_3/2ccbb239177928eca0edb6827c2229c43b787d3a63865bc48f8e00571d58dc2d.jpg)  
图 3.3: 不同目标在 ND = 2 时的 BER 性能

为验证 GPR 目标优于 PR 目标，进一步比较 ND = 2.5 时的系统性能，此时采用 5 抽头 GPR 目标（增加抽头数以适应更高的 ND）。在此情况下，首项系数约束目标为 $1 + 1.42D + 1.06D^2 + 0.43D^3 + 0.08D^4$，$h_1 = 1$ 约束目标为 $0.47 + D + 0.96D^2 + 0.53D^3 + 0.14D^4$，单位能量约束目标为 $0.20 + 0.5D + 0.66D^2 + 0.5D^3 + 0.2D^4$。图 3.4 比较了 ND = 2.5 时各种目标的系统性能，结果显示首项系数 $h_0 = 1$ 约束的目标性能最佳。这是因为 GPR 目标（特别是首项系数约束目标）的频率响应比 PR 目标更接近信道频率响应，如图 3.5 所示。

![](../source_final/images/chapter_3/c28a3b9e8664b4c821eed8d2122435ecdff1223ad302b7bd57a0226ff93f3814.jpg)  
图 3.4: 不同目标在 ND = 2.5 时的 BER 性能

此外，GPR 目标有助于使维特比检测器输入端的噪声分量呈现白噪声 (white noise) 特性，这是使维特比检测器以最高效率工作的关键要求 [15]。检测噪声 $w_k$ 是否具有白噪声特性，可以通过计算序列 $\{w_k\}$（见图 3.2）的自相关 (auto-correlation) 来实现。如果结果仅在时间差为零时有值，而在其他时间差时为零（或接近零），则可以判定序列 $w_k$ 具有白噪声特性。图 3.6 显示了 ND = 2.5 时各种目标下序列 $\{w_k\}$ 的自相关值。从图中可以看出，使用首项系数 $h_0 = 1$ 约束的 GPR 目标时，维特比检测器输入端的噪声分量最接近白噪声。

![](../source_final/images/chapter_3/c6569af5dc45feeb2f931e19c834663941f05f69b94ab984bc0500d8114d606d.jpg)  
图 3.5: ND = 2.5 时各种目标的频率响应与信道频率响应的比较

由于首项系数约束 $h_0 = 1$ 的 GPR 目标性能最佳，因此后续使用符号 "GPRn" 表示具有 $n$ 个抽头的首项系数约束目标。图 3.7(a) 比较了无介质抖动噪声 $(\sigma_j/T = 0\%)$ 时，不同 ND 下各种目标的性能。纵轴表示系统达到 $\mathrm{BER} = 10^{-4}$ 所需的 SNR，因此所需 SNR 越低的系统性能越好。从图中可以看出，GPR 目标性能优于 PR 目标，特别是在高 ND 条件下。这是因为 GPR 目标的频率响应比 PR 目标更接近信道频率响应（见图 3.5）。

图 3.7(b) 比较了 ND = 2.5 时，在不同 $\sigma_j/T$ 水平下各种目标的性能。同样可以看出，在所有 $\sigma_j/T$ 水平下，GPR 目标性能均优于 PR 目标（为达到相同的 $\mathrm{BER} = 10^{-4}$，所需 SNR 更低）。值得注意的是，当 $\sigma_j/T$ 较大时，PR2 目标所需 SNR 低于（即性能优于）EPR2 和 EEPR2 目标。这可能是因为抽头数较少的 PR 目标对介质抖动噪声的敏感度 (sensitivity) 低于抽头数较多的 PR 目标。相反，GPR 目标的性能随着抽头数的增加而始终提高，与 $\sigma_j/T$ 的水平无关。

![](../source_final/images/chapter_3/a5c63a611a99b3318de2186cd2753833d4192a96bb0ebd20cd2120335e02a665.jpg)  
![](../source_final/images/chapter_3/5c0c8e77b63a49d21c0ab641f14f2ac7d3817ac8c4cdc178cc76b5199eaeff3f.jpg)  
图 3.7: (a) $\sigma_j = 0\%$ 时所需 SNR 与 ND 的关系 (b) ND = 2.5 时所需 SNR 与 $\sigma_j$ 的关系

![](../source_final/images/chapter_3/7b630a96cee2aaf3cc391362a5139044ceea8414e75f6130da6440b81cd8dc06.jpg)  
图 3.6: ND = 2.5 时不同目标下序列 $\{w_k\}$ 的自相关

## 3.4 本章小结

GPR 目标比 PR 目标具有更好的性能，特别是在高 ND 条件下。这是因为 GPR 目标的频率响应比 PR 目标更接近信道的频率响应。此外，GPR 目标有助于使维特比检测器输入端的噪声分量呈白噪声特性，从而使维特比检测器能够更有效地工作。

目标和均衡器的设计可以通过多种方法实现。但在实际中会发现，基于 MMSE 的设计方法比其他目标设计方法更为简单。实验结果表明，采用这种简便方法（实际方法）设计的目标，其性能接近甚至优于其他方法设计的目标。此外，一个好的目标设计应根据读通道芯片 (read-channel chip) 的工作条件进行设计，例如针对每个 ND、SNR 和 $\sigma_j/T$ 分别设计目标，以使得目标在该工作条件下具有最佳性能。

## 3.5 课后习题

1. 推导方程 (3.9)

2. 推导方程 (3.24)

3. 使用图 3.2 所示的模型，针对纵向记录 (longitudinal recording) 系统，设 ND = 2、SNR = 20 dB。给定输入数据序列 $\{a_k\} = \{1, -1, 1, -1, 1, 1\}$ 及相应的均衡器输入序列 $\{s_k\} = \{0.0767, 0.6184, -0.1537, 0.0469, -0.2469, 0.2096\}$。求取 3 抽头 GPR 目标和 5 抽头均衡器，约束条件如下：

   a) 首项系数约束 $h_0 = 1$

   b) $h_1 = 1$ 约束

   c) 单位能量约束

   d) 固定目标约束，给定 $H(D) = 1 - D^2$

4. 使用 SCILAB 或 MATLAB 程序验证目标 $[1, -4, 1]$、$[1, -2, -2, 1]$ 和 $[1, 0, -8, 0, 1]$ 的频率响应，以确认这些目标在感兴趣的频带内与纵向记录系统的频率响应相匹配。
