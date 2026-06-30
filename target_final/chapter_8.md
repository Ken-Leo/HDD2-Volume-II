# 第8章 RLL码设计

本章将说明RLL码（run-length limited）[9]的功能和工作原理，该码在硬盘驱动器的信号处理系统中非常流行，同时展示简单RLL码的设计步骤，用于数据的编码和解码。

## 8.1 引言

RLL码是一种调制码，在硬盘驱动器设备中非常常用，其功能是定义数据序列中连续排列的"0"位和"1"位（按照NRZ1格式）的数量，这些数据序列将要写入记录介质。通常，RLL码由4个参数定义：m、n、d和k，以m/n (d, k)的形式表示，其中：

1) m 是每次编码的输入数据位数，用于进行RLL编码。

2) n 是每次编码的输出数据位数，由RLL编码得到。通常 $n \geq m$ 始终成立。

3) d 是定义两个1位之间最少0位个数的整数。

4) k 是定义两个1位之间最多0位个数的整数。其中1位对应于写入电流的状态变化，该电流输入到写磁头，使记录介质在需要写入数据的区域具有所需的磁化状态。而0位表示写入电流没有状态变化。因此，参数d有助于使两个1位之间保持距离，从而减少符号间干扰（ISI）的影响。而参数k则保证写入记录介质的数据序列有足够频繁的状态变化位，使定时恢复系统能够有效工作。例如，如果要写入记录介质的数据序列是：

![](../source_final/images/chapter_8/0faa3ab2b094b4b5153decc8917240d774acee179db272ac338109aeabb5902c.jpg)  
图8.1：RLL编码模型

$$
\cdots 1 1 1 1 1 \cdots 1 1 1 1 1 \cdots
$$

此数据序列被认为是差的数据序列，因为它会导致严重的ISI问题。相反，如果要写入记录介质的数据序列是：

$$
\dots \dots 0 0 0 0 0 \dots 0 0 0 0 0 0 \dots
$$

同样被认为是差的数据序列，因为它会导致定时恢复系统的同步问题。因此，为了避免这两种数据序列，有必要使用RLL码对数据序列进行编码。在实际应用中，使用RLL码进行编码和解码可以简单地通过使用"查找表"来实现。

图8.1显示了RLL编码模型，其中"码率"定义为输入位数m除以输出位数n，即：

$$
R = \frac { m } { n } \leq 1\tag{8.1}
$$

## 8.2 满足(d, k)约束的所有数据序列的数量

由于编码后的输出位数n总是大于或等于输入位数m，因此RLL编码的一个明显缺点就是会产生"冗余位"，这会导致硬盘驱动器中所需的数据存储空间部分损失。因此，在选择使用的RLL码时，应选择码率R尽可能接近1的RLL码，以减少存储空间的损失。本章内容将说明在给定参数m、n、d和k的情况下，简单RLL码的设计步骤。

### 8.2 满足(d, k)约束的所有数据序列的数量

设数据序列的总长度为L位。满足(d, k)约束的所有数据序列的数量可以通过以下方程求得[9]：

$$
N ( L ) ~ = ~ L + 1 , ~ 1 \leq L \leq d + 1\tag{8.2}
$$

$$
\begin{array} { r c l } { N ( L ) } & { = } & { N ( L - 1 ) + N ( L - d - 1 ) , \ d + 1 \leq L \leq k } \end{array}\tag{8.3}
$$

$$
N ( L ) ~ = ~ d + k + 1 - L + \sum _ { i = d } ^ { k } N ( L - i - 1 ) , ~ k < L \leq d + k\tag{8.4}
$$

$$
N ( L ) ~ = ~ \sum _ { i = d } ^ { k } N ( L - i - 1 ) , ~ L > d + k\tag{8.5}
$$

其中 $N ( L ) = 0$ 对于 $L < 0$，且 $N ( 0 ) = 1$。

当参数 $k = \infty$ 时，满足 $( d , \infty )$ 约束的所有数据序列的数量可以通过以下方程求得：

$$
N _ { d } ( L ) ~ = ~ L + 1 , ~ 1 \leq L \leq d + 1\tag{8.6}
$$

$$
\begin{array} { r c l } { { N _ { d } ( L ) } } & { { = } } & { { N _ { d } ( L - 1 ) + N _ { d } ( L - d - 1 ) , L > d + 1 } } \end{array}\tag{8.7}
$$

其中 $N _ { d } ( L ) = 0$ 对于 $L < 0$，且 $N _ { d } ( 0 ) = 1$。表8.1显示了长度为L、满足 $( d , \infty )$ 约束的所有数据序列数量 $N _ { d } ( L )$ 的示例。

表8.1：长度为L、满足 $( d , \infty )$ 约束的所有数据序列数量 $N _ { d } ( L )$ 示例
<table><tr><td rowspan=1 colspan=1> $d$ </td><td rowspan=1 colspan=1> $L = 4$ </td><td rowspan=1 colspan=1> $L = 5$ </td><td rowspan=1 colspan=1> $L = 6$ </td><td rowspan=1 colspan=1> $L = 7$ </td><td rowspan=1 colspan=1> $L = 8$ </td><td rowspan=1 colspan=1> $L = 9$ </td><td rowspan=1 colspan=1> $L = 1 0$ </td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>8</td><td rowspan=1 colspan=1>13</td><td rowspan=1 colspan=1>21</td><td rowspan=1 colspan=1>34</td><td rowspan=1 colspan=1>55</td><td rowspan=1 colspan=1>89</td><td rowspan=1 colspan=1>144</td></tr><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>o</td><td rowspan=1 colspan=1>9</td><td rowspan=1 colspan=1>13</td><td rowspan=1 colspan=1>19</td><td rowspan=1 colspan=1>28</td><td rowspan=1 colspan=1>41</td><td rowspan=1 colspan=1>60</td></tr><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>s</td><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>10</td><td rowspan=1 colspan=1>14</td><td rowspan=1 colspan=1>19</td><td rowspan=1 colspan=1>26</td><td rowspan=1 colspan=1>36</td></tr><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>s</td><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>8</td><td rowspan=1 colspan=1>11</td><td rowspan=1 colspan=1>15</td><td rowspan=1 colspan=1>20</td><td rowspan=1 colspan=1>26</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>6</td><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1>9</td><td rowspan=1 colspan=1>12</td><td rowspan=1 colspan=1>16</td><td rowspan=1 colspan=1>21</td></tr></table>

当知道满足(d, k)约束的所有数据序列数量 $N ( L )$ 后，可用于表示每个数据序列的总位数K等于：

$$
K = \left\lceil \log _ { 2 } \left\{ N ( L ) \right\} \right\rceil \quad ( { \mathrm { b i t s } } )\tag{8.8}
$$

其中 $\lceil x \rceil$ 表示大于或等于x的最小正整数。例如，如果 $N _ { 4 } ( 6 ) = 8$，则可以使用3位数据位 {000, 001, 010, 011, 100, 101, 110, 111} 来表示每种数据序列。

## 8.3 (d, k)型RLL码的容量

在通信系统理论中，"容量"指的是码率R能够达到的最大值，定义为[9]：

$$
C ( d , k ) = \operatorname* { l i m } _ { L \to \infty } \frac { 1 } { n } \log _ { 2 } \{ N ( L ) \}\tag{8.9}
$$

其中 $N ( L )$ 是满足 $( d , k )$ 约束的所有数据序列的数量。此外，容量值 $C ( d , k )$ 也是指示用户想要写入记录介质的信息数据存储能力（不计冗余位）的参数。也就是说，如果 $C ( d , k )$ 值越大，则系统可以存储的用户信息数据也越多。

此外，通过考虑"码效率"值，可以对各种RLL码的性能进行比较，其定义为：

$$
\eta = \frac { R } { C ( d , k ) }\tag{8.10}
$$

即，码效率值越高的RLL码，其使用效率也越高。

### 8.3.1 (d, k)型RLL码的渐近信息率

由于计算方程(8.9)中当 $L \to \infty$ 时的容量 $C ( d , k )$ 相当困难，因此通常通过"渐近信息率"来计算 $C ( d , k )$，其定义为[58]：

$$
C ( d , k ) = \log _ { 2 } \{ \lambda _ { \operatorname* { m a x } } \}\tag{8.11}
$$

其中 $\lambda _ { \mathrm { m a x } }$ 是以下方程中值最大的实根：

$$
x ^ { k + 2 } - x ^ { k + 1 } - x ^ { k - d + 1 } + 1 = 0 , k < \infty\tag{8.12}
$$

$$
x ^ { d + 1 } - x ^ { d } - 1 = 0 , k = \infty\tag{8.13}
$$

表8.2显示了通过求解方程(8.11)-(8.13)得到的各种(d, k)型RLL码的渐近信息率 $C ( d , k )$。观察表8.2中的 $C ( d , k )$ 值可以发现，通常使用的RLL码其参数 $d \leq 2$ 始终成立，以保证码率 $R \ge 1 / 2$。

### 8.3.2 密度比

密度比DR或packing density是表示经过RLL编码的数据序列中两个相邻状态变化位置之间物理距离的参数，定义为：

$$
{ \mathrm { D R } } = ( 1 + d ) R\tag{8.14}
$$

表8.2：各种(d, k)型RLL码的渐近信息率
<table><tr><td rowspan=1 colspan=1>k</td><td rowspan=1 colspan=1> $d = 0$ </td><td rowspan=1 colspan=1> $d = 1$ </td><td rowspan=1 colspan=1> $d = 2$ </td><td rowspan=1 colspan=1> $d = 3$ </td><td rowspan=1 colspan=1> $d = 4$ </td><td rowspan=1 colspan=1> $d = 5$ </td></tr><tr><td rowspan=2 colspan=1>123</td><td rowspan=2 colspan=1>0.69420.87920.9468</td><td rowspan=1 colspan=1>0.4057</td><td rowspan=2 colspan=1>0.2878</td><td rowspan=2 colspan=1></td><td rowspan=2 colspan=1></td><td rowspan=6 colspan=1>0.31580.3513</td></tr><tr><td rowspan=1 colspan=1>0.5515</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>0.9752</td><td rowspan=1 colspan=1>0.6174</td><td rowspan=1 colspan=1>0.4057</td><td rowspan=1 colspan=1>0.2232</td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>0.9881</td><td rowspan=1 colspan=1>0.6509</td><td rowspan=1 colspan=1>0.4650</td><td rowspan=1 colspan=1>0.3218</td><td rowspan=1 colspan=1>0.1823</td></tr><tr><td rowspan=1 colspan=1>10</td><td rowspan=1 colspan=1>0.9997</td><td rowspan=1 colspan=1>0.6909</td><td rowspan=1 colspan=1>0.5418</td><td rowspan=1 colspan=1>0.4460</td><td rowspan=1 colspan=1>0.3746</td></tr><tr><td rowspan=1 colspan=1>15</td><td rowspan=1 colspan=1>0.9999</td><td rowspan=1 colspan=1>0.6939</td><td rowspan=1 colspan=1>0.5501</td><td rowspan=1 colspan=1>0.4615</td><td rowspan=1 colspan=1>0.3991</td></tr><tr><td rowspan=1 colspan=1>∞</td><td rowspan=1 colspan=1>1.0000</td><td rowspan=1 colspan=1>0.6942</td><td rowspan=1 colspan=1>0.5515</td><td rowspan=1 colspan=1>0.4650</td><td rowspan=1 colspan=1>0.4057</td><td rowspan=1 colspan=1>0.3620</td></tr></table>

其中R是码率。

表8.3显示了容量 $C ( d , k )$ 与密度比DR之间的关系。可以看出，从方程(8.14)可知，当参数d增加时，DR值也增加。但参数d的增加意味着编码后的数据会有更多的冗余位（因为参数d是两个1位之间最少的0位个数）。如果考虑记录介质存储空间有限，那么系统可以存储的用户信息数据就会减少，因为需要留出部分空间来存储冗余位。因此，这会导致计算得到的容量 $C ( d , k )$ 值变小。

## 8.4 RLL码的有限状态机

RLL码的有限状态机展示了RLL码中根据(d, k)参数约束的状态变化。例如，$( d , k )$ 型RLL码的有限状态机如图8.2所示，其中 $S _ { i }$ 是状态i，箭头线上显示的数字是与参数 $( d , k )$ 约束相对应的输出数据位。从图8.2中，起始状态为 $S _ { 1 }$，这被认为是数据序列中遇到第一个1位的事件。因此，下一个位必须是至少连续d个0位（即状态 $S _ { 1 }$ 将沿直线行进到状态 $S _ { d + 1 }$）。当数据序列有d个0位后，根据 $( d , k )$ 约束，下一个位可以是0位或1位。如果它是1位，系统将必须返回到状态 $S _ { 1 }$ 重新开始。但如果它是0位，则最多还可以有 $k - d$ 个0位。当连续0位达到k个后，下一个位必须是1位。也就是说，系统将自动强制返回到状态 $S _ { 1 }$ 重新开始。

表8.3：容量 $C ( d , k )$ 与密度比DR的关系
<table><tr><td> $d$ </td><td> $C ( d , \infty )$ </td><td> $\mathrm { D R } = ( 1 + d ) C ( d , \infty )$ </td></tr><tr><td>1</td><td>0.6942</td><td>1.3884</td></tr><tr><td></td><td>0.5515</td><td>1.6545</td></tr><tr><td></td><td>0.4650</td><td>1.8600</td></tr><tr><td>2</td><td>0.4057</td><td>2.0285</td></tr><tr><td>4</td><td>0.3620</td><td>2.1720</td></tr></table>

![](../source_final/images/chapter_8/5b8da2100d8592f7d69c548895da995bee15d8cae834702b12f49bc926b3a080.jpg)  
图8.2：RLL码(d, k)型有限状态机

例8.1 请画出参数 $( d , k ) = ( 1 , 3 )$ 约束下RLL码的有限状态图。

解 参数(1, 3)表示数据序列在两个1位之间至少有一个0位或至多有三个0位。

![](../source_final/images/chapter_8/e3c07d94054304e92db0109e7c2be5d9afe3b399510e3786b1b408ac4992d191.jpg)  
图8.3：(1, 3)型RLL码的有限状态机  
连续排列在两个1位之间，可以写成如图8.3所示的有限状态机。

## 8.5 状态转移矩阵

$( d , k )$ 型RLL码的有限状态机可以写成"状态转移矩阵"的形式。其定义为矩阵D，大小为(k + 1)行×(k + 1)列。矩阵元素 $\mathbf { D } ( i , j )$，即第i行和第j列，由下式确定：

$$
\begin{array} { r c l } { \mathbf { D } ( i , 1 ) } & { = } & { 1 , ~ i \geq d + 1 } \\ & & { } & { } \\ { \mathbf { D } ( i , j ) } & { = } & { \left\{ \begin{array} { l l } { 1 , } & { j = i + 1 } \\ { 0 , } & { \mathrm { e l s e } } \end{array} \right. } \end{array}\tag{8.15}
$$

例如，图8.3中(1, 3)型RLL码的有限状态机可以写成如下的状态转移矩阵：

$$
\mathbf { D } = { \left[ \begin{array} { l l l l } { 0 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } & { 0 } \end{array} \right] }\tag{8.16}
$$

方程(8.16)中的矩阵D可以按以下方法构造。如果指定每行代表一个状态，即第一行代表状态 $S _ { 1 }$，第二行代表状态 $S _ { 2 }$，依此类推。同样地，每列代表一个状态，即第一列代表状态 $S _ { 1 }$，第二列代表状态 $S _ { 2 }$，依此类推。因此，在构造(1, 3)型RLL码有限状态机（图8.3）的状态转移矩阵时，逐列考虑。例如，在第一列（状态 $S _ { 1 }$），查看有哪些状态 $S _ { i }$ 的箭头指向状态 $S _ { 1 }$。从图8.3可以看出，有来自状态 $S _ { 2 }$、$S _ { 3 }$ 和 $S _ { 4 }$ 的箭头。因此，在此第一列中，值1被放入第二行、第三行和第四行，第一行则为0。类似地，如果考虑第二列（状态 $S _ { 2 }$），查看有哪些状态 $S _ { i }$ 的箭头指向状态 $S _ { 2 }$。从图8.3可以看出，只有来自状态 $S _ { 1 }$ 的一条箭头指向状态 $S _ { 2 }$。因此，值1被放入第一行，其他行为0，依此类推。

对于参数 $k = \infty$ 的情况，$( d , \infty )$ 型RLL码的有限状态机可以写成状态转移矩阵D的形式，大小为(d+1)行×(d+1)列。矩阵元素 $\mathbf { D } ( i , j )$ 由下式确定：

$$
\begin{array} { r c l } { { { \bf D } ( i , j ) } } & { { = } } & { { 1 , j = i + 1 } } \\ { { } } & { { } } & { { } } \\ { { { \bf D } ( d + 1 , 1 ) } } & { { = } } & { { { \bf D } ( d + 1 , d + 1 ) = 1 } } \\ { { } } & { { } } & { { } } \\ { { { \bf D } ( i , j ) } } & { { = } } & { { 0 , \mathrm { e l s e } } } \end{array}\tag{8.17}
$$

例8.2 请画出参数 $( d , k ) = ( 0 , 3 )$ 约束下RLL码的有限状态图和状态转移矩阵。

解 参数(0, 3)表示数据序列在两个1位之间至少有一个0位或至多有三个连续0位，可以写成如图8.4所示的有限状态机。与此有限状态机对应的状态转移矩阵为：

$$
\mathbf { D } = { \left[ \begin{array} { l l l l } { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } & { 0 } \end{array} \right] }
$$

![](../source_final/images/chapter_8/664fc2ef3363909ee32beb37b8339a74415dd6f3c74bd410df1b58101692b9ee.jpg)  
图8.4：(0,3)型RLL码的有限状态机

### 8.5.1 渐近信息率的计算

状态转移矩阵D可用于计算渐近信息率 $C ( d , k )$，使用方程(8.11)中的公式，即：

$$
C ( d , k ) = \log _ { 2 } \left\{ \lambda _ { \operatorname* { m a x } } ^ { D } \right\}\tag{8.18}
$$

其中 $\lambda _ { \mathrm { m a x } } ^ { D }$ 是状态转移矩阵D的最大实特征值，通过解以下方程求得：

$$
\operatorname* { d e t } ( \mathbf { D } - \lambda \mathbf { I } ) = 0\tag{8.19}
$$

其中 det() 是求行列式，I 是与矩阵D大小相同的单位矩阵，$\lambda$ 是特征值。

### 8.5.2 与(d, k)型RLL码有限状态机相对应的数据序列

从图8.2所示的(d, k)型RLL码有限状态机，其中 $S _ { i }$ 是状态i，所有可能的长度为L位、从状态 $S _ { i }$ 出发并在状态 $S _ { j }$ 结束的数据序列的数量，等于矩阵 $\mathbf { D } ^ { L }$ 中第i行第j列的值，即 $\mathbf { D } ^ { L } ( i , j )$。

例8.3 根据图8.5中(0, 2)型RLL码的状态转移矩阵D，找出所有可能的长度为2位的数据序列。

$$
0 \leq i , j \leq 3
$$

解 图8.5中(0, 2)型RLL码的有限状态机可以写成状态转移矩阵D的形式：

$$
\mathbf { D } = { \left[ \begin{array} { l l l } { 1 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } \end{array} \right] }\tag{8.20}
$$

因此，所有可能的长度为2位的数据序列可以从 $\mathbf { D } ^ { 2 }$ 求得，其值为：

$$
\mathbf { D } ^ { 2 } = { \left[ \begin{array} { l l l } { 2 } & { 1 } & { 1 } \\ { 2 } & { 1 } & { 0 } \\ { 1 } & { 1 } & { 0 } \end{array} \right] }\tag{8.21}
$$

方程(8.21)告诉我们：

从状态 $S _ { 1 }$ 到 $S _ { 1 }$ 的数据序列有 D(1, 1) = 2 个，即 {01, 11}

从状态 $S _ { 2 }$ 到 $S _ { 1 }$ 的数据序列有 D(2, 1) = 2 个，即 {01, 11}

从状态 $S _ { 3 }$ 到 $S _ { 1 }$ 的数据序列有 D(3, 1) = 1 个，即 {11}

从状态 $S _ { 1 }$ 到 $S _ { 2 }$ 的数据序列有 D(1, 2) = 2 个，即 {10}

## 8.6 RLL码的设计步骤

本节将通过以下示例展示用于RLL码编码和解码的查找表设计步骤。

例8.4 请为(0, 2)型RLL码创建编码和解码查找表，其中每次编码后的数据长度为 n = 3，并求码效率。

解 创建RLL码编码和解码查找表可以分为以下4个步骤：

步骤1：考虑3位数据共有多少种模式。结果有8种模式，即：

{000, 001, 010, 011, 100, 101, 110, 111}

步骤2：考虑哪些数据集不满足(0, 2)约束。发现共有7种数据模式通过(0,2)约束，即：

{001, 010, 011, 100, 101, 110, 111}

步骤3：尝试将步骤2中得到的每个数据向左和向右进行拼接，然后查看哪些数据在拼接后不满足(0, 2)约束。这里发现数据001和100在与其它数据拼接时会导致(0, 2)约束被违反。因此，数据001和100必须被剔除，剩下的只有5种通过(0, 2)约束的数据模式，即：

{010, 011, 101, 110, 111}

这些数据就是可以通过RLL编码后使用的数据。

步骤4：从步骤3中得到的5种数据模式中选择4种（任意选择），用于创建每次2位输入数据进行编码和解码的查找表，即 {00, 01, 10, 11}，如表8.4所示。由此可得码率为：

表8.4：(0, 2)型RLL码编码和解码查找表
<table><tr><td>输入数据</td><td>输出数据</td></tr><tr><td>00</td><td>010</td></tr><tr><td>01</td><td>011</td></tr><tr><td>10</td><td>101</td></tr><tr><td>11</td><td>110</td></tr></table>

$$
R = \frac { 2 } { 3 }
$$

同样地，RLL码的码效率可以按照以下步骤求得。首先，与图8.5中有限状态机相对应的状态转移矩阵如方程(8.20)所示，即：

$$
\mathbf { D } = { \left[ \begin{array} { l l l } { 1 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } \end{array} \right] }
$$

下一步是求矩阵D的特征值，可以通过解方程(8.19)得到：

$$
\begin{array} { r l r } { \operatorname* { d e t } \left( \left[ \begin{array} { l l l } { 1 } & { 1 } & { 0 } \\ { 1 } & { 0 } & { 1 } \\ { 1 } & { 0 } & { 0 } \end{array} \right] - \lambda \left[ \begin{array} { l l l } { 1 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 1 } \end{array} \right] \right) } & { = } & { 0 } \\ { \operatorname* { d e t } \left( \left[ \begin{array} { l l l } { 1 - \lambda } & { 1 } & { 0 } \\ { 1 } & { - \lambda } & { 1 } \\ { 1 } & { 0 } & { - \lambda } \end{array} \right] \right) } & { = } & { 0 } \\ { \medskip } & { } & { - \lambda ^ { 3 } + \lambda ^ { 2 } + \lambda + 1 \ = \ 0 } \end{array}\tag{8.22}
$$

解方程(8.22)得到：

$$
\lambda = 1 . 8 3 9 3 , - 0 . 4 1 9 6 + 0 . 6 0 6 3 i , - 0 . 4 1 9 6 - 0 . 6 0 6 3 i
$$

因此 $\lambda _ { \operatorname* { m a x } } ^ { D } = 1 . 8 3 9 3$ 被用于按照方程(8.18)计算容量 $C ( d , k )$，即：

$$
C ( d , k ) = \log _ { 2 } \{ \lambda _ { \operatorname* { m a x } } \} = \log _ { 2 } \{ 1 . 8 3 9 3 \} = 0 . 8 7 9 1 6
$$

码效率 $\eta$ 由方程(8.10)求得：

$$
\eta = \frac { R } { C ( d , k ) } = \frac { 2 / 3 } { 0 . 8 7 9 1 6 } = 0 . 7 5 8 3
$$

## 8.7 各种RLL码示例

RLL码有多种类型，取决于所使用的参数 $( d , k )$ 和码率R。在硬盘驱动器设备发展的初期，使用的RLL码称为"FM码（调频码）"，其编码和解码查找表如图8.6(a)所示。这种FM码与峰值检测电路配合使用，码率为 $R = 1 / 2$，这会导致硬盘驱动器约50%的空间损失用于存储冗余位。编码示例如下：如果输入数据序列是 {110000}，则FM编码后的数据序列是 {11 11 01 010101}。

可以观察到，FM码允许编码后的数据序列有连续的1位，这会导致ISI问题。因此，开发了称为"MFM码（改进型调频码）"的新码，有时也称为"米勒码"，其编码和解码查找表如图8.6(b)所示。其中，如果x位之前的位是1，则 $x = 0$，否则 $x = 1$。MFM码被认为是(1,3)型RLL码，码率为 $R = 1 / 2$，码效率 $\eta = 0 . 5 / 0 . 5 5 1 5 = 0 . 9 0 6 6$。编码示例如下：如果输入数据序列是 {1100011}，则MFM编码后的数据序列是 {01 01 00 10 10 01 01} 等。此外，图8.6(c)和8.6(d)显示了硬盘驱动器中使用的各种RLL码示例。从RLL码的发展演变可以看出，RLL码中使用的参数d逐渐减小，以减少冗余位的数量，从而可以在硬盘驱动器中存储更多的所需数据。

<table><tr><td>user bits</td><td>coded bits</td></tr><tr><td>0 1</td><td>01 11</td></tr></table>

(a) FM码

<table><tr><td>user bits</td><td>coded bits</td></tr><tr><td>0</td><td>x0</td></tr><tr><td>1</td><td>01</td></tr></table>

(b) MFM码

<table><tr><td rowspan=1 colspan=1>user bits</td><td rowspan=1 colspan=1>coded bits</td></tr><tr><td rowspan=1 colspan=1>0001</td><td rowspan=4 colspan=1>101100001010101000</td></tr><tr><td rowspan=1 colspan=1>10</td></tr><tr><td rowspan=1 colspan=1>11</td></tr><tr><td rowspan=1 colspan=1>0000</td></tr><tr><td rowspan=1 colspan=1>0001</td><td rowspan=1 colspan=1>100000</td></tr><tr><td rowspan=1 colspan=1>10001001</td><td rowspan=1 colspan=1>001000010000</td></tr></table>

(c) 2/3 (1,7) RLL码

<table><tr><td rowspan=1 colspan=1>user bits</td><td rowspan=1 colspan=1>coded bits</td></tr><tr><td rowspan=1 colspan=1>1011</td><td rowspan=2 colspan=1>01001000000100</td></tr><tr><td rowspan=1 colspan=1>000</td></tr><tr><td rowspan=1 colspan=1>010</td><td rowspan=1 colspan=1>100100</td></tr><tr><td rowspan=1 colspan=1>011</td><td rowspan=1 colspan=1>001000</td></tr><tr><td rowspan=1 colspan=1>0010</td><td rowspan=2 colspan=1>0010010000001000</td></tr><tr><td rowspan=1 colspan=1>0011</td></tr></table>

(d) 1/2 (1,7) RLL码  
图8.6：硬盘驱动器中使用的各种RLL码示例

决定在系统中使用哪种RLL码取决于以下几个因素：

1) 参数(d, k)

2) 码率 $R = m / n$

3) 容量 $C ( d , k )$

4) 码效率 $\eta$

5) 密度比DR

通常，需要综合考虑所有因素以适应系统的工作环境。曾经在硬盘驱动器中使用的RLL码，例如 $1 / 2 \left( 2 , 7 \right)$ 型RLL码、$4 / 5 \left( 0 , 2 \right)$ 型RLL码和 $8 / 9 \left( 0 , 3 \right)$ 型RLL码等。可以观察到，所使用的RLL码码率逐渐接近1，以减少冗余位的数量，同时使用的参数d值为0，即允许连续的1位。尽管这会导致ISI问题，但系统可以通过第4章中所述的PRML技术来处理此ISI。

## 8.8 用于PRML信道的 $( 0 , G / I )$ 码

对于使用PR4目标 $H ( D ) = 1 - D ^ { 2 }$ 的PRML信道，时刻k的无噪声信道输出值等于时刻k和 $k-2$ 的两个输入数据之差。因此，该信道具有一个特殊性质：奇数子序列独立于偶数子序列。因此，为了减少维特比检测器的路径存储器，每个子序列中连续0位的数量不能超过I个。而为了使定时恢复系统能够有效工作，总数据序列（奇数子序列与偶数子序列合并）中连续0位的数量不能超过 $G$ 个，类似于(d, k)型RLL码中的参数k。对于 $( 0 , G / I )$ 码中的0值，表示系统允许总数据序列中有连续的1位，类似于(d, k)型RLL码中的参数d [9, 59, 60]。这是因为PRML检测器能够处理所发生的ISI。

设 $\gamma = \{ \gamma _ { 1 } , \gamma _ { 2 } , . . . , \gamma _ { n } \}$ 是长度为n位的二进制数据序列。则奇数子序列 $\gamma ^ { o }$ 和偶数子序列 $\gamma ^ { e }$ 定义为[60]：

$$
\begin{array} { r c l } { { \gamma ^ { o } } } & { { = } } & { { \left\{ \gamma _ { 1 } , \gamma _ { 3 } , \gamma _ { 5 } , \ldots , \gamma _ { 2 \lceil n / 2 \rceil - 1 } \right\} } } \\ { { } } & { { } } & { { } } \\ { { \gamma ^ { e } } } & { { = } } & { { \left\{ \gamma _ { 2 } , \gamma _ { 4 } , \gamma _ { 6 } , \ldots , \gamma _ { 2 \lfloor n / 2 \rfloor } \right\} } } \end{array}
$$

其中 $\lfloor x \rfloor$ 表示小于或等于x的最大正整数。因此，奇数子序列 $\gamma ^ { o }$ 和偶数子序列 $\gamma ^ { e }$ 的长度分别为 $\lceil n / 2 \rceil$ 和 $\lfloor n / 2 \rfloor$。

当且仅当总数据序列γ中连续0位的数量不超过G个，且子序列 $\gamma ^ { o }$ 和 $\gamma ^ { e }$ 中连续0位的数量不超过I个时，该数据序列被称为满足 $( 0 , G / I )$ 约束的数据序列，其中G和I为正整数。

例8.5 设γ = {110100101000110011} 是用 $( 0 , G / I )$ 型RLL码编码的数据序列，求γ的参数G和I。

解 根据给定的数据序列γ，可得 $\gamma ^ { o } = \{ 1 0 0 1 1 0 1 0 1 \}$ 和 $\gamma ^ { e } = \{ 1 1 0 0 0 0 1 0 1 \}$。因此，$\gamma$、$\gamma ^ { o }$ 和 $\gamma ^ { e }$ 中最大连续0位的数量分别为3、2和4。因此可得 $G = 3$ 和 $I = 4$，即数据序列γ是用 $( 0 , 3 / 4 )$ 型RLL码编码的。

从例8.5可以观察到，正确的 $( 0 , G / I )$ 型RLL码编码的数据序列中，参数 $G \leq 2 I$ 始终成立。在硬盘驱动器信号处理系统中使用的 $( 0 , G / I )$ 码示例，如 $8 / 9 \left( 0 , 4 / 4 \right)$ 码和 $1 6 / 1 7 \left( 0 , 6 / 6 \right)$ 码等。

## 8.9 章末总结

一般来说，RLL码有多种形式。本章说明了(d, k)约束下RLL码的工作原理和设计步骤。其中，参数d定义了两个1位（按照NRZ1格式）之间最少0位的数量，而参数k定义了两个1位之间最多0位的数量。由于1位代表写入电流的状态变化，因此参数d有助于减少ISI的影响，而参数k则保证写入记录介质的数据序列有周期性的状态变化，使定时恢复系统能够有效工作。然而，目前常用的RLL码通常采用 $( 0 , G / I )$ 码的形式，这种码是为硬盘驱动器的PRML系统设计的。

在选择使用的RLL码时，必须考虑多个因素，包括：参数(d, k)、码率R、容量C(d, k)、码效率$\eta$以及密度比DR等，以针对特定应用获得最佳的RLL码。目前硬盘驱动器中使用的RLL码的一个观察结果是：参数d逐渐减小到0，并且所使用的RLL码率R越来越接近1。这都是为了减少系统中产生的冗余位数量，从而可以存储更多的用户信息数据。

## 8.10 课后习题

1. 求满足(d, k)约束、总长度为L位的所有数据序列的数量，当：

   1.1) d = 1, k = 7, 且 L = 10

   1.2) d = 2, k = 7, 且 L = 10

2. 画出有限状态图并计算参数(d, k)约束下RLL码的状态转移矩阵，当：

$$
2 . 1 ) \ d = 1 \ \mathsf { { u } } \mathsf { { u } } \mathsf { { u } } \ u = 5
$$

$$
2 . 2 ) \ d = 1 \ \mathsf { { u } } \mathsf { { u } } \mathsf { { e } } ^ { \circ } \ k = 7
$$

$$
2 . 3 ) \ d = 2 \ \mathsf { { u } } 6 \mathsf { { u } } ^ { \circ } \ k = 5
$$

3. 根据第2题中的条件，使用方程(8.12)计算容量 $C ( d , k )$，并将结果与使用方程(8.18)计算得到的C(d, k)进行比较。

4. 求(d, k)约束下RLL码的从状态 $S _ { i }$ 出发并在状态 $S _ { j }$ 结束的长度为L位的所有可能数据序列的数量，当：

   4.1) d = 0, k = 2, 且 L = 5

   4.2) d = 1, k = 3, 且 L = 5

   4.3) d = 1, k = 7, 且 L = 10

   4.4) d = 2, k = 7, 且 L = 10

5. 设以下数据序列是用(0, G/I)型RLL码编码的，求γ的参数G和I：

   5.1) γ = {10101000101001100101}

   5.2) γ = {10010100001101001100111101}

   5.3) γ = {11100011001010001001100101}

6. 为(0, 1)型RLL码创建编码和解码查找表，其中每次编码后的数据长度为 L = 2，并求码效率。

7. 为(1, 2)型RLL码创建编码和解码查找表，其中每次编码后的数据长度为 L = 3，并求码效率。

8. 为(1, 3)型RLL码创建编码和解码查找表，其中每次编码后的数据长度为 L = 4，并求码效率。
