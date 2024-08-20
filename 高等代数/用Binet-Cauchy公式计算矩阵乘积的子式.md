计算$A_{s\times n}B_{n\times s}\begin{pmatrix}i_{1},\dots,i_{r}\\j_{1},\dots,j_{r}\end{pmatrix}$，其中$r\le s$。

- 若$r>n$，则$s>n$，$rank(AB)\le rank(A)\le n<r$，则它的$r$阶子式必为$0$，上式为$0$。
- 否则$r\le n$。
设$M$为$AB\begin{pmatrix}i_{1},\dots,i_{r}\\j_{1},\dots,j_{r}\end{pmatrix}$对应的矩阵，$M(i;j)=AB(i_{i};j_{j})=\sum_{k=1}^n{a_{i_{i}k}b_{{kj_{j}}}}$，$M$可以视为$(a_{i_{i}k})_{r\times n}$与$(b_{kj_{j}})_{n\times r}$的乘积（它们是从$A,B$中提取的子矩阵），故用Binet-Cauchy公式展开得
$$
AB\begin{pmatrix}i_{1},\dots,i_{r}\\j_{1},\dots,j_{r}\end{pmatrix}=\sum_{1\leq k_{1}<k_{2}<\dots<k_{k}\le n}A\begin{pmatrix}
i_{1},\dots,i_{r}\\k_{1},\dots,k_{r}
\end{pmatrix}B\begin{pmatrix}
k_{1},\dots,k_{r}\\j_{1},\dots,j_{r}
\end{pmatrix}
$$