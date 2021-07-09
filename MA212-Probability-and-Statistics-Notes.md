# 概率论与数理统计 Probability and Statistics

南方科技大学 计算机科学与工程系 11812804 董正

---

[TOC]

---

## 前言 Preface

本笔记是把我曾经手写的笔记敲成电子版

---

## 第一章 概率

### 1.2 样本空间

#### 1.2.1 试验

* 试验的概念

  * 科学实验
  * 对某事物的某一特征进行观察

* 随机试验的特征

  1. 试验可以在相同的条件下重复进行
  2. 试验的结果可能不止一个，但试验前知道全部可能结果
  3. 试验的结果无法预知

  随机试验用字母 $E$ 表示

* 结果的分类

  1. 基本结果（不可分）$\omega$

     又称样本点、基本事件

     例：掷骰子掷出 6 点

  2. 复合结果（可分解）

     称为随机事件，简称事件

     * 基本事件的复合
     * 样本空间的子集

     例：掷出 3 以上的点数

#### 1.2.2 样本空间 $\Omega$

* 试验的全部样本点构成的集合

* 例：掷一枚骰子，观察出现的点数

  $\Omega=\{1, 2, 3, 4, 5, 6\}$

#### 1.2.3 几种特殊事件

1. 基本事件

   一个样本点构成的单点集 $\{\omega \}$

2. 必然事件

   每次试验都发生的事件

3. 不可能事件 $\empty$

   $\empty\subset\Omega$

4. 事件域

   $\mathcal A=\{A|A\subset\Omega, A 是事件\}$

#### 1.2.4 事件之间的关系及运算

##### 1.2.4.1 事件之间的关系

1. $A\subset B$：$A$ 包含于 $B$

   $A$ 发生必然导致 $B$ 发生

   $A=B\equiv A\subset B\land B\subset A$

2. $A\cup B=\{\omega|\omega\in A\lor \omega\in B \}$

   $A$ 发生或 $B$ 发生，称为 $A$ 与 $B$ 的和事件

3. $A\cap B=\{\omega|\omega\in A\land \omega\in B \}$

   $A$ 与 $B$ 同时发生，称为 $A$ 与 $B$ 的积事件，可记作 $AB$

   $\bigcap_{i=1}^nA_i=\{\omega|\omega\in A_i, i=1, 2,\dots, n \}$ ($n$ 可以是 $\infin$)

4. $A\backslash B=\{\omega|\omega\in A\land \omega\notin B \}$

   $A$ 发生 $B$ 不发生，称为 $A,B$ 的差

   若 $A\supset B$, 则称 $A\backslash B$ 为真差

   $A\backslash B$ 也记作 $A-B$ (存疑)

5. 若 $A\cap B=\empty$，则称 $A,B$ 互斥（互不相容）

   $A,B$ 不可同时发生

6. 若 $A\cup B=\Omega$ 且 $A\cap B=\empty$，则称 $A, B$ 互为对立事件（逆事件）

   $A=\Omega\backslash B=\overline B=B^c$

##### 1.2.4.2 运算律

1. 交换律

   $A\cup B=B\cup A$

   $A\cap B=B\cap A$

2. 结合律

   $(A\cup B)\cup C=A\cup(B\cup C)$

   $(A\cap B)\cap C=A\cap(B\cap C)$

3. 分配律

   $A\cup (B\cap C)=(A\cup B)\cap(A\cup C)$

   $A\cap (B\cup C)=(A\cap B)\cup(A\cap C)$

   <span style="color:blue">$A\cap(B\cap C)=AB\cap AC=ABC$</span>

4. 摩根律

   $\overline{A\cap B}=\overline A\cup\overline B$

   $\overline{A\cup B}=\overline A\cap\overline B$

   <span style="color:blue">$P(\overline A\cup\overline B)=1-P(\overline{\overline A\cup\overline B})=1-P(A\cap B)$</span>

---

### 1.3 概率测度

#### 1.3.1 频率

* 定义

  设 $A$ 为一随机事件，相同条件下重复 $n$ 次试验

  $n_A=n$ 次试验中 $A$ 发生的次数

  $f_n(A)=\frac{n_A}{n}$，称 $n_A$ 为 $A$ 的频数，$f_n(A)$ 为 $A$ 的频率

  * 一般来说 $n$ 越大 $n_A$ 越大
  * $n_A,f_n(A)$ 的值是随机的
  * $0\leqslant f_n(A)\leqslant 1$
  * $f_n(\Omega)=1$

* 频率依概率收敛于概率

  $\lim_{n\to\infin}f_n(A)=p$

* 有限可加性

  若 $A_1, A_2,\dots, A_m$ 是两两不相容事件，则
  $$
  f_n(\bigcup_{i=1}^m A_i)=\sum_{i=1}^m f_n(A_i)
  $$

#### 1.3.2 概率

* 概率的公理化定义 (柯尔莫哥洛夫, 1933)

  设 $\mathcal A$ 为样本空间 $\Omega$ 上的事件域，$\forall A\in \mathcal A$，若 $\exists P(A)\in \R$ 与其对应，且满足

  1. 非负性

     $P(A)\geqslant0$

  2. 规范性

     $P(\Omega)=1$

  3. 可列可加性

     对两两不相容的事件列 $\{A_k\}_{k=1}^\infin$ 有
     $$
     P(\bigcup_{k=1}^\infin A_k)=\sum_{k=1}^\infin P(A_k)
     $$

  则称 $P(A)$ 为事件的概率，称 $\{\Omega, A, P\}$ 为概率空间

  * 以上是概率这个概念的标准定义，并不是概率的确定方法，你可以说扔硬币正反面的概率是 0.2, 0.8，确实满足定义。但是，是否存在这样的一种硬币，以及一枚标准硬币是否是这样的概率分布，并不能通过公理进行证明。古典概型、几何概型那些才是怎么计算概率究竟是几。

    https://www.zhihu.com/question/50046323

* 概率的性质

  1. $P(\empty)=0$

     证明：

     $\because\empty=\empty\cup\empty\cup\cdots$

     $\therefore P(\empty)=P(\empty)+P(\empty)+\cdots$ (可列可加性)

     $\because P(\empty)\in\R$

     $\therefore P(\empty)=0$

  2. 有限可加性

     若 $A_1, A_2,\dots, A_n$ 是两两不相容事件，则
     $$
     P(\bigcup_{i=1}^n A_i)=\sum_{i=1}^nP(A_i)
     $$
     
3. 若 $A\subset B$ 则
  
   * $P(B\backslash A)=P(B)-P(A)$
     * $P(B)\geqslant P(A)$
  
   证明：
  
   $\because A\subset B$
  
   $\therefore B=A\cup(B\backslash A)$
  
   互斥事件，根据有限可加性，$P(B)=P(A)+P(B\backslash A)$
  
   $\therefore P(B\backslash A)=P(B)-P(A), P(B)\geqslant P(A)$
  
4. $0\leqslant P(A)\leqslant1$
  
5. $P(\overline A)=1-P(A)$
  
6. $P(A)\geqslant P(AB)$
  
7. 加法定律 (很重要)
  
   $P(A\cup B)=P(A)+P(B)-P(A\cap B)$
  
8. 挖补原理
     $$
     P(A_1\cup A_2\cup\cdots A_n)=\sum_{i=1}^nP(A_i)-\sum_{1\leqslant i\leqslant j\leqslant n}P(A_iA_j)+\sum_{1\leqslant i\leqslant j\leqslant k\leqslant n}P(A_iA_jA_k)-\cdots+(-1)^{n-1}P(A_1A_2\cdots A_n)
     $$
     规律：加奇减偶
  
例：已知空气中 PM 2.5 含量一般在 $0$ 到 $120\ \mu g/m^3$, SO~2~ 含量一般在 $0$ 到 $0.304\ ppm$ 之间，PM 2.5 含量在 $100.5\ \mu g/m^3$ 或 SO~2~ 含量在 $0.205\ ppm$ 以上，则认为空气有害。求空气有害的概率
  
几何概型
  
![](./images/1-3-1.png)
  
$P(A)+P(B)-P(A\cap B)$

---

### 1.4 概率计算

#### 1.4.1 古典概型

1. 古典概型的概念

   * 特征

     * $\Omega$ 只有有限个样本点，即 $\Omega=\{\omega_1, \omega_2,\dots,\omega_n \}$
     * 每个样本点出现的可能性相等，即 $P\{\omega_1\}=P\{\omega_2\}=\cdots=P\{\omega_n\}=\frac 1n$
     * 又称为等可能概型

   * 概率计算

     $A=\{\omega_{i_{1}},\omega_{i_{2}},\dots,\omega_{i_{k}} \}$

     则 $P(A)=P\{\omega_{i_{1}}\}+P\{\omega_{i_{2}}\}+\cdots+P\{\omega_{i_{k}}\}=\frac kn$

     $P(A)=\frac{A 的有利场合数}{样本点总数}$

2. 排列组合

   * 选排列

     $A_n^k=\frac{n!}{(n-k)!}=n(n-1)\cdots(n-k+1)$

   * 全排列

     $A_n^n=n!$

   * 组合

     $C_n^k=\binom nk=\frac{A_n^k}{A_k^k}=\frac{n!}{k!(n-k)!}=\frac{n(n-1)\cdots(n-k+1)}{k!}$

3. 加法原理

   做一件事有 $n$ 类方法，第 1 类有 $m_1$ 种方法，第 2 类有 $m_2$ 种方法...第 $n$ 类有 $m_n$ 种方法

   则方法总数 $N=\sum_{i=1}^n m_i$

4. 乘法原理

   做一件事有 $n$ 个步骤，第 1 步有 $m_1$ 种方法，第 2 步有 $m_2$ 种方法...第 $n$ 步有 $m_n$ 种方法

   则方法总数 $N=\prod_{i=1}^n m_i$

   * 推广

     $n$ 个对象分成 $r$ 类，第 $i$ 类有 $n_i$ 个对象，$i=1,2,\dots,r$ 且 $\sum_{i=1}^r n_i=n$，那么分类方式有
     $$
     \binom{n}{n_1n_2\cdots n_r}=\frac{n!}{n_1!n_2!\cdots n_r!}=C_n^{n_1}C_{n-n_1}^{n_2}C_{n-n_1-n_2}^{n_3}\cdots C_{n-n_1-n_2-\cdots-n_{r-1}}^{n_r}
     $$

* 例：$n$ 个球放入 $N$ 个不同盒，求每盒至多一球的概率

  共 $N^n$ 种投法（每个球有 $N$ 种选择）

  有利场合：$N$ 个盒中选 $n$ 个：$A_N^n$

  $\therefore P=\frac{A_N^n}{N^n}$

#### 1.4.2 几何概型

* 随机试验

  向平面有界区域 $\Omega$ 投掷一个点

* 样本空间

  $\Omega$

* 事件

  点落在可测量面积的平面区域 $A$

* 事件概率

  $P(A)=\frac{Area(A)}{Area(\Omega)}$

则称上述试验为几何概型

* 事件 $A$ 发生的概率与位置无关，只与 $A$ 的面积有关，这体现了某种等可能性
* 一维或者三维的情况就是长度、体积

#### 1.4.3 习题

1. 证明 $P(AB)+P(AC)-P(BC)\leqslant P(A)$

   证明：

   $\because P(A)\geqslant P(A\cap(B\cup C)), P(BC)\geqslant P(ABC)$

   $\therefore P(A)+P(BC)\geqslant P(A\cap(B\cup C))+P(ABC)$

   由加法定律，$P(A\cap(B\cup C))=P(AB\cup AC)=P(AB)+P(AC)-P(ABC)$

   $\therefore P(A)+P(BC)\geqslant P(AB)+P(AC)-P(ABC)+P(ABC)=P(AB)+P(AC)$

   $\therefore P(A)\geqslant P(AB)+P(AC)-P(BC)$

2. 证明 $P(AB)+P(AC)+P(BC)\geqslant P(A)+P(B)+P(C)-1$

   证明：

   即证 $P(A)+P(B)+P(C)-P(AB)-P(AC)-P(BC)\leqslant 1$

   $\because P(A\cup B\cup C)=P(A)+P(B)+P(C)-P(AB)-P(AC)-P(BC)+P(ABC)$

   $\therefore$ 即证 $P(A\cup B\cup C)-P(ABC)\leqslant 1$

   

   $\because P(A\cup B\cup C)\leqslant 1, P(ABC)\leqslant 1$

   $\therefore P(A\cup B\cup C)-P(ABC)\leqslant 1$

   $\therefore$ 原式得证

3. 把 $n$ 个 $0$ 与 $n$ 个 $1$ 随机排列，求没有两个 $1$ 连着的概率

   可以看成有 $2n$ 个位置，只需要考虑 1 放在哪里，剩下的自然是 0

   $\therefore$ 共 $C_{2n}^n$ 种放法

   接下来，用 0 把 1 隔开，需要 $n-1$ 个 0，还剩一个，考虑把它插到哪里

   1 0 1 0 1 0 ...

    $\uparrow$  $\uparrow$

   这两个位置效果一样，都是 1001，所以我们就假设这个 0 只插到 1 的右边，这样有 $n$ 种插法。还有一种是插在开头，所以一共 $n+1$ 种

   $\therefore P=\frac{n+1}{C_{2n}^n}$

4. 袋子中有 $n-1$ 个黑球和 1 个白球，每次从口袋中随机摸出一个球，并放入一个黑球，求第 $k$ 次摸球时摸到黑球的概率

   设 $A_k=\{第k次摸到黑球\}$，则 $\overline{A_k}=\{第k次摸到白球\}$

   考虑 $\overline{A_k}$ 的情况：

   因为袋子中只有 1 个白球，所以前 $k-1$ 次摸到的都是黑球

   $\therefore P(\overline{A_k})=(\frac{n-1}{n})^{k-1}\frac 1n=\frac 1n(1-\frac 1n)^{k-1}$

   $\therefore P(A_k)=1-P(\overline{A_k})=1-\frac 1n(1-\frac 1n)^{k-1}$

5. 掷 $n$ 课骰子，求出现点数最大为 5 的概率

   设 $A=\{最大点数为5\}, B=\{最大点数不超过5\}, C=\{最大点数不超过4\}$

   $\therefore C\subset B$ 且 $A=B\backslash C$

   $\therefore P(A)=P(B)-P(C)=(\frac 56)^n-(\frac 46)^n=\frac{5^n-4^n}{6^n}$

6. $n$ 个人围一圆桌坐，求甲、乙两人相邻的概率

   假设甲先坐好，则乙只有两个位置可坐

   $P=\frac{2}{n-1}$

---

### 1.5 条件概率





