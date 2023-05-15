### 5.1 微分法

**(Differentiable) $f:\R^m\to\R^n$ differentiable at $a\iff\exists $linear mapping $A:\R^m\to\R^n\ s.t.f(a+h)=f(a)+Ah+\omicron(||h||)$**

Proposition:

$(f\pm g)'=f'\pm g'$, etc.

Chain Rule. 

Inverse Function: $f:\R\to\R$ differentiable bijection, thus $f^{-1}$ is well-defined. If $f^{-1}(x)$ is differentiable at the point $x$.(This is important! Previous conditions cannot guarentee the existence of the derivation: $f(x)=x^3$) 

We have $(f^{-1}(x))'=\dfrac{1}{f'(f^{-1}(x))}$



**(Local Max/Min) $f\:(a,b)\to\R$, call $f$ reaches local maximum/minimum at point $x\in(a,b)$, if exists $B_r(x)\ s.t.\ \forall y\in B_r(x)\cap (a,b), f(y)\leq f(x)(\geq)$**

Similarly we have the definition of global maximum/minimum.



Prop.(Fermat's Lemma) $f:(a,b)\to\R$ differentiable and $x$ is a local maximum point, then $f'(x)=0$.



**(Rolle mean value theorem) $f:[a,b]\to\R$ continuous, differentiable on $(a,b)$ and $f(a)=f(b)$, then exists $\xi\in(a,b),f'(\xi)=0$.**

Similarly we get a wider version.

**(MVT) $f,g:[a,b]\to\R$ continuous, differentiable on $(a,b)$, $\exists \xi\in(a,b)\ s.t. \dfrac{f(b)-f(a)}{g(b)-g(a)}=\dfrac{f'(\xi)}{g'(\xi)}(g(a)\neq g(b))$**

(Take $g(x)=x$ we get Lagarange MVT)



Corollary: $f:\R\to\R$ differentiable, $f'\equiv0\iff f$ constant.



Prop. **(L'Hopital) $f,g:(a,b)\to\R$ differential and $\lim_{x\to a} \dfrac{f'(x)}{g'(x)}=A$**

**If: 1. $\lim_{x\to a} f(x)=\lim_{x\to a}g(x)=0$ Or 2. $\lim_{x\to a}g(x)=\infty$**

**Then $\lim_{x\to a}\dfrac{f(x)}{g(x)}=A$.**



**(Taylor expansion) $f:(a,b)\to\R$ is n-th differentiable, $f(x)=\sum_{k=0}^n \dfrac{f^{(k)}(x_0)}{k!}(x-x_0)^k+\dfrac{1}{(n+1)!}f^{(n+1)}(\xi)(x-x_0)^{n+1},\ (\xi\in(x,x_0))$**

Proof: We construct the function $g(x)=\sum_{k=0}^n \dfrac{f^{(k)}(x_0)}{k!}(x-x_0)^k+M(x-x_0)^{n+1}$, and let $g(x)=f(x),g(x_0)=f(x_0),thus\ \exists \xi\ s.t. g'(\xi)=f'(\xi)$

Use induction we get the desired result.



### 6.3 PDE

1. 热方程

$f:\R_t\times \R^3\to \R$

满足$\part_t f-\triangle f=0$，($\triangle f=\sum\part_{x_ix_i}^2f=\nabla(\nabla f)$)

假定：$f$代表温度；热流量$\vec{J}=-\kappa\nabla f$ (Fourier's law)；能量守恒$\part_t(\int_U fdt)=-\int_{\part U}\vec{J}\cdot \vec{n}$（区域能量损失等于通过边界的热流量）

而由Stokes' 定理$\int_{\part U}F\cdot \vec{n}=\int_U \nabla f$

于是$\int_U \big[\part_t f-\nabla\cdot (\kappa\nabla f)\big]=0\implies\part f=\kappa\triangle f$

2. 调和方程

即考虑热方程的稳态，此时$\triangle f=0$

(Poisson 方程：外加热源但是仍然进入稳态：$\triangle f=Const.$)

3. 波方程

$\part_{tt}u-\triangle u=0$

现在只考虑弦的震动，$\part_{tt}u$表示加速度，

### 8.2 ODE; Picard-Lindelof-Cauchy-Lipschitz Theorem

**（Picard-Lindelof）$D\subseteq \R\times \R^n, f:D\to \R^n$关于$t$连续，关于$x$Lipschitz在$[t_0-a,t_0+a]\times B_r(x_0)$上成立。那么存在$a'\geq0$，使得方程$x'(t)=f(t,x),x(t_0)=x_0$存在唯一的$[t_0-a',t_0+a']$上的$C^1$解。**

证：

记$X=\{f\in C(I,\R^n),I\in t_0(to\ be\ fixed),f(t_0)=x_0\}$，并且配备上确范数诱导的度量。它是$C(I)$的闭子集，于是自然完备。

考虑$X$上算子$T:X\to X:y(t)\mapsto z(t)$

${\displaystyle z(t)=y(t_0)+\int _{t_{0}}^{t}f(s,y(s))\,ds}$，那么$T(x)=x\iff Desired\ Solution.$

只需验证$T$满足压缩映射：$\displaystyle \sup||T(y)-T(z)||=\sup||\int_{t_0}^t f(s,y(s))-f(s,z(s))\,ds||\\\leq\sup\int_{t_0}^t L|y(s)-z(s)|\,ds\leq La'\sup||y(s)-z(s)||$

取$a'$充分小即可满足压缩映射，并且满足$y,z$不超过$[t_0-a,t_0+a]\times B_r(x_0)$。



### 8.3 反函数定理

反函数定理：$F:U\to \R^n$，Open Set $U\subseteq \R^n$。$F\in C^1(U)$，$DF(x_0)$ 可逆（其中$x_0\in U$）

那么存在$V\ni x_0,W\ni f(x_0)$。使得$F|_V:V\to W$是双射，并且反函数$F^{-1}:W\to V$也是$C^1$的。



单位扰动定理：$X$是Banach空间，$\Phi:X\to X$，记$\Psi(x)=\Phi(x)-x$。

如果在邻域$\overline{B_r(x_0)}$上有：$||\Psi(x_1)-\Psi(x_2)||\leq\gamma||x_1-x_2||$，$(0\leq\gamma<1)$

那么对于$y\in \overline{B_{(1-\gamma)r}(\Phi(x_0))}$，$y$在$\overline{B_r(x_0)}$中有唯一的原像。

证：

 固定$y$，希望找到$x\ s.t. \Phi(x)=y\iff x+\Psi(x)=y\iff x=y-\Psi(x)$

因此考虑映射$T:t\mapsto y-\Psi(t): B_r(x_0)\to B_r(x_0)$

（值域为$B_r(x_0)$因为：$||y-\Psi(t)-x_0||\leq||y-\Phi(x_0)||+||\Phi(x_0)-\Psi(t)-x_0||\leq(1-\gamma)r+||\Psi(x_0)-\Psi(t)||\\\leq (1-\gamma)r+\gamma r=r$)

$||T(x_1)-T(x_2)||=||\Psi(x_1)-\Psi(x_2)||\leq\gamma||x_1-x_2||$

于是由Banach不动点定理，结论自明。



回到反函数定理：

由于$F(x+x_0)-F(x_0)=DF(x_0)x+\omicron(||x||)$，$(DF(x_0))^{-1}(F(x+x_0)-F(x_0))=x+\omicron(||x||)$

因此（为了运用单位扰动定理），取$\Phi(x)=(DF(x_0))^{-1}(F(x+x_0)-F(x))=(DF(x_0))^{-1}(F(x+x_0)-F(x_0)-DF(x_0)x+DF(x_0)x)\\=x+(DF(x_0))^{-1}(F(x+x_0)-F(x_0)-DF(x_0)x)\\=x+\Psi(x)$

Check Conditions.

$||\Psi(x_1)-\Psi(x_2)||=||(DF(x_0)^{-1})(F(x+x_1)-F(x+x_2)-DF(x_0)(x_1-x_2))||\\\leq||DF(x_0)^{-1}||_{matrix\ norm}||\int_{0}^{1}\big[DF(x_2+t(x_2-x_1)\cdot(x_2-x_1)-DF(x_0)\cdot (x_2-x_1)\big]dt||$

可以寻找充分小的$r$，使得$||DF(x_2+t(x_2-x_1))-DF(x_0)||$较小，从而满足单位扰动定理条件）



那么对于每个$y\in B_{(1-\gamma )r}(x_0)$，存在唯一的$x\in B_r(x_0)$， $\Phi(x)=y$。

即$(DF(x_0))^{-1}(F(x+x_0)-F(x))=y\implies F(x_0+x)=F(x_0)+DF(x_0)y$

即对于集合$\{F(x_0)+DF(x_0)y|y\in B_{(1-\gamma)r}(x_0)\}$中的元素都能找到原像。



记反函数为$G$，那么：

$||G(y_1)-G(y_2)||=||x_1-x_2||\leq ||(x_1+\Psi(x_1))-(x_2+\Psi(x_2))||+||\Psi(x_1)-\Psi(x_2)||\\\leq ||y_1-y_2||+\gamma\cdot||x_1-x_2||$

于是$||x_1-x_2||\leq \dfrac{1}{1-\gamma}||y_1-y_2||$，从而说明了连续性。

### 10.0 Preliminaries

Prop. $1. f*g=g*f; 2. f*g\ continuous\ (as\ long\ as\ f,g\ integrable)$

Prop2.Pf.

若$g$连续，$(f*g)(x+\Delta x)-(f*g)(x)\\=\displaystyle{\int_{-\pi}^{\pi}f(y)[g(x+\Delta x-y)-g(x-y)]\text{d}y}\to0\ as\ \Delta x\to 0$

（这个证明不够强，但是指出卷积函数只要一个具有比较好的性质：连续、可微、光滑etc.，都能够保证卷积后的结果继承了这一性质）

Lem. 给定一个可积函数$g$，它当然有界：$|g|\leq B$，则存在一族连续函数$g_k$，$\sup |g_k|\leq B, \displaystyle\int_{-\pi}^\pi|g_k-g|\text{d}x\to 0$（很容易联想到简单逼近）

Lem.Pf. 

取$g_k(x)=\displaystyle{\sup_{[m/k,(m+1)/k]\ni x}f(x)}$，$g_k$满足条件，尽管不连续。

对$g_k$的间断点做插值，插值带来的误差是可以控制的：每段在端点处用$1/k^2$的长度做插值，带来的误差被$k\times 1/k^2\times B$控制。





取定$g_k$，$|(f*g)(x+\Delta x)-(f*g)(x)|\\\leq |(f*g)(x+\Delta x)-(f*g_k)(x+\Delta x)|\\+|(f*g_k)(x+\Delta x)-(f*g_k)(x)|+\\|(f*g_k)(x)-(f*g)(x)|$

第三项$|(f*g_k)(x)-(f*g)(x)|\leq\dfrac{1}{2\pi}\displaystyle{\int_{-\pi}^\pi|f(y)||g_k(x-y)-g(x-y)|}$从而被$k$控制。第一项同理，第二项被$\Delta x$控制，于是得证。

（或：$f*g_k\rightrightarrows f*g$，即说明连续）



### 10.1 Fouriér Series

Definiton: $f:\R\to \R$, $2\pi-$periodic. $[-\pi,\pi]$上Riemman可积。

$\hat{f}(n):=\dfrac{1}{2\pi}\displaystyle{\int_{-\pi}^{\pi} f(x)e^{-inx}\text{d}x}$，$f(x)\sim \displaystyle {\sum_{n\in\Z} \hat{f}(n)e^{inx}}$

（$\hat{f}(n)$的选取动机是$f$在基$e^{inx}$上的投影，其中配备的内积为卷积）

这里：右侧求和定义为对称求和主值$\displaystyle{\lim_{k\to \infty} \sum_{n=-k}^{n=k} \hat{f}(n)e^{-inx}}$.

Examples. Given $f(x)=\begin{cases}1&[0,\pi)\\-1&[-\pi,0)\end{cases}$, $\hat{f}(n)=\dfrac{1}{2\pi}\displaystyle{\int_{-\pi}^\pi f(x)(\cos nx-i\sin nx)\text{d}x=-\dfrac{i}{\pi}\int_{0 }^\pi }\sin nx\text{d}x\\=\dfrac{[(-1)^n-1]i}{n\pi}(n\neq0)$

$n=0, \hat{f}(n)=0$

于是$\displaystyle{\sum_{n\in \Z}\dfrac{i[(-1)^n-1]}{n\pi}}e^{inx}$在$x=0$时恒为0，自然不逐点收敛到函数$f$。



接下来对这一级数的收敛性进行讨论：

正如对称主值那样，记$S_Nf(x)=\displaystyle {\sum _{n\leq|N|}\hat{f}(n)e^{inx}}$，在何时$S_nf(x)\to f(x)$. 是否能更进一步做到$\rightrightarrows$? (Fejér Thm.)



$S_Nf(x)=\displaystyle{\sum_{n\leq|N|} \dfrac{1}{2\pi}\int_{-\pi}^\pi f(y)e^{in(x-y)}\text{d}y=\dfrac{1}{2\pi}\int_{-\pi}^{\pi}\sum_{n\leq |N|}e^{-in(x-y)}f(y)\text{d}y}\\\displaystyle{=\begin{cases}(2N+1)\int_{-\pi}^{\pi} f(y)\text{d}y&x=y\\\int_{-\pi}^{\pi}\frac{\sin (N+1/2)(x-y)}{\sin 1/2(x-y)}f(y)\text{d}y&x\neq y\end{cases}}$

记$D_N(x)=\dfrac{\sin[(N+1/2)x]}{\sin1/2 x}$，其中$2k\pi$处延拓成$2N+1$，称为Dirichlet核。

那么$S_Nf= D_N*f$

有性质**（时域卷积=频域乘积）$\widehat{f*g}(n)=\hat{f}(n)\hat{g}(n)$**

证：

$\widehat{f*g}(n)=\dfrac{1}{2\pi}\displaystyle{\int_{-\pi}^\pi(f*g)(x)e^{-inx}\text{d}x}=\dfrac{1}{2\pi}\displaystyle{\int_{-\pi}^\pi}\int_{-\pi}^{\pi}f(x-y)g(y)\text{d}y\ e^{-inx}\text{d}x\\\displaystyle{\xlongequal[]{Fubini}\int_{-\pi}^{\pi}g(y)e^{-iny}\cdot \big[\dfrac{1}{2\pi}\int_{-\pi}^\pi f(x-y)e^{-in(x-y)}\text{d}x\big]\text{d}y}=\hat{f}(n)\hat{g}(n)$



### 10.2 Good Kernels - Féjer Theorem.

Given a series of kernel function ($2\pi-$periodic) satisfies the following:

a. $\dfrac{1}{2\pi}\int_{-\pi}^{\pi}K_n(x)\text{d}x=1\\$; b. $\exists M,\forall n, \int_{-\pi}^{\pi}|K_n(x)|\text{d}x\leq M\ (L^1\\$一致有界$)$; c. $\int_{\delta<|x|<\pi}
|K_n(x)|\text{d}x\to 0 (n\to+\infty)\\$



Prop.(Good Kernel Approximation) Given good kernels $\{K_n\}$, $f$ integrable, then if $f$ continuous at $x_0$, $(K_n*f)(x_0)\to f(x_0)$. Moreover if $f\in C[-\pi,\pi]$, then $(K_n*f)(x)\rightrightarrows f(x)$

Proof:

$|K_n*f(x_0)-f(x_0)|=\mid \dfrac{1}{2\pi}\int_{-\pi}^{\pi} K_n(y)\big[f(x_0-y)-f(x_0)\big]\text{d}y\mid\\\leq \dfrac{1}{2\pi}\int_{\delta\leq|y|\leq\pi} |K_n(y)||f(x_0-y)-f(x_0)|\text{d}y+\dfrac{1}{2\pi}\int_{|y|\le \delta } |K_n(y)||f(x_0-y)-f(x_0)|\text{d}y$ 

第一项$\le \dfrac{1}{2\pi} \sup|f|\int_{\delta\le|y|\le\pi} |K_n(y)|\text{d}y\longrightarrow 0\\$

第二项：选取适当的$\delta$, $|f(x_0-y)-f(x_0)|<\varepsilon$对$|y|\le \delta$成立。

从而第二项$\le \varepsilon M/(2\pi)\longrightarrow 0$

Thus $(K_n* f)(x_0)\to f(x_0)$.

Moreover if $f\in C[-\pi,\pi]$, $f$ is uniformly continuous, thus $\delta$ can be choosen uniformly, and we get the result $K_n*f\rightrightarrows f$



Unfortunately Dirichlet Kernel is not a good kernel. $\int_{-\pi}^{\pi} |K_n(x)|\text{d}x\ge c\log n\\$. 于是我们不能利用Good Kernel逼近给出Fouriér级数的点态收敛性。



然而我们发现Cesaro和具有Good Kernel性质！即取$F_N*f=\dfrac{1}N\sum_{n=0}^{N-1} (D_n*f)\\$，$F_N=\dfrac{1}{N}\sum D_n$（称为Féjer核）

计算知$F_N=\dfrac{1-\cos Nx}{N(1-\cos x)}$满足Good Kernel。于是这就说明Fouriér级数的Cesaro和具有点态收敛性质。



### 10.3 $L^2$逼近

定义$<f,g>=\dfrac{1}{2\pi}\int_{-\pi}^{\pi} f(t)\overline{g}(t)\text{d}t\\$，其中$f,g: 2\pi$-periodic,$[-\pi,\pi]\to \C$，$||f||_{L^2}:=<f,f>^{1/2}$.

下面看到Fourier级数在$L^2$下逼近效果最好。



**（$L^2$最佳逼近）**取$g=\sum_{|n|\leq N}c_ne^{inx}$, $c_n$ 任意选取。

$f$可积则$||f-S_Nf||_{L^2}\le ||f-g||_{L^2}$

证：$||f-g||_{L^2}^2=||f-S_N f||^2+||S_Nf-g||^2+2Re<f-S_Nf,S_Nf-g>$

$<f-S_Nf,S_Nf-g>=0$，于是得证。



做为推论得到：

**（$L^2$收敛）** $f$可积，$||f-S_Nf||_{L^2}\stackrel{N\to +\infty}\longrightarrow 0$

**（Parseval恒等式）$||f||_{L^2}=\sum |\hat{f}(n)|^2$**

证：$(L^2):$  

如果$f\in C[-\pi,\pi]$，$||f-S_Nf||_{L^2}\leq ||f- F_N*f||_{L^2}\to 0(N\to +\infty)$

对于一般的$f$，可以找到一族$f_k$，在$L^1$范数下逼近$f$，并且$|f_k|\leq \sup |f|$.(10.0)

由于最佳逼近$||f-S_Nf||_{L^2}\leq ||f-S_Nf_k||_{L^2}$

则$||f-S_Nf||_{L^2}\leq ||f-f_k||_{L^2}+||f_k-S_Nf_k||_{L^2}$

第一项$\leq \sup |f-f_k|\cdot ||f-f_k||_{L^1}$

第二项由前述趋于0.

**Parseval**显然。



**（Riemann-Lebesgue定理）$\hat{f}(N)\to 0$**

### 10.4 点态收敛







### 12.1 Applications of Fourier series

#### **Weyl Equidistribution Thm.**

Given an irrational number $\gamma$, $\xi_n= <n\gamma>:=n\gamma-[n\gamma]$. It is reasonable to guess that $\xi_n$ distribute equally over the interval $[0,1)$.

This guess is somehow true, and the result is usually called Weyl Equidistribution Theorem.

Rmk. $(\xi_n=<n\gamma>)$ is dense in $[0,1)$ (Using Kronecker's trick)

$\mathscr{Def.}$  Equidistribution. （渐进均匀分布）

A series $\xi_n\in [0,1)$ is called equi-distributed iff $\forall a.b\in [0,1)$, $\displaystyle \lim_{N\to +\infty}\dfrac{\# \{\xi_n|1\leq n\leq N:\xi_n\in [a,b)\}}{N}=b-a$

The main result is the previously mentioned theorem.

**Theorem. (Weyl Equidistribution Theorem) $\xi_n$ is equi-distributed $\iff\gamma $ is irrational. **



To prove the theorem, we claim the following criterion.

**Weyl Equidistribution Criterion. An arbitrary series $\xi_n$ is equi-distributed $\iff\displaystyle\forall k\in \N\backslash\{0\},\ \lim_{N\to +\infty} \dfrac{1}{N}\sum_{n=1}^N e^{2\pi i k \xi_n}=0$ **

Assuming the criterion, we apply the criterion to the series $<n\gamma>$, here $\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}e^{2\pi ikn\gamma}=\dfrac{1}{N} \sum_{n=1}^N (e^{2\pi ik\gamma})^n=\dfrac{1}{N} \cdot\dfrac{e^{2\pi ik\gamma}-e^{2\pi i k\gamma(N+1)}}{1-e^{2\pi ik\gamma}}=0$, hence the result.



Proof of the Criterion.

$\Longleftarrow$. 

Equi-distribution  $\iff \displaystyle\frac{1}{N}\sum_{n=1}^N\mathbb{1}_{[a,b)}(\xi_n)\stackrel{N\to +\infty}\longrightarrow b-a=\int_{0}^{1}\mathbb{1}_{[a,b)}(t)\text{d}t$

Then it suffices to prove the following statement $\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$ holds when $f$ is a step function.



**Step 1. Continuous cases.**

Suppose the Weyl's Criteria, $f\in C([0,1])$, and periodic $1$. Then the following holds.

$\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$

Recalling that $F_N*f\rightrightarrows f$, here $F_N$ is the Fejer Kernel.



Then $\displaystyle|\frac{1}{N}\sum_{n=1}^Nf(\xi_n) -\int_0^1 f(t)\text{d}t|\leq \frac{1}{N}\sum_{n=1}^N |f-(F_M*f)|(\xi_n)+|\frac{1}{N}\sum_{n=1}^N(F_M*f)(\xi_n)-\int_0^{1} (F_M*f)(t)\text{d}t|\\+\int_{0}^{1}|F_M*f-f|(t)\text{d}{t}$

2nd term holds since $F_M*f$ has the form $\sum a_me^{2\pi i k t}$, through direct check one can verify it can be controlled by increasing $N$, after choosing a satsfying $n$, 1st and 3rd term can be controlled by adjusting $M$.

Thus we prove the continuous cases.



**Step 2. Step Function cases.**

For an arbitrary step function (or more specificly $\mathbb{1}_{[a,b]}$), we have the following continuous function approximation.

<img src="https://i.postimg.cc/pLBL0TRw/image-20230508141842943.png" alt="image-20230508141842943" style="zoom:70%;" />

Obv. that $f_\varepsilon^+\geq f\geq f_\varepsilon^-$

By taking limits (over $\varepsilon$), we obtain that for an arbitrary step function $f$.

 $\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$

($\limsup \sum f\leq \limsup \sum f^+=\int f^+=\int f+\varepsilon$, similarly we get the other side)

Since linear relation, indicator function cases holds implies the entire step function cases.

Thus we get the $\Longleftarrow$ direction.



**Remark. A useless step 3. Riemann Integrable Function cases.**

$\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$ also holds for $f$ Riemann integrable over $[0,1]$

By approaching $f$ using step function from both sides, we get desired results.



$\implies. $

$\displaystyle\frac{1}{N}\sum_{n=1}^N\mathbb{1}_{[a,b)}(\xi_n)\stackrel{N\to +\infty}\longrightarrow b-a=\int_{0}^{1}\mathbb{1}_{[a,b)}(t)\text{d}t$  holds. Thus $\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$ holds for Step functions, thus Riemann Integrable functions, thus Continuous Function. Namely $\displaystyle \lim_{N\to +\infty}\dfrac{1}{N}\displaystyle \sum_{n=1}^{N}f(\xi_n)=\int_0^1 f(t)\text{d}t$ holds for $e^{2k\pi ix}\iff Continuous\iff Step \iff Riemann\ Integrable$ 

Thus we get the result.





#### **Heat Equation on a circle**

Question: $\begin{cases}\part_t u=\part_{xx} u\\u(0,x)=f(x)\end{cases}$, $u\ C^1$ over $t, C^2$ over $x$, periodic on $x$.
Solution: **Step 1. Separation of variable: Suppose $u(t,x)=A(t)B(x)$, with $A,B\neq 0$**
Thus $\dfrac{A'(t)}{A(t)}=\dfrac{B''(x)}{B(x)}$

Adjusting $x,t$, we have $\dfrac{A'(t)}{A(t)}=\dfrac{B''(x)}{B(x)}=\lambda$.

Thus $B(x)=e^{2\pi i n x}$, since periodic. Then we get $\lambda =-4\pi^2 n^2$, $A(t)=e^{-4\pi^2n^2t}$.

**Step 2. Linear operations.**

We get a series of solutions $u(t,x)\sim \sum _n c_n e^{-4\pi^2n^2t}e^{2\pi i nx}$

To obtain the boundary condition, it is easy to verify that $c_n=\hat{f}(n)$.





Following Contents are Real Analysis Parts.

### 13.1 Measure

**Definition. ($\sigma-$algebra)  $\mathcal{F}\subseteq P(E)$ is a $\sigma-$algebra over the set $E$ if it satisfies the following 3 conditions.**

**1. $E\in \mathcal{F}$**

**2. $A\in\mathcal{F}\implies A^c\in\mathcal{F}$**

**3. $A_{i\in I}\in\mathcal F\implies \cup_{i=1}^{+\infty}A_i\in \mathcal F$, $I$ a countable index set.**



**($\sigma-Closure$) Given a $C\subseteq P(E)$, $\sigma(C)=\cap_{\mathcal F\supseteq C} \mathcal{F}$**

**Given arbitarily many $\sigma-$algebras $\mathcal F_n$, $\cap \mathcal F_n$ is also a $\sigma-$ algebra.**



**(Borel Sets) For an Topological Space $X$, its open sets are $O$, $B(E)=\sigma(O)$**



**Definition. (Measure) Given $(E,\mathcal{F})$, a function $\mu:\mathcal{F}\to [0,+\infty]$ is called a measure if it satisfies:**

**1. $\mu(\varnothing)=0$, 2. $\mu(\sqcup_{n=1}^{+\infty} A_n)=\sum_{n=1}^{+\infty}\mu(A_n)$ ($\sigma$-addictivity)**



Examples. 1. $E=\mathbb{Z},\mathcal{F}=P(A),\mu(A)=|A|$; 

$2. E=\mathbb{R},\mathcal{F}=Borel,\mu([a,b])=b-a$

Existence: Caratheodory Construction.



**Prop. $\mu$ a measure over $(E,\mathcal{F})$**

**1. $A\subseteq B\implies \mu(A)\leq \mu(B)$**

**2. $\mu(A)+\mu(B)=\mu(A\cup B)+\mu(A\cap B)$**

**3. $A_n\subseteq A_{n+1}$, $\mu(\cup_{n=1}^{+\infty} A_n)=\lim_{n\to+\infty}\mu(A_n)$**

**4. $B_n\supseteq B_{n+1}$, $\mu(B_1)<+\infty$, $\mu(\cap_{n=1}^{+\infty}B_n)=\lim_{n\to+\infty}\mu(B_n)$**

**5. $\mu(\cup_{n=1}^{+\infty} A_n)=\sum_{n=1}^{+\infty}\mu(A_n)$**



### 13.2 Integration

$f(x)=\sum_{i=1}^n\alpha_i\mathbb{1}_{A_i}$, $A_i\in\mathcal{F}$, disjoint.

Define $\int_E f\text{d}\mu=\sum_{i=1}^n \alpha_i\mu(A_i)\\$



**Definition (Measurable Function) $f:(E_1,\mathcal{F_1})\to (E_2,\mathcal{F_2})$ is measurable if $\forall A\in\mathcal{F_2},f^{-1}(A)\in\mathcal{F_1}$**

If $(E_2,\mathcal{F_2})=(\mathbb{R},Borel)$, we usally call $f$ a $\mathcal{F_1}$ measurable funtion.

**Definition (Integration)**

**1. $f\geq 0, \int_E f\text{d}\mu =\sup _{h\leq f,h\ simple} \int_E h\text{d}\mu$**

**2. $\int_E f\text{d}\mu=\int_E f^+\text{d}\mu -\int_E f^-\text{d}\mu$**