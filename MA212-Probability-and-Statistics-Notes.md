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

#### 1.2.1 频率

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

#### 1.2.2 概率



