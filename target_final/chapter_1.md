# 第 1 章

# 引言

本章将概述硬盘驱动器 (hard disk drive) 数据存储系统的整体架构，为读者理解数字数据存储系统相关的基础知识做好准备，包括硬盘驱动器中数据写入和读取过程的工作原理，为后续章节中关于硬盘驱动器信号处理系统分析和接收电路设计的讨论奠定基础。

## 1.1 数字磁记录基础

磁记录 (magnetic recording) 是指将数据比特以介质中磁化状态 (magnetization) 变化的形式进行存储。磁记录可分为两种类型 [1]：模拟 (analog) 记录和数字 (digital) 记录。本书仅讨论用于硬盘驱动器的数字磁记录。数字磁记录利用某些材料的磁特性——当处于饱和 (saturated) 状态时，介质中的磁化方向指向某一方向或相反方向。这种记录方式适用于具有两种状态的数字数据存储，即比特 "1" 和比特 "0"，也称为"二进制数据 (binary data)"。因此，这些材料被用作存储二进制数据的记录介质。由于当今大多数数据都采用数字形式，如计算机数据和通过互联网传输的数据等。此外，模拟数据也可以通过脉冲编码调制 (PCM: pulse code modulation) [2] 过程转换为数字形式，以便于数据存储。因此，数字磁记录非常适合当前的数据存储需求。

![](../source_final/images/chapter_1/9d85eef55c63d3f8bb645c3ef5afff9b6819de6c143dc9e9f7189e7b6c4aa371.jpg)  
图 1.1: 磁记录的基本原理

当前，各种电子设备（如计算机、移动电话、便携式音乐播放器和数码相机等）对数据存储容量的需求日益增长。数字磁记录技术被认为是各种应用 (application) 中数据存储的主要方法，包括软盘 (magnetic floppy disk)、磁带 (magnetic tape)、硬盘驱动器、光盘 (CD: compact disc) 和数字多功能光盘 (DVD: digital versatile disc) 等。然而，所有这些应用都基于相同的核心工作原理，涉及读头 (read head)、写头 (write head) 和磁记录介质 (magnetic media)，如图 1.1 所示。其中，感应式 (inductive) 读写头由矫顽力 (coercivity) 低、磁导率 (permeability) 高的马蹄形磁性材料制成 [1, 3]，周围绕有线圈，而记录介质则由矫顽力高的磁性材料制成。

本书将讨论两种数据记录技术：水平记录 (longitudinal recording) 和垂直记录 (perpendicular recording)。水平记录技术是硬盘驱动器从过去沿用至今的数据记录技术，即记录介质的磁化方向与磁盘 (magnetic disk) 平面平行，如图 1.1 所示。而垂直记录技术已开始在当今的硬盘驱动器中使用，记录介质的磁化方向垂直于磁盘平面。目前，关于垂直记录技术的研究正在快速发展，因为水平记录技术正接近"超顺磁极限 (superparamagnetic limit)" [1, 3, 4, 10]，使得硬盘驱动器的数据容量无法超过 1 TB (terabyte)。此外，与水平记录技术相比，垂直记录技术可以将硬盘驱动器的数据容量提升数十倍 [3, 5]。

## 1.2 硬盘驱动器数字数据存储系统模型

硬盘驱动器中的数字数据存储系统 (digital data storage system) 可以用图 1.2 所示的通用框图来建模。信息比特 (message bits) 首先由"纠错码编码器 (error-correction code (ECC) encoder)" 进行编码。RS 码 (Reed Solomon code) [7, 8] 是目前硬盘驱动器中常用的纠错码。编码后的数据再由"调制编码器 (modulation encoder)" 进行第二次编码，以调整数据特性使其适合硬盘驱动器信道，例如使数据序列 (data sequence) 具有所需的格式或消除数据中的直流 (d.c.) 分量等。调制编码器中常用的码是 RLL 码 (run-length limited code) [9]。调制编码器输出的数据被认为是即将写入记录介质的数据，称为"记录比特 (recorded bit)"。

![](../source_final/images/chapter_1/2dbfd582f9f15bde683b51f708eaa605ad5450d270cdf99b6cac1b6bddb02d52.jpg)  
图 1.2: 硬盘驱动器数字数据存储系统的通用模型 [6]

随后，记录比特被送入"调制器 (modulator)"将数据比特转换为写电流波形 (write current waveform)。然后写电流波形被馈送到写头，将数据写入记录介质。

在数据读取过程中，读头从记录介质读取数据。当读头移动到磁化状态发生变化（见图 1.1）的区域时，将产生电压波形信号，称为"读回信号 (read-back signal)"。然后读回信号被送入读通道 (read channel) 进行处理。读通道由以下组件组成：低通滤波器 (LPF: low-pass filter)、采样器 (sampler 或 analog-to-digital converter)、均衡器 (equalizer) 和检测器 (detector) 等。最终输出数据通过调制解码器 (modulation decoder) 和纠错码解码器 (ECC decoder) 进行解码，以获得发送端信息比特的估计值。

## 1.3 写入过程

在数据写入过程 [10] 中，数据比特被转换为矩形电流波形 (rectangular current waveform)，称为"写电流 (write current)"（见图 1.1），由调制器 (modulator) [1, 4] 完成。然后写电流被馈送到写头 (write head) 的线圈，在记录介质与写头之间的间隙 (gap) 区域产生磁写场 (magnetic write field)。通常，磁写场的强度必须大于记录介质的矫顽力，才能使得该区域记录介质的磁化方向与所施加的磁写场方向一致。此外，记录介质的磁化状态转变 (magnetization transition) 可以通过改变写入磁场的方向（即写电流的方向）来实现，以对应于写入比特 0 和比特 1。

在实际应用中，硬盘驱动器的数字数据存储系统采用"二进制记录 (binary recording)"，即记录介质中的磁化方向只有两种。换言之，系统只能记录两个电平（或两个值），这与可记录多个电平的 DVD 不同。这是因为写入过程本身存在相当大的非线性。如果向硬盘驱动器记录介质写入两个以上的电平，非线性效应将更加严重，从而导致系统整体性能大幅下降 [4]。

## 1.4 读取过程

在数据读取过程 [10] 中，读头检测磁通量 (magnetic flux) 在磁化状态转变位置的变化，根据法拉第定律 (Faraday's law) 在线圈中感应产生电压脉冲信号。对于孤立转变 (isolated transition)，读头输出称为"转变脉冲 (transition pulse)"的电压脉冲信号 $g(t)$ 或 $-g(t)$，具体取决于记录介质中磁化的方向（见图 1.1）。

对于水平记录系统，转变脉冲（或称洛伦兹脉冲）可以表示为如下数学方程 [4]：

$$
g(t) = \frac{1}{1 + \left( \frac{2t}{\mathrm{PW}_{50}} \right)^2} \tag{1.1}
$$

其中 $\mathrm{PW}_{50}$ 是脉冲信号 $g(t)$ 在脉冲高度为最大高度一半处的宽度。对于垂直记录，转变脉冲的方程如下 [11]：

$$
g(t) = \mathrm{erf}\left( \frac{2t \sqrt{\ln 2}}{PW_{50}} \right) \tag{1.2}
$$

其中 $\ln(\cdot)$ 是自然对数 (natural logarithm)，$\mathrm{erf}(\cdot)$ 是误差函数 (error function)，定义为 $\mathrm{erf}(x) = \frac{2}{\sqrt{\pi}} \int_0^x e^{-t^2} dt$，$\mathrm{PW}_{50}$ 是脉冲 $g'(t)$（即 $g(t)$ 的导数）在半高处的宽度。

在硬盘驱动器记录系统中，归一化记录密度 (ND: normalized recording density) 或记录密度 [4] 定义为：

$$
\mathrm{ND} = \frac{\mathrm{PW}_{50}}{T} \tag{1.3}
$$

其中 $T$ 是一个数据比特的时间周期，也称为"比特单元 (bit cell)"，表示 $\mathrm{PW}_{50}$ 区域可以存储多少比特。因此，如果 $T$ 固定，当 $\mathrm{PW}_{50}$ 或 ND 增大时，意味着硬盘驱动器可以存储更多数据。图 1.3 显示了在不同 ND 水平下，水平记录和垂直记录的转变响应。可以看出，两种系统的转变脉冲信号都覆盖了多个比特单元的时间范围，特别是当 ND 增大时更为明显。换句话说，当 ND 增大时，读回信号中的码间干扰 (ISI: intersymbol interference) 会更加严重。

在读头移动到连续的转变位置相邻的区域时（间距为 $T$），得到的净脉冲信号称为"双比特脉冲 (dibit pulse)"或"双比特响应 (dibit response)" [4]，其值为：

$$
m(t) = g(t) - g(t - T) \tag{1.4}
$$

如图 1.4 所示。

![](../source_final/images/chapter_1/6d4d1f8f483a0bf4ec0c0c300f0e56c80b891438dc50d989bded6f9873dfab93.jpg)  
![](../source_final/images/chapter_1/28b1556b28612d4f220b0ee3a4a5c4bd83259797054a0299703033966619ae7b.jpg)  
图 1.3: 转变脉冲信号：(a) 水平记录 (b) 垂直记录

![](../source_final/images/chapter_1/e4b09f159a226034d8c8cbc20a86944707945280b47f44dfd1e683034b80bf85.jpg)  
![](../source_final/images/chapter_1/fe2f203f620115d8b88b8f9b270e748aa5d41c61e2977d7f6ead33378b63bbd2.jpg)  
图 1.4: 双比特响应：(a) 水平记录 (b) 垂直记录

对 $m(t)$ 应用连续时间傅里叶变换 (continuous-time Fourier transform) [12]，可以得到水平记录系统的 $m(t)$ 的频率响应 (frequency response)：

$$
M(\Omega) = \exp\{ -\pi |\Omega| \mathrm{ND} \} (1 - \exp\{ -j 2\pi \Omega \}) \tag{1.5}
$$

其中 $\exp\{\cdot\}$ 是指数函数 (exponential function)。而垂直记录系统的 $m(t)$ 的频率响应为：

$$
M(\Omega) = \frac{T}{j\pi\Omega} \exp\left\{ -\frac{\pi^2 \Omega^2 \mathrm{ND}^2}{\ln(16)} \right\} (1 - \exp\{ -j 2\pi\Omega \}) \tag{1.6}
$$

其中 $\Omega = fT$ 是归一化频率 (normalized frequency)，$f$ 是以赫兹 (Hertz) 为单位的频率，$|x|$ 是 $x$ 的绝对值 (absolute value)，$j = \sqrt{-1}$ 是虚数单位 (imaginary unit)。图 1.5 显示了双比特脉冲的频率响应。可以看出，当 ND 增大时，两种双比特脉冲的频率响应形状都被压缩到低频区域。此外，水平记录信道在频率 $f = 0$ 处具有频谱零点 (spectral null)，意味着没有直流分量，而垂直记录信道则具有直流分量。

![](../source_final/images/chapter_1/425d0e7a2cd17509f57f6f1a2536b932b749f701b397b1b6011ca8b17bfb9127.jpg)  
![](../source_final/images/chapter_1/19742f2904ecfdb0fa3d4bbfe5aad0a224d2a41ab7f05427eb7c5348671a9bf7.jpg)  
图 1.5: 双比特脉冲的频率响应：(a) 水平记录 (b) 垂直记录

注意，本书使用 SCILAB [14] 程序绘制各种信号图形以及系统仿真结果。读者应尝试绘制本书中的各种图形，以帮助更好地理解课程内容。

## 1.5 磁记录信道模型

通常，磁记录系统的信道可以建模为两种类型：虚拟信道模型 (realistic channel model) 和理想信道模型 (ideal channel model)。虚拟信道模型 [10] 的工作特性接近实际系统，因为它包含了硬盘驱动器"读通道体系结构 (read-channel architecture)" [8, 10] 中的所有重要组件。而理想信道模型常用于研究和分析硬盘驱动器信号处理系统的基本工作原理，因为该模型不复杂且易于理解。

### 1.5.1 虚拟信道模型

图 1.2 中的部分 A 可以用图 1.6 所示的数学模型表示。二进制输入数据序列 $a_k \in \{0, 1\}$ 的比特周期 (bit period) 为 $T$，被送入理想微分器 (ideal differentiator) $1 - D$，其中 $D$ 是 $T$ 单位延迟算子，得到转变数据序列 $b_k \in \{-1, 0, 1\}$。$b_k = \pm 1$ 表示正转变 (positive transition) 或负转变 (negative transition)，$b_k = 0$ 表示无转变。转变数据序列 $b_k$ 被送入由转变响应 $g(t)$ 表示的信道，并受到噪声 $n(t)$ 的干扰。读回信号 $p(t)$ 经过低通滤波器 (LPF) 滤除带外噪声 (out-of-band noise)，然后在由时钟恢复 (timing recovery) 系统控制的时间点进行采样。采样器的输出数据被送入均衡器和符号检测器 (symbol detector)，以找出最可能的输入数据序列，即估计 $\hat{a}_k$。

![](../source_final/images/chapter_1/ce7ae17b88d6a823c2925f980f14dbbc06970e6bd05537ddd63b39c3aba86a6c.jpg)  
图 1.6: 虚拟信道模型

磁记录系统中常用的符号检测器是"维特比检测器 (Viterbi detector)" [15]。然而，维特比检测器的复杂度随信道记忆长度 (channel memory) 呈指数增长。因此，均衡器是必需的，用于将整个系统的总响应调整为目标响应，称为"目标响应 (target response)" $H(D)$ [4]，从而降低维特比检测器的复杂度（详见第 3 章）。

### 1.5.2 理想信道模型

假设系统具有完美均衡 (perfect equalization)，图 1.6 的模型可以简化为理想信道模型，如图 1.7 所示。二进制输入数据序列 $a_k$ 的比特周期为 $T$，与理想奈奎斯特脉冲 (ideal Nyquist pulse) $q(t) = \sin(\pi t/T)/(\pi t/T)$ [16] 进行调制，并受到噪声 $n(t)$ 干扰。接收端接收到的信号 $p(t)$ 经过低通滤波器滤除带外噪声，然后在由时钟恢复系统控制的时间点进行采样。采样器的输出数据随后被送入符号检测器，以找出最可能的输入数据序列。

水平记录中认可的部分响应目标，即"PR 目标 (partial response)" [17]，其方程形式如下 [4]：

$$
H(D) = (1 - D)(1 + D)^n \tag{1.7}
$$

![](../source_final/images/chapter_1/c67c49b0e1a6ee4cfbbfa16174fb2e124cbef4db7df8e087464da04aa9f95a40.jpg)  
图 1.7: 理想信道模型

垂直记录系统的 PR 目标为：

$$
H(D) = (1 + D)^n \tag{1.8}
$$

其中 $n$ 是正整数。从式 (1.8) 可以看出，垂直记录系统没有 $(1 - D)$ 项，这是因为垂直记录信道具有直流分量（见图 1.5）。图 1.8 比较了各种目标的频率响应。方括号 $[\dots]$ 中的数字表示目标的每个抽头系数。例如，"PR4 [10 -1]" 表示 PR4（IV 类部分响应）目标，其在 D 域 [10] 的传递函数为 $H(D) = 1 - D^2$；"EEPR2 [1 4 6 4 1]" 表示 EEPR2 目标，其 D 域传递函数为 $H(D) = 1 + 4D + 6D^2 + 4D^3 + D^4$ 等。

![](../source_final/images/chapter_1/93ebd2adb79dcfe61ee5ceafbcafaa8d58f8e3bba6d643b698640f780101960d.jpg)  
![](../source_final/images/chapter_1/309e2842347ef8bbc0595d6ad198d2486e75fce5b8abacbcb0b646fd7aea21d0.jpg)  
图 1.8: 各种目标在 (a) 水平记录和 (b) 垂直记录信道中的频率响应

从图 1.8 可以看出，当信道 ND 增大时，所使用的目标应具有更多的抽头（$n$ 更大），以使目标响应尽可能接近信道响应，从而使维特比检测器更有效地工作（详见第 3 章）。此外，从式 (1.7) 和 (1.8) 可以看出，所有 PR 目标的系数都是整数。然而，如果使用系数为实数的目标，称为"广义部分响应 (GPR: generalized partial response) 目标"，系统整体性能将优于使用 PR 目标 [18, 19]。

## 1.6 本章小结

本章介绍了数字磁记录的基础知识，包括硬盘驱动器中数据写入和读取过程的工作原理。此外，还阐述了硬盘驱动器的工作模型，包括虚拟信道模型和理想信道模型。这两种模型将在后续章节中用于系统仿真。

由于硬盘驱动器信号处理系统的分析涉及大量与信号处理和数字通信相关的数学基础知识，读者应在学习本书之前回顾这些知识。与硬盘驱动器信号处理系统分析相关的各类数学基础知识，可以参考《信号处理用于数字数据存储 第 1 卷：读写通道基础》[10] 一书。

## 1.7 课后习题

1. 请解释磁记录的基本工作原理。
2. 请解释水平记录与垂直记录系统之间的区别。
3. 请解释硬盘驱动器中数据写入和读取的基本过程。
4. 请解释虚拟信道模型的工作原理。
5. 请解释理想信道模型的工作原理。
6. 请举出至少 4 个用于水平记录系统的 PR 目标示例。
7. 请举出至少 4 个用于垂直记录系统的 PR 目标示例。
