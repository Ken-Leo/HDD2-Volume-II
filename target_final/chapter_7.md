# 第7章 PDNP检测器

本章将介绍PDNP（pattern-dependent noise-predictive，模式依赖噪声预测）检测器[54]的来源、工作原理和优势。PDNP检测器专门设计用于处理介质抖动噪声（media jitter noise），这种噪声在高数据容量的磁记录系统中十分常见。本章将对此进行详细说明，并展示PDNP检测器与PRML检测器之间的性能比较结果。

## 7.1 引言

如第4章所述，PRML技术是部分响应均衡器（PR equalizer）与Viterbi检测器（Viterbi detector）的联合应用技术，广泛应用于硬盘驱动器的信号处理系统中[27]。PRML技术分两个步骤工作：第一步，将接收到的信号波形调整为所需目标的形状；第二步，利用根据指定目标构建的Viterbi检测器对数据进行译码。

Viterbi检测器仅在待译码信号中隐含的噪声分量具有加性高斯白噪声特性时，才被视为"最优序列检测器（optimal sequence detector）"[15]。然而，在实际应用中，PR均衡器的使用会导致Viterbi检测器输入端的噪声分量呈现有色噪声（colored noise）特性，尤其是在硬盘驱动器数据容量较高（ND较高）的情况下，此时Viterbi检测器不再是最优序列检测器。因此，NPML（noise-predictive maximum-likelihood，噪声预测最大似然）检测器[51, 52]被引入以提高系统性能。NPML检测器具有将噪声白化的处理过程，然后再将结果送入Viterbi检测器进行译码。第6章表明，NPML检测器的性能优于PRML检测器，尤其是在硬盘驱动器数据容量较高的情况下。

此外，在高ND条件下，Viterbi检测器输入端的噪声分量还呈现依赖于"数据模式（data pattern）"的特性。例如，介质抖动噪声可视为"模式依赖噪声（pattern-dependent noise）"，即介质抖动噪声的强度取决于写入介质的的数据模式。已有多种技术被提出[54, 55]，用于在Viterbi检测器译码之前将此类噪声白化。以下各节将解释PDNP检测器[54]的工作原理及其复杂度降低技术。

## 7.2 噪声的模式依赖性

考虑图7.1所示的信道模型。设 $C ( D ) = ( 1 - D ) G ( D )$ 为D域的信道响应，$H(D)$ 为D域的目标响应，$Q(D)$ 为低通滤波器和均衡器在D域中的联合响应。为便于说明，本节采用迫零均衡器（zero-forcing equalizer）[2, 16]，即 $Q ( D ) = H ( D ) / C ( D )$。在实际中，由有限冲激响应（FIR）线性滤波器构建的目标和均衡器，其传递函数将与理论上的 $H ( D )$ 和 $Q ( D )$ 有所不同。因此，设 $H ^ { \prime } ( D )$ 和 $Q ^ { \prime } ( D ) = H ^ { \prime } ( D ) / C ( D )$ 分别为目标和均衡器的实际传递函数，其中 $H ^ { \prime } ( D ) \neq H ( D )$ 且 $Q ^ { \prime } ( D ) \neq Q ( D )$。则均衡器的输出数据可用数学方程表示为

![](../source_final/images/chapter_7/ff779f285af386750b0ac11d221b5e5dfbcbfa24778a7b7657420b1ef84bb5bd.jpg)  
图7.1: 信道模型

$$
\begin{array} { r c l } { { Y ( D ) } } & { { = } } & { { A ( D ) C ( D ) Q ^ { \prime } ( D ) + N ( D ) Q ^ { \prime } ( D ) } } \\ { { } } & { { = } } & { { A ( D ) H ^ { \prime } ( D ) + N ( D ) Q ^ { \prime } ( D ) } } \\ { { } } & { { = } } & { { A ( D ) H ^ { \prime } ( D ) + N ( D ) Q ^ { \prime } ( D ) + \left[ A ( D ) H ( D ) - A ( D ) H ( D ) \right] } } \\ { { } } & { { = } } & { { A ( D ) H ( D ) + \underbrace { A ( D ) [ H ^ { \prime } ( D ) - H ( D ) ] + N ( D ) Q ^ { \prime } ( D ) } _ { W ( D ) } } } \end{array}\tag{7.1}
$$

其中 $N ( D )$ 是加性高斯白噪声（AWGN），$W ( D )$ 是序列检测器输入端的总噪声。由式（7.1）可见，噪声 $W ( D )$ 具有数据依赖（data-dependent）特性，因为其中包含 $A(D)$ 项。

介质抖动噪声是磁化过程中"随机跳变位置偏移（random transition shift）"的结果。其概率密度函数为高斯分布，均值为零，方差为 $| b _ { k } | \sigma _ { j } ^ { 2 }$（即 $\Delta t _ { k } \sim \mathcal N ( 0 , | b _ { k } | \sigma _ { j } ^ { 2 } )$），且被限制不超过 $T / 2$。其中 $\sigma _ { j }$ 定义为比特单元 $T$ 的百分比，$\left| b _ { k } \right|$ 是 $b _ { k }$ 的绝对值。由于跳变位置由输入数据比特 $\{ a _ { k } \}$ 决定，因此如图7.2所示，介质抖动噪声的强度取决于 $\{ a _ { k } \}$ 的数据模式。

![](../source_final/images/chapter_7/cc3623b08ad6a649844ed16e160d3b6b1c3b7c6aa3e55a4836d9c1bef5fca429.jpg)  
图7.2: 针对目标EEPR2 $[ 1 ~ 4 ~ 6 ~ 4 ~ 1 ]$ 的垂直记录系统，在 ${ \mathrm { N D } } = 2 . 5 , { \mathrm { S N R } } = 3 0$ dB 且 $\sigma _ { j } / T = 1 0 \%$ 条件下，均衡器输出端的数据依赖噪声功率

显示了针对目标EEPR2（$H ( D ) = 1 + 4 D + 6 D ^ { 2 } + 4 D ^ { 3 } + D ^ { 4 }$）设计的21抽头（tap）均衡器输出端的数据依赖噪声功率（noise power），用于ND = 2.5、SNR = 30 dB 且 $\sigma _ { j } / T = 1 0 \%$ 的垂直记录（perpendicular recording）系统。可以清楚地看到，当数据序列发生多次跳变时（如"010"和"101"等数据模式），噪声功率较高。

## 7.3 PDNP算法

考虑Viterbi检测器[15]，其分支度量（branch metric）由下式计算

$$
\lambda _ { k } ( u , v ) = | y _ { k } - \underbrace { \sum _ { i = 0 } ^ { \nu } h _ { i } a _ { k - 1 } } _ { \hat { r } _ { k } ( u , v ) } | ^ { 2 }\tag{7.2}
$$

其中 $( u , v )$ 表示在网格图（trellis diagram）中从状态 u 到状态 v 的状态转移，$y _ { k }$ 是待由Viterbi检测器译码的数据，$\hat { r } _ { k } ( u , v )$ 是与 $( u , v )$ 对应的无噪声信道输出数据（即网格图中每条分支上显示的值，如图4.6所示），由下式求得

$$
r _ { k } = a _ { k } * h _ { k } = \sum _ { i = 0 } ^ { \nu } a _ { k - i } h _ { i }\tag{7.3}
$$

其中 $*$ 是卷积算子，$\begin{array} { r } { H ( D ) = \sum _ { k = 0 } ^ { \nu } h _ { k } D ^ { k } } \end{array}$ 是所需目标，$h _ { k }$ 是目标的第 k 个系数，$\nu$ 是目标的记忆长度。

由于隐含在数据 $y _ { k }$ 中的噪声分量可表示为（参见图3.2的目标设计模型）

$$
\boldsymbol { w } _ { k } = \boldsymbol { y } _ { k } - \boldsymbol { r } _ { k }\tag{7.4}
$$

其D变换结果 $W ( D )$ 如式（7.1）所示。如果直接将数据 $y _ { k }$ 送入Viterbi检测器进行译码，该噪声将具有数据依赖特性，从而获得的误比特率（BER）性能不佳。因此，为了提升系统的整体性能，必须引入噪声白化过程（noise whitening process），使数据 $w _ { k }$ 具有白噪声特性，然后再将结果送入Viterbi检测器进行译码。因此，将噪声预测（noise prediction）技术与Viterbi检测器结合使用时，式（7.2）中的分支度量需要修改为

$$
\lambda _ { k } ( u , v ) = | y _ { k } - \hat { r } _ { k } ( u , v ) - \hat { w } _ { k } | ^ { 2 }\tag{7.5}
$$

其中 $\hat { w } _ { k }$ 是预测得到的噪声，由下式求得

$$
\hat { w } _ { k } = \sum _ { i = 1 } ^ { L } p _ { i } w _ { k - i }\tag{7.6}
$$

其中 $\begin{array} { r } { P ( D ) = \sum _ { i = 1 } ^ { L } p _ { i } D ^ { i } } \end{array}$ 是L抽头噪声预测滤波器（prediction filter），$p _ { i }$ 是噪声预测滤波器的第 i 个系数。由预测产生的误差 $e _ { k }$ 为

$$
e _ { k } = w _ { k } - { \hat { w } } _ { k }\tag{7.7}
$$

或

$$
w _ { k } = \sum _ { i = 1 } ^ { L } p _ { i } w _ { k - i } + e _ { k }\tag{7.8}
$$

一个好的噪声预测滤波器 $P ( D )$ 应使预测误差 $e _ { k }$ 尽可能接近高斯白噪声。

当系统在高硬盘容量下工作时，噪声的强度将取决于数据模式。因此，最优噪声预测滤波器 $P ( D )$ 也应该依赖于数据模式。因此，在求解 $P ( D )$ 的系数时，需要将式（7.8）重新整理如下

$$
w _ { k } ( \underline { { a } } ) = \sum _ { i = 1 } ^ { L } p _ { i } ( \underline { { a } } ) w _ { k - i } ( \underline { { a } } ) + e _ { k } ( \underline { { a } } )\tag{7.9}
$$

其中 $\underline { { a } }$ 表示各种可能的数据模式。式（7.9）可以写成矩阵形式

$$
\begin{array} { r } { w _ { k } ( \underline { { a } } ) = \mathbf { p } ( \underline { { a } } ) ^ { \mathrm { T } } \mathbf { w } ( \underline { { a } } ) + e _ { k } ( \underline { { a } } ) } \end{array}\tag{7.10}
$$

其中 $\mathbf { p } ( \underline { { a } } ) \ = \ [ p _ { 1 } ( \underline { { a } } ) , p _ { 2 } ( \underline { { a } } ) , \dots , p _ { L } ( \underline { { a } } ) ] ^ { \mathrm { T } }$ 是预测滤波器系数的列向量，$\mathbf { w } ( \underline { { a } } ) = [ w _ { k - 1 } ( \underline { { a } } ) , w _ { k - 2 } ( \underline { { a } } ) , \dots , w _ { k - L } ( \underline { { a } } ) ] ^ { \mathrm { T } }$。

$P ( D )$ 的系数可以通过将式（7.10）两边同时乘以向量 ${ \mathbf w } ( \underline { { a } } ) ^ { \mathrm { T } }$ 并应用期望算子（expectation operator）求得，结果为

$$
\begin{array} { r c l } { E \left[ w _ { k } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right] } & { = } & { \mathbf { p } ( \underline { { a } } ) ^ { \mathrm { T } } E \left[ \mathbf { w } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right] } \\ & & { = } & { \mathbf { p } ( \underline { { a } } ) ^ { \mathrm { T } } \mathbf { R } ( \underline { { a } } ) } \end{array}\tag{7.11}
$$

其中 $\mathbf { R } ( \underline { { a } } ) = E \left[ \mathbf { w } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right]$ 是噪声 $w _ { k } ( \underline { { a } } )$ 的自相关矩阵（auto-correlation matrix），且根据正交性原理（orthogonality principle）[25]，$E \left[ e _ { k } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right] = 0$。求解式（7.11）可得

$$
{ \bf p } ( \underline { { a } } ) ^ { \mathrm { T } } = E [ w _ { k } ( \underline { { a } } ) { \bf w } ( \underline { { a } } ) ^ { \mathrm { T } } ] { \bf R } ^ { - 1 } ( \underline { { a } } )\tag{7.12}
$$

预测误差方差（predictor error variance）为[54]

$$
\sigma _ { p } ^ { 2 } ( \underline { { a } } ) = E \left[ w _ { k } ( \underline { { a } } ) ^ { 2 } \right] - E \left[ w _ { k } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right] \mathbf { R } ^ { - 1 } ( \underline { { a } } ) E \left[ w _ { k } ( \underline { { a } } ) \mathbf { w } ( \underline { { a } } ) ^ { \mathrm { T } } \right] ^ { \mathrm { T } }\tag{7.13}
$$

式（7.12）和（7.13）表明，预测滤波器的系数和预测误差方差取决于所考虑的时间点 k。对于每个时间点 k，可能对应的数据模式不同。如果系统是平稳的（stationary）[10, 26]，这些参数是固定的；如果是非平稳系统，则可以采用自适应算法（adaptive algorithm）[4, 10, 16] 来调整预测滤波器的系数和预测误差方差。

由于预测误差方差（即噪声白化过程的结果）依赖于数据模式，如式（7.13）所示，PDNP检测器的分支度量也必须考虑这种数据依赖性。因此，PDNP检测器的分支度量可写为

$$
\lambda _ { k } ( u , v ) = \log \left( \sigma _ { p } ( u , v ) \right) + \frac { | y _ { k } - \hat { r } _ { k } ( u , v ) - \hat { w } _ { k } ( u , v ) | ^ { 2 } } { 2 \sigma _ { p } ^ { 2 } ( u , v ) }\tag{7.14}
$$

其中 $\sigma _ { p } ^ { 2 } ( u , v )$ 是与 $( u , v )$ 及其相关数据模式对应的预测误差方差，$\hat { w } _ { k } ( u , v )$ 是与 $( u , v )$ 及其相关数据模式对应的预测噪声，由下式求得

$$
{ \hat { w } } _ { k } ( u , v ) = \sum _ { i = 1 } ^ { L } p _ { i } ( u , v ) \{ y _ { k - i } - { \hat { r } } _ { k - i } ( u , v ) \}\tag{7.15}
$$

从式（7.12）和（7.13）可以发现，噪声预测滤波器 $\begin{array} { r } { P ( D ) = \sum _ { i } ^ { L } p _ { i } D ^ { i } } \end{array}$ 和预测误差方差 $\sigma _ { p } ^ { 2 }$ 取决于每条分支上的数据模式。因此，在网格图各分支上用于计算分支度量的参数 $P ( D )$ 和 $\sigma _ { p } ^ { 2 }$ 的值，将根据与状态转移 $( u , v )$ 对应的数据模式而有所不同。

在实际应用中，噪声预测滤波器的系数 ${ \bf p } ( \underline { { a } } )$ 取决于有限滑动窗口（finite sliding window）[56] 内的数据比特，用符号 $a _ { k - M } ^ { W }$ 表示，其中 M 和 W 为正整数。因此，PDNP检测器使用的网格图状态数为 $2^{\max(\nu + L , M) + W}$。然而，为便于解释PDNP算法的工作原理，本节仅考虑 $W = 0$ 且 $M < \nu + L$ 的情况。因此，网格图使用的总状态数为 $2 ^ { \nu + L }$。

## 7.4 PS-PDNP算法

7.3节所述的PDNP算法需要总状态数为 $2 ^ { \nu + L }$ 的网格图。然而，PDNP检测器的复杂度可以通过使用"判决反馈（decision-feedback）"[53] 的概念来降低。为了使系统具有可接受的性能，这一概念所需的判决反馈深度（depth）相对较小，与噪声预测滤波器的长度（即抽头数）相比而言。这意味着所使用的网格图仍然需要扩展（trellis expansion），即状态数比不使用噪声预测滤波器的系统更多。

本节将解释文献[53]中提出的方法，该方法类似于"逐幸存处理（PSP: per-survivor processing）"[57] 的概念，用于降低PDNP算法的复杂度。本书将由此得到的新算法称为"PS-PDNP算法（per-survivor PDNP algorithm）"。PS-PDNP检测器在PSP概念的基础上按照PDNP算法运行，这使得PS-PDNP检测器中使用的网格图状态数与不使用噪声预测滤波器的系统相同（即保持不变）。也就是说，PS-PDNP检测器不是扩大网格图，而是沿网格图中到达当前考虑节点（node）的幸存路径（survivor path）回溯，然后使用与幸存路径对应的各种数据来计算预测噪声值。换言之，PS-PDNP检测器仍然使用式（7.14）计算分支度量，但预测噪声的计算方式不同

$$
\hat { w } _ { k } ( u , v ) = \sum _ { i = 1 } ^ { L } p _ { i } ( u , v ) \hat { z } _ { k - i } ( u , v )\tag{7.16}
$$

(0)  
(1)  
(2)  
![](../source_final/images/chapter_7/055f1f96b3fb488eabe59a731461edd3c906c8f93129e6e456b5cc905cc20115.jpg)  
(3)  
(a) Trellis diagram: PR4

![](../source_final/images/chapter_7/c71ac6ecb0900421e9df491428536bc72a2c4155607ce5269bf784acae66f5ce.jpg)  
(b) Decoding procedure  
图7.3: (a) PR4目标的网格图，以及 (b) 网格图译码步骤

其中 $\hat { z } _ { k - i } ( u , v )$ 是隐含在数据 $y _ { k }$ 中、导致状态转移的噪声，对应于导致状态转移 $( u , v )$ 的幸存路径，定义为

$$
\hat { z } _ { k } ( u , v ) = y _ { k } ( u , v ) - \hat { r } _ { k } ( u , v )\tag{7.17}
$$

因此可以看出，PS-PDNP检测器使用的网格图状态数为 $2 ^ { \nu }$，但需要额外的步骤来为每条幸存路径存储 $\{ \hat { z } _ { k - 1 } , \hat { z } _ { k - 2 } , \dots , \hat { z } _ { k - L } \}$ 的值。

示例7.1 图7.3展示了在PR4目标 $H ( D ) = 1 - D ^ { 2 }$ 的系统中，根据式（7.17）求取与 $( u , v )$ 对应的、隐含在数据 $y _ { k }$ 中、导致状态转移的噪声值的示例。其网格图如图7.3(a)所示，所使用的噪声预测滤波器抽头数 $L = 2$。

解：考虑图7.3(b)中 $k + 1$ 时刻的状态 (1)。可以看到，有两条路径汇聚到状态 (1)，即路径A和路径B。因此，式（7.16）中 i = 1 和 2 时的 $\hat { z } _ { k - i } ( u , v )$ 值可计算如下：

对于路径A

$$
\begin{array} { l l l } { \hat { z } _ { k } ( 0 , 1 ) } & { = } & { y _ { k } - \hat { r } _ { k } ( 0 , 1 ) = 0 . 1 5 - 2 = - 1 . 8 5 } \end{array}
$$

$$
\begin{array} { r c l } { \hat { z } _ { k - 1 } ( \mathrm { A } ) } & { = } & { \hat { z } _ { k - 1 } ( 0 , 1 ) = y _ { k - 1 } - \hat { r } _ { k - 1 } ( 0 , 0 ) = 1 - 0 = 1 } \end{array}
$$

$$
\begin{array} { l l l } { \hat { z } _ { k - 2 } ( \mathrm { A } ) } & { = } & { \hat { z } _ { k - 2 } ( 0 , 1 ) = y _ { k - 2 } - \hat { r } _ { k - 2 } ( 0 , 0 ) = 0 . 5 - 0 = 0 . 5 } \end{array}
$$

对于路径B

$$
\begin{array} { l l l } { \hat { z } _ { k } ( 2 , 1 ) } & { = } & { y _ { k } - \hat { r } _ { k } ( 2 , 1 ) = 0 . 1 5 - 0 = 0 . 1 5 } \end{array}
$$

$$
\begin{array} { r c l } { { \hat { z } _ { k - 1 } ( \mathrm { B } ) } } & { { = } } & { { \hat { z } _ { k - 1 } ( 2 , 1 ) = y _ { k - 1 } - \hat { r } _ { k - 1 } ( 3 , 2 ) = 1 - ( - 2 ) = 3 } } \end{array}
$$

$$
\begin{array} { l c l } { { \hat { z } _ { k - 2 } ( \mathrm { B } ) } } & { { = } } & { { \hat { z } _ { k - 2 } ( 2 , 1 ) = y _ { k - 2 } - \hat { r } _ { k - 2 } ( 1 , 3 ) = 0 . 5 - 2 = - 1 . 5 } } \end{array}
$$

## 7.5 PDNP检测器的复杂度

在比较检测器的复杂度时，考虑每个检测器运行所需的加法（addition）和乘法（multiplication）算子数量。表7.1比较了PDNP和PS-PDNP检测器的复杂度，其中 $N _ { p }$ 是PDNP和PS-PDNP检测器中使用的数据模式数量。从表中可以看出，PS-PDNP检测器的复杂度和所需内存（memory requirement）远低于PDNP检测器。

## 7.6 实验结果

本节将使用图7.1所示的信道模型来比较PRML和PDNP检测器的性能。其中读回信号（read-back signal）可以表示为数学方程

表7.1: PDNP和PS-PDNP检测器每比特数据所使用的算子数量
<table><tr><td rowspan=2 colspan=1>检测器(detector)</td><td rowspan=1 colspan=2>每比特数据所使用的算子数量</td><td rowspan=2 colspan=1>所需内存(memory requirement)</td></tr><tr><td rowspan=1 colspan=1>加法</td><td rowspan=1 colspan=1>乘法</td></tr><tr><td rowspan=1 colspan=1>PDNP检测器</td><td rowspan=1 colspan=1> $( 4 L + 7 ) 2 ^ { \nu + L }$ </td><td rowspan=1 colspan=1> $( 2 L + 8 ) 2 ^ { \nu + L }$ </td><td rowspan=1 colspan=1> $( 2 L + 4 ) 2 ^ { \nu + L } + N _ { p } L + 2$ </td></tr><tr><td rowspan=1 colspan=1>PS-PDNP检测器</td><td rowspan=1 colspan=1> $( 2 L + 8 ) 2 ^ { \nu }$ </td><td rowspan=1 colspan=1> $( 2 L + 8 ) 2 ^ { \nu }$ </td><td rowspan=1 colspan=1> $( 2 L + 8 ) 2 ^ { \nu } + N _ { p } L$ </td></tr></table>

即

$$
p ( t ) = \sum _ { k = 0 } ^ { S - 1 } b _ { k } g ( t - k T + \Delta t _ { k } ) + n ( t )\tag{7.18}
$$

其中 $a _ { k } \in \{ 0 , 1 \}$ 是总数为 $S = 4 0 9 6$ 比特的输入数据比特，$b _ { k } = \left( a _ { k } - a _ { k - 1 } \right)$ 是跳变比特（$b _ { k } = \pm 1$ 对应正或负的状态变化，$b _ { k } = 0$ 表示无状态变化），$g ( t )$ 是根据式（1.1）（适用于水平记录系统）或式（1.2）（适用于垂直记录系统）的跳变脉冲信号，$n ( t )$ 是双边功率谱密度为 $N _ { 0 } / 2$ 的加性高斯白噪声（AWGN），$\Delta t _ { k }$ 是介质抖动噪声（media jitter noise），其概率密度函数为高斯分布，均值为零，方差为 $| b _ { k } | \sigma _ { j } ^ { 2 }$（即 $\Delta t _ { k } \sim \mathcal N ( 0 , | b _ { k } | \sigma _ { j } ^ { 2 } )$），且被限制不超过 $T / 2$。其中 $\sigma _ { j }$ 定义为比特单元 $T$ 的百分比，$\left| b _ { k } \right|$ 是 $b _ { k }$ 的绝对值（absolute value）。

读回信号 $p ( t )$ 被送入7阶巴特沃斯低通滤波器（LPF: low-pass filter），然后以 $1 / T$ 的采样频率进行采样，假设采样过程在读回信号和采样器之间具有完美的同步（perfect synchronization）。然后，输出数据序列 $\{ s _ { k } \}$ 被送入均衡器，以将信号特性调整为所需的目标形状，再将得到的输出数据序列 $\left\{ y _ { k } \right\}$ 送入检测器（detector）进行译码，以估计最可能的输入数据序列 $\{ a _ { k } \}$。

在本章中，SNR定义为

$$
\mathrm { S N R } = 1 0 \log _ { 1 0 } \left( \frac { E _ { i } } { N _ { 0 } } \right)\tag{7.19}
$$

其中 $E _ { i }$ 是信道冲激响应的能量。此外，每个BER数据点通过使用多个扇区（sector）的数据进行计算，直到获得的误比特数大于或等于1000比特。

三种检测器，即PRML检测器、PDNP检测器和PS-PDNP检测器，将在使用GPR3目标（根据单调约束条件设计的3抽头目标[19]）和21抽头均衡器的系统中进行性能比较。其中，水平记录系统的GPR3目标为 $H ( D ) = 1 + 0 . 0 5 D - 0 . 6 5 D ^ { 2 }$，垂直记录系统的GPR3目标为 $H ( D ) = 1 + 1 . 2 5 D + 0 . 6 2 D ^ { 2 }$。图7.4比较了三种检测器在ND = 2.5、介质抖动噪声 $\sigma _ { j } / T = 1 0 \%$ 条件下，针对水平记录和垂直记录系统的BER性能。

从图7.4(a)可以看出，对于水平记录系统，PS-PDNP检测器的性能接近PDNP检测器，但这两种检测器的性能都优于PRML检测器，尤其是在高SNR条件下（即系统中的主要噪声为介质抖动噪声）。而对于垂直记录系统（见图7.4(b)），在低SNR条件下，PRML检测器的性能似乎略优于PS-PDNP和PDNP检测器。这可能是因为在低SNR条件下，系统中的主要噪声不是介质抖动噪声，因此专门设计用于处理介质抖动噪声的PS-PDNP和PDNP检测器无法有效工作。然而，在高SNR条件下，PS-PDNP和PDNP检测器的性能远优于PRML检测器。实验结果表明，PS-PDNP检测器的性能接近PDNP检测器。因此，在实际应用中，由于PS-PDNP检测器的复杂度远低于PDNP检测器，可以替代PDNP检测器使用。

![](../source_final/images/chapter_7/230845a8053c744325468c3f1ef410bb3581589cab26d3145249cb6ffa8c6e25.jpg)

![](../source_final/images/chapter_7/45fbb0f20dde75c931b2b87f56de04b2ce6826264c199e0309ccda5d9ab3ba71.jpg)  
图7.4: 在ND = 2.5且 $\sigma _ { j } / T = 1 0 \%$ 条件下，各种检测器在 (a) 水平记录和 (b) 垂直记录系统中的BER性能

## 7.7 本章小结

随着硬盘驱动器数据容量的提高，符号检测器输入端的噪声不仅呈现有色噪声（colored noise）特性，还呈现依赖数据模式（data pattern）的特性。例如，介质抖动噪声（media jitter noise）的严重程度取决于记录在介质上的数据模式。PDNP检测器正是为处理这些噪声而设计的，它通过噪声预测滤波器与维特比算法的协同工作来实现。

尽管PDNP检测器的性能远优于PRML检测器，但其复杂度也更高，因为PDNP检测器使用的网格图状态数更多（取决于噪声预测滤波器的抽头数）。然而，这一问题可以通过将PDNP维特比算法与PSP（逐幸存路径处理）概念相结合来解决，得到PS-PDNP检测器，其性能接近PDNP检测器，但复杂度显著降低。

## 7.8 课后习题

1. 请解释PDNP算法概念的来源。

2. 请推导均方误差值，根据方程(7.13)。

3. 请推导PDNP检测器使用的算法值，根据方程(7.14)。

4. 请解释PRML检测器、NPML检测器和PDNP检测器之间的区别。

5. 请解释PS-PDNP检测器的工作原理。

6. 请推导每1比特数据所需的加法和比较次数，如表7.1所示。

7. 请推导所需的存储单元数，如表7.1所示。
