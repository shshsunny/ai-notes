- @Jordan块$J_{l}(k)=\begin{pmatrix}k&1&0&\dots&0\\0&k&1&\dots&0\\\dots\\0&0&0&\dots&k\end{pmatrix}$（$l$阶矩阵）
- ~==$\mathcal{A=kI+B}$==（$\mathcal{B}$为幂零指数为$l$的幂零变换），是域$F$上$l$维线性空间$V$上的线性变换，则存在$\alpha\ne 0$，$\mathcal{B^{l-1}}\alpha,\mathcal{B}\alpha,\dots,\mathcal{B}\alpha,\alpha$为$V$一基，且$\mathcal{A}$在该基下的矩阵为$J_{l}(k)$。
  >$J_{l}(k)$的最小多项式即$\mathcal{A}$的最小多项式$(\lambda-k)^l$（由前）
- 推论：$l$阶矩阵$A\in F^{l\times l}$与$J_{l}(k)$相似$\iff$$A$的最小多项式为$(\lambda-k)^l$
  > $\Rightarrow$：$A\sim J_l(k)$$\Rightarrow$$A,J_{l}(k)$的最小多项式相同，由已知得。
> 	$\Leftarrow$：任取$V$一基，设$\mathcal{A}$在该基下矩阵为$A$，则$\mathcal{A}$最小多项式为$(\lambda-k)^l$，由前得$\mathcal{A=kI+B}$，故存在另一基使$\mathcal{A}$在该基下矩阵为$J_{l}(k)$，从而$A\sim J_{l}(k)$。
> 	**$\mathcal{A}$统领了一整个相似类，相似类中的矩阵共享相同的相似不变量。**