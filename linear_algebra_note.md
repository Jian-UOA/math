# 2. 矩阵及其运算

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
  (i) 反身性 $A\sim B $
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
		x_1-x_2-x_3=2\\
		2x_1-x_2-3x_3=1\\
		3x_1+2x_2-5x_3
		\end{cases}
		$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg3MzMwMTg3MSwtOTQ2NzI0NDM5LDIwMD
gwNjk2OTEsNzc0NzE4NDQ3LDExMjI1NDgzNzYsMTUwNTIwNDE2
OSwtODIwNzQyNDg3LC0xMDU5NTgzNzksLTEyMjM4NDM1MTQsMj
EwNjk2ODc5NywyMDg2NTg2MTc4LDEzMjQ0OTQ0NzMsLTE2NjEw
NDUwNiwxOTExMTI0NzcsOTQxNDg5OTY0LC0xMjYwODUyMDAyLC
03Njc2NDc0ODEsLTExNTE5MzQyNDgsLTc2NzMwMDYxNSwxNDgy
NjU2MjgyXX0=
-->