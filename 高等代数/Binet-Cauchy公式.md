**Binet-Cauchy公式是行列式乘法定理的推广**。
# 表述
$A_{{s\times n}},B_{n\times s}$，则
1. $s>n$时$|AB|=0$
2. $s\le n$时
$$
|AB|=\sum_{1\le i_{1}<\dots<i_{s}\le n}A\begin{pmatrix}
1,2,\dots,s\\i_{1},i_{2},\dots,i_{s}
\end{pmatrix}
B\begin{pmatrix}
i_{1},i_{2},\dots,i_{s}\\1,2,\dots,s
\end{pmatrix}
$$
# 证明
情况1：$s>n$，则由矩阵乘积的秩的公式，$rank(AB)\le rank(B)\le n<s$，从而$AB$非满秩，$|AB|=0$

情况2：$s\le n$，$s=n$时同行列式乘法定理；$s<n$时类似于行列式乘法定理的证明：


$$
\begin{vmatrix}
O&AB\\-I_{n}&B
\end{vmatrix}=\begin{vmatrix}
A & O\\-I_{n} & B
\end{vmatrix}
$$
将右边的行列式按$A$的$s$行展开：
$$
=\sum_{1\le i_{1}<\dots<i_{s}\le n}A\begin{pmatrix}
1,2,\dots,s\\i_{1},i_{2},\dots,i_{s}
\end{pmatrix}(-1)^{1+\dots+s+i_{1}+\dots+i_{s}}|-\epsilon_{i_{1}'},\dots,-\epsilon_{i'_{n-s}},B|
$$
右边的行列式按左边$n-s$列展开，只有取第$i_{1}',\dots,i_{n-s}'$行时$|-\epsilon_{i_{1}'},\dots,-\epsilon_{i_{n-s}'}|$的子式不为零（它的子式中只有主子式不为零），于是
$$
|-\epsilon_{i_{1}'},\dots,-\epsilon_{i'_{n-s}},B|=(-1)^{n-s}(-1)^{1+2+\dots+n-s+i_{1}'+\dots+i_{n}'}B\begin{pmatrix}
i_{1},i_{2},\dots,i_{s}\\1,2,\dots,s
\end{pmatrix}
$$
代入前面一式，$(-1)$的指数为
$$
\begin{aligned}
(1+\dots+s)+(1+\dots+n-s)+(n-s)+(i_{1}+\dots+i_{s}+i_{1'}+\dots+i_{n-s}')=\\
\frac{s(s+1)}{2}+\frac{(n-s)(n-s+1)}{2}+(n-s)+\frac{n(n+1)}{2}=\\
s^2+n^2-ns+2n-s
\end{aligned}

$$
另一方面：
$$
\begin{vmatrix}
O&AB\\-I_{n}&B
\end{vmatrix}=|AB|(-1)^{(n+1+n+2+\dots+n+s)+(1+2+\dots+s)}(-1)^n
$$
其$(-1)$的指数为
$$
s^2+ns+s+n
$$
综合两边$(-1)$的指数：$s^2+n^2-ns+2n-s-(s^2+ns+s+n)=n(n-1)-2ns-2s$为偶数，故原式得证。