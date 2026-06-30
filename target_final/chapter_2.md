# 第 2 章

# 时钟恢复 (Timing Recovery)

本章将阐述时钟恢复 (timing recovery) 的重要性，并解释基于锁相环 (PLL: phase-locked loop) 的常规时钟恢复 (conventional timing recovery) 的工作原理。此外，还将介绍如何利用线性化锁相环模型 (linearized PLL model) 来设计锁相环的参数，并通过实验结果展示时钟恢复系统的关键作用。

## 2.1 引言

当今，通信技术发展迅速，特别是应用于移动电话系统和硬盘驱动器内部信号处理等各种系统中的数字通信。因此，提高系统的整体性能至关重要，以确保能够更可靠地接收和发送数据。

在数字通信系统 (digital communication system) 中，信号从发送端传送到接收端。发送端将数字信号 (digital) 转换为模拟信号 (analog) 后发送。当模拟信号到达接收端时，它被送入采样器 (sampler)，将模拟信号重新转换为数字形式的离散数据 (discrete data)，即所谓的"样本 (sample)"。如果模拟信号的采样时机不对，会对系统的整体性能产生极大影响。时钟恢复的作用是将采样器与接收到的模拟信号同步 (synchronize)，从而提取出质量最好的样本，以便后续进行进一步的处理，例如将其送入均衡器 (equalizer) 和解码器 (decoder) 等。因此，时钟恢复是数字通信系统中至关重要的一环。如果采样器工作不佳，会导致提取的样本质量差或错误较多，从而使得均衡器和解码器的处理结果出现大量错误，最终导致系统的误码率 (BER: bit-error rate) 升高，而这正是需要避免的。

通常，时钟恢复基于锁相环 (PLL) [4] 实现，它由时钟误差检测器 (TED: timing error detector)、环路滤波器 (loop filter) 和压控振荡器 (VCO: voltage-controlled oscillator) 组成。在实际应用中，时钟恢复结构主要分为两种形式：演绎式 (deductive) 和归纳式 (inductive)，这取决于时钟信息是在采样器之前还是之后被提取。演绎式时钟恢复 (deductive timing recovery) 从采样器的模拟输入端提取被称为"时钟色调 (timing tone)"[16] 的时钟信息，如图 2.1 所示。在这种结构中，PLL 用于减轻模拟信号中潜藏的时钟抖动 (timing jitter) 的影响。而归纳式时钟恢复 (inductive timing recovery) 则使用反馈式 PLL，从采样器的输出端提取时钟信息，如图 2.2 所示。归纳式时钟恢复的优点是其所有组件都可以用数字电路实现。由于归纳式时钟恢复应用极其广泛，因此在本书中将其称为"常规时钟恢复 (conventional timing recovery)"。关于演绎式时钟恢复的详细信息可参考 [20]。

## 2.2 常规时钟恢复

![](../source_final/images/chapter_2/f313918d8069d3a78d934d4e32950ebe7924355f96b5bb0667ceb7b781cdab52.jpg)  
图 2.2: 理想信道模型及归纳式时钟恢复

考虑图 2.2 所示的理想信道模型 (ideal channel model)。输入数据序列 $a_k \in \{\pm 1\}$ 的比特周期为 $T$，它经过信道 $H(D) = \sum_{k=0}^{\nu} h_k D^k$，其中 $h_k$ 是第 $k$ 个信道系数，$D$ 是延迟算子 (delay operator)，$\nu$ 是信道记忆长度。因此，读回信号 (read-back signal) 可以写为：

$$
p(t) = \sum_k r_k q(t - kT - \tau_k) + n(t) \tag{2.1}
$$

其中 $r_k = \sum_i a_{k-i} h_i$ 是无噪声的信道输出，$q(t) = \sin(\pi t/T)/(\pi t/T)$ 是 sinc 函数或称为零过剩带宽 (zero-excess-bandwidth) 的奈奎斯特脉冲 (Nyquist pulse) [16]，$\tau_k$ 是第 $k$ 个未知的时间偏移 (unknown timing offset)，$n(t)$ 是加性高斯白噪声 (AWGN: additive white Gaussian noise)，其双边功率谱密度 (power spectrum density) 为 $N_0/2$。在本书中，时间偏移 $\tau_k$ 被建模为"随机游走 (random walk)"[21]：

$$
\tau_{k+1} = \tau_k + w_k \tag{2.2}
$$

其中 $w_k$ 是独立同分布 (i.i.d.) 的高斯随机变量，均值为零，方差为 $\sigma_w^2$，记为 $w_k \sim \mathcal{N}(0, \sigma_w^2)$。$\sigma_w$ 的值决定了时钟抖动 (timing jitter) 的严重程度。

在接收端，读回信号首先通过一个低通滤波器 (LPF: low-pass filter)，其冲激响应为 $q(t)/T$，截止频率 (cut-off frequency) 为 $1/(2T)$，用于滤除带外噪声。然后在时刻 $kT + \hat{\tau}_k$ 对信号进行采样，得到采样数据：

$$
y_k = y(kT + \hat{\tau}_k) = \sum_i r_i q(kT + \hat{\tau}_k - iT - \tau_i) + n_k \tag{2.3}
$$

其中 $\hat{\tau}_k$ 是 $\tau_k$ 的估计值，也称为第 $k$ 个采样的相位偏移 (phase offset)，$n_k$ 是均值为零、方差为 $\sigma_n^2 = N_0/(2T)$ 的 AWGN，即 $n_k \sim \mathcal{N}(0, \sigma_n^2)$。

TED 的作用是计算时间误差 (timing error) $\epsilon_k = \tau_k - \hat{\tau}_k$ 的估计值，即接收到的模拟信号与 PLL 时钟信号之间的相位失配。实际中有多种类型的 TED [4]，取决于 TED 输入端数据的利用方式。一般来说，时钟恢复的性能取决于 TED 的质量。本书只考虑最常用的 Mueller 和 Müller TED（简称 M&M TED）[24]，它按下式计算：

$$
\hat{\epsilon}_k = K_T \{ y_k \hat{r}_{k-1} - y_{k-1} \hat{r}_k \} \tag{2.4}
$$

其中 $\hat{r}_k$ 是 $r_k$ 的估计值，$K_T$ 是一个常数，用于确保在高信噪比 (SNR: signal-to-noise ratio) 下 $E[\hat{\epsilon}_k | \epsilon] = \epsilon$。换句话说，$K_T$ 用于将 S 曲线 (S-curve) [4] 在原点的斜率归一化为 1，$E[\cdot]$ 是期望算子 (expectation operator) [10, 25, 26]。从式 (2.4) 可以看出，TED 的性能取决于决策值 $\{\hat{r}_k\}$，因此时钟恢复的性能是决策可靠性和 SNR 的函数。这就是为什么时钟恢复中使用的符号检测器 (symbol detector) 是维特比检测器 (Viterbi detector) [15]（决策延迟为 $dT$，例如 $d=4$），而不是多电平阈值检测器 (multi-level threshold detector) [27]。

然后，估计的时间误差 $\hat{\epsilon}_k$ 被送入环路滤波器以滤除噪声。下一个采样相位偏移 $\hat{\tau}_{k+1}$ 由二阶 PLL 按下式更新 [4]：

$$
\hat{\theta}_{k+1} = \hat{\theta}_k + \beta \hat{\epsilon}_k \tag{2.5}
$$

$$
\hat{\tau}_{k+1} = \hat{\tau}_k + \alpha \hat{\epsilon}_k + \hat{\theta}_{k+1} \tag{2.6}
$$

其中 $\hat{\theta}_k$ 是估计的频率误差 (frequency error) [27]，$\alpha$ 和 $\beta$ 是 PLL 参数 [4]，它们决定了环路带宽 (loop bandwidth) 和收敛速率 (convergence rate)。也就是说，PLL 参数值越大，环路带宽越宽，收敛速度越快，但进入 PLL 的噪声也越多。如果系统只有相位误差 (phase error)，接收端可以使用一阶 PLL (first-order PLL) 代替二阶 PLL，此时下一个采样相位偏移的更新式为 [4]：

$$
\hat{\tau}_{k+1} = \hat{\tau}_k + \alpha \hat{\epsilon}_k \tag{2.7}
$$

一般来说，时钟恢复工作在两种模式下：

1) **捕获模式 (acquisition mode)**：在同步过程的开始阶段工作，借助称为"前导码 (preamble)"[27] 的已知数据模式。由于时钟恢复确定地知道 preamble 的特征，因此能够知道正确的 $\hat{r}_k$ 值。在此模式下，PLL 使用 $\hat{r}_k = r_k$ 根据式 (2.4) 计算 $\hat{\epsilon}_k$（时钟恢复中使用的符号检测器在此阶段尚未启用），从而获得准确的结果。因此，此阶段的时钟恢复过程非常可靠。捕获模式的主要目的是获得隐藏在待采样模拟信号中的相位偏移和频率偏移 (frequency offset) 的初始估计值。

2) **跟踪模式 (tracking mode)**：在捕获模式之后工作。在此步骤中，用于根据式 (2.4) 计算 $\hat{\epsilon}_k$ 的 $\hat{r}_k$ 来自时钟恢复中使用的符号检测器（与使用真实的 $r_k$ 相比，其质量可能较差）。因此，跟踪模式的主要目的是修正和改进从捕获模式获得的相位偏移和频率偏移的初始值。

可以看出，在捕获模式下，PLL 确切地知道 preamble 是什么，因此 PLL 可以使用较大的 $\alpha$ 和 $\beta$ 值来实现快速的收敛速度。然而，当时钟恢复进入跟踪模式时，所使用的 $\alpha$ 和 $\beta$ 值应该减小，以降低进入 PLL 的噪声影响 [28]。因此，系统设计者在设计 $\alpha$ 和 $\beta$ 参数时，必须在环路带宽和收敛速率之间进行权衡。

## 2.3 PLL 参数设计

从系统仿真结果来看，设计 PLL 参数（$\alpha$ 和 $\beta$）的最佳方法是选择使接收端 BER 最小的 PLL 参数。然而，这种方法在实际中并不可行，因为找到最优的 PLL 参数需要很长的仿真时间。因此，通常使用线性化 PLL 模型来设计 PLL 参数 [4]。一个可行的准则 (criterion) 是选择 $\alpha$ 和 $\beta$，使得系统响应能够跟踪读回信号相位和频率的变化，且跟踪时间在 $C$ 个比特周期内。可以认为这一准则与收敛速率相对应，即 $C$ 值越小，时钟恢复的收敛速度越快。

### 2.3.1 一阶 PLL 的线性分析

一阶 PLL 只能处理相位误差（无法处理频率误差）。本节将介绍一阶 PLL 的参数设计方法，这对于学习高阶 PLL 将很有帮助。在本分析中，相位误差被建模为阶跃函数 (step function)，即当 $k \geq 0$ 时 $\tau_k = T$，当 $k < 0$ 时 $\tau_k = 0$。

考虑一阶 PLL 的下一个采样相位偏移 $\hat{\tau}_{k+1}$ 的更新方程：

$$
\hat{\tau}_{k+1} = \hat{\tau}_k + \alpha \hat{\epsilon}_{k-d} \tag{2.8}
$$

其中 $d$ 是时钟环路中的延迟量，单位为比特周期 $T$；$\hat{\epsilon}_k = \epsilon_k + v_k$ 是估计的时间误差；$\epsilon_k = \tau_k - \hat{\tau}_k$ 是残余时间误差 (residual timing error)；$v_k$ 是 TED 中的噪声。假设 $v_k$ 非常小（可以忽略），则根据式 (2.8) 的系统传递函数 (transfer function) [12] 可以通过 Z 变换 [12, 16] 求得：

$$
G(z) = \frac{\hat{\Gamma}(z)}{\Gamma(z)} = \frac{\alpha z^{-(d+1)}}{1 - z^{-1} + \alpha z^{-(d+1)}} \tag{2.9}
$$

其中 $\hat{\Gamma}(z)$ 和 $\Gamma(z)$ 分别是 $\hat{\tau}_k$ 和 $\tau_k$ 的 Z 变换。因此，误差 $\epsilon_k = \tau_k - \hat{\tau}_k$ 的传递函数可以写为：

$$
E(z) = \Gamma(z) - \hat{\Gamma}(z) = \frac{1 - z^{-1}}{1 - z^{-1} + \alpha z^{-(d+1)}} \Gamma(z) \tag{2.10}
$$

其中 $E(z)$ 是 $\epsilon_k$ 的 Z 变换。

选择 $\alpha$ 的一个准则是选择使系统稳定 (stable) 且收敛速率令人满意的 $\alpha$ 值，对于每个给定的环路延迟量 $d$。此方法可以同时使用式 (2.9) 或 (2.10)。首先，找出所有能使系统稳定的 $\alpha$ 值。根据式 (2.9) 和 (2.10)，当且仅当所有极点 (poles) 或分母的根 (roots) 位于单位圆 (unit circle) 内时，系统才稳定 [16]。求解可得使系统稳定的 $\alpha$ 范围为 [4]：

$$
0 < \alpha < 2 \sin\left(\frac{\pi}{4d + 2}\right) \tag{2.11}
$$

图 2.3 显示了对于每个 $d$ 值，能够保持系统稳定的最大 $\alpha$ 值。可以清楚地看到，$\alpha$ 的稳定范围随着 $d$ 的增大而迅速减小。尽管存在多个 $\alpha$ 值能使系统稳定，但只选择一个 $\alpha$ 值，使得系统响应能在 $C$ 个比特内跟踪阶跃响应 (step response)，且允许的误差容限为 $M_0\% \pm 5\%$。5% 的数值被用来放宽设计准则，以减少进入 PLL 的噪声影响。图 2.4(a) 显示了使系统稳定且在 $C$ 个比特内收敛的 $\alpha_C$ 值。可以观察到，收敛速度越快（即 $C$ 越小），$\alpha$ 值就越大。从图 2.4(a) 可以看出，对于给定的 $C$，只有某些 $\alpha$ 值对于特定的 $d$ 值是稳定的。例如，$\alpha_{100}$ 仅对于 $d$ 从 0 到 $30T$ 的值才能使系统稳定并在 100 个比特内收敛。图 2.4(b) 显示了使用 $\alpha_{100}$ 时，对于 $d = 0$ 到 $30T$ 的系统的阶跃响应，这与设定的设计准则相一致。

![](../source_final/images/chapter_2/35f38b2e8265d4e2add6309caeff109d7836cd36b99412fb5e4f7bed7e4cdeb2.jpg)  
图 2.3: 对于每个 $d$ 值，能保持系统稳定的最大 $\alpha$ 值

由于 $\alpha_{100}$ 被设计为使系统能在 100 个比特内以 $\pm 5\%$ 的容限跟踪阶跃响应，因此根据式 (2.10) 的误差响应 $E(z)$ 的绝对幅度应在经过 100 个比特后小于 0.05。如图 2.5 所示，对于 $d = 14T$，有两个 $\alpha$ 值（$\alpha = 0.0218$ 和 $\alpha = 0.055$）能使系统在 100 个比特内以 $\pm 5\%$ 的容限收敛。然而，在实践中，会选择较小的 $\alpha$ 值用于 PLL 电路，以使环路带宽较小，从而减少进入 PLL 的噪声影响。

![](../source_final/images/chapter_2/480511b783d2432ee742638a737b0d593aaea80528c40d64d62fc859c95cb82f.jpg)  
![](../source_final/images/chapter_2/705de11a8d3e98bc23622f590189cc9d7fba777dcd3d7218e2ca469129676e39.jpg)  
图 2.4: (a) 对于每个 $d$，使系统稳定并在 $C$ 个比特内收敛的 $\alpha_C$ 值；(b) 使用 $\alpha_{100}$ 时 $d$ 从 0 到 $30T$ 的系统响应

![](../source_final/images/chapter_2/5d5599ef50368d47bb00449eb1d464405ba41a6b7de66ef52578756b587d4055.jpg)  
![](../source_final/images/chapter_2/df5de1f89a4805ae4be636da7fa8226f739b6a63be81d46886ecefe7d9440c37.jpg)  
图 2.5: (a) 系统阶跃响应和 (b) 对于 $d = 14T$ 和不同 $\alpha$ 值的误差响应

### 2.3.2 二阶 PLL 的线性分析

当系统存在频率偏移 (frequency offset) 分量时，必须使用二阶 PLL 代替一阶 PLL。需要计算的参数是 $\alpha$ 和 $\beta$。对于二阶 PLL 的参数设计，首先假设系统中只有相位误差（即使用 2.3.1 节中描述的 $\alpha$ 设计方法），对于给定的 $d$ 和 $C$ 求出 $\alpha$ 值。然后，利用二阶 PLL 的线性分析，针对给定的频率偏移量求出 $\beta$ 值。在此分析中，频率误差被建模为 $\tau_k = k f_d$，其中 $f_d$ 是频率偏移量，单位为比特周期 $T$ 的百分比。

考虑二阶 PLL 的下一个采样相位偏移 $\hat{\tau}_{k+1}$ 的更新方程：

$$
\hat{\theta}_{k+1} = \hat{\theta}_k + \beta \hat{\epsilon}_{k-d} \tag{2.12}
$$

$$
\hat{\tau}_{k+1} = \hat{\tau}_k + \alpha \hat{\epsilon}_{k-d} + \hat{\theta}_{k+1} \tag{2.13}
$$

同样，假设 TED 中没有噪声（即 $\hat{\epsilon}_k = \epsilon_k = \tau_k - \hat{\tau}_k$），则根据式 (2.12) 和 (2.13) 的系统传递函数可以通过 Z 变换求得：

$$
G(z) = \frac{\hat{\Gamma}(z)}{\Gamma(z)} = \frac{(\alpha + \beta) z^{-(d+1)} - \alpha z^{-(d+2)}}{1 - 2z^{-1} + z^{-2} + (\alpha + \beta) z^{-(d+1)} - \alpha z^{-(d+2)}} \tag{2.14}
$$

误差传递函数为：

$$
E(z) = \Gamma(z) - \hat{\Gamma}(z) = \frac{1 - 2z^{-1} + z^{-2}}{1 - 2z^{-1} + z^{-2} + (\alpha + \beta) z^{-(d+1)} - \alpha z^{-(d+2)}} \Gamma(z) \tag{2.15}
$$

类似地，选择 $\beta$ 的准则是选择使系统稳定且收敛速率令人满意的 $\beta$ 值，对于每个给定的 $d$、$C$ 和 $\alpha_C$ 以及给定的频率偏移量。对于给定的 $d$、$C$ 和 $\alpha_C$，第一步是选择使系统稳定的 $\beta$ 值。根据式 (2.14) 和 (2.15)，当且仅当所有极点或分母的根位于单位圆内时，系统才稳定。尽管存在多个 $\beta$ 值能使系统稳定，但只选择一个使 $E(z)$ 在经过 $C$ 个比特后幅度最小的 $\beta$ 值，以减少进入 PLL 的噪声影响。图 2.6 显示了对于 $d = 14T$ 和 $\alpha_C$，经过 $C$ 个比特后 $E(z)$ 的最大幅度。可以观察到，此分析方法将得到相同的 $\beta$ 值，与频率偏移量的大小无关——$E(z)$ 的幅度仅随频率偏移量的不同而变化。

![](../source_final/images/chapter_2/328472c94ffc7cf11efecc66dfc9d32c7a2459835365e03b385def01fc4f5afc.jpg)  
图 2.6: 对于 $d = 14$ 和 $\alpha_C$，经过 $C$ 个比特后 $E(z)$ 的最大幅度

注意，上述 PLL 参数设计方法基于式 (2.4) 的 S 曲线 (S-curve) 斜率在原点处为 1 且 TED 内部无噪声的假设。因此，在将上述设计方法得到的 $\alpha$ 和 $\beta$ 值投入实际使用之前，必须先将 TED 的 S 曲线斜率在原点处归一化为 1。

### 2.3.3 S 曲线的求取

时钟函数 (timing function) 或 S 曲线 (S-curve) [22] 定义为 $\{\hat{\epsilon}_k\}$ 的均值 (mean)，假设来自符号检测器的 $\hat{r}_k$ 值全部正确，即对所有 $k$ 有 $\hat{r}_k = r_k$，且每个输入比特不相关 (uncorrelated) 且能量为 1 单位。因此：

$$
S_{\mathrm{TED}}(\epsilon) = E[\hat{\epsilon}_k \mid \epsilon, \hat{r}_k = r_k \text{ for } \forall k] \tag{2.16}
$$

其中 $\epsilon = \tau - \hat{\tau}$ 是时间误差。由于时钟函数的图形类似于字母 "S"（将图形旋转 90 度后），因此被称为"S 曲线 (S-curve)"，可用于衡量 TED 的性能。

此外，如果已知信道的冲激响应，S 曲线可以直接计算得到 [22]。例如，考虑图 2.2 中的 PR4（IV 类部分响应）信道模型，其中 $H(D) = 1 - D^2$。则此信道的 M&M TED 的 S 曲线为：

$$
\begin{aligned}
S_{\mathrm{TED}}(\epsilon) &= E[\hat{\epsilon}_k \mid \epsilon, \hat{r}_{k-1} = r_{k-1}, \hat{r}_k = r_k] \\
&= K_T E[r_{k-1} y_k - r_k y_{k-1}] \\
&= K_T E\left[(a_{k-1} - a_{k-3}) \sum_i a_i h(kT - iT - \epsilon) \right. \\
&\qquad \left. - (a_k - a_{k-2}) \sum_i a_i h(kT - T - iT - \epsilon) \right] \\
&= \frac{3T}{16} \left\{ -h(-T - \epsilon) + 2h(T - \epsilon) - h(3T - \epsilon) \right\} \tag{2.17}
\end{aligned}
$$

其中 $r_k = a_k - a_{k-2}$ 是第 $k$ 个无噪声信道输出，$y_k = \sum_i a_i h(kT - iT - \epsilon)$ 是第 $k$ 个采样器的输出，$h(t) = q(t) - q(t-2T)$ 是 PR4 脉冲信号。常数 $K_T = 3T/16$ 用于使式 (2.17) 中的 S 曲线斜率在原点处为 1。

![](../source_final/images/chapter_2/cfc825c0aa2a8eac9816b3d8b77827e20a7da88f825274c1b2bb209a0f1c3975.jpg)  
图 2.7: S 曲线求取的模型

对于未知信道冲激响应的情况，S 曲线仍然可以通过系统仿真来获得。具体方法是打开图 2.2 模型的时钟环路（即断开环路滤波器和 VCO），得到如图 2.7 所示的新模型。信号 $y(t)$ 在时刻 $kT$ 进行采样（即设 $\hat{\tau} = 0$），并用 $\epsilon$ 代替 $\tau$。然后计算每个 $\epsilon$ 的 $\{\hat{\epsilon}_k\}$ 的时间平均值 (time average)，得到一个 $S_{\mathrm{TED}}(\epsilon)$ 值。重复此过程，计算 $\epsilon$ 从 $-0.5T$ 到 $0.5T$ 范围内的 $S_{\mathrm{TED}}(\epsilon)$ 值，最后绘制 $\epsilon/T$ 与 $S_{\mathrm{TED}}(\epsilon)/T$ 之间的关系图，从而得到 S 曲线。

图 2.8 显示了使用常规时钟恢复的 PR4 信道的 M&M TED 的 S 曲线，在不同每比特 $E_b/N_0$ 水平下，单位为分贝 (dB)。PLL 使用来自无记忆三电平阈值检测器 (memoryless threshold detector) 的瞬时硬判决 (instantaneous hard decision)，阈值电平为 $\pm 1$，即：

$$
\hat{r}_k = \begin{cases} 2 & \text{if } y_k > 1 \\ -2 & \text{if } y_k < -1 \\ 0 & \text{else} \end{cases} \tag{2.18}
$$

![](../source_final/images/chapter_2/becf0eb31a3924c2e8c490d39172efd669620da9b7ba6a54ab9587e1585be60f.jpg)  
图 2.8: 使用常规时钟恢复的 PR4 信道的 M&M TED 的 S 曲线

"归一化时钟函数 (normalized timing function)" 的曲线来自式 (2.17)。从图 2.8 可以看出，S 曲线相对于 $\epsilon = 0$ 呈现奇对称 (odd symmetric)，这意味着由 PLL 调节的采样相位偏移最终将稳定在稳定点 (stable point) $\epsilon = 0$。可以观察到，当 $\epsilon/T$ 较小时，仿真得到的 S 曲线 $S_{\mathrm{TED}}(\epsilon)/T$ 与归一化时钟函数吻合较好。这是因为 $\hat{r}_k = r_k$ 对所有 $k$ 的假设在 $\epsilon/T$ 较大时不再成立。因此，这就解释了为什么 $S_{\mathrm{TED}}(\epsilon)/T$ 与归一化时钟函数在 $\epsilon/T$ 较大时不再吻合。

![](../source_final/images/chapter_2/35e782f0c80a62dc6ede26ab4318b4cb54b77a881ff810331df968e38d95ecaa.jpg)  
图 2.9: 循环滑动的示例特征

此外，S 曲线与 x 轴的交点，即 $S_{\mathrm{TED}}(\epsilon)/T = 0$ 时，称为"平衡点 (equilibrium point)"，这是 PLL 能够很好地跟踪时间偏移的工作点。然而，在实际中，平衡点有多个位置：$\epsilon = 0, \pm T, \pm 2T, \ldots, \pm nT$，其中 $n$ 是整数。系统中的噪声和干扰可能会在采样相位偏移的调整过程中引起较大的误差，导致 PLL 的工作状态从一个平衡点转移到另一个平衡点。这种现象称为"循环滑动 (cycle slip)"，将在检测器处引起大量错误。图 2.9 显示了循环滑动的示例特征。从图中可以看出，在数据包 (data packet) 的开始阶段，PLL 能够很好地跟踪 $\tau$ 的变化。但当循环滑动发生时，PLL 将逐渐失去对 $\tau$ 的跟踪，直到 PLL 进入另一个新的平衡点。因此，可以说循环滑动是导致 PLL 在数据包结束时 $\hat{\tau}$ 与 $\tau$ 相差约 $T$ 的原因。可以清楚地看到，循环滑动对于时钟恢复系统来说是非常危险的。因此，研究人员提出了各种管理循环滑动的方法，感兴趣的读者可以参阅 [29, 30, 31, 32, 33] 了解详细信息。

## 2.4 常规时钟恢复的性能

考虑图 2.2 所示的 PR4 信道模型，可以看出时钟恢复和符号检测器是独立工作的。因此，未编码系统 (uncoded system) 的整体性能取决于时钟恢复系统的质量。

本节将展示使用常规时钟恢复系统的性能，该系统采用多电平无记忆阈值检测器 (multi-level memoryless threshold detector)，其输出数据按照式 (2.18) 进行。对于数据检测过程，数据序列 $\{y_k\}$ 将被送入具有 60T 决策延迟的维特比检测器，以找出最可能的输入数据序列。此外，每个 BER 值都是通过使用大量数据组进行计算，直到总错误数达到 1000 个比特。

对于没有频率偏移的系统，接收端可以使用一阶 PLL，这可以通过设置 $\tau_0 = 0$ 来实现，从而不需要使用 preamble 数据。每组数据包含 4096 个比特。图 2.10 比较了均方根 (RMS: root mean square) 时间误差 $\sigma_\epsilon = \sqrt{E[(\tau_k - \hat{\tau}_k)^2]}$ 和 BER 的性能。使用的 PLL 参数 ($\alpha$) 按照 2.3.1 节所述设计为能在 100 个比特内跟踪相位变化（即 $\alpha_{100} = 0.0295$）。可以看出，当时间抖动严重程度 $\sigma_w/T$ 越大时，系统性能就越差（无论是 $\sigma_\epsilon/T$ 还是 BER 方面）。此外，如果系统的 $\sigma_\epsilon/T$ 较小，系统的 BER 也较低。因此，参数 $\sigma_\epsilon/T$ 和 BER 可以作为比较各种时钟恢复系统性能的准则。

![](../source_final/images/chapter_2/c199bc52975f3a0ee9d368a019df36f542cbf7af8576a1274a4b8cc944e3a761.jpg)  
![](../source_final/images/chapter_2/d16e0e496e1be468915f6eeafb11808538fd1fc5fad8e32af7871379ba335b33.jpg)  
图 2.10: (a) 对于理想 PR4 信道，在不同 $\sigma_w/T$ 值下 RMS 时间误差 $\sigma_\epsilon/T$ 和 (b) BER 性能（无频率偏移）

类似地，对于存在频率偏移的系统，接收端必须使用二阶 PLL 来处理此频率偏移。考虑系统工作在中等条件 (moderate condition) 下，即 $\sigma_w/T = 0.5\%$ 和频率偏移 0.2%。同样，使用的 $\alpha$ 和 $\beta$ 参数按照 2.3.2 节所述设计，使系统能在 $C$ 个比特内跟踪相位和频率变化。对于 $d = 0$，设计 $\alpha$ 值在 $C = 50, 100, 256$ 时分别为 0.012, 0.029 和 0.058，而设计 $\beta$ 值分别为 0.00015, 0.000885 和 0.00325。此外，只考虑 PLL 在捕获模式和跟踪模式使用相同的 $\alpha$ 和 $\beta$ 值的情况。每组数据由 $C$ 个比特的 preamble 和 4096 个比特的信息位组成。图 2.11 显示了使用为每个 $C$ 设计的 PLL 参数时，常规时钟恢复的性能。标记为"Perfect timing"的曲线代表使用 $\hat{\tau}_k = \tau_k$ 对 $y(t)$ 进行采样的常规时钟恢复。可以看出，当系统需要快速收敛时，即使用为较小 $C$ 设计的 PLL 参数时，常规时钟恢复无法很好地工作。

![](../source_final/images/chapter_2/9377543e1cc72e21412f7549be57464f3e4e77ef0af834e5f570886fb51a1b2c.jpg)  
图 2.11: 理想 PR4 信道在 $\sigma_w/T = 0.5\%$ 和频率偏移 0.2% 时常规时钟恢复的 BER 性能

## 2.5 数字时钟恢复

本章所述的常规时钟恢复具有混合 (hybrid) 特性，即既有处理模拟信号的部分，也有处理数字信号的部分。从图 2.2 来看，VCO 通常是模拟电路，其工作特性复杂且价格昂贵。本节将介绍全数字的时钟恢复系统，已在某些读通道芯片 (read-channel chip) 中使用。

数字时钟恢复使用与接收到的模拟信号异步 (asynchronous) 的采样速率 (sampling rate)，只需采样频率 (sampling frequency) 高于模拟信号的奈奎斯特频率5 (Nyquist frequency) [2, 10]。换句话说，采样器使用过采样率 (oversampling rate) [34, 35]。由于采样器得到的采样数据与发送端的数据比特不同步，因此需要通过一种称为"插值技术 (interpolation technique)" 的数字方法来"调整时间 (timing adjustment)"，以获得与发送端数据比特相对应的采样数据。使用此技术的时钟恢复系统通常称为"插值时钟恢复 (interpolated timing recovery)"，其结构如图 2.12 所示。PLL 中的所有组件都是全数字的，这有助于降低时钟恢复系统的构建成本。实验发现，如果选择合适的插值滤波器 (interpolation filter)，插值时钟恢复的性能与常规时钟恢复相当。感兴趣的读者可以在 [34, 35, 36, 37] 中找到有关插值时钟恢复的更多详细信息。

![](../source_final/images/chapter_2/a773b562aa981ae89ea19af31182ae434e85fc7546c481a83e7c25f5a7a34b31.jpg)  
图 2.12: 插值时钟恢复的结构

## 2.6 时钟恢复系统的未来趋势

从图 2.10 和 2.11 所示的结果可以总结出，当系统存在较大的时间误差或需要快速收敛时，常规时钟恢复的性能不佳。提高常规时钟恢复性能的最简单方法是将时钟环路中使用的符号检测器从硬阈值检测器 (hard threshold detector) 更换为软阈值检测器 (soft threshold detector) [33]，或者使用决策延迟 $dT$ 较短的维特比检测器 [27]。然而，这些方法只能带来微小的性能提升。

因此，非常需要一种比常规时钟恢复更高效的新型时钟恢复系统。文献 [30, 38] 提出了一种称为"逐幸存路径时钟恢复 (per-survivor timing recovery)" 的新型时钟恢复形式，用于未编码系统，其性能优于常规时钟恢复，如图 2.13 所示。其中 y 轴表示使系统 BER 达到 $10^{-4}$ 所需的 $E_b/N_0$ 值（以 dB 为单位），换句话说，y 轴表示发送端传输数据所需的功率，以使接收端的 BER 达到 $10^{-4}$。从图 2.13 可以看出，"Genie-aided detector" 曲线表示 PLL 使用 $\hat{r}_k = r_k$（见图 2.2）来调整下一个采样相位偏移的常规时钟恢复；而 "tentative decision $(d=4)$" 表示时钟环路中使用的符号检测器是决策延迟 $d = 4T$ 的维特比检测器。实验结果表明，逐幸存路径时钟恢复的性能优于常规时钟恢复（在达到相同 BER = $10^{-4}$ 的情况下，使用的 $E_b/N_0$ 更小），特别是在时间抖动严重程度 $\sigma_w/T$ 较高时更加明显。

![](../source_final/images/chapter_2/98c416d5d0b66eed722e403bf9599dafd8e18fcc2c37c88363be9f5d942a32fc.jpg)  
图 2.13: 理想 PR4 信道下各种时钟恢复的性能

为了考察各种时钟恢复的收敛速率，使用图 2.2 所示的模型，设 $\sigma_w/T = 0\%$，$\hat{\tau}_0 = 0.5T$，频率偏移为 0%，PLL 参数设计为 $C = 50$，即 $\alpha_{50}$ 对于 $d = 0$ 和 $4T$ 分别为 0.058 和 0.049。图 2.14 比较了各种时钟恢复的收敛速率，平均取自 10000 组数据。系统在时刻 $k$ 被认为成功收敛的条件是：对于所有 $i \geq k$，$\hat{\tau}_i$ 在 $\pm 10\%$ 的容限内等于 0 或 $T$。从图中可以看出，使用"Genie-aided detector" 的系统在 50 个比特内收敛，这与使用的 $\alpha_{50}$ 相一致，因为"Genie-aided detector" 的 PLL 使用正确的值（即 $\hat{r}_k = r_k$）来调整下一个采样相位偏移。此外还发现，逐幸存路径时钟恢复比常规时钟恢复具有更快的收敛速度。

![](../source_final/images/chapter_2/10ab17bb27b9d4852174709bd4769deceee06b102fbdf8d7acd28df8ac67de5b.jpg)  
图 2.14: 在 $E_b/N_0 = 10$ dB 下使用 $\alpha_{50}$ 时各种时钟恢复的收敛速率

与纠错码 (ECC: error-correction code) 结合使用的结果称为"迭代逐幸存路径时钟恢复 (per-survivor iterative timing recovery)" [30, 39, 40]，用于编码系统 (coded system)。实验结果表明，迭代逐幸存路径时钟恢复的性能远优于常规时钟恢复，特别是当系统存在较大的时间误差或需要快速收敛时。感兴趣的读者可以在 [30, 39, 40] 中找到更多详细信息，这些文档可以从 http://home.npru.ac.th/~t3058 下载。

## 2.7 本章小结

本章阐述了常规时钟恢复的工作原理，以及利用线性化 PLL 模型设计 PLL 参数的方法。实验结果表明，根据设定准则设计得到的 PLL 参数值在各种频率偏移量下都是一致的。在将本章设计方法得到的 PLL 参数投入实际使用前，用户必须先将 TED 的 S 曲线斜率在原点处归一化为 1。此外，实验结果表明，当系统存在较大的时间误差或需要快速收敛时，常规时钟恢复的性能不佳。

然而，在实际应用中，常规时钟恢复仍然被广泛应用于几乎所有场合，因为它电路简单、易于构建，并且只要选择合适的 PLL 参数、系统时间误差不大、且系统不需要快速收敛，它就能充分胜任工作。

## 2.8 课后习题

1. 请简要说明锁相环 (PLL: phase-locked loop) 的工作原理。
2. 请说明一阶 PLL 参数的设计步骤。
3. 请说明二阶 PLL 参数的设计步骤。
4. 请说明 S 曲线的特性和用途。
5. 请计算 M&M TED 的 S 曲线方程，并绘制以下信道 $H(D)$ 的时钟函数图：

   5.1) $H(D) = 1 - D$
   5.2) $H(D) = 1 + D$
   5.3) $H(D) = 1 + 2D + D^2$
   5.4) $H(D) = 1 + D - D^2 - D^3$
   5.5) $H(D) = 1 + 3D + 3D^2 + D^3$

6. 请简要比较常规时钟恢复和插值时钟恢复的工作原理。
