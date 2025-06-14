# 2. 矩阵及其运算
﻿
﻿矩阵一般不满足的情况：
$①.AB≠BA$ （不满足交换律）
$②.AB=O ≠> A=O 或 B=O$ （阵积是零阵推不出因阵是零阵）
$③.A≠O,A(X-Y)=O ≠> X=Y$ （不满足消去律）

## 2.5 矩阵分块法

### 2.5.5 副对角线 `分块对角矩阵`的行列式与逆矩阵

设有副对角线分块对角矩阵

$$
C = 
\left[
\begin{matrix}
 &A_n\\
 B_m&  
\end{matrix}
\right]
$$

(m,n=1,2,...), 则其行列式

$$
|C| = (-1)^{mn}|A_n|\cdot|B_m|
$$

其逆矩阵(注意：A与B**调换位置**)

$$
C^{-1} = 
\left[
\begin{matrix}
 & {B_m}^{-1}\\
 {A_n}^{-1}
\end{matrix}
\right]
$$

# 3. 矩阵的初等变换与线性方程组

## 3.1 矩阵的初等变换

解线性方程组:

$$
\left\{
\begin{array}{ll}
2x_1-\text{ }\text{ }x_2-\text{ }\text{ }x_3+\text{ }\text{ }x_4=2,\text{ }\text{ }\text{①} \\
\text{ }\text{ }x_1+\text{ }\text{ }x_2-2x_3+\text{ }\text{ }x_4=4,\text{ }\text{ }\text{②} \\
4x_1-6x_2+2x_3-2x_4=4,\text{ }\text{ }\text{③} \\
3x_1+6x_2-9x_3+7x_4=9.\text{ }\text{ }\text{ }\text{④}
\end{array}
\right.
$$

 `方程`的初等变换：
①交换两方程位置
②用非零数乘以某方程
③用某方程的 `n倍`加到另一方程上去

增广矩阵：
B=(A, b)

$$
B = 
\left[
\begin{array}{cccc:c}
2 & -1 & -1 & 1 & 2\\
1  & 1 & -2 & 1 & 4\\
4 & -6 & 2 & -2 & 4\\
3 & 6 & -9 & 7 & 9
\end{array}
\right]
$$

* **`矩阵`的三种初等行变换:**
  ①交换两行
  ②用非零数k乘以某一行
  ③某一行的n倍加到另一行上去
* 矩阵的等价
* | 类型   | 定义                               | 记作                    |
  | ------ | ---------------------------------- | ----------------------- |
  | 行等价 | 矩阵A经过有限次初等行变换得到矩阵B | $A \overset{r}\sim B$ |
  | 列等价 | 矩阵A经过有限次初等行变换得到矩阵B | $A \overset{c}\sim B$ |
  | 等价   | 矩阵A经过有限次初等变换得到矩阵B   | $A \sim B$            |
* 矩阵的性质
  (i) 反身性 $A \sim B$
  (ii) 对称性 若$A \sim B$，则$B \sim A$
  (iii) 传递性 若 $A \sim B$, $B \sim C$, 则 $A \sim C$
* **行阶梯形矩阵**
  非零矩阵若满足:
  (i) 非零行在零行的上面；
  (ii) 非零行的首非零元所在的列，在上一行(若存在的话)的首非零元的右面，
  则称此矩阵为行阶梯形矩阵。如：$B_4$。

  $$
  \begin{bmatrix}
  1 & 1 & -2 & 1 & 4 \\
  0 & 1 & -1 & 1 & 0 \\
  0 & 0 & 0 & 1 & -3 \\
  0 & 0 & 0 & 0 & 0
  \end{bmatrix}
  =B_4
  $$
* **行最简形矩阵**
  若A是行阶梯形矩阵，且满足：
  (i) 非零行的首非零元为1；
  (ii) 首非零元所在列的其他元均为0，
  则称A为行最简形矩阵。如: $B_5$。

  $$
  \begin{bmatrix}
  1 & 0 & -1 & 0 & 4 \\
  0 & 1 & -1 & 0 & 3 \\
  0 & 0 & 0 & 1 & -3 \\
  0 & 0 & 0 & 0 & 0
  \end{bmatrix}
  =B_5
  $$
* 结论
  - 任何非零矩阵$A_{m \times n}$，总可经有限次初等变换，把它变为行阶梯形矩阵和行最简形矩阵。
  - 行最简形矩阵是**唯一**的。但混入列初等变换就不一定了。
* **标准形矩阵**
  对行最简形矩阵再施以初等变换，将其变为左上角是单位矩阵，其余元全为0的矩阵$F$，该矩阵称为标准型。

  $$
  \begin{bmatrix}
  1 & 0 & 0 & 0 & 0 \\
  0 & 1 & 0 & 0 & 0 \\
  0 & 0 & 1 & 0 & 0 \\
  0 & 0 & 0 & 0 & 0
  \end{bmatrix}
  = F
  $$

  对于矩阵$A_{m \times n}$，总可经过出等变换把它化为标准型：

  $$
  F=
  \begin{bmatrix}
  E_r & O\\
  O & O
  \end{bmatrix}
  $$

  此标准形由$m, n, r$三个数完全确定，其中$r$是阶梯形矩阵中非零行的行数。
* **定理1** 设A与B均为$m \times n$的矩阵， 那么
  - (i) $A \overset{r} \sim B$ 的充分必要条件是存在$m$阶可逆矩阵的$P=P_s \dots P_1$，使得$PA=B$；即：
	  - $A \overset{r} \sim B \Leftrightarrow P=P_s \dots P_1, PA=B$，其中：
		  - $(P_s \dots P_1)^{-1} = P_1^{-1} \dots P_s^{-1}$
		  - $|P|=|P_s| \dots |P_1| \neq 0$
  - (ii) $A \overset{c} \sim B$ 的充分必要条件是存在$n$阶可逆矩阵$Q=Q_1 \dots Q_t$，使得$AQ=B$；即：
	  - $A \overset{c} \sim B \Leftrightarrow Q=Q_1 \dots Q_t, AQ=B$
  - (iii) $A \sim B$ 的充分必要条件是存在$m$阶可逆矩阵$P$及n阶可逆矩阵$Q$， 使得$PAQ=B$。即：
	  - $A \sim B, P_s \dots P_1AQ_1 \dots Q_t, PAQ=B$

- **定义 3** 由单位矩阵E经过一次初等变换得到的矩阵成为 `初等矩阵`。
- 三种初等变换，对应有三种初等矩阵：

  - (i) 把单位矩阵中第i, j两行(列)对换， 得到的初等矩阵；
	  -	对换相同序数的**行、列**变换得到的初等矩阵是一样的，即:
		  -	$E(r_i \leftrightarrow r_j) = E(c_i \leftrightarrow c_j)$
  - (ii) 以数$k\neq 0$ 乘单位矩阵的第i行(列)， 得到的初等矩阵;
	  - 在单位矩阵相同序数的**行、列**上乘以一个数，得到的矩阵是相同的，即：
		  - $E(kr_i) = E(kc_i)$
  - (iii) 以$k \neq 0$ 乘单位矩阵的第$j$行(列)加到第$i$行(列)上，得到的初等矩阵。  
	  - **注意:** 单位矩阵E通过第三种**行**变换和**列**变换得到的初等矩阵是不一样的，即：
		  - $E(kr_i + r_j) \neq E(kc_i + c_j)$

- **课本性质1(变换性质)** 
	- 用初等矩阵**左**乘$A$相当于对A做**同种**的初等**行**变换。如：对$A_{m \times n}$ **左**乘$m$阶初等矩阵$P_m$，相当于对其做相应的初等**行**变换:
		- $P_m A_{m \times n} \overset{r} \sim A_{m \times n}$
	- 用初等矩阵**右**乘$A$，相当于对$A$做**同种**的初等**列**变换。如：对$A_{m \times n}$ **右**乘$n$阶初等矩阵$Q_n$，相当于对其做相应的初等**列**变换：
		- $A_{m \times n}P_n \overset{c} \sim A_{m \times n}$
- **转置性质** 初等矩阵的**转置**仍是 **同种**的初等矩阵
	- $[E(i\leftrightarrow j)]^T = E(i\leftrightarrow j)$
	- $[E(i(k))]^T = E(i(k))$
	- $[E(ij(k))]^T = E(ji(k))$
- **可逆性质** 初等矩阵均可逆，其逆阵也是**同种**的初阵
	- **第1种初等矩阵**的行列式等于$-1 \neq 0$，故可逆。其逆矩阵等于它本身，即：
		- $[E(i \leftrightarrow j)]^{-1} = E(i \leftrightarrow j)$
	- **第2种初等矩阵**的行列式等于所乘系数$k \neq 0$，故可逆。其逆矩阵等于它本身：
		- $[E(i(k))]^{-1} = E(i(\frac{1}{k}))$
	- **第3种初等矩阵**的行列式等于$1 \neq 0$，故可逆
		- $[E(ij(k))]{-1} = E(ij(-k))$
- **课本性质2** 方阵$A$可逆的**充要**条件是存在**有限个**初等矩阵$P_1, P_2, \ldots, P_l$, 使$A=P_1P_2 \ldots P_l$. 即：
	- $A$可逆 $\Leftrightarrow \exist 初阵P_1, P_2, \dots, P_l, 使 A=P_1P_2 \ldots P_l$
- **课本推论**
	-  方阵A可逆的**充要**条件是 $A \overset{r} \sim E$，即：
		- $A_n可逆 \Leftrightarrow A_n \overset{r} \sim E$

* **求可逆矩阵P:**
$$
PA=B \Leftrightarrow
\begin{cases}
PA=B\\
PE=P
\end{cases}
\Leftrightarrow
P(A, E)=(PA, PE)=(B, P)
\Leftrightarrow
(A, E) \overset{r} \sim (B, P)
$$
	- 当$F$中有**0行**时(A行满秩)，$P$ **不**唯一，否则(A不是行满秩)$P$ **唯一**。
	- ***课本例1**设
	$$
	A=
	\begin{bmatrix}
	2&-1&-1\\
	1&1&-2\\
	4&-6&2
	\end{bmatrix}
	$$ $的行最简形矩阵为F，求F，并求一个可逆矩阵P，使PA=F$.
- **求$A^{-1}$**
	- $(A, E) \overset{r} \sim (F, P), 当F=E时，P=A^{-1}$
	- 解释：由上面“*求可逆矩阵$P$”的过程知，在$(A, E) \overset{r} \sim (F, P)$中，F是行最简形矩阵，若$F=E$，由上面的推论知$A$可逆，且由$PA=F=E$可知，$P$为A的逆矩阵，即$P=A^{-1}$。
	- **课本例2:** 设
	$$
	A=
	\left[ \begin{matrix} 
	0 & -2 & 1\\
	3 & 0 & -2 \\ 
	-2 & 3 & 0 
	\end{matrix} \right]
	$$, 证明$A$可逆，并求$A^{-1}$。
- **解矩阵方程$AX=B$**
	- **课本例3:**
	求解矩阵方程$AX=B$，其中
	$$
	A=
	\left[\begin{matrix}
	2 & 1 & -3\\
	1 & 2 & -2\\
	-1 & 3 & 2
	\end{matrix}\right],
	B=
	\left[\begin{matrix}
	1 & -1\\
	2 & 0\\
	-2 & 5
	\end{matrix}\right].
	$$
	- **思路1:**
	$$
	(A, E) \overset{r} \sim (E, A^{-1}) \Rightarrow A^{-1}，\\
	对AX=B两边同乘以A^{-1}，即：\\
	A^{-1}AX=A^{-1}B \\
	\Rightarrow X=A^{-1}B
	$$
	- **思路2：** 
		$$
		由(A, B)=
		\left[
		\begin{array}{ccc:cc}
		2 & 1 & -3 & 1 & -1\\
		1 & 2 & -2 & 2 & 0\\
		-1 & 3 & 2 & -2 & 5
		\end{array}
		\right]
		\overset{r} \sim 
		\left[
		\begin{array}{ccc:cc}
		1 & 0 & 0 &-4 & 2\\
		0 & 1 & 0 & 0 & 1\\
		0 & 0 & 1 & -3 & 2
		\end{array}
		\right]
		$$ 
		$$可见
		A \overset{r} \sim E，因此A可逆，且
		X=A^{-1}B=
		\left[\begin{matrix}
		-4 & 2\\
		0 & 1\\
		-3 & 2
		\end{matrix}\right]
		即为所给方程的唯一解。
		$$
	$A^{-1}=P_1 \dots P_s$
	
	|前提|推导|
	|:----:|:----:|
	|$A^{-1}A=E$ <br> $X=A^{-1}B$ | $P_1 \dots P_sA=E$ <br> $P_1 \dots P_sB=X$|

- ***求解线性方程组**
	- **课本例4：** 求解线性方程组
		$$
		\begin{cases}
		\text{ }\text{ }x_1-\text{ }\text{ }x_2-\text{ }\text{ }x_3=2\\
		2x_1-\text{ }\text{ }x_2-3x_3=1\\
		3x_1+2x_2-5x_3=0.
		\end{cases}
		$$
		解： 记此方程组为$Ax=b$，则增广矩阵
		$$
		\overset{-}A=(A, b)=
		\left[
		\begin{array}{lll:l}
		1&-1&-1&2\\
		2&-2&-3&1\\
		3&2&-5&0
		\end{array}
		\right]
		\overset{r}\sim 
		\left[
		\begin{array}{lll:l}
		1&0&0&5\\
		0&1&0&0\\
		0&0&1&3
		\end{array}
		\right]
$$
$$
\because A \overset{r} \sim E \\
\therefore A可逆 \\
\therefore 方程组有解，解为：\\
x=A^{-1}b=
\left[
\begin{matrix}
3\\
0\\
5
\end{matrix}
\right]
$$
## 3.2 矩阵的秩
### 3.2.1 定义4 $k$阶子式
$在m \times n 矩阵A中，任取k行与k列(k \leq m, k \leq n )， 位于这些行列交叉处的k^2个元素，不改变它们在A中所处的位置次序而得的k阶行列式，称为$ **矩阵$A$的$k$阶子式**.

$A_{m \times n}$的$k$阶子式共有$C_m^k \cdot  C_n^k$个.
### 3.2.2 引理
**设$A \overset{r} \sim B$，则$A$与$B$中非零子式的最高阶数相等**.
### 3.2.3 定义5 矩阵的秩
$设在矩阵A中有一个不等于0的r阶子式D，且所有r+1阶子式(若存在的话)全等于0， 那么D称为矩阵A的$ **最高阶非零子式** ，$阶数r称为$**矩阵$A$的秩**，$记作r(A). 并规定零矩阵的秩等于0.$

$\because r(A) 是A的非零子式的最高阶数$
$\therefore 若A中由某个s阶子式不为0，则r(A) \geq s; 若A中所有t阶子式全为0，则r(A)<t.$

$若A为 m \times n矩阵，则 0 \leq r(A) \leq min \{m, n\}$

$r(A^T)=r(A)$

$对于A_n，当|A| \neq 0时，r(A)=n，当|A|=0时，r(A)<n. 故，可逆矩阵的秩等于其阶数，不可逆矩阵的秩小于其阶数. 可逆矩阵又称$**满秩矩阵**, 不可逆矩阵(奇异矩阵)又称**降秩矩阵**.

### 3.2.4 定理2 若$A \sim B$，则$r(A)=r(B)$.
初等变换，不改变矩阵的秩。
$\because A \sim B \Leftrightarrow \exist 可逆矩阵P、Q，使PAQ=B$ 
$\therefore 可得$
- **推论** $若可逆矩阵P，Q使PAQ=B，则r(A)=r(B).$
- 行阶梯形矩阵的秩等于非零行的行数.
### 3.2.5 矩阵的秩的性质
$①0\leq r(A_{m \times n}) \leq min\{m, n\}.$
$②r(A^T)=r(A).$
$③A \sim B \Leftrightarrow r(A)=r(B).$
$④若P、Q可逆，则r(A)=r(PA)=r(AQ)=r(PAQ).$
$k \neq 0, 则 r(kA)=r(A).$
$⑤max\{r(A), r(B)\} \leq r(A, B) \leq r(A)+r(B).$
$⑥r(A+B) \leq r(A) + r(B).$
$⑦R(AB) \leq min\{r(A), r(B)\}$
$⑧若A_{m \times n}B_{n \times l}=O, 则r(A)+r(B) \leq n$
- **例8**证明：$若A为n阶方阵，则r(A+E)+r(A-E) \geq n.$
- **秩**等于其列数的矩阵，称为**列满秩矩阵**. 当列满秩矩阵是**方阵**时，称为**满秩矩阵**，即可逆矩阵。
- **例9** 证明：$若A_{m \times n}B_{n \times l}=C， 且r(A)=n， 则r(B)=r(C).$
**证:** $$
由r(A)=n， 知A的行最简形矩阵为
\left[\begin{matrix}
E_n\\
O
\end{matrix}\right]_{m \times n}，\\
并有m阶可逆矩阵P, 使PA=
\left[\begin{matrix}
E_n\\
O
\end{matrix}\right]. 于是\\
PC=PAB=\left[\begin{matrix}
E_n\\
O
\end{matrix}\right]B=
\left[\begin{matrix}
E_nB\\
OB
\end{matrix}\right]
=
\left[\begin{matrix}
B\\
O
\end{matrix}\right].\\
由矩阵秩的性质④，知r(C)=r(PC)， 而
r\left[\begin{matrix}
B\\
O
\end{matrix}\right]=r(B)， 故\\
r(C)=r(B).
$$

- **例9结论** **设$AB=O$，若$A$为列满秩矩阵，则$B=O.$**
$这是因为，按本例的结论，这时有r(B)=0， 故B=O. 这一结论通常称为$**矩阵乘法的消去律.**
- **例9方阵结论** **若$A$为$n$阶方阵，且$r(A)=n$，则$A$可逆，则$r(B)=r(AB)=r(C)$**

## 3.3 线性方程组的解
### 3.3.1定理3 
- **$n$元线性方程组$Ax=b$**
	- ① 当$r(A) = r(\overset{-} A)=n$时，有唯一解；
	- ② 当$r(A) = r(\overset{-}A)<n$时，无穷多解；
	- ③ 当$r(A) \neq r(\overset{-}A)$时，无解。
- **$n$元齐次线性方程组$Ax=0$**
	- 当$x=0$时，$A \cdot 0=0$一定成立，故$Ax=0$一定有解，至少有$0$解。
	- $r(A)=r(\overset{-}A)$
	- $r(A)=n$时，只有0解.
	- $r(A)<n$时，有无穷多非0解.

**\*Note:** 如果只是判断方程组有解还是误解，只将$\overset{-}A$划至$\tilde A$即可；若要求出解，必须划至**行最简形矩阵**。解齐次线性方程组时，只用A，不用$\overset{-}A$。
设$r(A)=r(\overset{-}A)=r$，把**行最简形**中$r$个非零行的首非零元所对应的未知数取作非自由未知数，其余$n-r$个未知数取作自由未知数，并令自由未知数分别等于$c_1，c_2，\dots，c_{n-r}$，由$\overset{-}A$是行最简形矩阵，即可写出含$n-r$个参数的通解. 例如课本例12的行最简形矩阵是：
$$
\left[\begin{matrix}
1&0&-\frac{3}{2}&\frac{3}{4}&\frac{5}{4}\\
0&1&-\frac{3}{2}&-\frac{7}{4}&-\frac{1}{4}\\
0&0&0&0&0
\end{matrix}\right]
$$

其通解可写为：

**x**=$\left[\begin{matrix}
x_1\\
x_2\\
x_3\\
x_4
\end{matrix}\right]
=c_1
\left[\begin{matrix}
\frac{3}{2}\\
\frac{3}{2}\\
1\\
0
\end{matrix}\right]+c_2
\left[\begin{matrix}
-\frac{3}{4}\\
\frac{7}{4}\\
0\\
1
\end{matrix}\right]+
\left[\begin{matrix}
\frac{5}{4}\\
-\frac{1}{4}\\
0\\
0
\end{matrix}\right]$
### 3.3.2 定理5
线性方程组**Ax=b**有解的充要条件是**r(A)=r(A, b)**.即：
$Ax=b有解 \Leftrightarrow r(A) = r(A, b)$
### 3.3.2 课本定理6
$AX=B$有解，当且仅当A的秩等于增广矩阵(A, B)的秩。
$AX=B$有解 $\Leftrightarrow r(A)=r(A, B)$ 
### 3.3.3 课本定理7
**设$AB=C$，则$r(c) \leq min\{r(A), r(B)\}$**.

# 4. 向量组的线性相关性
<!--stackedit_data:
eyJoaXN0b3J5IjpbODc4MTg0NDI3LDEwNTg5ODQzNTgsMTc1Nz
AwOTUyOCwxMzY2MDY2MDkzLDE2MDk5NDU1MDMsLTUxMTkxMzQw
MSwtMTY1NDE5NTM1Miw5MjI5NTMyMjgsMjQ5OTIxNjE2LDE0ND
I0OTgyMiw1MTYwNTQ0NTksLTE0OTEzNDg0ODMsNDY3MDc1ODYs
LTIxMDAwNjQ5MTksLTg4OTIyMTM5OCw1MzYwNjQ0ODcsMjQxOT
Q0MzQ2LC0xMjkzNDgzMDI4LC05NTA5NjkxNzAsMjAzNDAwNjM3
N119
-->