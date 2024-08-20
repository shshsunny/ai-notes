# *图论Problem Sets

# PS15 图论导引

## PS15AP6

* a)易证
* b)容易看出反证法比较适合，因为原命题的否定是全称命题，效力强：假设$G$的任何子图都满足$\delta (H)\le \frac{a}{2}$，那么$G$首先有$\delta (G)\le \frac{a}{2}$，从而取一点$x$度数不超过$\frac{a}{2}$，从而$\bar d(G-x)=a_2\ge a$，又有$\delta(G-x)\le \frac{a}{2}\le \frac{a_2}{2}$，从而取$y$，如此下到最后必然存在$\delta (G_k)\le \frac{a}{2}\le \frac{a_k}{2}$，$a_{k-1}>0$但$a_k=0$（最差情况下$k=n-1$，即删到只剩一个点时必有$a_k=0$），矛盾！故假设不成立
* b)也可使用**归纳法**，而且更简单！

## PS15BP3

$G,H$同构，则$\exists f:V_1\cup E_1 \to V_2\cup E_2, V_1\to V_2, E_1\to E_2$是双射，$\gamma_1(e)=\{u,v\}\Leftrightarrow \gamma_2(f(e))=\{f(u),f(v)\}$，即$u-v \Leftrightarrow f(u)-f(v)$。因为$(u-v)_G\Leftrightarrow \neg(u-v)_{\bar G}, (f(u)-f(v))_H\Leftrightarrow \neg(f(u)-f(v))_{\bar H}$，故$(u-v)_{\bar G}\Leftrightarrow (f(u)-f(v))_{\bar H}$，得证。

## PS15BP4

* 同构的必要条件->边数相等
* 补图的性质->$G\cup \bar G=K_n$->边数$E$为$\frac{n(n-1)}{2}$应当为偶数->得证

## PS15BP7

* 正则图->正则图的顶点度性质：由

  $$
  \sum _{i=1}^nd(v_i)=2e
  $$

  推知

  $$
  kn=2e
  $$

  根据之前题的结论：不包含$K_3$的图必须有$e\le \frac{v^2}{4}$，从而$\frac{kn}{2}\le\frac{n^2}{4}$，得$n\ge 2k$。再发现$n=2k$时为避免包含$K_3$，该图一定与$K_{k,k}$同构。
