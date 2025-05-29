# 2. 矩阵及其运算
## 2.5 矩阵分块法
### 2.5.5 副对角线`分块对角矩阵`的行列式与逆矩阵
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
③用某方程的`n倍`加到另一方程上去

增广矩阵：
B=(A, b)
`矩阵`的三种初等行变换：
①交换两行
②用非零数k乘以某一行
③某一行的n倍加到另一行上去
