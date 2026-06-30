## ภาคผนวกก

## ตารางฟังก์ชั้น Q

ฟังก์ชัน Q(x) เป็นฟังก์ชันที่สามารถจัดให้อยู่ในรูปของฟังก์ชันการแจกแจงสะสมของตัวแปรสุ่มแบบ เกาส์เซียนได้ซึ่งเป็นที่นิยมใช้งานทางด้านสถิติศาสตร์และด้านวิศวกรรมศาสตร์ โดยฟังก์ชัน Q(x) จะ นิยามดังนี้

$$
Q ( x ) = { \frac { 1 } { \sqrt { 2 \pi } } } \int _ { x } ^ { \infty } \exp \left\{ - { \frac { y ^ { 2 } } { 2 } } \right\} d y\tag{ก.1}
$$

ซึ่งเป็นการหาค่าปริพันธ์ส่วนหางของฟังก์ชันความหนาแน่นความน่าจะเป็นแบบเกาส์เซียนเมื่อ exp[} คือ ฟังก์ชันเลขชี้กำลัง (exponential function) โดยทั่วไป ค่าของฟังก์ชัน Q(x) สำหรับค่า x ต่างๆ สามารถหาได้จากตารางค้นหา (l๐ok-นp table) แต่ในกรณีที่ x > 3 ฟังก์ชัน Q(x) สามารถประมาณ ค่าได้ดังนี้

$$
Q ( x ) \approx \frac { 1 } { x \sqrt { 2 \pi } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\}\tag{ก.2}
$$

ตารางต่อไปนี้จะแสดงค่าของฟังก์ชัน Q(x) สำหรับ $0 \leq x \leq 3 . 5 9$

<table><tr><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">0.50000</td><td colspan="1" rowspan="1">0.36</td><td colspan="1" rowspan="1">0.35942</td><td colspan="1" rowspan="1">0.72</td><td colspan="1" rowspan="1">0.23576</td><td colspan="1" rowspan="1">1.08</td><td colspan="1" rowspan="1">0.14007</td><td colspan="1" rowspan="1">1.44</td><td colspan="1" rowspan="1">0.0749340</td></tr><tr><td colspan="1" rowspan="1">0.01</td><td colspan="1" rowspan="1">0.49601</td><td colspan="1" rowspan="1">0.37</td><td colspan="1" rowspan="1">0.35569</td><td colspan="1" rowspan="1">0.73</td><td colspan="1" rowspan="1">0.23270</td><td colspan="1" rowspan="1">1.09</td><td colspan="1" rowspan="1">0.13786</td><td colspan="1" rowspan="1">1.45</td><td colspan="1" rowspan="1">0.0735290</td></tr><tr><td colspan="1" rowspan="1">0.02</td><td colspan="1" rowspan="1">0.49202</td><td colspan="1" rowspan="1">0.38</td><td colspan="1" rowspan="1">0.35197</td><td colspan="1" rowspan="1">0.74</td><td colspan="1" rowspan="1">0.22965</td><td colspan="1" rowspan="1">1.10</td><td colspan="1" rowspan="1">0.13567</td><td colspan="1" rowspan="1">1.46</td><td colspan="1" rowspan="1">0.0721450</td></tr><tr><td colspan="1" rowspan="1">0.03</td><td colspan="1" rowspan="1">0.48803</td><td colspan="1" rowspan="1">0.39</td><td colspan="1" rowspan="1">0.34827</td><td colspan="1" rowspan="1">0.75</td><td colspan="1" rowspan="1">0.22663</td><td colspan="1" rowspan="1">1.11</td><td colspan="1" rowspan="1">0.133500</td><td colspan="1" rowspan="1">1.47</td><td colspan="1" rowspan="1">0.070781</td></tr><tr><td colspan="1" rowspan="1">0.04</td><td colspan="1" rowspan="1">0.48405</td><td colspan="1" rowspan="1">0.40</td><td colspan="1" rowspan="1">0.34458</td><td colspan="1" rowspan="1">0.76</td><td colspan="1" rowspan="1">0.22363</td><td colspan="1" rowspan="1">1.12</td><td colspan="1" rowspan="1">0.131360</td><td colspan="1" rowspan="1">1.48</td><td colspan="1" rowspan="1">0.069437</td></tr><tr><td colspan="1" rowspan="1">0.05</td><td colspan="1" rowspan="1">0.48006</td><td colspan="1" rowspan="1">0.41</td><td colspan="1" rowspan="1">0.34090</td><td colspan="1" rowspan="1">0.77</td><td colspan="1" rowspan="1">0.22065</td><td colspan="1" rowspan="1">1.13</td><td colspan="1" rowspan="1">0.129240</td><td colspan="1" rowspan="1">1.49</td><td colspan="1" rowspan="1">0.068112</td></tr><tr><td colspan="1" rowspan="1">0.06</td><td colspan="1" rowspan="1">0.47608</td><td colspan="1" rowspan="1">0.42</td><td colspan="1" rowspan="1">0.33724</td><td colspan="1" rowspan="1">0.78</td><td colspan="1" rowspan="1">0.21770</td><td colspan="1" rowspan="1">1.14</td><td colspan="1" rowspan="1">0.127140</td><td colspan="1" rowspan="1">1.50</td><td colspan="1" rowspan="1">0.066807</td></tr><tr><td colspan="1" rowspan="1">0.07</td><td colspan="1" rowspan="1">0.47210</td><td colspan="1" rowspan="1">0.43</td><td colspan="1" rowspan="1">0.33360</td><td colspan="1" rowspan="1">0.79</td><td colspan="1" rowspan="1">0.21476</td><td colspan="1" rowspan="1">1.15</td><td colspan="1" rowspan="1">0.125070</td><td colspan="1" rowspan="1">1.51</td><td colspan="1" rowspan="1">0.065522</td></tr><tr><td colspan="1" rowspan="1">0.08</td><td colspan="1" rowspan="1">0.46812</td><td colspan="1" rowspan="1">0.44</td><td colspan="1" rowspan="1">0.32997</td><td colspan="1" rowspan="1">0.80</td><td colspan="1" rowspan="1">0.21186</td><td colspan="1" rowspan="1">1.16</td><td colspan="1" rowspan="1">0.123020</td><td colspan="1" rowspan="1">1.52</td><td colspan="1" rowspan="1">0.064255</td></tr><tr><td colspan="1" rowspan="1">0.09</td><td colspan="1" rowspan="1">0.46414</td><td colspan="1" rowspan="1">0.45</td><td colspan="1" rowspan="1">0.32636</td><td colspan="1" rowspan="1">0.81</td><td colspan="1" rowspan="1">0.20897</td><td colspan="1" rowspan="1">1.17</td><td colspan="1" rowspan="1">0.121000</td><td colspan="1" rowspan="1">1.53</td><td colspan="1" rowspan="1">0.063008</td></tr><tr><td colspan="1" rowspan="1">0.10</td><td colspan="1" rowspan="1">0.46017</td><td colspan="1" rowspan="1">0.46</td><td colspan="1" rowspan="1">0.32276</td><td colspan="1" rowspan="1">0.82</td><td colspan="1" rowspan="1">0.20611</td><td colspan="1" rowspan="1">1.18</td><td colspan="1" rowspan="1">0.119000</td><td colspan="1" rowspan="1">1.54</td><td colspan="1" rowspan="1">0.061780</td></tr><tr><td colspan="1" rowspan="1">0.11</td><td colspan="1" rowspan="1">0.45620</td><td colspan="1" rowspan="1">0.47</td><td colspan="1" rowspan="1">0.31918</td><td colspan="1" rowspan="1">0.83</td><td colspan="1" rowspan="1">0.20327</td><td colspan="1" rowspan="1">1.19</td><td colspan="1" rowspan="1">0.117020</td><td colspan="1" rowspan="1">1.55</td><td colspan="1" rowspan="1">0.060571</td></tr><tr><td colspan="1" rowspan="1">0.12</td><td colspan="1" rowspan="1">0.45224</td><td colspan="1" rowspan="1">0.48</td><td colspan="1" rowspan="1">0.31561</td><td colspan="1" rowspan="1">0.84</td><td colspan="1" rowspan="1">0.20045</td><td colspan="1" rowspan="1">1.20</td><td colspan="1" rowspan="1">0.115070</td><td colspan="1" rowspan="1">1.56</td><td colspan="1" rowspan="1">0.059380</td></tr><tr><td colspan="1" rowspan="1">0.13</td><td colspan="1" rowspan="1">0.44828</td><td colspan="1" rowspan="1">0.49</td><td colspan="1" rowspan="1">0.31207</td><td colspan="1" rowspan="1">0.85</td><td colspan="1" rowspan="1">0.19766</td><td colspan="1" rowspan="1">1.21</td><td colspan="1" rowspan="1">0.113140</td><td colspan="1" rowspan="1">1.57</td><td colspan="1" rowspan="1">0.058208</td></tr><tr><td colspan="1" rowspan="1">0.14</td><td colspan="1" rowspan="1">0.44433</td><td colspan="1" rowspan="1">0.50</td><td colspan="1" rowspan="1">0.30854</td><td colspan="1" rowspan="1">0.86</td><td colspan="1" rowspan="1">0.19489</td><td colspan="1" rowspan="1">1.22</td><td colspan="1" rowspan="1">0.111230</td><td colspan="1" rowspan="1">1.58</td><td colspan="1" rowspan="1">0.057053</td></tr><tr><td colspan="1" rowspan="1">0.15</td><td colspan="1" rowspan="1">0.44038</td><td colspan="1" rowspan="1">0.51</td><td colspan="1" rowspan="1">0.30503</td><td colspan="1" rowspan="1">0.87</td><td colspan="1" rowspan="1">0.19215</td><td colspan="1" rowspan="1">1.23</td><td colspan="1" rowspan="1">0.109350</td><td colspan="1" rowspan="1">1.59</td><td colspan="1" rowspan="1">0.055917</td></tr><tr><td colspan="1" rowspan="1">0.16</td><td colspan="1" rowspan="1">0.43644</td><td colspan="1" rowspan="1">0.52</td><td colspan="1" rowspan="1">0.30153</td><td colspan="1" rowspan="1">0.88</td><td colspan="1" rowspan="1">0.18943</td><td colspan="1" rowspan="1">1.24</td><td colspan="1" rowspan="1">0.107490</td><td colspan="1" rowspan="1">1.60</td><td colspan="1" rowspan="1">0.054799</td></tr><tr><td colspan="1" rowspan="1">0.17</td><td colspan="1" rowspan="1">0.43251</td><td colspan="1" rowspan="1">0.53</td><td colspan="1" rowspan="1">0.29806</td><td colspan="1" rowspan="1">0.89</td><td colspan="1" rowspan="1">0.18673</td><td colspan="1" rowspan="1">1.25</td><td colspan="1" rowspan="1">0.105650</td><td colspan="1" rowspan="1">1.61</td><td colspan="1" rowspan="1">0.053699</td></tr><tr><td colspan="1" rowspan="1">0.18</td><td colspan="1" rowspan="1">0.42858</td><td colspan="1" rowspan="1">0.54</td><td colspan="1" rowspan="1">0.29460</td><td colspan="1" rowspan="1">0.90</td><td colspan="1" rowspan="1">0.18406</td><td colspan="1" rowspan="1">1.26</td><td colspan="1" rowspan="1">0.103830</td><td colspan="1" rowspan="1">1.62</td><td colspan="1" rowspan="1">0.052616</td></tr><tr><td colspan="1" rowspan="1">0.19</td><td colspan="1" rowspan="1">0.42465</td><td colspan="1" rowspan="1">0.55</td><td colspan="1" rowspan="1">0.29116</td><td colspan="1" rowspan="1">0.91</td><td colspan="1" rowspan="1">0.18141</td><td colspan="1" rowspan="1">1.27</td><td colspan="1" rowspan="1">0.102040</td><td colspan="1" rowspan="1">1.63</td><td colspan="1" rowspan="1">0.051551</td></tr><tr><td colspan="1" rowspan="1">0.20</td><td colspan="1" rowspan="1">0.42074</td><td colspan="1" rowspan="1">0.56</td><td colspan="1" rowspan="1">0.28774</td><td colspan="1" rowspan="1">0.92</td><td colspan="1" rowspan="1">0.17879</td><td colspan="1" rowspan="1">1.28</td><td colspan="1" rowspan="1">0.100270</td><td colspan="1" rowspan="1">1.64</td><td colspan="1" rowspan="1">0.050503</td></tr><tr><td colspan="1" rowspan="1">0.21</td><td colspan="1" rowspan="1">0.41683</td><td colspan="1" rowspan="1">0.57</td><td colspan="1" rowspan="1">0.28434</td><td colspan="1" rowspan="1">0.93</td><td colspan="1" rowspan="1">0.17619</td><td colspan="1" rowspan="1">1.29</td><td colspan="1" rowspan="1">0.098525</td><td colspan="1" rowspan="1">1.65</td><td colspan="1" rowspan="1">0.049471</td></tr><tr><td colspan="1" rowspan="1">0.22</td><td colspan="1" rowspan="1">0.41294</td><td colspan="1" rowspan="1">0.58</td><td colspan="1" rowspan="1">0.28096</td><td colspan="1" rowspan="1">0.94</td><td colspan="1" rowspan="1">0.17361</td><td colspan="1" rowspan="1">1.30</td><td colspan="1" rowspan="1">0.096800</td><td colspan="1" rowspan="1">1.66</td><td colspan="1" rowspan="1">0.048457</td></tr><tr><td colspan="1" rowspan="1">0.23</td><td colspan="1" rowspan="1">0.40905</td><td colspan="1" rowspan="1">0.59</td><td colspan="1" rowspan="1">0.27760</td><td colspan="1" rowspan="1">0.95</td><td colspan="1" rowspan="1">0.17106</td><td colspan="1" rowspan="1">1.31</td><td colspan="1" rowspan="1">0.095098</td><td colspan="1" rowspan="1">1.67</td><td colspan="1" rowspan="1">0.047460</td></tr><tr><td colspan="1" rowspan="1">0.24</td><td colspan="1" rowspan="1">0.40517</td><td colspan="1" rowspan="1">0.60</td><td colspan="1" rowspan="1">0.27425</td><td colspan="1" rowspan="1">0.96</td><td colspan="1" rowspan="1">0.16853</td><td colspan="1" rowspan="1">1.32</td><td colspan="1" rowspan="1">0.093418</td><td colspan="1" rowspan="1">1.68</td><td colspan="1" rowspan="1">0.046479</td></tr><tr><td colspan="1" rowspan="1">0.25</td><td colspan="1" rowspan="1">0.40129</td><td colspan="1" rowspan="1">0.61</td><td colspan="1" rowspan="1">0.27093</td><td colspan="1" rowspan="1">0.97</td><td colspan="1" rowspan="1">0.16602</td><td colspan="1" rowspan="1">1.33</td><td colspan="1" rowspan="1">0.091759</td><td colspan="1" rowspan="1">1.69</td><td colspan="1" rowspan="1">0.045514</td></tr><tr><td colspan="1" rowspan="1">0.26</td><td colspan="1" rowspan="1">0.39743</td><td colspan="1" rowspan="1">0.62</td><td colspan="1" rowspan="1">0.26763</td><td colspan="1" rowspan="1">0.98</td><td colspan="1" rowspan="1">0.16354</td><td colspan="1" rowspan="1">1.34</td><td colspan="1" rowspan="1">0.090123</td><td colspan="1" rowspan="1">1.70</td><td colspan="1" rowspan="1">0.044565</td></tr><tr><td colspan="1" rowspan="1">0.27</td><td colspan="1" rowspan="1">0.39358</td><td colspan="1" rowspan="1">0.63</td><td colspan="1" rowspan="1">0.26435</td><td colspan="1" rowspan="1">0.99</td><td colspan="1" rowspan="1">0.16109</td><td colspan="1" rowspan="1">1.35</td><td colspan="1" rowspan="1">0.088508</td><td colspan="1" rowspan="1">1.71</td><td colspan="1" rowspan="1">0.043633</td></tr><tr><td colspan="1" rowspan="1">0.28</td><td colspan="1" rowspan="1">0.38974</td><td colspan="1" rowspan="1">0.64</td><td colspan="1" rowspan="1">0.26109</td><td colspan="1" rowspan="1">1.00</td><td colspan="1" rowspan="1">0.15866</td><td colspan="1" rowspan="1">1.36</td><td colspan="1" rowspan="1">0.086915</td><td colspan="1" rowspan="1">1.72</td><td colspan="1" rowspan="1">0.042716</td></tr><tr><td colspan="1" rowspan="1">0.29</td><td colspan="1" rowspan="1">0.38591</td><td colspan="1" rowspan="1">0.65</td><td colspan="1" rowspan="1">0.25785</td><td colspan="1" rowspan="1">1.01</td><td colspan="1" rowspan="1">0.15625</td><td colspan="1" rowspan="1">1.37</td><td colspan="1" rowspan="1">0.085343</td><td colspan="1" rowspan="1">1.73</td><td colspan="1" rowspan="1">0.041815</td></tr><tr><td colspan="1" rowspan="1">0.30</td><td colspan="1" rowspan="1">0.38209</td><td colspan="1" rowspan="1">0.66</td><td colspan="1" rowspan="1">0.25463</td><td colspan="1" rowspan="1">1.02</td><td colspan="1" rowspan="1">0.15386</td><td colspan="1" rowspan="1">1.38</td><td colspan="1" rowspan="1">0.083793</td><td colspan="1" rowspan="1">1.74</td><td colspan="1" rowspan="1">0.040930</td></tr><tr><td colspan="1" rowspan="1">0.31</td><td colspan="1" rowspan="1">0.37828</td><td colspan="1" rowspan="1">0.67</td><td colspan="1" rowspan="1">0.25143</td><td colspan="1" rowspan="1">1.03</td><td colspan="1" rowspan="1">0.15151</td><td colspan="1" rowspan="1">1.39</td><td colspan="1" rowspan="1">0.082264</td><td colspan="1" rowspan="1">1.75</td><td colspan="1" rowspan="1">0.040059</td></tr><tr><td colspan="1" rowspan="1">0.32</td><td colspan="1" rowspan="1">0.37448</td><td colspan="1" rowspan="1">0.68</td><td colspan="1" rowspan="1">0.24825</td><td colspan="1" rowspan="1">1.04</td><td colspan="1" rowspan="1">0.14917</td><td colspan="1" rowspan="1">1.40</td><td colspan="1" rowspan="1">0.080757</td><td colspan="1" rowspan="1">1.76</td><td colspan="1" rowspan="1">0.039204</td></tr><tr><td colspan="1" rowspan="1">0.33</td><td colspan="1" rowspan="1">0.37070</td><td colspan="1" rowspan="1">0.69</td><td colspan="1" rowspan="1">0.24510</td><td colspan="1" rowspan="1">1.05</td><td colspan="1" rowspan="1">0.14686</td><td colspan="1" rowspan="1">1.41</td><td colspan="1" rowspan="1">0.079270</td><td colspan="1" rowspan="1">1.77</td><td colspan="1" rowspan="1">0.038364</td></tr><tr><td colspan="1" rowspan="1">0.34</td><td colspan="1" rowspan="1">0.36693</td><td colspan="1" rowspan="1">0.70</td><td colspan="1" rowspan="1">0.24196</td><td colspan="1" rowspan="1">1.06</td><td colspan="1" rowspan="1">0.14457</td><td colspan="1" rowspan="1">1.42</td><td colspan="1" rowspan="1">0.077804</td><td colspan="1" rowspan="1">1.78</td><td colspan="1" rowspan="1">0.037538</td></tr><tr><td colspan="1" rowspan="1">0.35</td><td colspan="1" rowspan="1">0.36317</td><td colspan="1" rowspan="1">0.71</td><td colspan="1" rowspan="1">0.23885</td><td colspan="1" rowspan="1">1.07</td><td colspan="1" rowspan="1">0.14231</td><td colspan="1" rowspan="1">1.43</td><td colspan="1" rowspan="1">0.076359</td><td colspan="1" rowspan="1">1.79</td><td colspan="1" rowspan="1">0.036727</td></tr><tr><td colspan="1" rowspan="1">1.80</td><td colspan="1" rowspan="1">0.035930</td><td colspan="1" rowspan="1">2.16</td><td colspan="1" rowspan="1">0.0153860</td><td colspan="1" rowspan="1">2.52</td><td colspan="1" rowspan="1">0.0058677</td><td colspan="1" rowspan="1">2.88</td><td colspan="1" rowspan="1">0.00198840</td><td colspan="1" rowspan="1">3.24</td><td colspan="1" rowspan="1">0.00059765</td></tr><tr><td colspan="1" rowspan="1">1.81</td><td colspan="1" rowspan="1">0.035148</td><td colspan="1" rowspan="1">2.17</td><td colspan="1" rowspan="1">0.0150030</td><td colspan="1" rowspan="1">2.53</td><td colspan="1" rowspan="1">0.0057031</td><td colspan="1" rowspan="1">2.89</td><td colspan="1" rowspan="1">0.00192620</td><td colspan="1" rowspan="1">3.25</td><td colspan="1" rowspan="1">0.00057703</td></tr><tr><td colspan="1" rowspan="1">1.82</td><td colspan="1" rowspan="1">0.034380</td><td colspan="1" rowspan="1">2.18</td><td colspan="1" rowspan="1">0.0146290</td><td colspan="1" rowspan="1">2.54</td><td colspan="1" rowspan="1">0.0055426</td><td colspan="1" rowspan="1">2.90</td><td colspan="1" rowspan="1">0.00186580</td><td colspan="1" rowspan="1">3.26</td><td colspan="1" rowspan="1">0.00055706</td></tr><tr><td colspan="1" rowspan="1">1.83</td><td colspan="1" rowspan="1">0.033625</td><td colspan="1" rowspan="1">2.19</td><td colspan="1" rowspan="1">0.0142620</td><td colspan="1" rowspan="1">2.55</td><td colspan="1" rowspan="1">0.0053861</td><td colspan="1" rowspan="1">2.91</td><td colspan="1" rowspan="1">0.00180710</td><td colspan="1" rowspan="1">3.27</td><td colspan="1" rowspan="1">0.00053774</td></tr><tr><td colspan="1" rowspan="1">1.84</td><td colspan="1" rowspan="1">0.032884</td><td colspan="1" rowspan="1">2.20</td><td colspan="1" rowspan="1">0.0139030</td><td colspan="1" rowspan="1">2.56</td><td colspan="1" rowspan="1">0.0052336</td><td colspan="1" rowspan="1">2.92</td><td colspan="1" rowspan="1">0.00175020</td><td colspan="1" rowspan="1">3.28</td><td colspan="1" rowspan="1">0.00051904</td></tr><tr><td colspan="1" rowspan="1">1.85</td><td colspan="1" rowspan="1">0.032157</td><td colspan="1" rowspan="1">2.21</td><td colspan="1" rowspan="1">0.0135530</td><td colspan="1" rowspan="1">2.57</td><td colspan="1" rowspan="1">0.0050849</td><td colspan="1" rowspan="1">2.93</td><td colspan="1" rowspan="1">0.00169480</td><td colspan="1" rowspan="1">3.29</td><td colspan="1" rowspan="1">0.00050094</td></tr><tr><td colspan="1" rowspan="1">1.86</td><td colspan="1" rowspan="1">0.031443</td><td colspan="1" rowspan="1">2.22</td><td colspan="1" rowspan="1">0.0132090</td><td colspan="1" rowspan="1">2.58</td><td colspan="1" rowspan="1">0.0049400</td><td colspan="1" rowspan="1">2.94</td><td colspan="1" rowspan="1">0.00164110</td><td colspan="1" rowspan="1">3.30</td><td colspan="1" rowspan="1">0.00048342</td></tr><tr><td colspan="1" rowspan="1">1.87</td><td colspan="1" rowspan="1">0.030742</td><td colspan="1" rowspan="1">2.23</td><td colspan="1" rowspan="1">0.0128740</td><td colspan="1" rowspan="1">2.59</td><td colspan="1" rowspan="1">0.0047988</td><td colspan="1" rowspan="1">2.95</td><td colspan="1" rowspan="1">0.00158890</td><td colspan="1" rowspan="1">3.31</td><td colspan="1" rowspan="1">0.00046648</td></tr><tr><td colspan="1" rowspan="1">1.88</td><td colspan="1" rowspan="1">0.030054</td><td colspan="1" rowspan="1">2.24</td><td colspan="1" rowspan="1">0.0125450</td><td colspan="1" rowspan="1">2.60</td><td colspan="1" rowspan="1">0.0046612</td><td colspan="1" rowspan="1">2.96</td><td colspan="1" rowspan="1">0.00153820</td><td colspan="1" rowspan="1">3.32</td><td colspan="1" rowspan="1">0.00045009</td></tr><tr><td colspan="1" rowspan="1">1.89</td><td colspan="1" rowspan="1">0.029379</td><td colspan="1" rowspan="1">2.25</td><td colspan="1" rowspan="1">0.0122240</td><td colspan="1" rowspan="1">2.61</td><td colspan="1" rowspan="1">0.0045271</td><td colspan="1" rowspan="1">2.97</td><td colspan="1" rowspan="1">0.00148900</td><td colspan="1" rowspan="1">3.33</td><td colspan="1" rowspan="1">0.00043423</td></tr><tr><td colspan="1" rowspan="1">1.90</td><td colspan="1" rowspan="1">0.028717</td><td colspan="1" rowspan="1">2.26</td><td colspan="1" rowspan="1">0.0119110</td><td colspan="1" rowspan="1">2.62</td><td colspan="1" rowspan="1">0.0043965</td><td colspan="1" rowspan="1">2.98</td><td colspan="1" rowspan="1">0.00144120</td><td colspan="1" rowspan="1">3.34</td><td colspan="1" rowspan="1">0.00041889</td></tr><tr><td colspan="1" rowspan="1">1.91</td><td colspan="1" rowspan="1">0.028067</td><td colspan="1" rowspan="1">2.27</td><td colspan="1" rowspan="1">0.0116040</td><td colspan="1" rowspan="1">2.63</td><td colspan="1" rowspan="1">0.0042692</td><td colspan="1" rowspan="1">2.99</td><td colspan="1" rowspan="1">0.00139490</td><td colspan="1" rowspan="1">3.35</td><td colspan="1" rowspan="1">0.00040406</td></tr><tr><td colspan="1" rowspan="1">1.92</td><td colspan="1" rowspan="1">0.027429</td><td colspan="1" rowspan="1">2.28</td><td colspan="1" rowspan="1">0.0113040</td><td colspan="1" rowspan="1">2.64</td><td colspan="1" rowspan="1">0.0041453</td><td colspan="1" rowspan="1">3.00</td><td colspan="1" rowspan="1">0.00134990</td><td colspan="1" rowspan="1">3.36</td><td colspan="1" rowspan="1">0.00038971</td></tr><tr><td colspan="1" rowspan="1">1.93</td><td colspan="1" rowspan="1">0.026803</td><td colspan="1" rowspan="1">2.29</td><td colspan="1" rowspan="1">0.0110110</td><td colspan="1" rowspan="1">2.65</td><td colspan="1" rowspan="1">0.0040246</td><td colspan="1" rowspan="1">3.01</td><td colspan="1" rowspan="1">0.00130620</td><td colspan="1" rowspan="1">3.37</td><td colspan="1" rowspan="1">0.00037584</td></tr><tr><td colspan="1" rowspan="1">1.94</td><td colspan="1" rowspan="1">0.026190</td><td colspan="1" rowspan="1">2.30</td><td colspan="1" rowspan="1">0.0107240</td><td colspan="1" rowspan="1">2.66</td><td colspan="1" rowspan="1">0.0039070</td><td colspan="1" rowspan="1">3.02</td><td colspan="1" rowspan="1">0.00126390</td><td colspan="1" rowspan="1">3.38</td><td colspan="1" rowspan="1">0.00036243</td></tr><tr><td colspan="1" rowspan="1">1.95</td><td colspan="1" rowspan="1">0.025588</td><td colspan="1" rowspan="1">2.31</td><td colspan="1" rowspan="1">0.0104440</td><td colspan="1" rowspan="1">2.67</td><td colspan="1" rowspan="1">0.0037926</td><td colspan="1" rowspan="1">3.03</td><td colspan="1" rowspan="1">0.00122280</td><td colspan="1" rowspan="1">3.39</td><td colspan="1" rowspan="1">0.00034946</td></tr><tr><td colspan="1" rowspan="1">1.96</td><td colspan="1" rowspan="1">0.024998</td><td colspan="1" rowspan="1">2.32</td><td colspan="1" rowspan="1">0.0101700</td><td colspan="1" rowspan="1">2.68</td><td colspan="1" rowspan="1">0.0036811</td><td colspan="1" rowspan="1">3.04</td><td colspan="1" rowspan="1">0.00118290</td><td colspan="1" rowspan="1">3.40</td><td colspan="1" rowspan="1">0.00033693</td></tr><tr><td colspan="1" rowspan="1">1.97</td><td colspan="1" rowspan="1">0.024419</td><td colspan="1" rowspan="1">2.33</td><td colspan="1" rowspan="1">0.0099031</td><td colspan="1" rowspan="1">2.69</td><td colspan="1" rowspan="1">0.0035726</td><td colspan="1" rowspan="1">3.05</td><td colspan="1" rowspan="1">0.00114420</td><td colspan="1" rowspan="1">3.41</td><td colspan="1" rowspan="1">0.00032481</td></tr><tr><td colspan="1" rowspan="1">1.98</td><td colspan="1" rowspan="1">0.023852</td><td colspan="1" rowspan="1">2.34</td><td colspan="1" rowspan="1">0.0096419</td><td colspan="1" rowspan="1">2.70</td><td colspan="1" rowspan="1">0.0034670</td><td colspan="1" rowspan="1">3.06</td><td colspan="1" rowspan="1">0.00110670</td><td colspan="1" rowspan="1">3.42</td><td colspan="1" rowspan="1">0.00031311</td></tr><tr><td colspan="1" rowspan="1">1.99</td><td colspan="1" rowspan="1">0.023295</td><td colspan="1" rowspan="1">2.35</td><td colspan="1" rowspan="1">0.0093867</td><td colspan="1" rowspan="1">2.71</td><td colspan="1" rowspan="1">0.0033642</td><td colspan="1" rowspan="1">3.07</td><td colspan="1" rowspan="1">0.00107030</td><td colspan="1" rowspan="1">3.43</td><td colspan="1" rowspan="1">0.00030179</td></tr><tr><td colspan="1" rowspan="1">2.00</td><td colspan="1" rowspan="1">0.022750</td><td colspan="1" rowspan="1">2.36</td><td colspan="1" rowspan="1">0.0091375</td><td colspan="1" rowspan="1">2.72</td><td colspan="1" rowspan="1">0.0032641</td><td colspan="1" rowspan="1">3.08</td><td colspan="1" rowspan="1">0.00103500</td><td colspan="1" rowspan="1">3.44</td><td colspan="1" rowspan="1">0.00029086</td></tr><tr><td colspan="1" rowspan="1">2.01</td><td colspan="1" rowspan="1">0.022216</td><td colspan="1" rowspan="1">2.37</td><td colspan="1" rowspan="1">0.0088940</td><td colspan="1" rowspan="1">2.73</td><td colspan="1" rowspan="1">0.0031667</td><td colspan="1" rowspan="1">3.09</td><td colspan="1" rowspan="1">0.00100080</td><td colspan="1" rowspan="1">3.45</td><td colspan="1" rowspan="1">0.00028029</td></tr><tr><td colspan="1" rowspan="1">2.02</td><td colspan="1" rowspan="1">0.021692</td><td colspan="1" rowspan="1">2.38</td><td colspan="1" rowspan="1">0.0086563</td><td colspan="1" rowspan="1">2.74</td><td colspan="1" rowspan="1">0.0030720</td><td colspan="1" rowspan="1">3.10</td><td colspan="1" rowspan="1">0.00096760</td><td colspan="1" rowspan="1">3.46</td><td colspan="1" rowspan="1">0.00027009</td></tr><tr><td colspan="1" rowspan="1">2.03</td><td colspan="1" rowspan="1">0.021178</td><td colspan="1" rowspan="1">2.39</td><td colspan="1" rowspan="1">0.0084242</td><td colspan="1" rowspan="1">2.75</td><td colspan="1" rowspan="1">0.0029798</td><td colspan="1" rowspan="1">3.11</td><td colspan="1" rowspan="1">0.00093544</td><td colspan="1" rowspan="1">3.47</td><td colspan="1" rowspan="1">0.00026023</td></tr><tr><td colspan="1" rowspan="1">2.04</td><td colspan="1" rowspan="1">0.020675</td><td colspan="1" rowspan="1">2.40</td><td colspan="1" rowspan="1">0.0081975</td><td colspan="1" rowspan="1">2.76</td><td colspan="1" rowspan="1">0.0028901</td><td colspan="1" rowspan="1">3.12</td><td colspan="1" rowspan="1">0.00090426</td><td colspan="1" rowspan="1">3.48</td><td colspan="1" rowspan="1">0.00025071</td></tr><tr><td colspan="1" rowspan="1">2.05</td><td colspan="1" rowspan="1">0.020182</td><td colspan="1" rowspan="1">2.41</td><td colspan="1" rowspan="1">0.0079763</td><td colspan="1" rowspan="1">2.77</td><td colspan="1" rowspan="1">0.0028028</td><td colspan="1" rowspan="1">3.13</td><td colspan="1" rowspan="1">0.00087403</td><td colspan="1" rowspan="1">3.49</td><td colspan="1" rowspan="1">0.00024151</td></tr><tr><td colspan="1" rowspan="1">2.06</td><td colspan="1" rowspan="1">0.019699</td><td colspan="1" rowspan="1">2.42</td><td colspan="1" rowspan="1">0.0077603</td><td colspan="1" rowspan="1">2.78</td><td colspan="1" rowspan="1">0.0027179</td><td colspan="1" rowspan="1">3.14</td><td colspan="1" rowspan="1">0.00084474</td><td colspan="1" rowspan="1">3.50</td><td colspan="1" rowspan="1">0.00023263</td></tr><tr><td colspan="1" rowspan="1">2.07</td><td colspan="1" rowspan="1">0.019226</td><td colspan="1" rowspan="1">2.43</td><td colspan="1" rowspan="1">0.007 5494</td><td colspan="1" rowspan="1">2.79</td><td colspan="1" rowspan="1">0.0026354</td><td colspan="1" rowspan="1">3.15</td><td colspan="1" rowspan="1">0.00081635</td><td colspan="1" rowspan="1">3.51</td><td colspan="1" rowspan="1">0.00022405</td></tr><tr><td colspan="1" rowspan="1">2.08</td><td colspan="1" rowspan="1">0.018763</td><td colspan="1" rowspan="1">2.44</td><td colspan="1" rowspan="1">0.0073436</td><td colspan="1" rowspan="1">2.80</td><td colspan="1" rowspan="1">0.0025551</td><td colspan="1" rowspan="1">3.16</td><td colspan="1" rowspan="1">0.00078885</td><td colspan="1" rowspan="1">3.52</td><td colspan="1" rowspan="1">0.00021577</td></tr><tr><td colspan="1" rowspan="1">2.09</td><td colspan="1" rowspan="1">0.018309</td><td colspan="1" rowspan="1">2.45</td><td colspan="1" rowspan="1">0.0071428</td><td colspan="1" rowspan="1">2.81</td><td colspan="1" rowspan="1">0.0024771</td><td colspan="1" rowspan="1">3.17</td><td colspan="1" rowspan="1">0.00076219</td><td colspan="1" rowspan="1">3.53</td><td colspan="1" rowspan="1">0.00020778</td></tr><tr><td colspan="1" rowspan="1">2.10</td><td colspan="1" rowspan="1">0.017864</td><td colspan="1" rowspan="1">2.46</td><td colspan="1" rowspan="1">0.0069469</td><td colspan="1" rowspan="1">2.82</td><td colspan="1" rowspan="1">0.0024012</td><td colspan="1" rowspan="1">3.18</td><td colspan="1" rowspan="1">0.00073638</td><td colspan="1" rowspan="1">3.54</td><td colspan="1" rowspan="1">0.00020006</td></tr><tr><td colspan="1" rowspan="1">2.11</td><td colspan="1" rowspan="1">0.017429</td><td colspan="1" rowspan="1">2.47</td><td colspan="1" rowspan="1">0.0067557</td><td colspan="1" rowspan="1">2.83</td><td colspan="1" rowspan="1">0.0023274</td><td colspan="1" rowspan="1">3.19</td><td colspan="1" rowspan="1">0.00071136</td><td colspan="1" rowspan="1">3.55</td><td colspan="1" rowspan="1">0.00019262</td></tr><tr><td colspan="1" rowspan="1">2.12</td><td colspan="1" rowspan="1">0.017003</td><td colspan="1" rowspan="1">2.48</td><td colspan="1" rowspan="1">0.0065691</td><td colspan="1" rowspan="1">2.84</td><td colspan="1" rowspan="1">0.0022557</td><td colspan="1" rowspan="1">3.20</td><td colspan="1" rowspan="1">0.00068714</td><td colspan="1" rowspan="1">3.56</td><td colspan="1" rowspan="1">0.00018543</td></tr><tr><td colspan="1" rowspan="1">2.13</td><td colspan="1" rowspan="1">0.016586</td><td colspan="1" rowspan="1">2.49</td><td colspan="1" rowspan="1">0.0063872</td><td colspan="1" rowspan="1">2.85</td><td colspan="1" rowspan="1">0.0021860</td><td colspan="1" rowspan="1">3.21</td><td colspan="1" rowspan="1">0.00066367</td><td colspan="1" rowspan="1">3.57</td><td colspan="1" rowspan="1">0.00017849</td></tr><tr><td colspan="1" rowspan="1">2.14</td><td colspan="1" rowspan="1">0.016177</td><td colspan="1" rowspan="1">2.50</td><td colspan="1" rowspan="1">0.0062097</td><td colspan="1" rowspan="1">2.86</td><td colspan="1" rowspan="1">0.0021182</td><td colspan="1" rowspan="1">3.22</td><td colspan="1" rowspan="1">0.00064095</td><td colspan="1" rowspan="1">3.58</td><td colspan="1" rowspan="1">0.00017180</td></tr><tr><td colspan="1" rowspan="1">2.15</td><td colspan="1" rowspan="1">0.015778</td><td colspan="1" rowspan="1">2.51</td><td colspan="1" rowspan="1">0.0060366</td><td colspan="1" rowspan="1">2.87</td><td colspan="1" rowspan="1">0.0020524</td><td colspan="1" rowspan="1">3.23</td><td colspan="1" rowspan="1">0.00061895</td><td colspan="1" rowspan="1">3.59</td><td colspan="1" rowspan="1">0.00016534</td></tr></table>

ภาคผนวกข

# สูตรคณิตศาสตร์ที่สำคัญ )

ภาคผนวกนี้จะแสดงสูตรคณิตศาสตร์ที่ใช้่บ่อยสำหรับการวิเคราะห์ระบบการประมวลผลสัญญาณของ ฮาร์ดดิสก์ไดรฟ์ของหนังสือเล่มนี้

## ข.1 ตรีโกณมิติ (Trigonometric)

sin(−α) = − sin(α)   
cOS(−α) = cOs(α)   
sin(α) = coS(α − π/2)   
sin2(α) + cos2(α) = 1   
sin(α ± β) = sin(α) cos(β) ± cos(α) sin(β)   
cOs(α ± β) = cos(α) cos(β) F sin(α) sin(β)   
sin(α) sin(β) = 2 cos(α − β) − 2 cos(α + β)   
sin(α) cos(β) = 1 sin(α + β) + 2 sin(α − β)   
cOS(α) coS(β) = 2 coS(α − β) + 2 coS(α + β)   
cos(α) sin(β) = 2 sin(α + β) − 2 sin(α − β)

$$
\begin{array} { r l } & { \sin ( 2 \alpha ) = 2 \sin ( \alpha ) \cos ( \alpha ) } \\ & { \cos ( 2 \alpha ) = \cos ^ { 2 } ( \alpha ) - \sin ^ { 2 } ( \alpha ) = 1 - 2 \sin ^ { 2 } ( \alpha ) = 2 \cos ^ { 2 } ( \alpha ) - 1 } \\ & { \sin ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 - \cos ( 2 \alpha ) \} } \\ & { \cos ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 + \cos ( 2 \alpha ) \} } \\ & { e ^ { j \alpha } - \cos ( \alpha ) + j \sin ( \alpha ) } \\ & { \sin ( \alpha ) = ( e ^ { j \alpha } - e ^ { - j \alpha } ) / ( 2 j ) } \\ & { \cos ( \alpha ) = ( e ^ { j \alpha } + e ^ { - j \alpha } ) / 2 } \end{array}
$$

## ข.2 ปริพันธ์ไม่จำกัดเขต (Indefinite Integral)

f u dv = uv − f v du เมื่อ น และ V เป็นฟังก์ชันของ x   
f xn dx = xn+1 / (n + 1) เมื่อ n ± −1   
f x−1 dx = ln(x)   
f eax dx = eax /a   
f ln(x) dx = x ln(x) − x   
f xeax dx = eax(ax − 1)/a2   
f x2eax dx = eax (a2x2 − 2ax + 2)/a3   
f sin(ax) dx = −(1/a) cos(ax)   
f cos(ax) dx = (1/a) sin(ax)   
f sin2(ax) dx = x /2 − sin(2ax)/4a   
f x sin(ax) dx = (1/ a2){sin(ax) − ax cos(ax)}   
f cos2(ax) dx = x /2 + sin(2ax)/4a   
f x cos(ax) dx = (1/a2){cos(ax) + ax sin(ax)}

# การหาอนุพันธ์ของเวกเตอร์และเมทริกซ์

ภาคผนวกนีจะสรุปสูตรการหาอนุพันธ์ (differeทtiatioก) ของเวกเตอร์และเมทริกซ์ซึงจะเป็นประโยชน์ ต่อการวิเคราะห์ระบบการประมวลผลสัญญาณของฮาร์ดดิสก์ไดรฟ์ในหนังสือเล่มนี้

กำหนดให้u และ x เป็นเวกเตอร์แนวตั้ง (column vector) ขนาด $k \times 1$ (นั่นคือมีจำนวน k แถว และ 1 แนวตั้ง) และให้ A เป็นเมทริกซ์จัตุรัส (square matrix) ขนาด $k \times k$ ดังนั้น จากการหาอนุพันธ์ของเวกเตอร์และเมทริกซ์จะได้ความสัมพันธ์ดัง $\ddot { \ P }$

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

และ

$$
{ \frac { \partial \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A } \mathbf { u } \right) } { \partial \mathbf { u } } } = \left( \mathbf { A } + \mathbf { A } ^ { \mathrm { T } } \right) \mathbf { u }\tag{ค.5}
$$

$\mathbf { A } = \mathbf { A } ^ { \mathrm { T } }$ จะได้ว่า

$$
\frac { \partial \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A u } \right) } { \partial \mathbf { u } } = 2 \mathbf { A u }\tag{ค.6}
$$

และ

$$
\frac { \partial ^ { 2 } \left( \mathbf { u } ^ { \mathrm { T } } \mathbf { A } \mathbf { u } \right) } { \partial \mathbf { u } \partial \mathbf { u } ^ { \mathrm { T } } } = 2 \mathbf { A }\tag{ค.7}
$$

## ภาคผนวกง

## คำศัพท์เทคนิค

กระบวนการเขียน write process

กระบวนการทำให้มีค่าน้อยสุด minimization process

กระบวนการในการทำนายสัญญาณรบกวน noise prediction process

กระบวนการในการทำให้สัญญาณรบกวนเป็นสีขาว noise whitening process

กระบวนการอ่าน read process

กระแสไฟฟ้าเขียน write current

กลุ่มข้อมูล data packet

การกล้ำรหัสพัลส์ PCM (pulse code modulation)

การกล้ำสัญญาณ (การมอดูเลต) modulation

การขยายสัญญาณรบกวน noise enhancement

การเข้าจังหวะ synchroni zation

การเข้าจังหวะอย่างสมบูรณ์ perfect synchronization

การคาดหมาย, ค่าคาดหมาย expectation

การจัดเก็บข้อมูล data storage

การจัดเก็บข้อมูลดิจิทัล digital data storage

การฉาย projection

การชักตัวอย่าง sampling

การเดินแบบสุ่ม random walk

การได้มา acquisition

การตรวจหาลำดับ sequence detection

การติดตาม tracking

การทำนายสัญญาณรบกวน noise prediction   
การแทรกสอด interference   
การ แทรกสอดระ หว่างสัญลักษณ์ ISI (intersymbol interference)   
การบวก-การเปรียบเทียบ-การเลือก ACS (add-compare-select)   
การบันทึกrecording   
การบันทึกแบบแนวตั้ง perpendicular recording   
การบันทึกแบบแนวนอน longitudinal recording   
การบันทึกแบบไบนารีbinary recording   
การบันทึกระบบแม่เหล็ก magnetic recording   
การประมวลผลแบบเพอเซอร์ไวเวอร์ PSP (per-survivor processing)   
การประมวลผลสัญญาณดิจิทัล digital signal processing   
การปรับค่าทางเวลา timing adjustment   
การ ป้อนก ลับfeedback   
การป้อนก ลับค่าตัดสินใจ decision- feedback   
การเปลี่ยนสถานะ transition   
การเปลี่ยนสถานะ เอกเทศ isolated transition   
การแปลงซีZ transform   
การแปลงฟูเรียร์Fourier transform   
การแปลงฟูเรียร์ที่ต่อเนื่องทางเวลา continuous-time Fourier transform   
การ แพร่กระจายของข้อผิดพลาด error propagation   
การรบกวน di sturbance   
การ ลบล้างสภาพแม่เหล็กdemagnetization   
การเลื่อนตำ แหน่งของการเปลี่ยนสถานะ transition shift   
การ เลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบสุ่ม random transition shift   
การหน่วงเวลาการตัดสินใจ decision delay   
การหาอนุพันธ์ differentiation   
กำลัง power   
เกาส์เซียน Gaussian   
ขนาด magnitude   
ข้อผิดพลาด error   
ข้อผิดพลาดการทำนาย prediction error   
ข้อผิดพลาดกำ ลังสองเฉลี่ย MSE (mean-squared error)   
ข้อผิดพลาดกำ ลังสองเฉลี่ยที่น้อยสุด MMsE (minimum mean-squared error)   
ข้อผิดพลาดทางความถี frequency error   
ข้อผิดพลาดทางเฟส phase error   
ข้อผิดพลาดทางเวลา timing error   
ข้อผิดพลาดทางเวลาที่หลงเหลืออยู่ residual timing error   
ข้อมูลไบนารี binary data   
ข้อมูลวิยุต (แซมเปิล)discrete data   
ควรจะ เป็นมากสุด ML (maximum-likelihood)   
ความจุ capacity   
ความจุช่องสัญญาณ channel capacity   
ความซับซ้อน complexity   
ความถีการ ชักตัวอย่างsampling rate cut-off frequency   
ความถี่แบบนอร์มอลไลซ์normalized frequency   
ความถี่ไนควิตส์Nyquist frequency   
ความน่าจะ เป็น probability   
ความน่าจะ เป็นของข้อผิดพลาด probability of error   
ความน่าจะ เป็นของข้อผิดพลาดลำดับ probability of sequence error   
ความแปรปรวน variance   
ความไม่เป็นเชิงเส้น nonlinearity   
ความหนาแน่นการบรรจุ packing density   
ความหนาแน่นของการบันทึกแบบนอร์มอลไลซ์ ND (normalized recording density)   
ความหนาแน่นเชิงพื้นที่ areal density   
ความหนาแน่นสเปกตรัมกำ ลัง power spectral density   
คอนโวลูชันconvolution   
ค่ากำลังสองเฉลี่ย mean square   
ค่าเฉลี่ย mean   
ค่าตัดสินใจ decision   
ค่าตัดสินใจขณะหนึ่งแบบแข็ง instantaneous hard decision   
คาบ (เวลา)period   
คาบการชักตัวอย่าง sampling period   
คาบเวลาของบิต bit period   
ค่าเมตริกสาขา branch metric   
ค่าเมตริกเส้นทาง path metric   
ค่าลักษณะเฉพาะ eigenvalue   
เครื่องสถานะจำกัด FsM (finite state machine)   
เครื่องหมายเข้าจังหวะ sync mark   
งานประยุกต์ (แอพลิเคชัน)application   
เงื่อนไขบังคับ constraint   
เงื่อนไขบังคับแบบโมนิก monic constraint   
จาน (จานบันทึก) disk   
จานบันทึกแม่เหล็ก magnetic disk   
จิตเตอร์ jitter   
จิตเตอร์ทางเวลา timing jitter   
จุดต่อ node   
จุดสมดุล equilibrium point   
จุดเสถียร ภาพ stable point   
ช่องสัญญาณ channel   
ช่องสัญญาณวิยุต discrete channel   
ช่องสัญญาณสื่อสาร communication channel   
ช่องสัญญาณอ่าน read channel   
ซิปช่องสัญญาณอ่าน read-channel chip   
เชิงเส้น linear   
ซ้อนเหลื่อม overlap   
ซูเปอร์พาราแมกเนติก superparamagnetic   
เซกเตอร์ sector   
แซมเปิล, ตัวอย่างsample   
ไซเคิลสลิปcycle slip   
ดิจิทัลdigital   
ดีเทอร์มิแนนต์determinant   
เดซิเบล dB (decibel)   
โดเมน domain   
โดเมน D D domain   
โดเมน Z Z domain   
โดเมนความถี่frequency domain   
โดเมนเวลา time domain   
ตัวคูณลากรานจ์Lagrange multiplier   
ตัวชีบอก indicator   
ตัวดำเนินการคอนโวลูชัน convolution operator   
ตัวดำเนินการค่าคาดหมาย expectation operator   
ตัวดำเนินการหน่วงเวลาdelay operator   
ตัวนำหน้า predecessor   
ตารางค้นหา look-นp table   
ผลตอบสนอง response   
ผลตอบสนองการเปลี่ยนสถานะ transition response   
ผลตอบสนองของระบบ system response   
ผลตอบสนองเชิงความถี frequency response   
ผลตอบสนองไดบิต dibit response   
ผลตอบสนองทาร์เก็ต target response   
ผลตอบสนองบางส่วน PR (partial response)   
ผลตอบสนองบางส่วนควรจะ เป็นมากสุด PRML (partial-response maximum-likelihood)   
ผลตอบสนองบางส่วนแบบทั่วไปGPR (generalized partial-response)   
ผลตอบสนองอิมพัลส์ impulse response   
ผลตอบสนองอิมพัลส์จำกัด FIR (finite impulse response)   
ผลตอบสนองอิมพัลส์ไม่จำกัด IIR (infinite impulse response)   
แผ่นซีดี CD (compact disc)   
แผ่นดีวีดี DVD (digital versatile disc)   
แผ่นบันทึกแม่เหล็ก magnetic floppy disk   
แผนภาพ diagram   
แผนภาพเทร ลลิส trellis diagram   
พลังงาน energy   
พลังงานหนึ่งหน่วย unit energy   
พหุนาม (โพลิโนเมียล)polynomial   
เพอเซอร์ไวเวอร์ไทมมิ่งริคัฟเวอรี per-survivor timing recovery   
เพอเซอร์ไวเวอร์ไทมมิ่งริคัฟเวอรีแบบทำงานซ้ำ per-survivor iterative timing recovery   
โพลpole   
ฟลักซ์fux   
ฟังก์ชันfunction   
ฟังก์ชันขั้นบันไดstep function   
ฟังก์ชันความหนาแน่นความน่าจะ เป็น probability density function   
ฟังก์ชันความหนาแน่นความน่าจะ เป็นแบบเกาส์เชียน Gaussian probability density function   
ฟังก์ชันโครเนคเกอร์ เดลตา Kronecker delta function   
ฟังก์ชันไดเรคเดลตา Dirac delta function   
ฟังก์ชันถ่ายโอน transfer function   
ฟังก์ชันอิมพัลส์ impulse function   
ไฟฟ้ากระแสตรง d.c. (direct current)   
ภาวะ mode   
ภาวะการได้มา acquisition mode   
ภาวะการได้มาแบบสมบูรณ์ perfect acquisition   
ภาวะการติดตาม tracking mode   
ภาวะการฝึกอบรม training mode   
เมตริก (ตัววัด) metric   
เมทริกซ์การเปลี่ยนสถานะ state transition matrix   
เมทริก ซัสหสัมพันธุ์ข้าม cross-correlation matrix   
เมทริกซ์อัตสหสัมพันธ์ auto-correlation matrix   
เมทริกซ์เอกลักษณ์ identity matrix   
ไม่เข้าจังหวะ asynchronous   
ไม่มีสหสัมพันธ์กัน uncorrelated   
ร หัสแก้ไขข้อผิดพลาด ECC (error-correction code)   
รหัสคอนโวลูชัน convolutional code   
รหัสมอดูเลชัน modulation code   
ระดับขีดเริ่มเปลี่ยน threshold level   
ระบบการจัดเก็บข้อมูล data storage system   
ระบบการบันทึกแม่เหล็ก magnetic recording system   
ระบบที่ถูกเข้ารหัส coded system   
ระบบที่มีแถบความถี่จำกัด band-limited system   
ระบบที่ไม่ได้ถูกเข้ารหัส uncoded system   
ระบบสื่อสารดิจิทัล digital communication system   
ระยะ stage   
ระยะทางกำลังสองเฉลี่ย MSD (mean-squared distance)   
ระยะทางประสิทธิผล effective di stance   
ระ ยะ ทางประ สิทธิผลกำลังสองsquared effective distance   
ระยะทางยุคลิด Euclidean distance   
ระยะทางยุคลิดกำ ลังสอง squared Euclidean distance   
รากกำลังสองเฉลี่ย RMS (root mean square)   
รูปคลื่น waveform   
เรจิสเตอร์แบบเลื่อน shift register   
ลอการิทึมธรรมชาติ natural logarithm   
ลองผิดลองถูก trial and error   
ลำดับ sequence   
ลำดับข้อผิดพลาด error sequence   
ลำดับข้อผิดพลาดอินพุต input error sequence   
ลำดับข้อผิดพลาดอินพุตที่ถูกต้อง valid input error sequence   
ลำดับข้อมูล data sequence   
ลำดับข้อมูลย่อยเลขคี odd subsequence   
ลำดับข้อมูลย่อยเลขคู่ even subsequence   
วงจร VCO VCO (voltage-controlled oscillator)   
วงจรกรอง filter   
วงจรกรองการประมาณค่าในช่วง interpolation filter   
วงจรกรองข้อผิดพลาดการทำนาย prediction error filter   
วงจรกรองทำนาย predictor filter   
วงจรกรองในการทำให้สัญญาณรบกวนเป็นสีขาว noise whitening filter   
วงจรกรองแบบเชิงเส้น linear filter   
วงจรกรองผ่านต่ำ LPF (low-pass filter)   
วงจรกรองผ่านต่ำอุดมคติ ideal low-pass filter   
วงจรกรองลูป loop filter   
วงจรเข้ารหัส encoder   
วงจรเข้ารหัสแก้ไขข้อผิดพลาด error-correction code (ECC) encoder   
วงจรเข้ารหัสมอดูเลชัน modulation encoder   
วงจรชักตัวอย่าง sampler   
วงจรตรวจหา detector   
วงจรตรวจหาข้อผิดพลาดทางเวลา TED (timing error detector)   
วงจรตรวจหาขีดเริ่มเปลี่ยนที่ไม่มีหน่วยความจำ memoryless threshold detector   
วงจรตรวจหาขีดเริ่ มเปลี่ยนที่ไม่มีหน่วยความจำแบบหลายระดับ multi-level memoryless threรhold detector   
วงจรตรวจหาขีดเริ่มเปลี่ยนแบบหลายระ ดับ multi-level threshold detector   
วงจรตรวจหาจุดสูงสุด peak detector   
วงจรตรวจหาลำดับ sequence detector   
วงจรตรวจหา ลำดับที่ควรจะ เป็นมากสุด MLsD (maximum-likelihood sequence detector)   
วงจรตรวจหาลำดับทีเหมาะ ทีสุด optimal sequence detector   
วงจรตรวจหาวีเทอร์บิ Viterbi detector   
วงจรตรวจหาสัญลักษณ์ symbol detector   
วงจรตรวจหาที่เหมาะ ที่สุด opimal detector   
วงจรถอดรหัส decoder   
วงจรถอดรหัสแก้ไขข้อผิดพลาด error-correction code (ECC) decoder   
วงจรถอดรหัสมอดเลชัน modulation decoder   
วงจรกรองทำนายหนึ่งขั้นแบบเชิงเส้นlinear one-step predictor   
วงจรเปลียนสัญญาณแอนะ ล็อกเป็นสัญญาณดิจิทัล ADC (analog-to-digital converter)   
วงจร เฟส ล็อกลูป PLL (phase-locked loop)   
วงจร ภาครับ receiver   
วงจรภาคส่ง tran smitter   
วงจรมอดูเลเตอร์ modulator   
วงจรหาอนุพันธ์ di fferentiator   
เวกเตอร์ ลักษณะ เฉพาะ eigenvector   
เวกเตอร์ ลักษณะ เฉพาะ แบบนอร์มอลไลซ์ normalized eigenvector   
สเตชันเนรี stationary   
สถานะ state   
สถานะต่อไป next state   
สถานะเริ่มต้น start state   
สถาปัตยกรรมช่องสัญญาณอ่าน read-channel architecture   
สเปกตรัมค่าศนย์ spectral null   
สภาพความเป็นแม่เหล็ก (การทำให้เป็นแม่เหล็ก) magnetization   
สภาพความเป็นแม่เหล็กของสื่อบันทึก medium magnetization   
สภาพลบล้างแม่เหล็กcoercivity   
สภาพให้ซึมผ่านได้permeability   
สมการนอร์มอล normal equation   
สมการปรับค่า update equation   
สลับเปลี่ยน (ทรานสโพส) transpose   
ส่วนประกอบ component   
สหสัมพันธุ์ correlation   
สหสัมพันธ์ข้าม cross-correlation   
สัญญาณ signal   
สัญญาณไบนารี (สัญญาณสองระ ดับ) binary signal   
สัญญาณพัลส์ไดบิต dibit pulse   
สัญญาณพัลส์ในควิตส์อุดมคติ ideal Nyquist pulse   
สัญญาณพัลส์ เปลี่ยนสถานะ transition pulse   
สัญญาณพัลส์ เปลี่ยนสถานะ เอกเทศ isolated transition pulse   
สัญญาณรบกวน noise   
สัญญาณรบกวนการเปลี่ยนสถานะtraทร์toก noise   
สัญญาณรบกวนเกาส์สีขาว white Gauรsiaท noise   
สัญญาณรบกวนเกาส์สีขาวแบบบวก AWGN (additive white Gaussiaท noise)   
สัญญาณรบกวนความร้อนthermal noise   
สัญญาณรบกวนจิตเตอร์ของสื่อบันทึกmedia jitter noise   
สัญญาณรบกวนที่ขึ้นอยู่กับแบบข้อมูล pattern-dependent noise   
สัญญาณรบกวนที่อยู่นอกแถบความถี่ out-of-band noise   
สัญญาณรบกวนแบบสิ colored noise   
สัญญาณรบกวนสีขาว white noise   
สัญญาณรบกวนสื่อบันทึก media noise   
สัญญาณแอนะ ล็อกทางไฟฟ้าที่ได้จากหัวอ่าน (สัญญาณ read-back) read-back signal   
สัมประสิทธิ์ coefficient   
สื่อบันทึก (จานแม่เหล็ก) media (or medium)   
เสถียรภาพ stable   
เส้นโค้งรูปตัวเอส S-curve   
เส้นทางที่ยังมีชีวิตอยู่ survivor path   
เส้นสาขาbranch   
หน่วงเวลา delay   
หน่วยความจำของช่องสัญญาณ channel memory   
หน่วยความจำเส้นทางpath memory   
หลักการ เชิงตั้งฉาก Orthogonality principle   
หัวเขียน write head   
หัวอ่าน read head   
เหตุการณ์ event   
เหตุการณ์ข้อผิดพลาด error event   
เหตุการณ์ข้อผิดพลาดที่โดดเด่น dominant error event   
แหล่งต้นทาง source   
แหล่งปลายทาง destination   
ออฟเซตทางความถี่ frequency off set   
ออฟเซตทางเฟส phase offset   
ออฟเซตทางเฟสของการชักตัวอย่าง sampling phase offset   
ออฟเซตทางเวลา timing offset   
อัตราการขยาย gain   
อัตราการ ชักตัวอย่าง sampling rate   
อัตราการชัก ตัวอย่างแบบเกินจริง oversampling rate   
อัตราการ ลู่เข้า convergence rate   
อัตราข้อผิดพลาดบิต BER (bit-error rate)   
อัตราข่าวสาร เชิงเส้นกำกับasymptotic information rate   
อัตราความหนาแน่น density ratio   
อัตราบิต bit rate

ทาร์เก็ต target   
ทาร์เก็ตที่เหมาะที่สุด optimal target   
ทาร์เก็ตแบบ GPR generalized partial-response (GPR) target   
ทาร์เก็ตแบบ PR partial-response (PR) target   
ทำให้เป็นบรรทัดฐาน normalize   
เทคนิคการประมาณค่าในช่วง interpolation technique   
เทระไบต์ TB (terabyte)   
แท็ปtap   
ไทมมิ่งฟังก์ชัน timing function   
ไทมมิ่งฟังก์ชันแบบนอร์มอลไลซ์ normalized timing function   
ไทมมิ่งริคัฟเวอรีtiming recovery   
ไทมมิ่งริ คัฟเวอรี แบบที่ใช้กันทั่วไป conventional timing recovery   
ไทมมิ่งริ คัฟเวอรี แบบนิร นัย deductive timing recovery   
ไทมมิงริ คัฟเวอรี แบบประมาณค่าในช่วง interpolated timing recovery   
-ล inductive timing recovery   
ไทมมิ่งลูป timing loop   
บิตbit   
บิตข่าวสาร message bit   
บิตเซลล์ (คาบของเวลาในหนึ่งบิต) bit cell   
บิตเปลี่ยนสถานะ transition bit   
บิตส่วนเกินredundant bit   
แบนด์วิดท์bandwidth   
แบนด์วิดท์เกินเป็นศูนย์ zero-excess-bandwidth   
แบนด์วิดท์ของลูปloop bandwidth   
แบบข้อมูล data pattern   
แบบจำลอง model   
แบบจำลองการ ทำงานของวงจรเฟสล็อก ลูปแบบเชิงเส้นlinearized phase-locked loop (PLL) model   
แบบจำลองช่องสัญญาณที่ไม่ต่อเนื่องทางเวลาแบบสมมูล equivalent discrete-time channel model   
แบบจำลองช่องสัญญาณเสมือนจริง reali stic channel model   
แบบจำลองช่องสัญญาณอุดมคติ ideal chanทel model   
ไบต์ (1 ไบต์ = 8 บิต) byte   
ไบนารี (ฐานสอง) binary   
ประสิทธิผลของร หัส code efficiency   
ปรับค่า (ให้เป็นปัจจุบัน)update   
ปริมาณหน่วงเวลาในลูป l00p delay

อัตรารหัส code rate

อัตราส่งข้อมูล data rate

อัตราส่วนค่ากำ ลังเฉลี่ยของสัญญาณที่ต้องการต่อค่ากำลังเฉ ลี่ยของสัญญาณรบกวน SNR (signal-to-noi se

อัตสหสัมพันธุ์ auto-correlation

อัลกอริทึม (ขั้นตอนวิธี) algorithm

อัลกอริทึมวีเทอร์บิ Viterbi algorithm

อินดักทีฟ (ประเภทของหัวอ่าน) inductive

อินพุต (รับเข้า, นำเข้า) input

อิ่มตัว saturated

อีควอไลเซซันแบบสมบูรณ์ perfect equalization

อีควอไลเซอร์ equalizer

อีควอไลเซอร์แบบ PR partial-response (PR) equalizer

อีควอไลเซอร์แบบผลตอบสนองเต็ม full-response equalizer

เอาต์พุต (ส่งออก, นำออก) output

เอาต์พุตของช่องสัญญาณ channel output

แอนะ ล็อก analog

ฮาร์ดดิสก์ไดรฟ์ hard disk drive

เฮิรตซ์ Hz (hertz)

## บรรณานุกรม

[1] S. X. Wang and A. M. Taratorin, Magnetic information storage technology. San Diego: Academic Press, 1999.

[2] B. Sklar, Digital communications: fundamentals and applications: Prentice Hall, 2nd-edition, 2001.

[3] A. M. Taratorin, Magnetic recording systems and measurements: Guzik Technical Enterprises, 2004.

[4] J. W. M. Bergmans, Digital baseband transmission and recording. Boston/London/ Dordrecht: Kluwer Academic Publishers, 1996.

[5] T. Suzuki, "Perpendicular magnetic recording: Its basics and potential for the future," IEEE Trans. on Magnetics, vol. MAG-20, no. 5, pp. 675 – 680, September 1984.

[6] J. Moon, "The role of signal processing in data-storage," IEEE Signal Processing Magazine, pp. 54 – 72, July 1998.

[7] S. B. Wicker, Error control systems for digital communication and storage. New Jersey: Printice Hall International, 1995.

[8] B. Vasic and E. M. Kurtas, Coding and signal processing for magnetic recording systems. New York: CRC Press, 2005.

[9] K. A. S Immink, "Runlength-limited sequences," in Proc. of the IEEE, vol. 78, no. 11, pp. 1745 – 1759, November 1990.

[10] ปิยะ โควินท์ทวีวัฒน์, การประมวลผลสัญญาณสำหรับการจัดเก็บข้อมูลดิจิทัล เล่ม 1: พื้นฐาน ช่องสัญญาณอ่าน-เขียน, ศูนย์เทคโนโลยีอิเล็กทรอนิกส์และคอมพิวเตอร์แห่งชาติ (เนคเทค), 2550.

[11] T A. Roscamp, E. D. Boerner, and G. J. Parker, "Three-dimensional modeling of perpendicular recording with soft underlayer," J. of Applied Physics, vol. 91, no. 10, May 2002.

[12] A. V. Oppenheim, A. S. Willsky, and S. H. nawab, Signals and systems. New Jersey: Prentice Hall, 2nd-edition, 1997.

[13] Available online at http://www.mathworks.com

[14] ปิยะ โควินท์ทวีวัฒน์, คู่มือโปรแกรมภาษา รCIAB สำหรับผู้เริ่มต้น (พิมพ์ครั้งที่ 2), ศูนย์ผลิต ตำราเรียน, สถาบันเทคโนโลยีพระจอมเกล้าพระนครเหนือ, 2549.

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

## ดรรชนี

PW50, 6 การบันทึกแบบแนวตั้ง, 6 การบันทึกแบบแนวนอน, 6

GPRML, 133

NPML, 115–135, 138 การทำให้สัญญาณรบกวนเป็นสีขาว, 117 ข้อผิดพลาดกำลังสองเฉลีย, 119 ที่น้อยสุด, 120 ความซับซ้อน, 126 ทาร์เก็ตประสิทธิผล, 122, 123 ประสิทธิภาพ, 129 วงจรกรองทำนาย, 117, 118 หลักการทำงาน, 120–129 หลักการเชิงตังฉาก, 119 เมตริกสาขา, 121, 122

PDNP, 137–150 การทำให้สัญญาณรบกวนเป็นสีขาว, 141 ความซับซ้อน, 146 ประสิทธิภาพ, 146 วงจรกรองทำนาย, 141

หลักการเชิงตังฉาก, 142   
อัลกอริทึม, 140–144   
เพอเซอร์ไวเวอร์ (PรP), 144   
เมตริกสาขา, 140, 141

PLL, 18, 21, 67 การออกแบบค่าพารามิเตอร์, 23–30 อันดับที่สอง การวิเคราะห์เชิงเส้น, 28–30 สมการปรับค่า, 22 อันดับที่หนึ่ง การวิเคราะห์เชิงเส้น, 23–28 สมการปรับค่า, 22 เสถียรภาพ, 24, 28   
preamble, 22, 34   
PRML, 44, 65–88, 115, 126, 137 รหัส (0, G/I), 166 วงจรตรวจหาวีเทอร์บิ,69 อัลกอริทึมวีเทอร์บิ, 75 อีควอไลเซอร์, 66 เครื่องสถานะจำกัด, 71 แผนภาพเทรลลิส, 72

SCILAB, 8, 54

SNR, 21, 104, 130 Electronics, 55 ของเหตุการณ์ข้อผิดพลาด, 100 ต่อบิต (Eb/N0), 31 ประสิทธิผล, 47, 101, 103

กฎของฟาราเดย์, 5   
กระบวนการ การทำให้สัญญาณรบกวนเป็นสีขาว, 116, 138 141 อ่าน, 5–8 เขียน, 5   
กระแสไฟฟ้าเขียน, 4, 5, 152   
การกล้ำรหัสพัลส์ (PCM), 2 ซ   
การชักตัวอย่าง, 11, 18, 21, 36   
การบวก-การเปรียบเทียบ-การเลือก, 122   
การบันทึกระบบแม่เหล็ก, 1 แบบจำลองช่องสัญญาณ, 9   
การบันทึกแบบแนวตั้ง, 3, 44, 54, 96, 103, 147 ทาร์เก็ตแบบ PR, 13, 44 ผลตอบสนองเชิงความถี, 8 สัญญาณพัลส์เปลียนสถานะ, 6 เหตุการณ์ข้อผิดพลาด, 97   
การบันทึกแบบแนวนอน, 3, 96, 129, 147 ทาร์เก็ตแบบ PR, 12, 44 ผลตอบสนองเชิงความถี, 8

สัญญาณพัลส์เปลียนสถานะ, 6 เหตุการณ์ข้อผิดพลาด, 96 การบันทึกแบบไบนารี, 5 ความไม่เป็นเชิงเส้น, 5 การปรับค่าทางเวลา, 37 การออกแบบทาร์เก็ต, 47–54 แบบ h1 = 1, 52 แบบทาร์เก็ตเฉพาะ, 53 แบบพลังงานหนึ่งหน่วย, 53 แบบโมนิก (h0 = 1), 49 การเข้าจังหวะ, 18, 22, 34, 67 แบบสมบูรณ์, 55, 104, 130, 147 การเดินแบบสุ่ม, 20 การเปลี่ ยนสถานะ, 4, 11, 33, 76, 139, 152 ที่ดีที่สุด, 77 ผลตอบสนอง, 6, 45 สภาพความเป็นแม่เหล็ก, 5 เมทริกซ์, 158 เอกเทศ. 6, 55, 104, 130 การเลื่อนตำแหน่งของการเปลี่ยนสถานะแบบสุ่ม, 55, 139 การแทรกสอดระหว่างสัญลักษณ์ (Iร1), 6, 65, 69, 152 การแปลง Z, 24, 28 การแปลงฟูเรียร์ที่ต่อเนื่องทางเวลา, 8 ขีดจำกัดซูเปอร์พาราแมกเนติก, 3

ข้อผิดพลาด กำลังสองเฉลี่ย (MSE), 47, 119 กำลังสองเฉลียที่น้อยสุด (MMรE), 47, 120 การออกแบบทาร์เกิต, 47–54 ทางเวลา, 21, 24, 30, 38 แบบรากกำลังสองเฉลี่ย (RMS), 34

ควรจะ เป็นมากสุด (ML), 44   
ความถี่แบบนอร์มอลไลซ์, 8   
ความถี่ไนควิตส์, 44   
ความหนาแน่น การบรรจุ, 155 ของการบันทึกข้อมล, 6 ของการบันทึกแบบนอร์มอลไลซ์ (ND), 6 สเปกตรัมกำลัง, 20, 55, 103, 130, 147

ช่องสัญญาณอ่าน, 4

ทาร์เก็ต, 53 ที่เหมาะที่สุด, 47 ประสิทธิผล, 122 แบบ GPR, 13, 45 แบบ h1 = 1, 52 แบบทาร์เก็ตเฉพาะ, 53 -ซ แบบพลังงานหนึงหน่วย, 53 แบบโมนิก, 49, 104, 133, 148 แบบ PR, 12 การบันทึกแบบแนวตั้ง, 44

## การบันทึกแบบแนวนอน, 44

บิตเซลล์, 6, 24, 55, 103, 147

ผลตอบสนอง, 116 การเปลี่ยนสถานะ, 6, 45 ขั้นบันได, 25 ข้อผิดพลาด, 26 ทาร์เก็ต, 12, 45, 68, 138 บางส่วน (PR), 12, 43, 68 อิมพัลส์, 20, 30, 148 อิมพัลส์จำกัด (FIR), 67, 117, 138 อิมพัลส์ไม่จำกัด (1IR), 117 เชิงความถี่, 8, 43 เต็ม, 67 ไดบิต, 8, 45

ฟังก์ชัน ขั้นบันได, 23 ข้อผิดพลาด, 6 ความหนาแน่นความน่าจะเป็นแบบเกาส์เซียน, 55, 78, 103, 139, 147 ซิงก์, 20 ถ่ายโอน, 13, 24, 46, 117, 138 เลขชี้กำลัง, 8 โครเนคเกอร์เดลตา, 81

ภาวะ, 22 การติดตาม, 22

การได้มา, 22   
การได้มาแบบสมบูรณ์, 34

รหัส (0, G/I), 166–167   
รหัส RLL, 3, 91, 151–167 ISI, 152 การออกแบบ, 162–164 ความหนาแน่นการบรรจุ, 155 ความจุ, 154–155 ตารางค้นหา, 152, 164 บิตส่วนเกิน, 153 พารามิเตอร์, 151 รหัส (0, G/I), 166 รหัส FM, 164 รหัส MFM, 164 รหัส Miller, 164 อัตราข่าวสารเชิงเส้นกำกับ, 155, 160 อัตราความหนาแน่น, 155–156 อัตรารหัส, 152 ส เครืองสถานะจำกัด, 156–158 เงื่อนไขบังคับ จำนวนลำดับข้อมูล, 153–154 เมทริกซ์การเปลี่ยนสถานะ, 158–159 ไทมมิ่งริศัฟเวอะรี, 152   
รหัส RS, 3   
รหัสคอนโวลูชัน, 69   
รหัสมอดูเลชัน, 151

ระบบการจัดเก็บข้อมูลดิจิทัล, 3 แบบจำลอง, 4 ระบบสือสารดิจิทัล, 17 รูปแบบ NRZI, 4, 151

ลำดับข้อผิดพลาด, 93 อินพุตทีถูกต้อง, 94

วงจร VCO, 18   
วงจรกรอง ข้อผิดพลาดการทำนาย, 118 ทำนาย, 117 ทำนายหนึงขันแบบเชิงเส้น, 118 ผ่านต่ำ, 4 ความถี่ตัด, 20 ลูป, 18   
วงจรชักตัวอย่าง, 4, 18   
วงจรตรวจหา, 4 ขีดเริ่มเปลี่ยน ที่ไม่มีหน่วยความจำ, 31 ที่ไม่มีหน่วยความจำแบบหลายระดับ, 34 แบบหลายระดับ, 21 แบบอ่อน, 38 แบบแข็ง., 38 ข้อผิดพลาดทางเวลา, 18 ที่เหมาะที่สุด, 69 ลำดับที่ควรจะเป็นมากสุด (MLรD), 77 ลำดับเหมาะที่สุด, 137   
วีเทอร์บิ, 12, 21, 69, 115 ความซับซ้อน, 80 ความลึกการถอดรหัส, 80 ความน่าจะเป็นของข้อผิดพลาดลำดับ, 88 ประสิทธิภาพ, 87 วงจรตรวจหาลำดับ, 69 อัลกอริทึม, 69, 75–80 เครืองสถานะจำกัด, 70–72 แผนภาพเทรลลิส, 70, 72–75   
สัญลักษณ์, 21

วงจรถอดรหัส มอดูเลชัน, 4 แก้ไขข้อผิดพลาด, 4

วงจรมอดูเลเตอร์, 4, 5

วงจรเข้ารหัส ก่อน, 91 มอดูเลชัน, 3 แก้ไข้อผิดพลาด, 3

สถาปัตยกรรมช่องสัญญาณอ่าน, 11   
สภาพความเป็นแม่เหล็ก, 1, 139, 152   
สภาพลบล้างแม่เหล็ก, 2, 5   
สภาพให้ซึมผ่านได้, 3   
สมการนอร์มอล, 119

สัญญาณพัลส์ เปลี่ยนสถานะ, 6, 55, 103, 130, 147 0 การบันทึกแบบแนวตั้ง. 6

การบันทึกแบบแนวนอน, 6 เอกเทศ, 55, 104, 130 ไดบิต, 8 ในควิตส์, 20 ในควิตส์อุดมคติ, 12

สัญญาณรบกวน, 11, 20, 21, 45, 68, 93 การขยาย, 45, 66 การขินอยู่กับแบบข้อมูล, 138–140 การทำนาย, 117, 141 จิตเตอร์ของสือบันทึก, 55, 61, 103, 107, 138, 139 สู่ซู ที่ขินอยูกับแบบข้อมูล, 138 ที่อยู่นอกแถบความถี, 11, 20 ภายในวงจรชักตัวอย่าง, 18 สีขาว, 60, 119 เกาส์สีขาว, 69 เกาส์สี ขาวแบบบวก, 20, 55, 66, 75, 99, 103, 115, 138 แบบสี, 93, 99, 116, 138

สเปกตรัมค่าศูนย์, 8, 44, 68

e หลักการเชิงตังฉาก, 119, 142

ออฟเซต ทางความถี, 22, 35 ทางเฟส, 21, 22, 33 สมการปรับค่า, 24, 28 ทางเวลา, 20, 33

อัตราการชักตัวอย่าง, 37 แบบเกินจริง, 37   
อัตราการลู่เข้า, 22–25, 28, 38   
อัตราข้อผิดพลาดบิต (BER), 47   
อัตรารหัส, 69, 152, 154, 156   
อัตสหสัมพันธุ์, 49, 60, 100, 119, 142   
อัลกอริทึม PDNP, 140–144 PS-PDNP, 144–146 วีเทอร์บิ, 69–80, 122 แบบปรับตัว, 143   
อีควอไลเซอร์, 4, 12, 47, 53, 66, 104 อัตราการลู่เข้า, 67 แบบ zero-forcing, 138 แบบผลตอบสนองบางส่วน (PR), 43, 68, 115 แบบผลตอบสนองเต็ม, 67   
เครืองสถานะจำกัด, 70, 71 รหัส RLL, 156 วงจรตรวจหาวีเทอร์บิ, 71   
เทคนิคการประมาณค่าในช่วง, 37   
เพอเซอร์ไวเวอร์ไทมมิ่งริคัฟเวอรี, 38 แบบทำงานซำ, 40   
เส้นทางที่ยังมีชีวิตอยู่, 80, 92   
เส้นโค้งรูปตัวเอส, 21, 30–34 จุดสมดุล, 33

จุดเสถียรภาพ, 32 เหตุการณ์ข้อผิดพลาด, 91 การวิเคราะห์, 91–111 การวิเคราะห์ระยะทางที่น้อยสุด, 104–107 ความสัมพันธ์ระหว่าง SNReff และ BER, 107–109 ความหมาย, 93 นิยาม, 95 รหัส RLL, 91 ระยะทางประสิทธิผล, 99–103 ระยะทางประสิทธิผลกำลังสอง, 101 ที่น้อยสุด, 101 ระยะทางยุคลิด, 97–99 ระยะทางยุคลิดกำลังสอง, 97 ที่น้อยสุด, 99 4บ วงจรเข้ารหัสก่อน, 91

แบนด์วิดท์ ของลูป, 22, 28 เกินเป็นศูนย์, 20   
แบบข้อมูล, 138   
แบบจำลอง การทำให้สัญญาณรบกวนเป็นสีขาว, 117 การทำงานของวงจร PLL, 23 การออกแบบทาร์เก็ต, 47 ช่องสัญญาณ GPR แบบสมมูล, 93 การบันทึกระบบแม่เหล็ก. 9 ที่ไม่ต่อเนื่องทางเวลาแบบสมมูล, 66 อดมคติ, 12–13, 19 เสมื่อนจริง, 11–12 ระบบการจัดเก็บข้อมูลดิจิทัล, 3   
แผนภาพเทรลลิส, 70, 72, 91, 115, 141   
ไซเคิลสลิป, 33   
ไทมมิ่งจิตเตอร์, 18, 20, 39   
ไทมมิ่งฟังก์ชัน, 30 แบบนอร์มอลไลซ์, 32   
ไทมมิ่งริคัฟเวอรี, 12, 17–41 การออกแบบค่าพารามิเตอร์, 23–34 ภาวะการติดตาม, 22 ภาวะการได้มา, 22 แบบดิจิทัล, 37 แบบที่ใช้กันทั่วไป, 18–23 ประสิทธิ ภาพ, 34–37 แบบนิรนัย, 18 แบบประมาณค่าในช่วง, 37 แบบอุปนัย, 18