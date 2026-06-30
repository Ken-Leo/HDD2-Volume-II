# 附录

## 附录A

## Q函数表

Q(x)函数可以表示为高斯随机变量的累积分布函数形式，在统计学和工程学领域中被广泛使用。Q(x)函数定义如下：

$$
Q ( x ) = { \frac { 1 } { \sqrt { 2 \pi } } } \int _ { x } ^ { \infty } \exp \left\{ - { \frac { y ^ { 2 } } { 2 } } \right\} d y\tag{ก.1}
$$

这是高斯概率密度函数的尾部积分，其中exp[ ]是指数函数。通常，对于不同的x值，Q(x)函数的值可以通过查找表获得。但在x > 3的情况下，Q(x)函数可以近似如下：

$$
Q ( x ) \approx \frac { 1 } { x \sqrt { 2 \pi } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\}\tag{ก.2}
$$

下表显示了 $0 \leq x \leq 3.59$ 范围内Q(x)函数的值。

<table><tr><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">0.50000</td><td colspan="1" rowspan="1">0.36</td><td colspan="1" rowspan="1">0.35942</td><td colspan="1" rowspan="1">0.72</td><td colspan="1" rowspan="1">0.23576</td><td colspan="1" rowspan="1">1.08</td><td colspan="1" rowspan="1">0.14007</td><td colspan="1" rowspan="1">1.44</td><td colspan="1" rowspan="1">0.0749340</td></tr><tr><td colspan="1" rowspan="1">0.01</td><td colspan="1" rowspan="1">0.49601</td><td colspan="1" rowspan="1">0.37</td><td colspan="1" rowspan="1">0.35569</td><td colspan="1" rowspan="1">0.73</td><td colspan="1" rowspan="1">0.23270</td><td colspan="1" rowspan="1">1.09</td><td colspan="1" rowspan="1">0.13786</td><td colspan="1" rowspan="1">1.45</td><td colspan="1" rowspan="1">0.0735290</td></tr><tr><td colspan="1" rowspan="1">0.02</td><td colspan="1" rowspan="1">0.49202</td><td colspan="1" rowspan="1">0.38</td><td colspan="1" rowspan="1">0.35197</td><td colspan="1" rowspan="1">0.74</td><td colspan="1" rowspan="1">0.22965</td><td colspan="1" rowspan="1">1.10</td><td colspan="1" rowspan="1">0.13567</td><td colspan="1" rowspan="1">1.46</td><td colspan="1" rowspan="1">0.0721450</td></tr><tr><td colspan="1" rowspan="1">0.03</td><td colspan="1" rowspan="1">0.48803</td><td colspan="1" rowspan="1">0.39</td><td colspan="1" rowspan="1">0.34827</td><td colspan="1" rowspan="1">0.75</td><td colspan="1" rowspan="1">0.22663</td><td colspan="1" rowspan="1">1.11</td><td colspan="1" rowspan="1">0.133500</td><td colspan="1" rowspan="1">1.47</td><td colspan="1" rowspan="1">0.070781</td></tr><tr><td colspan="1" rowspan="1">0.04</td><td colspan="1" rowspan="1">0.48405</td><td colspan="1" rowspan="1">0.40</td><td colspan="1" rowspan="1">0.34458</td><td colspan="1" rowspan="1">0.76</td><td colspan="1" rowspan="1">0.22363</td><td colspan="1" rowspan="1">1.12</td><td colspan="1" rowspan="1">0.131360</td><td colspan="1" rowspan="1">1.48</td><td colspan="1" rowspan="1">0.069437</td></tr><tr><td colspan="1" rowspan="1">0.05</td><td colspan="1" rowspan="1">0.48006</td><td colspan="1" rowspan="1">0.41</td><td colspan="1" rowspan="1">0.34090</td><td colspan="1" rowspan="1">0.77</td><td colspan="1" rowspan="1">0.22065</td><td colspan="1" rowspan="1">1.13</td><td colspan="1" rowspan="1">0.129240</td><td colspan="1" rowspan="1">1.49</td><td colspan="1" rowspan="1">0.068112</td></tr><tr><td colspan="1" rowspan="1">0.06</td><td colspan="1" rowspan="1">0.47608</td><td colspan="1" rowspan="1">0.42</td><td colspan="1" rowspan="1">0.33724</td><td colspan="1" rowspan="1">0.78</td><td colspan="1" rowspan="1">0.21770</td><td colspan="1" rowspan="1">1.14</td><td colspan="1" rowspan="1">0.127140</td><td colspan="1" rowspan="1">1.50</td><td colspan="1" rowspan="1">0.066807</td></tr><tr><td colspan="1" rowspan="1">0.07</td><td colspan="1" rowspan="1">0.47210</td><td colspan="1" rowspan="1">0.43</td><td colspan="1" rowspan="1">0.33360</td><td colspan="1" rowspan="1">0.79</td><td colspan="1" rowspan="1">0.21476</td><td colspan="1" rowspan="1">1.15</td><td colspan="1" rowspan="1">0.125070</td><td colspan="1" rowspan="1">1.51</td><td colspan="1" rowspan="1">0.065522</td></tr><tr><td colspan="1" rowspan="1">0.08</td><td colspan="1" rowspan="1">0.46812</td><td colspan="1" rowspan="1">0.44</td><td colspan="1" rowspan="1">0.32997</td><td colspan="1" rowspan="1">0.80</td><td colspan="1" rowspan="1">0.21186</td><td colspan="1" rowspan="1">1.16</td><td colspan="1" rowspan="1">0.123020</td><td colspan="1" rowspan="1">1.52</td><td colspan="1" rowspan="1">0.064256</td></tr><tr><td colspan="1" rowspan="1">0.09</td><td colspan="1" rowspan="1">0.46414</td><td colspan="1" rowspan="1">0.45</td><td colspan="1" rowspan="1">0.32636</td><td colspan="1" rowspan="1">0.81</td><td colspan="1" rowspan="1">0.20897</td><td colspan="1" rowspan="1">1.17</td><td colspan="1" rowspan="1">0.121000</td><td colspan="1" rowspan="1">1.53</td><td colspan="1" rowspan="1">0.063008</td></tr><tr><td colspan="1" rowspan="1">0.10</td><td colspan="1" rowspan="1">0.46017</td><td colspan="1" rowspan="1">0.46</td><td colspan="1" rowspan="1">0.32276</td><td colspan="1" rowspan="1">0.82</td><td colspan="1" rowspan="1">0.20611</td><td colspan="1" rowspan="1">1.18</td><td colspan="1" rowspan="1">0.119000</td><td colspan="1" rowspan="1">1.54</td><td colspan="1" rowspan="1">0.061780</td></tr><tr><td colspan="1" rowspan="1">0.11</td><td colspan="1" rowspan="1">0.45620</td><td colspan="1" rowspan="1">0.47</td><td colspan="1" rowspan="1">0.31918</td><td colspan="1" rowspan="1">0.83</td><td colspan="1" rowspan="1">0.20327</td><td colspan="1" rowspan="1">1.19</td><td colspan="1" rowspan="1">0.117020</td><td colspan="1" rowspan="1">1.55</td><td colspan="1" rowspan="1">0.060571</td></tr><tr><td colspan="1" rowspan="1">0.12</td><td colspan="1" rowspan="1">0.45224</td><td colspan="1" rowspan="1">0.48</td><td colspan="1" rowspan="1">0.31561</td><td colspan="1" rowspan="1">0.84</td><td colspan="1" rowspan="1">0.20045</td><td colspan="1" rowspan="1">1.20</td><td colspan="1" rowspan="1">0.115070</td><td colspan="1" rowspan="1">1.56</td><td colspan="1" rowspan="1">0.059380</td></tr><tr><td colspan="1" rowspan="1">0.13</td><td colspan="1" rowspan="1">0.44828</td><td colspan="1" rowspan="1">0.49</td><td colspan="1" rowspan="1">0.31207</td><td colspan="1" rowspan="1">0.85</td><td colspan="1" rowspan="1">0.19766</td><td colspan="1" rowspan="1">1.21</td><td colspan="1" rowspan="1">0.113140</td><td colspan="1" rowspan="1">1.57</td><td colspan="1" rowspan="1">0.058208</td></tr><tr><td colspan="1" rowspan="1">0.14</td><td colspan="1" rowspan="1">0.44433</td><td colspan="1" rowspan="1">0.50</td><td colspan="1" rowspan="1">0.30854</td><td colspan="1" rowspan="1">0.86</td><td colspan="1" rowspan="1">0.19489</td><td colspan="1" rowspan="1">1.22</td><td colspan="1" rowspan="1">0.111230</td><td colspan="1" rowspan="1">1.58</td><td colspan="1" rowspan="1">0.057053</td></tr><tr><td colspan="1" rowspan="1">0.15</td><td colspan="1" rowspan="1">0.44038</td><td colspan="1" rowspan="1">0.51</td><td colspan="1" rowspan="1">0.30503</td><td colspan="1" rowspan="1">0.87</td><td colspan="1" rowspan="1">0.19215</td><td colspan="1" rowspan="1">1.23</td><td colspan="1" rowspan="1">0.109350</td><td colspan="1" rowspan="1">1.59</td><td colspan="1" rowspan="1">0.055917</td></tr><tr><td colspan="1" rowspan="1">0.16</td><td colspan="1" rowspan="1">0.43644</td><td colspan="1" rowspan="1">0.52</td><td colspan="1" rowspan="1">0.30153</td><td colspan="1" rowspan="1">0.88</td><td colspan="1" rowspan="1">0.18943</td><td colspan="1" rowspan="1">1.24</td><td colspan="1" rowspan="1">0.107490</td><td colspan="1" rowspan="1">1.60</td><td colspan="1" rowspan="1">0.054799</td></tr><tr><td colspan="1" rowspan="1">0.17</td><td colspan="1" rowspan="1">0.43251</td><td colspan="1" rowspan="1">0.53</td><td colspan="1" rowspan="1">0.29806</td><td colspan="1" rowspan="1">0.89</td><td colspan="1" rowspan="1">0.18673</td><td colspan="1" rowspan="1">1.25</td><td colspan="1" rowspan="1">0.105650</td><td colspan="1" rowspan="1">1.61</td><td colspan="1" rowspan="1">0.053699</td></tr><tr><td colspan="1" rowspan="1">0.18</td><td colspan="1" rowspan="1">0.42858</td><td colspan="1" rowspan="1">0.54</td><td colspan="1" rowspan="1">0.29460</td><td colspan="1" rowspan="1">0.90</td><td colspan="1" rowspan="1">0.18406</td><td colspan="1" rowspan="1">1.26</td><td colspan="1" rowspan="1">0.103830</td><td colspan="1" rowspan="1">1.62</td><td colspan="1" rowspan="1">0.052616</td></tr><tr><td colspan="1" rowspan="1">0.19</td><td colspan="1" rowspan="1">0.42465</td><td colspan="1" rowspan="1">0.55</td><td colspan="1" rowspan="1">0.29116</td><td colspan="1" rowspan="1">0.91</td><td colspan="1" rowspan="1">0.18141</td><td colspan="1" rowspan="1">1.27</td><td colspan="1" rowspan="1">0.102040</td><td colspan="1" rowspan="1">1.63</td><td colspan="1" rowspan="1">0.051551</td></tr><tr><td colspan="1" rowspan="1">0.20</td><td colspan="1" rowspan="1">0.42074</td><td colspan="1" rowspan="1">0.56</td><td colspan="1" rowspan="1">0.28774</td><td colspan="1" rowspan="1">0.92</td><td colspan="1" rowspan="1">0.17879</td><td colspan="1" rowspan="1">1.28</td><td colspan="1" rowspan="1">0.100270</td><td colspan="1" rowspan="1">1.64</td><td colspan="1" rowspan="1">0.050503</td></tr><tr><td colspan="1" rowspan="1">0.21</td><td colspan="1" rowspan="1">0.41683</td><td colspan="1" rowspan="1">0.57</td><td colspan="1" rowspan="1">0.28434</td><td colspan="1" rowspan="1">0.93</td><td colspan="1" rowspan="1">0.17619</td><td colspan="1" rowspan="1">1.29</td><td colspan="1" rowspan="1">0.098525</td><td colspan="1" rowspan="1">1.65</td><td colspan="1" rowspan="1">0.049471</td></tr><tr><td colspan="1" rowspan="1">0.22</td><td colspan="1" rowspan="1">0.41294</td><td colspan="1" rowspan="1">0.58</td><td colspan="1" rowspan="1">0.28096</td><td colspan="1" rowspan="1">0.94</td><td colspan="1" rowspan="1">0.17361</td><td colspan="1" rowspan="1">1.30</td><td colspan="1" rowspan="1">0.096800</td><td colspan="1" rowspan="1">1.66</td><td colspan="1" rowspan="1">0.048457</td></tr><tr><td colspan="1" rowspan="1">0.23</td><td colspan="1" rowspan="1">0.40905</td><td colspan="1" rowspan="1">0.59</td><td colspan="1" rowspan="1">0.27760</td><td colspan="1" rowspan="1">0.95</td><td colspan="1" rowspan="1">0.17106</td><td colspan="1" rowspan="1">1.31</td><td colspan="1" rowspan="1">0.095098</td><td colspan="1" rowspan="1">1.67</td><td colspan="1" rowspan="1">0.047460</td></tr><tr><td colspan="1" rowspan="1">0.24</td><td colspan="1" rowspan="1">0.40517</td><td colspan="1" rowspan="1">0.60</td><td colspan="1" rowspan="1">0.27425</td><td colspan="1" rowspan="1">0.96</td><td colspan="1" rowspan="1">0.16853</td><td colspan="1" rowspan="1">1.32</td><td colspan="1" rowspan="1">0.093418</td><td colspan="1" rowspan="1">1.68</td><td colspan="1" rowspan="1">0.046479</td></tr><tr><td colspan="1" rowspan="1">0.25</td><td colspan="1" rowspan="1">0.40129</td><td colspan="1" rowspan="1">0.61</td><td colspan="1" rowspan="1">0.27093</td><td colspan="1" rowspan="1">0.97</td><td colspan="1" rowspan="1">0.16602</td><td colspan="1" rowspan="1">1.33</td><td colspan="1" rowspan="1">0.091759</td><td colspan="1" rowspan="1">1.69</td><td colspan="1" rowspan="1">0.045514</td></tr><tr><td colspan="1" rowspan="1">0.26</td><td colspan="1" rowspan="1">0.39743</td><td colspan="1" rowspan="1">0.62</td><td colspan="1" rowspan="1">0.26763</td><td colspan="1" rowspan="1">0.98</td><td colspan="1" rowspan="1">0.16354</td><td colspan="1" rowspan="1">1.34</td><td colspan="1" rowspan="1">0.090123</td><td colspan="1" rowspan="1">1.70</td><td colspan="1" rowspan="1">0.044565</td></tr><tr><td colspan="1" rowspan="1">0.27</td><td colspan="1" rowspan="1">0.39358</td><td colspan="1" rowspan="1">0.63</td><td colspan="1" rowspan="1">0.26435</td><td colspan="1" rowspan="1">0.99</td><td colspan="1" rowspan="1">0.16109</td><td colspan="1" rowspan="1">1.35</td><td colspan="1" rowspan="1">0.088508</td><td colspan="1" rowspan="1">1.71</td><td colspan="1" rowspan="1">0.043632</td></tr><tr><td colspan="1" rowspan="1">0.28</td><td colspan="1" rowspan="1">0.38974</td><td colspan="1" rowspan="1">0.64</td><td colspan="1" rowspan="1">0.26109</td><td colspan="1" rowspan="1">1.00</td><td colspan="1" rowspan="1">0.15866</td><td colspan="1" rowspan="1">1.36</td><td colspan="1" rowspan="1">0.086915</td><td colspan="1" rowspan="1">1.72</td><td colspan="1" rowspan="1">0.042716</td></tr><tr><td colspan="1" rowspan="1">0.29</td><td colspan="1" rowspan="1">0.38591</td><td colspan="1" rowspan="1">0.65</td><td colspan="1" rowspan="1">0.25785</td><td colspan="1" rowspan="1">1.01</td><td colspan="1" rowspan="1">0.15625</td><td colspan="1" rowspan="1">1.37</td><td colspan="1" rowspan="1">0.085343</td><td colspan="1" rowspan="1">1.73</td><td colspan="1" rowspan="1">0.041815</td></tr><tr><td colspan="1" rowspan="1">0.30</td><td colspan="1" rowspan="1">0.38209</td><td colspan="1" rowspan="1">0.66</td><td colspan="1" rowspan="1">0.25463</td><td colspan="1" rowspan="1">1.02</td><td colspan="1" rowspan="1">0.15386</td><td colspan="1" rowspan="1">1.38</td><td colspan="1" rowspan="1">0.083793</td><td colspan="1" rowspan="1">1.74</td><td colspan="1" rowspan="1">0.040930</td></tr><tr><td colspan="1" rowspan="1">0.31</td><td colspan="1" rowspan="1">0.37828</td><td colspan="1" rowspan="1">0.67</td><td colspan="1" rowspan="1">0.25143</td><td colspan="1" rowspan="1">1.03</td><td colspan="1" rowspan="1">0.15151</td><td colspan="1" rowspan="1">1.39</td><td colspan="1" rowspan="1">0.082264</td><td colspan="1" rowspan="1">1.75</td><td colspan="1" rowspan="1">0.040059</td></tr><tr><td colspan="1" rowspan="1">0.32</td><td colspan="1" rowspan="1">0.37448</td><td colspan="1" rowspan="1">0.68</td><td colspan="1" rowspan="1">0.24825</td><td colspan="1" rowspan="1">1.04</td><td colspan="1" rowspan="1">0.14917</td><td colspan="1" rowspan="1">1.40</td><td colspan="1" rowspan="1">0.080757</td><td colspan="1" rowspan="1">1.76</td><td colspan="1" rowspan="1">0.039204</td></tr><tr><td colspan="1" rowspan="1">0.33</td><td colspan="1" rowspan="1">0.37070</td><td colspan="1" rowspan="1">0.69</td><td colspan="1" rowspan="1">0.24510</td><td colspan="1" rowspan="1">1.05</td><td colspan="1" rowspan="1">0.14686</td><td colspan="1" rowspan="1">1.41</td><td colspan="1" rowspan="1">0.079270</td><td colspan="1" rowspan="1">1.77</td><td colspan="1" rowspan="1">0.038364</td></tr><tr><td colspan="1" rowspan="1">0.34</td><td colspan="1" rowspan="1">0.36693</td><td colspan="1" rowspan="1">0.70</td><td colspan="1" rowspan="1">0.24196</td><td colspan="1" rowspan="1">1.06</td><td colspan="1" rowspan="1">0.14457</td><td colspan="1" rowspan="1">1.42</td><td colspan="1" rowspan="1">0.077804</td><td colspan="1" rowspan="1">1.78</td><td colspan="1" rowspan="1">0.037538</td></tr><tr><td colspan="1" rowspan="1">0.35</td><td colspan="1" rowspan="1">0.36317</td><td colspan="1" rowspan="1">0.71</td><td colspan="1" rowspan="1">0.23885</td><td colspan="1" rowspan="1">1.07</td><td colspan="1" rowspan="1">0.14231</td><td colspan="1" rowspan="1">1.43</td><td colspan="1" rowspan="1">0.076359</td><td colspan="1" rowspan="1">1.79</td><td colspan="1" rowspan="1">0.036727</td></tr></table>

## 附录B

# 重要数学公式

本附录列出了本书中用于硬盘驱动信号处理系统分析的常用数学公式。

## B.1 三角函数 (Trigonometric)

sin(−α) = − sin(α)   
cos(−α) = cos(α)   
sin(α) = cos(α − π/2)   
sin²(α) + cos²(α) = 1   
sin(α ± β) = sin(α) cos(β) ± cos(α) sin(β)   
cos(α ± β) = cos(α) cos(β) ∓ sin(α) sin(β)   
sin(α) sin(β) = ½ cos(α − β) − ½ cos(α + β)   
sin(α) cos(β) = ½ sin(α + β) + ½ sin(α − β)   
cos(α) cos(β) = ½ cos(α − β) + ½ cos(α + β)   
cos(α) sin(β) = ½ sin(α + β) − ½ sin(α − β)

$$
\begin{array} { r l } & { \sin ( 2 \alpha ) = 2 \sin ( \alpha ) \cos ( \alpha ) } \\ & { \cos ( 2 \alpha ) = \cos ^ { 2 } ( \alpha ) - \sin ^ { 2 } ( \alpha ) = 1 - 2 \sin ^ { 2 } ( \alpha ) = 2 \cos ^ { 2 } ( \alpha ) - 1 } \\ & { \sin ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 - \cos ( 2 \alpha ) \} } \\ & { \cos ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 + \cos ( 2 \alpha ) \} } \\ & { e ^ { j \alpha } - \cos ( \alpha ) + j \sin ( \alpha ) } \\ & { \sin ( \alpha ) = ( e ^ { j \alpha } - e ^ { - j \alpha } ) / ( 2 j ) } \\ & { \cos ( \alpha ) = ( e ^ { j \alpha } + e ^ { - j \alpha } ) / 2 } \end{array}
$$

## B.2 不定积分 (Indefinite Integral)

∫ u dv = uv − ∫ v du，其中 u 和 v 是 x 的函数   
∫ xⁿ dx = xⁿ⁺¹ / (n + 1)，其中 n ≠ −1   
∫ x⁻¹ dx = ln(x)   
∫ eᵃˣ dx = eᵃˣ /a   
∫ ln(x) dx = x ln(x) − x   
∫ x eᵃˣ dx = eᵃˣ(ax − 1)/a²   
∫ x² eᵃˣ dx = eᵃˣ (a²x² − 2ax + 2)/a³   
∫ sin(ax) dx = −(1/a) cos(ax)   
∫ cos(ax) dx = (1/a) sin(ax)   
∫ sin²(ax) dx = x/2 − sin(2ax)/4a   
∫ x sin(ax) dx = (1/a²){sin(ax) − ax cos(ax)}   
∫ cos²(ax) dx = x/2 + sin(2ax)/4a   
∫ x cos(ax) dx = (1/a²){cos(ax) + ax sin(ax)}

# 向量和矩阵的微分

本附录总结了向量和矩阵的微分公式，这对于本书中硬盘驱动信号处理系统的分析非常有用。

设 u 和 x 为大小为 $k \times 1$ 的列向量（即k行1列），A 为大小为 $k \times k$ 的方阵。由向量和矩阵的微分可得如下关系式：

$$
\mathbf { x } ^ { \mathrm { T } } \mathbf { u } = \mathbf { u } ^ { \mathrm { T } } \mathbf { x }\tag{ค.1}
$$

$$
\frac { \partial \left( \mathbf { x } ^ { \mathrm { { T } } } \mathbf { u } \right) } { \partial \mathbf { u } } = \mathbf { x }\tag{ค.2}
$$

$$
\frac { \partial \left( \mathbf { A u } \right) } { \partial \mathbf { u } } = \mathbf { A } ^ { \mathrm { T } }\tag{ค.3}
$$

$$
\frac { \partial \left( \mathbf { A u } \right) } { \partial \mathbf { u } ^ { \mathrm { T } } } = \mathbf { A }\tag{ค.4}
$$

以及

$$
{ \frac { \partial \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A } \mathbf { u } \right) } { \partial \mathbf { u } } } = \left( \mathbf { A } + \mathbf { A } ^ { \mathrm { T } } \right) \mathbf { u }\tag{ค.5}
$$

若 $\mathbf { A } = \mathbf { A } ^ { \mathrm { T } }$，则可得

$$
\frac { \partial \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A u } \right) } { \partial \mathbf { u } } = 2 \mathbf { A u }\tag{ค.6}
$$

以及

$$
\frac { \partial ^ { 2 } \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A } \mathbf { u } \right) } { \partial \mathbf { u } \partial \mathbf { u } ^ { \mathrm { T } } } = 2 \mathbf { A }\tag{ค.7}
$$

## 附录D

## 技术词汇

写过程/กระบวนการเขียน — write process

最小化过程/กระบวนการทำให้มีค่าน้อยสุด — minimization process

噪声预测过程/กระบวนการในการทำนายสัญญาณรบกวน — noise prediction process

噪声白化过程/กระบวนการในการทำให้สัญญาณรบกวนเป็นสีขาว — noise whitening process

读过程/กระบวนการอ่าน — read process

写电流/กระแสไฟฟ้าเขียน — write current

数据包/กลุ่มข้อมูล — data packet

脉冲编码调制/การกล้ำรหัสพัลส์ — PCM (pulse code modulation)

调制/การกล้ำสัญญาณ (การมอดูเลต) — modulation

噪声增强/การขยายสัญญาณรบกวน — noise enhancement

同步/การเข้าจังหวะ — synchronization

完全同步/การเข้าจังหวะอย่างสมบูรณ์ — perfect synchronization

期望/การคาดหมาย, ค่าคาดหมาย — expectation

数据存储/การจัดเก็บข้อมูล — data storage

数字数据存储/การจัดเก็บข้อมูลดิจิทัล — digital data storage

投影/การฉาย — projection

采样/การชักตัวอย่าง — sampling

随机游走/การเดินแบบสุ่ม — random walk

捕获/การได้มา — acquisition

序列检测/การตรวจหาลำดับ — sequence detection

跟踪/การติดตาม — tracking

噪声预测/การทำนายสัญญาณรบกวน — noise prediction   
干扰/การแทรกสอด — interference   
码间串扰/การแทรกสอดระหว่างสัญลักษณ์ — ISI (intersymbol interference)   
加-比-选/การบวก-การเปรียบเทียบ-การเลือก — ACS (add-compare-select)   
记录/การบันทึก — recording   
垂直记录/การบันทึกแบบแนวตั้ง — perpendicular recording   
水平记录/การบันทึกแบบแนวนอน — longitudinal recording   
二进制记录/การบันทึกแบบไบนารี — binary recording   
磁记录/การบันทึกระบบแม่เหล็ก — magnetic recording   
逐幸存处理/การประมวลผลแบบเพอเซอร์ไวเวอร์ — PSP (per-survivor processing)   
数字信号处理/การประมวลผลสัญญาณดิจิทัล — digital signal processing   
定时调整/การปรับค่าทางเวลา — timing adjustment   
反馈/การป้อนกลับ — feedback   
判决反馈/การป้อนกลับค่าตัดสินใจ — decision feedback   
转移/การเปลี่ยนสถานะ — transition   
孤立转移/การเปลี่ยนสถานะเอกเทศ — isolated transition   
Z变换/การแปลงซี — Z transform   
傅里叶变换/การแปลงฟูเรียร์ — Fourier transform   
连续时间傅里叶变换/การแปลงฟูเรียร์ที่ต่อเนื่องทางเวลา — continuous-time Fourier transform   
差错传播/การแพร่กระจายของข้อผิดพลาด — error propagation   
扰动/การรบกวน — disturbance   
退磁/การลบล้างสภาพแม่เหล็ก — demagnetization   
转移偏移/การเลื่อนตำแหน่งของการเปลี่ยนสถานะ — transition shift   
随机转移偏移/การเลื่อนตำแหน่งของการเปลี่ยนสถานะแบบสุ่ม — random transition shift   
判决延迟/การหน่วงเวลาการตัดสินใจ — decision delay   
微分/การหาอนุพันธ์ — differentiation   
功率/กำลัง — power   
高斯/เกาส์เซียน — Gaussian   
幅度/ขนาด — magnitude   
误差/ข้อผิดพลาด — error   
预测误差/ข้อผิดพลาดการทำนาย — prediction error   
均方误差/ข้อผิดพลาดกำลังสองเฉลี่ย — MSE (mean-squared error)   
最小均方误差/ข้อผิดพลาดกำลังสองเฉลี่ยที่น้อยสุด — MMSE (minimum mean-squared error)   
频率误差/ข้อผิดพลาดทางความถี่ — frequency error   
相位误差/ข้อผิดพลาดทางเฟส — phase error   
定时误差/ข้อผิดพลาดทางเวลา — timing error   
残余定时误差/ข้อผิดพลาดทางเวลาที่หลงเหลืออยู่ — residual timing error   
二进制数据/ข้อมูลไบนารี — binary data   
离散数据/ข้อมูลวิยุต (แซมเปิล) — discrete data   
最大似然/ควรจะเป็นมากสุด — ML (maximum-likelihood)   
容量/ความจุ — capacity   
信道容量/ความจุช่องสัญญาณ — channel capacity   
复杂度/ความซับซ้อน — complexity   
采样率/ความถี่การชักตัวอย่าง — sampling rate / cut-off frequency   
归一化频率/ความถี่แบบนอร์มอลไลซ์ — normalized frequency   
奈奎斯特频率/ความถี่ไนควิตส์ — Nyquist frequency   
概率/ความน่าจะเป็น — probability   
差错概率/ความน่าจะเป็นของข้อผิดพลาด — probability of error   
序列差错概率/ความน่าจะเป็นของข้อผิดพลาดลำดับ — probability of sequence error   
方差/ความแปรปรวน — variance   
非线性/ความไม่เป็นเชิงเส้น — nonlinearity   
堆积密度/ความหนาแน่นการบรรจุ — packing density   
归一化记录密度/ความหนาแน่นของการบันทึกแบบนอร์มอลไลซ์ — ND (normalized recording density)   
面密度/ความหนาแน่นเชิงพื้นที่ — areal density   
功率谱密度/ความหนาแน่นสเปกตรัมกำลัง — power spectral density   
卷积/คอนโวลูชัน — convolution   
均方/ค่ากำลังสองเฉลี่ย — mean square   
均值/ค่าเฉลี่ย — mean   
判决/ค่าตัดสินใจ — decision   
瞬时硬判决/ค่าตัดสินใจขณะหนึ่งแบบแข็ง — instantaneous hard decision   
周期/คาบ (เวลา) — period   
采样周期/คาบการชักตัวอย่าง — sampling period   
比特周期/คาบเวลาของบิต — bit period   
分支度量/ค่าเมตริกสาขา — branch metric   
路径度量/ค่าเมตริกเส้นทาง — path metric   
特征值/ค่าลักษณะเฉพาะ — eigenvalue   
有限状态机/เครื่องสถานะจำกัด — FSM (finite state machine)   
同步标记/เครื่องหมายเข้าจังหวะ — sync mark   
应用/งานประยุกต์ (แอพลิเคชัน) — application   
约束/เงื่อนไขบังคับ — constraint   
首一约束/เงื่อนไขบังคับแบบโมนิก — monic constraint   
磁盘/จาน (จานบันทึก) — disk   
磁盘/磁记录盘/จานบันทึกแม่เหล็ก — magnetic disk   
抖动/จิตเตอร์ — jitter   
定时抖动/จิตเตอร์ทางเวลา — timing jitter   
节点/จุดต่อ — node   
平衡点/จุดสมดุล — equilibrium point   
稳定点/จุดเสถียรภาพ — stable point   
信道/ช่องสัญญาณ — channel   
离散信道/ช่องสัญญาณวิยุต — discrete channel   
通信信道/ช่องสัญญาณสื่อสาร — communication channel   
读信道/ช่องสัญญาณอ่าน — read channel   
读通道芯片/ซิปช่องสัญญาณอ่าน — read-channel chip   
线性/เชิงเส้น — linear   
重叠/ซ้อนเหลื่อม — overlap   
超顺磁/ซูเปอร์พาราแมกเนติก — superparamagnetic   
扇区/เซกเตอร์ — sector   
样本/แซมเปิล, ตัวอย่าง — sample   
周跳/ไซเคิลสลิป — cycle slip   
数字/ดิจิทัล — digital   
行列式/ดีเทอร์มิแนนต์ — determinant   
分贝/เดซิเบล — dB (decibel)   
域/โดเมน — domain   
D域/โดเมน D — D domain   
Z域/โดเมน Z — Z domain   
频域/โดเมนความถี่ — frequency domain   
时域/โดเมนเวลา — time domain   
拉格朗日乘子/ตัวคูณลากรานจ์ — Lagrange multiplier   
指示符/ตัวชีบอก — indicator   
卷积算子/ตัวดำเนินการคอนโวลูชัน — convolution operator   
期望算子/ตัวดำเนินการค่าคาดหมาย — expectation operator   
延迟算子/ตัวดำเนินการหน่วงเวลา — delay operator   
前驱/ตัวนำหน้า — predecessor   
查找表/ตารางค้นหา — look-up table   
响应/ผลตอบสนอง — response   
转移响应/ผลตอบสนองการเปลี่ยนสถานะ — transition response   
系统响应/ผลตอบสนองของระบบ — system response   
频率响应/ผลตอบสนองเชิงความถี่ — frequency response   
双位响应/ผลตอบสนองไดบิต — dibit response   
目标响应/ผลตอบสนองทาร์เก็ต — target response   
部分响应/ผลตอบสนองบางส่วน — PR (partial response)   
部分响应最大似然/ผลตอบสนองบางส่วนควรจะเป็นมากสุด — PRML (partial-response maximum-likelihood)   
广义部分响应/ผลตอบสนองบางส่วนแบบทั่วไป — GPR (generalized partial-response)   
冲激响应/ผลตอบสนองอิมพัลส์ — impulse response   
有限冲激响应/ผลตอบสนองอิมพัลส์จำกัด — FIR (finite impulse response)   
无限冲激响应/ผลตอบสนองอิมพัลส์ไม่จำกัด — IIR (infinite impulse response)   
光盘/แผ่นซีดี — CD (compact disc)   
数字多功能光盘/แผ่นดีวีดี — DVD (digital versatile disc)   
软盘/แผ่นบันทึกแม่เหล็ก — magnetic floppy disk   
图/แผนภาพ — diagram   
网格图/แผนภาพเทรลลิส — trellis diagram   
能量/พลังงาน — energy   
单位能量/พลังงานหนึ่งหน่วย — unit energy   
多项式/พหุนาม (โพลิโนเมียล) — polynomial   
逐幸存定时恢复/เพอเซอร์ไวเวอร์ไทมมิ่งริคัฟเวอรี — per-survivor timing recovery   
迭代逐幸存定时恢复/เพอเซอร์ไวเวอร์ไทมมิ่งริคัฟเวอรีแบบทำงานซ้ำ — per-survivor iterative timing recovery   
极点/โพล — pole   
磁通/ฟลักซ์ — flux   
函数/ฟังก์ชัน — function   
阶跃函数/ฟังก์ชันขั้นบันได — step function   
概率密度函数/ฟังก์ชันความหนาแน่นความน่าจะเป็น — probability density function   
高斯概率密度函数/ฟังก์ชันความหนาแน่นความน่าจะเป็นแบบเกาส์เซียน — Gaussian probability density function   
克罗内克δ函数/ฟังก์ชันโครเนคเกอร์เดลตา — Kronecker delta function   
狄拉克δ函数/ฟังก์ชันไดเรคเดลตา — Dirac delta function   
传递函数/ฟังก์ชันถ่ายโอน — transfer function   
冲激函数/ฟังก์ชันอิมพัลส์ — impulse function   
直流/ไฟฟ้ากระแสตรง — d.c. (direct current)   
模式/ภาวะ — mode   
捕获模式/ภาวะการได้มา — acquisition mode   
完全捕获/ภาวะการได้มาแบบสมบูรณ์ — perfect acquisition   
跟踪模式/ภาวะการติดตาม — tracking mode   
训练模式/ภาวะการฝึกอบรม — training mode   
度量/เมตริก (ตัววัด) — metric   
状态转移矩阵/เมทริกซ์การเปลี่ยนสถานะ — state transition matrix   
互相关矩阵/เมทริกซ์สหสัมพันธ์ข้าม — cross-correlation matrix   
自相关矩阵/เมทริกซ์อัตสหสัมพันธ์ — auto-correlation matrix   
单位矩阵/เมทริกซ์เอกลักษณ์ — identity matrix   
异步/ไม่เข้าจังหวะ — asynchronous   
不相关/ไม่มีสหสัมพันธ์กัน — uncorrelated   
纠错码/รหัสแก้ไขข้อผิดพลาด — ECC (error-correction code)   
卷积码/รหัสคอนโวลูชัน — convolutional code   
调制码/รหัสมอดูเลชัน — modulation code   
阈值电平/ระดับขีดเริ่มเปลี่ยน — threshold level   
数据存储系统/ระบบการจัดเก็บข้อมูล — data storage system   
磁记录系统/ระบบการบันทึกแม่เหล็ก — magnetic recording system   
编码系统/ระบบที่ถูกเข้ารหัส — coded system   
带限系统/ระบบที่มีแถบความถี่จำกัด — band-limited system   
未编码系统/ระบบที่ไม่ได้ถูกเข้ารหัส — uncoded system   
数字通信系统/ระบบสื่อสารดิจิทัล — digital communication system   
级/ระยะ — stage   
均方距离/ระยะทางกำลังสองเฉลี่ย — MSD (mean-squared distance)   
有效距离/ระยะทางประสิทธิผล — effective distance   
有效距离平方/ระยะทางประสิทธิผลกำลังสอง — squared effective distance   
欧氏距离/ระยะทางยุคลิด — Euclidean distance   
欧氏距离平方/ระยะทางยุคลิดกำลังสอง — squared Euclidean distance   
均方根/รากกำลังสองเฉลี่ย — RMS (root mean square)   
波形/รูปคลื่น — waveform   
移位寄存器/เรจิสเตอร์แบบเลื่อน — shift register   
自然对数/ลอการิทึมธรรมชาติ — natural logarithm   
试错法/ลองผิดลองถูก — trial and error   
序列/ลำดับ — sequence   
差错序列/ลำดับข้อผิดพลาด — error sequence   
输入差错序列/ลำดับข้อผิดพลาดอินพุต — input error sequence   
有效输入差错序列/ลำดับข้อผิดพลาดอินพุตที่ถูกต้อง — valid input error sequence   
数据序列/ลำดับข้อมูล — data sequence   
奇子序列/ลำดับข้อมูลย่อยเลขคี่ — odd subsequence   
偶子序列/ลำดับข้อมูลย่อยเลขคู่ — even subsequence   
压控振荡器/วงจร VCO — VCO (voltage-controlled oscillator)   
滤波器/วงจรกรอง — filter   
内插滤波器/วงจรกรองการประมาณค่าในช่วง — interpolation filter   
预测误差滤波器/วงจรกรองข้อผิดพลาดการทำนาย — prediction error filter   
预测滤波器/วงจรกรองทำนาย — predictor filter   
噪声白化滤波器/วงจรกรองในการทำให้สัญญาณรบกวนเป็นสีขาว — noise whitening filter   
线性滤波器/วงจรกรองแบบเชิงเส้น — linear filter   
低通滤波器/วงจรกรองผ่านต่ำ — LPF (low-pass filter)   
理想低通滤波器/วงจรกรองผ่านต่ำอุดมคติ — ideal low-pass filter   
环路滤波器/วงจรกรองลูป — loop filter   
编码器/วงจรเข้ารหัส — encoder   
纠错码编码器/วงจรเข้ารหัสแก้ไขข้อผิดพลาด — error-correction code (ECC) encoder   
调制编码器/วงจรเข้ารหัสมอดูเลชัน — modulation encoder   
采样器/วงจรชักตัวอย่าง — sampler   
检测器/วงจรตรวจหา — detector   
定时误差检测器/วงจรตรวจหาข้อผิดพลาดทางเวลา — TED (timing error detector)   
无记忆阈值检测器/วงจรตรวจหาขีดเริ่มเปลี่ยนที่ไม่มีหน่วยความจำ — memoryless threshold detector   
多电平无记忆阈值检测器/วงจรตรวจหาขีดเริ่มเปลี่ยนที่ไม่มีหน่วยความจำแบบหลายระดับ — multi-level memoryless threshold detector   
多电平阈值检测器/วงจรตรวจหาขีดเริ่มเปลี่ยนแบบหลายระดับ — multi-level threshold detector   
峰值检测器/วงจรตรวจหาจุดสูงสุด — peak detector   
序列检测器/วงจรตรวจหาลำดับ — sequence detector   
最大似然序列检测器/วงจรตรวจหาลำดับที่ควรจะเป็นมากสุด — MLSD (maximum-likelihood sequence detector)   
最优序列检测器/วงจรตรวจหาลำดับที่เหมาะที่สุด — optimal sequence detector   
维特比检测器/วงจรตรวจหาวีเทอร์บิ — Viterbi detector   
符号检测器/วงจรตรวจหาสัญลักษณ์ — symbol detector   
最优检测器/วงจรตรวจหาที่เหมาะที่สุด — optimal detector   
译码器/วงจรถอดรหัส — decoder   
纠错码译码器/วงจรถอดรหัสแก้ไขข้อผิดพลาด — error-correction code (ECC) decoder   
调制译码器/วงจรถอดรหัสมอดเลชัน — modulation decoder   
线性一步预测滤波器/วงจรกรองทำนายหนึ่งขั้นแบบเชิงเส้น — linear one-step predictor   
模数转换器/วงจรเปลี่ยนสัญญาณแอนะล็อกเป็นสัญญาณดิจิทัล — ADC (analog-to-digital converter)   
锁相环/วงจรเฟสล็อกลูป — PLL (phase-locked loop)   
接收机/วงจรภาครับ — receiver   
发射机/วงจรภาคส่ง — transmitter   
调制器/วงจรมอดูเลเตอร์ — modulator   
微分器/วงจรหาอนุพันธ์ — differentiator   
特征向量/เวกเตอร์ลักษณะเฉพาะ — eigenvector   
归一化特征向量/เวกเตอร์ลักษณะเฉพาะแบบนอร์มอลไลซ์ — normalized eigenvector   
平稳/สเตชันเนรี — stationary   
状态/สถานะ — state   
下一状态/สถานะต่อไป — next state   
起始状态/สถานะเริ่มต้น — start state   
读通道架构/สถาปัตยกรรมช่องสัญญาณอ่าน — read-channel architecture   
谱零点/สเปกตรัมค่าศูนย์ — spectral null   
磁化/สภาพความเป็นแม่เหล็ก (การทำให้เป็นแม่เหล็ก) — magnetization   
介质磁化/สภาพความเป็นแม่เหล็กของสื่อบันทึก — medium magnetization   
矫顽力/สภาพลบล้างแม่เหล็ก — coercivity   
磁导率/สภาพให้ซึมผ่านได้ — permeability   
正规方程/สมการนอร์มอล — normal equation   
更新方程/สมการปรับค่า — update equation   
转置/สลับเปลี่ยน (ทรานสโพส) — transpose   
分量/ส่วนประกอบ — component   
相关/สหสัมพันธ์ — correlation   
互相关/สหสัมพันธ์ข้าม — cross-correlation   
信号/สัญญาณ — signal   
二进制信号/สัญญาณไบนารี (สัญญาณสองระดับ) — binary signal   
双位脉冲/สัญญาณพัลส์ไดบิต — dibit pulse   
理想奈奎斯特脉冲/สัญญาณพัลส์ไนควิตส์อุดมคติ — ideal Nyquist pulse   
转移脉冲/สัญญาณพัลส์เปลี่ยนสถานะ — transition pulse   
孤立转移脉冲/สัญญาณพัลส์เปลี่ยนสถานะเอกเทศ — isolated transition pulse   
噪声/สัญญาณรบกวน — noise   
转移噪声/สัญญาณรบกวนการเปลี่ยนสถานะ — transition noise   
白色高斯噪声/สัญญาณรบกวนเกาส์สีขาว — white Gaussian noise   
加性白高斯噪声/สัญญาณรบกวนเกาส์สีขาวแบบบวก — AWGN (additive white Gaussian noise)   
热噪声/สัญญาณรบกวนความร้อน — thermal noise   
介质抖动噪声/สัญญาณรบกวนจิตเตอร์ของสื่อบันทึก — media jitter noise   
模式相关噪声/สัญญาณรบกวนที่ขึ้นอยู่กับแบบข้อมูล — pattern-dependent noise   
带外噪声/สัญญาณรบกวนที่อยู่นอกแถบความถี่ — out-of-band noise   
有色噪声/สัญญาณรบกวนแบบสี — colored noise   
白噪声/สัญญาณรบกวนสีขาว — white noise   
介质噪声/สัญญาณรบกวนสื่อบันทึก — media noise   
回读信号/สัญญาณแอนะล็อกทางไฟฟ้าที่ได้จากหัวอ่าน (สัญญาณ read-back) — read-back signal   
系数/สัมประสิทธิ์ — coefficient   
介质/สื่อบันทึก (จานแม่เหล็ก) — media (or medium)   
稳定/เสถียรภาพ — stable   
S曲线/เส้นโค้งรูปตัวเอส — S-curve   
幸存路径/เส้นทางที่ยังมีชีวิตอยู่ — survivor path   
分支/เส้นสาขา — branch   
延迟/หน่วงเวลา — delay   
信道记忆长度/หน่วยความจำของช่องสัญญาณ — channel memory   
路径记忆长度/หน่วยความจำเส้นทาง — path memory   
正交性原理/หลักการเชิงตั้งฉาก — Orthogonality principle   
写磁头/หัวเขียน — write head   
读磁头/หัวอ่าน — read head   
事件/เหตุการณ์ — event   
差错事件/เหตุการณ์ข้อผิดพลาด — error event   
主导差错事件/เหตุการณ์ข้อผิดพลาดที่โดดเด่น — dominant error event   
信源/แหล่งต้นทาง — source   
信宿/แหล่งปลายทาง — destination   
频率偏移/ออฟเซตทางความถี่ — frequency offset   
相位偏移/ออฟเซตทางเฟส — phase offset   
采样相位偏移/ออฟเซตทางเฟสของการชักตัวอย่าง — sampling phase offset   
定时偏移/ออฟเซตทางเวลา — timing offset   
增益/อัตราการขยาย — gain   
采样率/อัตราการชักตัวอย่าง — sampling rate   
过采样率/อัตราการชักตัวอย่างแบบเกินจริง — oversampling rate   
收敛速度/อัตราการลู่เข้า — convergence rate   
误比特率/อัตราข้อผิดพลาดบิต — BER (bit-error rate)   
渐近信息率/อัตราข่าวสารเชิงเส้นกำกับ — asymptotic information rate   
密度比/อัตราความหนาแน่น — density ratio   
比特率/อัตราบิต — bit rate   
码率/อัตรารหัส — code rate   
数据率/อัตราส่งข้อมูล — data rate   
信噪比/อัตราส่วนค่ากำลังเฉลี่ยของสัญญาณที่ต้องการต่อค่ากำลังเฉลี่ยของสัญญาณรบกวน — SNR (signal-to-noise ratio)   
自相关/อัตสหสัมพันธุ์ — auto-correlation   
算法/อัลกอริทึม (ขั้นตอนวิธี) — algorithm   
维特比算法/อัลกอริทึมวีเทอร์บิ — Viterbi algorithm   
感应式/อินดักทีฟ (ประเภทของหัวอ่าน) — inductive   
输入/อินพุต (รับเข้า, นำเข้า) — input   
饱和/อิ่มตัว — saturated   
完全均衡/อีควอไลเซซันแบบสมบูรณ์ — perfect equalization   
均衡器/อีควอไลเซอร์ — equalizer   
部分响应均衡器/อีควอไลเซอร์แบบ PR — partial-response (PR) equalizer   
全响应均衡器/อีควอไลเซอร์แบบผลตอบสนองเต็ม — full-response equalizer   
输出/เอาต์พุต (ส่งออก, นำออก) — output   
信道输出/เอาต์พุตของช่องสัญญาณ — channel output   
模拟/แอนะล็อก — analog   
硬盘驱动器/ฮาร์ดดิสก์ไดรฟ์ — hard disk drive   
赫兹/เฮิรตซ์ — Hz (hertz)

目标/ทาร์เก็ต — target   
最优目标/ทาร์เก็ตที่เหมาะที่สุด — optimal target   
广义部分响应目标/ทาร์เก็ตแบบ GPR — generalized partial-response (GPR) target   
部分响应目标/ทาร์เก็ตแบบ PR — partial-response (PR) target   
归一化/ทำให้เป็นบรรทัดฐาน — normalize   
内插技术/เทคนิคการประมาณค่าในช่วง — interpolation technique   
太字节/เทระไบต์ — TB (terabyte)   
抽头/แท็ป — tap   
定时函数/ไทมมิ่งฟังก์ชัน — timing function   
归一化定时函数/ไทมมิ่งฟังก์ชันแบบนอร์มอลไลซ์ — normalized timing function   
定时恢复/ไทมมิ่งริคัฟเวอรี — timing recovery   
传统定时恢复/ไทมมิ่งริคัฟเวอรีแบบที่ใช้กันทั่วไป — conventional timing recovery   
演绎定时恢复/ไทมมิ่งริคัฟเวอรีแบบนิรนัย — deductive timing recovery   
内插定时恢复/ไทมมิ่งริคัฟเวอรีแบบประมาณค่าในช่วง — interpolated timing recovery   
归纳定时恢复/ไทมมิ่งริคัฟเวอรีแบบอุปนัย — inductive timing recovery   
定时环路/ไทมมิ่งลูป — timing loop   
比特/บิต — bit   
消息比特/บิตข่าวสาร — message bit   
比特单元/บิตเซลล์ (คาบของเวลาในหนึ่งบิต) — bit cell   
转移比特/บิตเปลี่ยนสถานะ — transition bit   
冗余比特/บิตส่วนเกิน — redundant bit   
带宽/แบนด์วิดท์ — bandwidth   
零过剩带宽/แบนด์วิดท์เกินเป็นศูนย์ — zero-excess-bandwidth   
环路带宽/แบนด์วิดท์ของลูป — loop bandwidth   
数据模式/แบบข้อมูล — data pattern   
模型/แบบจำลอง — model   
线性化锁相环模型/แบบจำลองการทำงานของวงจรเฟสล็อกลูปแบบเชิงเส้น — linearized phase-locked loop (PLL) model   
等效离散时间信道模型/แบบจำลองช่องสัญญาณที่ไม่ต่อเนื่องทางเวลาแบบสมมูล — equivalent discrete-time channel model   
实际信道模型/แบบจำลองช่องสัญญาณเสมือนจริง — realistic channel model   
理想信道模型/แบบจำลองช่องสัญญาณอุดมคติ — ideal channel model   
字节/ไบต์ (1 ไบต์ = 8 บิต) — byte   
二进制/ไบนารี (ฐานสอง) — binary   
码效率/ประสิทธิผลของรหัส — code efficiency   
更新/ปรับค่า (ให้เป็นปัจจุบัน) — update   
环路延迟/ปริมาณหน่วงเวลาในลูป — loop delay

## 参考文献

[1] S. X. Wang and A. M. Taratorin, Magnetic information storage technology. San Diego: Academic Press, 1999.

[2] B. Sklar, Digital communications: fundamentals and applications: Prentice Hall, 2nd-edition, 2001.

[3] A. M. Taratorin, Magnetic recording systems and measurements: Guzik Technical Enterprises, 2004.

[4] J. W. M. Bergmans, Digital baseband transmission and recording. Boston/London/ Dordrecht: Kluwer Academic Publishers, 1996.

[5] T. Suzuki, "Perpendicular magnetic recording: Its basics and potential for the future," IEEE Trans. on Magnetics, vol. MAG-20, no. 5, pp. 675 – 680, September 1984.

[6] J. Moon, "The role of signal processing in data-storage," IEEE Signal Processing Magazine, pp. 54 – 72, July 1998.

[7] S. B. Wicker, Error control systems for digital communication and storage. New Jersey: Printice Hall International, 1995.

[8] B. Vasic and E. M. Kurtas, Coding and signal processing for magnetic recording systems. New York: CRC Press, 2005.

[9] K. A. S Immink, "Runlength-limited sequences," in Proc. of the IEEE, vol. 78, no. 11, pp. 1745 – 1759, November 1990.

[10] Piya Kovintavewat (ปิยะ โควินท์ทวีวัฒน์), 数字数据存储信号处理 第1卷：读写通道基础, 国家电子与计算机技术中心 (NECTEC), 2007.

[11] T A. Roscamp, E. D. Boerner, and G. J. Parker, "Three-dimensional modeling of perpendicular recording with soft underlayer," J. of Applied Physics, vol. 91, no. 10, May 2002.

[12] A. V. Oppenheim, A. S. Willsky, and S. H. nawab, Signals and systems. New Jersey: Prentice Hall, 2nd-edition, 1997.

[13] Available online at http://www.mathworks.com

[14] Piya Kovintavewat (ปิยะ โควินท์ทวีวัฒน์), SCILAB 编程语言入门指南 (第2版), 北曼谷先皇技术学院教材出版中心, 2006.

[15] G. D. Forney, "Maximum-likelihood sequence estimation of digital sequences in the presence of intersymbol interference," IEEE Trans. on Information Theory, vol. IT-18, no. 3, pp. 363 - 378, May 1972.

[16] J. R. Barry, E. A. Lee, and D. G. Messerschmitt, Digital communication. Boston: Kluwer Academic Publishers, 3nd-edition, 2003.

[17] H. K. Thapar and A. M. Patel, "A class of partial response systems for increasing storage density in magnetic recording," IEEE Trans. on Magnetics, vol. 23, no. 5, pp. 3666 - 3668, September 1987.

[18] P. Kovintavewat, I. Ozgunes, E. Kurtas, J. R. Barry, and S. W. McLaughlin, "Generalized partial response targets for perpendicular recording with jitter noise," IEEE Trans. on Magnetics, vol. 38, no. 5, pp. 2340 – 2342, September 2002.

[19] J. Moon and W. Zeng, "Equalization for maximum likelihood detector," IEEE Trans. on Magnetics, vol. 31, no. 2, pp. 1083 – 1088, March 1995.

[20] S. Raghaven and H. K. Thapar, "Feed-forward timing recovery for digital magnetic recording," in Proc. of ICC'91, vol. 2, pp. 794 – 798, June 1991.

[21] A. N. D' Andrea, U. Mengali, and G. M. Vitetta, 'Approximate ML decoding of coded PSK with no explicit carrier phase reference," IEEE Trans. on Communication, vol. 42, no. 2/3/4, pp. 1033 – 1039, Feb/Mar/Apr 1994.

[22] U. Mengali and A. N. D' Andrea, "Synchronization techniques for digital receivers," New York: Plenum Press, 1997.

[23] J. Moon and L. R. Carley, "Performance comparison of detection methods in magnetic recording," IEEE Trans. on Magnetics, vol. 26, pp. 3155 – 3172, November 1990.

[24] K. H. Mueller and M. Müller, "Timing recovery in digital synchronous data receivers," IEEE Trans. on Communication, vol. COM-24, no. 5, pp. 516 – 531, May 1976.

[25] M. H. Hayes, Statistical digital signal processing and modeling. John Wiley & Sons Inc., New York, 1996.

[26] A. Leon-Garcia, Probability and random processes for electrical engineering. New York: Addison-Wesley Inc., 2nd-edition, 1994.

[27] R. D. Cideciyan, F. Dolivo, R. Hermann, W. Hirt, and W. Schott, 'A PRML system for digital magnetic recording," IEEE J. Selected Areas Commun., vol. 10, no. 1, pp. 38 – 56, January 1992.

[28] H. Shafiee, "Timing recovery for sampling detectors in digital magnetic recording," in Proc. of ICC'96, vol. 1, pp. 577 – 581, January 1996.

[29] A. R. Nayak, "Iterative timing recovery for magnetic recording channels with low signal-to-noise ratio," Ph.D. dissertation, Georgia Institute of Technology, Georgia, June 2004.

[30] P. Kovintavewat, "Timing recovery based-on per-survivor processing," Ph.D. dissertation, Georgia Institute of Technology, Georgia, October 2004.

[31] J. R. Barry, A. Kavcic, S. W. McLaughlin, and A. R. Nayak, "Iterative timing recovery," IEEE Signal Processing Magazine, vol. 21, pp. 89 – 102, January 2004.

[32] X. Jin and A. Kavci, "Cycle-slip detection using soft-output information," in Proc. of ICC'01, vol. 9, pp. 2706 - 2710, June 2001.

[33] A. R. Nayak, J. R. Barry, and S. W. McLaughlin, "Joint timing recovery and turbo equalization for coded partial response channels," IEEE Trans. on Magnetics, vol. 38, no. 5, pp. 2295 – 2297, September 2003.

[34] F. M. Gardner, "Interpolation in digital modems — Part I: Fundamentals," IEEE Trans. on Communication, vol. 41, no. 3, pp. 501 – 507, March 1993.

[35] L. Erup, F. M. Gardner, and R. A. Harris, "Interpolation in digital modems — Part II: Implementation and performance," IEEE Trans. on Communication, vol. 41, no. 6, pp. 998 – 1008, June 1993.

[36] Z. Wu, J. M. Cioff, and K. D. Fisher 'A MMSE interpolated timing recovery scheme for the magnetic recording channel," in Proc. of ICC'97, vol. 3, pp. 1625 – 1629, 1997.

[37] M. Spurbeck and R. T. Behrens, "Interpolated timing recovery for hard disk drive read channels," in Proc. of ICC'97, vol. 3, pp. 1618 – 1624, 1997.

[38] P. Kovintavewat, J. R. Barry, F. M. Erden, and E. M. Kurtas, "Per-survivor timing recovery for uncoded partial response channels," in Proc. of ICC'04, Paris, France, vol. 5, pp. 2715 – 2719, June 20 – 24, 2004.

[39] P. Kovintavewat, J. R. Barry, F. M. Erden, and E. M. Kurtas, "Per-survivor iterative timing recovery for coded partial response channels," in Proc. of Globecom'04, Texas, USA, vol. 4, pp. 2604 – 2608, Nov 29 - Dec 3, 2004.

[40] P. Kovintavewat, J. R. Barry, M. F. Erden, and E. M. Kurtas, "Robustness of Per-Survivor Iterative Timing Recovery in Perpendicular Recording Channels," IEEE International Conference on Magnetics (INTERMAG 2005), Nagoya, Japan, pp. 1613 – 1614, April 4 – 8, 2005.

[41] D. G. Messerschmitt, "Design of finite impulse response for the Viterbi algorithm and decision-feedback equalizer," in Proc. of ICC'74, pp. 37D-1-5, June 1974.

[42] J. Fitzpatrick, J. K. Wolf, and L. Barbosa, 'New equalizer targets for sampled magnetic recording system," in Proc. of the 25th Asilomar Conference on Signals Systems and Computers, pp. 30 – 34, November 1991.

[43] T. Oenning and J. Moon, "Partial response maximum likelihood detection for perpendicular recording," IEEE International Conference on Magnetics (INTERMAG 2000), p. HT-08, 2000.

[44] I. Lee, C. Modlin, and J. M. Cioff, "Equalized maximum likelihood receiver in a magnetic recording channel," in Proc. of ICC'93, pp. 1970 – 1973, November 1993.

[45] C. T. Beare, "The choice of the desired impulse response in combined linear-Viterbi algorithm equalizers," IEEE Trans. on Communication, vol. COM-26, no. 8, pp. 1301 – 1307, August 1978.

[46] I. Lee and J. M. Cioff, "Equalized maximum likelihood receiver with a unit energy constraint," IEEE Trans. on Magnetics, vol. 33, no. 1, pp. 855 – 862, January 1997.

[47] A. Ghrayeb and W. E. Ryan, "Precoder design for concatenating convolutional codes with generalized partial response channels," in Proc. of Globecom'00, San Francisco, CA, 2000, pp. 1859 - 1864.

[48] L. C. Barbosa, "Maximum likelihood sequence estimators: a geometric view," IEEE Trans. on Information Theory, vol. 35, no. 2, pp. 419 – 427, March 1989.

[49] J. Caroselli and J. K. Wolf, "Error event characterization of partial response systems in magnetic recording systems with medium noise," in Proc. of Globecom'98, vol. 5, pp. 2724 - 2728.

[50] B. E. Moision, P. H. Siegel, and E. Soljanin, "Distance-enhancing for digital recording," IEEE Trans. on Magnetics, vol. 34, no. 1, pp. 68 – 74, January 1998.

[51] P. R. Chevillat, E. Eleftheriou, and D. Maiwald, "Noise-predictive partial-response equalizers and applications," in Proc. of ICC'92, vol. 2, pp. 942 – 947, June 1992.

[52] E. Eleftheriou and W. Hirt, 'Noise-predictive maximum-likelihood (NPML) detection for the magnetic recording channel," in Proc. of ICC'96, vol. 1, pp. 556 – 560, June 1996.

[53] S. Altekar, "Detection and coding techniques for magnetic recording channels," Ph.D. dissertation, Univ. Calif. San Diego, June 1997.

[54] J. Moon and J. Park, "Pattern-dependent noise prediction in signal-dependent noise," IEEE J. Selected Areas Comm., vol. 19, no. 4, pp. 730 – 743, June 2001.

[55] J. Caroselli, S. A. Altekar, P. McEwen, and J. K. Wolf, "Improved detection for magnetic recording systems with media noise," IEEE Trans. on Magnetics, vol. 33, no. 5, pp. 2779 – 2781, 1997.

[56] X. Yang and E. Kurtas, "Noise predictive equalization and detection," Internal report, Channels Department, Seagate Technology, Pittsburgh, PA, May 2003.

[57] R. Raheli, A. Polydoros, and C. K. Tzou, "Per-survivor processing: a general approach to MLSE in uncertain environments," IEEE Trans. on Commun., vol. 43, no. 2, pp. 354 – 364, Feb./Mar./Apr. 1995.

[58] C. E. Shannon, 'A mathematical theory of communication," The Bell system technical journal, vol. 27, pp. 379 – 423, 623 – 656, July, October, 1948.

[59] P. H. Siegel and J. K. Wolf, "Modulation and coding for information storage," IEEE Communications Magazine, pp. 68 – 86, December 1991.

[60] K. A. S. Abdel-Ghaffar and J. H. Weber, "Constrained block codes for class-IV partialresponse channels with maximum-likelihood sequence estimation," IEEE Trans. on Information Theory, vol. 42, no. 5, pp. 1405 – 1424, September 1996.

## 索引

PW50, 6 — 垂直记录, 6 — 水平记录, 6

GPRML, 133

NPML, 115–135, 138 — 噪声白化, 117 — 均方误差, 119 — 最小均方误差, 120 — 复杂度, 126 — 有效目标, 122, 123 — 性能, 129 — 预测滤波器, 117, 118 — 工作原理, 120–129 — 正交性原理, 119 — 分支度量, 121, 122

PDNP, 137–150 — 噪声白化, 141 — 复杂度, 146 — 性能, 146 — 预测滤波器, 141 — 正交性原理, 142 — 算法, 140–144 — 逐幸存处理 (PSP), 144 — 分支度量, 140, 141

PLL, 18, 21, 67 — 参数设计, 23–30 — 二阶线性分析, 28–30 — 更新方程, 22 — 一阶线性分析, 23–28 — 更新方程, 22 — 稳定性, 24, 28   
preamble, 22, 34   
PRML, 44, 65–88, 115, 126, 137 — 码 (0, G/I), 166 — 维特比检测器, 69 — 维特比算法, 75 — 均衡器, 66 — 有限状态机, 71 — 网格图, 72

SCILAB, 8, 54

SNR, 21, 104, 130 — 电子学, 55 — 差错事件, 100 — 每比特 (Eb/N0), 31 — 有效, 47, 101, 103

法拉第定律, 5   
过程 — 噪声白化, 116, 138, 141 — 读, 5–8 — 写, 5   
写电流, 4, 5, 152   
脉冲编码调制 (PCM), 2   
采样, 11, 18, 21, 36   
加-比-选, 122   
磁记录, 1 — 信道模型, 9   
垂直记录, 3, 44, 54, 96, 103, 147 — PR目标, 13, 44 — 频率响应, 8 — 转移脉冲, 6 — 差错事件, 97   
水平记录, 3, 96, 129, 147 — PR目标, 12, 44 — 频率响应, 8 — 转移脉冲, 6 — 差错事件, 96   
二进制记录, 5 — 非线性, 5   
定时调整, 37   
目标设计, 47–54 — h1 = 1型, 52 — 特定目标型, 53 — 单位能量型, 53 — 首一型 (h0 = 1), 49   
同步, 18, 22, 34, 67 — 完全同步, 55, 104, 130, 147   
随机游走, 20   
转移, 4, 11, 33, 76, 139, 152 — 最优, 77 — 响应, 6, 45 — 磁化, 5 — 矩阵, 158 — 孤立, 6, 55, 104, 130 — 随机转移偏移, 55, 139   
码间串扰 (ISI), 6, 65, 69, 152 — Z变换, 24, 28 — 连续时间傅里叶变换, 8 — 超顺磁极限, 3

误差 — 均方误差 (MSE), 47, 119 — 最小均方误差 (MMSE), 47, 120 — 目标设计, 47–54 — 定时误差, 21, 24, 30, 38 — 均方根 (RMS), 34

最大似然 (ML), 44   
归一化频率, 8   
奈奎斯特频率, 44   
密度 — 堆积密度, 155 — 记录密度, 6 — 归一化记录密度 (ND), 6 — 功率谱密度, 20, 55, 103, 130, 147

读通道, 4

目标, 53 — 最优, 47 — 有效, 122 — GPR型, 13, 45 — h1 = 1型, 52 — 特定目标型, 53 — 单位能量型, 53 — 首一型, 49, 104, 133, 148 — PR型, 12 — 垂直记录, 44

水平记录, 44

比特单元, 6, 24, 55, 103, 147

响应, 116 — 转移响应, 6, 45 — 阶跃响应, 25 — 误差响应, 26 — 目标响应, 12, 45, 68, 138 — 部分响应 (PR), 12, 43, 68 — 冲激响应, 20, 30, 148 — 有限冲激响应 (FIR), 67, 117, 138 — 无限冲激响应 (IIR), 117 — 频率响应, 8, 43 — 全响应, 67 — 双位响应, 8, 45

函数 — 阶跃函数, 23 — 误差函数, 6 — 高斯概率密度函数, 55, 78, 103, 139, 147 — sinc函数, 20 — 传递函数, 13, 24, 46, 117, 138 — 指数函数, 8 — 克罗内克δ函数, 81

模式, 22 — 跟踪模式, 22 — 捕获模式, 22 — 完全捕获, 34

码 (0, G/I), 166–167   
RLL码, 3, 91, 151–167 — ISI, 152 — 设计, 162–164 — 堆积密度, 155 — 容量, 154–155 — 查找表, 152, 164 — 冗余比特, 153 — 参数, 151 — (0, G/I)码, 166 — FM码, 164 — MFM码, 164 — Miller码, 164 — 渐近信息率, 155, 160 — 密度比, 155–156 — 码率, 152 — 有限状态机, 156–158 — 约束, — 序列数, 153–154 — 状态转移矩阵, 158–159 — 定时恢复, 152   
RS码, 3   
卷积码, 69   
调制码, 151

数字数据存储系统, 3 — 模型, 4 — 数字通信系统, 17 — NRZI格式, 4, 151

差错序列, 93 — 有效输入差错序列, 94

压控振荡器 (VCO), 18   
滤波器 — 预测误差滤波器, 118 — 预测滤波器, 117 — 线性一步预测滤波器, 118 — 低通, 4 — 截止频率, 20 — 环路滤波器, 18   
采样器, 4, 18   
检测器 — 阈值检测器, — 无记忆, 31 — 多电平无记忆, 34 — 多电平, 21 — 软判决, 38 — 硬判决, 38 — 定时误差检测器, 18 — 最优检测器, 69 — 最大似然序列检测器 (MLSD), 77 — 最优序列检测器, 137   
维特比检测器, 12, 21, 69, 115 — 复杂度, 80 — 译码深度, 80 — 序列差错概率, 88 — 性能, 87 — 序列检测器, 69 — 算法, 69, 75–80 — 有限状态机, 70–72 — 网格图, 70, 72–75   
符号检测器, 21

译码器 — 调制译码器, 4 — 纠错译码器, 4

调制器, 4, 5

编码器 — 预编码器, 91 — 调制编码器, 3 — 纠错编码器, 3

读通道架构, 11   
磁化, 1, 139, 152   
矫顽力, 2, 5   
磁导率, 3   
正规方程, 119

脉冲信号 — 转移脉冲, 6, 55, 103, 130, 147 — 垂直记录, 6 — 水平记录, 6 — 孤立转移脉冲, 55, 104, 130 — 双位脉冲, 8 — 奈奎斯特脉冲, 20 — 理想奈奎斯特脉冲, 12

噪声, 11, 20, 21, 45, 68, 93 — 噪声增强, 45, 66 — 模式相关噪声, 138–140 — 预测, 117, 141 — 介质抖动噪声, 55, 61, 103, 107, 138, 139 — 模式相关, 138 — 带外噪声, 11, 20 — 采样器内部噪声, 18 — 白噪声, 60, 119 — 白色高斯噪声, 69 — 加性白高斯噪声, 20, 55, 66, 75, 99, 103, 115, 138 — 有色噪声, 93, 99, 116, 138

谱零点, 8, 44, 68

正交性原理, 119, 142

偏移 — 频率偏移, 22, 35 — 相位偏移, 21, 22, 33 — 更新方程, 24, 28 — 定时偏移, 20, 33

采样率, 37 — 过采样率, 37   
收敛速度, 22–25, 28, 38   
误比特率 (BER), 47   
码率, 69, 152, 154, 156   
自相关, 49, 60, 100, 119, 142   
算法 — PDNP, 140–144 — PS-PDNP, 144–146 — 维特比, 69–80, 122 — 自适应, 143   
均衡器, 4, 12, 47, 53, 66, 104 — 收敛速度, 67 — 迫零, 138 — 部分响应 (PR), 43, 68, 115 — 全响应, 67   
有限状态机, 70, 71 — RLL码, 156 — 维特比检测器, 71   
内插技术, 37   
逐幸存定时恢复, 38 — 迭代式, 40   
幸存路径, 80, 92   
S曲线, 21, 30–34 — 平衡点, 33 — 稳定点, 32

差错事件, 91 — 分析, 91–111 — 最小距离分析, 104–107 — SNReff与BER的关系, 107–109 — 定义, 93 — 概念, 95 — RLL码, 91 — 有效距离, 99–103 — 有效距离平方, 101 — 最小有效距离, 101 — 欧氏距离, 97–99 — 欧氏距离平方, 97 — 最小欧氏距离, 99 — 预编码器, 91

带宽 — 环路带宽, 22, 28 — 零过剩带宽, 20   
数据模式, 138   
模型 — 噪声白化, 117 — PLL工作模型, 23 — 目标设计, 47 — 等效GPR信道, 93 — 磁记录, 9 — 等效离散时间信道, 66 — 理想信道, 12–13, 19 — 实际信道, 11–12 — 数字数据存储系统, 3   
网格图, 70, 72, 91, 115, 141   
周跳, 33   
定时抖动, 18, 20, 39   
定时函数, 30 — 归一化, 32   
定时恢复, 12, 17–41 — 参数设计, 23–34 — 跟踪模式, 22 — 捕获模式, 22 — 数字式, 37 — 传统式, 18–23 — 性能, 34–37 — 演绎式, 18 — 内插式, 37 — 归纳式, 18
