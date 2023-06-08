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

### 10. Fouriér Analysis

#### 10.0 Preliminaries

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



#### 10.1 Fouriér Series

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



#### 10.2 Good Kernels - Féjer Theorem.

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



#### 10.3 $L^2$逼近

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

#### 10.4 点态收敛







#### 12.1 Applications of Fourier series

##### **Weyl Equidistribution Thm.**

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





##### **Heat Equation on a circle**

Question: $\begin{cases}\part_t u=\part_{xx} u\\u(0,x)=f(x)\end{cases}$, $u\ C^1$ over $t, C^2$ over $x$, periodic on $x$.
Solution: **Step 1. Separation of variable: Suppose $u(t,x)=A(t)B(x)$, with $A,B\neq 0$**
Thus $\dfrac{A'(t)}{A(t)}=\dfrac{B''(x)}{B(x)}$

Adjusting $x,t$, we have $\dfrac{A'(t)}{A(t)}=\dfrac{B''(x)}{B(x)}=\lambda$.

Thus $B(x)=e^{2\pi i n x}$, since periodic. Then we get $\lambda =-4\pi^2 n^2$, $A(t)=e^{-4\pi^2n^2t}$.

**Step 2. Linear operations.**

We get a series of solutions $u(t,x)\sim \sum _n c_n e^{-4\pi^2n^2t}e^{2\pi i nx}$

To obtain the boundary condition, it is easy to verify that $c_n=\hat{f}(n)$.



### 13. Measure Theory

Following Contents are Real Analysis Parts.

#### 13.1 Measure

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

Caratheodory Construction.

${\mu:\mathcal{S}\to [0,\infty]\atop{pre\ measure} }\longrightarrow{\mu^*:2^X\to [0,\infty]\atop outer\ measure}\stackrel{Caratheodory\ Condition}\longrightarrow {\bar{\mu}:\mathcal{M}=\mu^*-measurable\to [0,\infty]\atop{measure}}$

Take the semi-ring $\mathcal{S}=bounded\ intervals,\mu\ map\ interval\ to \ its\ length$.

Through this construction (and using some conclusions of Caratheodory-Hahn Thm.) we get a measure $\bar{\mu}$ (Actually a unique expension on $\mathcal M$) on $\mathcal{M}$, where $\mathcal{M}$ is a $\sigma$ algebra containing intervals. Thus $\mathcal{M}$ contains Borel sets.



**Prop. $\mu$ a measure over $(E,\mathcal{F})$**

**1. $A\subseteq B\implies \mu(A)\leq \mu(B)$**

**2. $\mu(A)+\mu(B)=\mu(A\cup B)+\mu(A\cap B)$**

**3. $A_n\subseteq A_{n+1}$, $\mu(\cup_{n=1}^{+\infty} A_n)=\lim_{n\to+\infty}\mu(A_n)$**

**4. $B_n\supseteq B_{n+1}$, $\mu(B_1)<+\infty$, $\mu(\cap_{n=1}^{+\infty}B_n)=\lim_{n\to+\infty}\mu(B_n)$**

**5. $\mu(\cup_{n=1}^{+\infty} A_n)\leq\sum_{n=1}^{+\infty}\mu(A_n)$**



#### 13.2 Integration

$f(x)=\sum_{i=1}^n\alpha_i\mathbb{1}_{A_i}$, $A_i\in\mathcal{F}$, disjoint.

Define $\int_E f\text{d}\mu=\sum_{i=1}^n \alpha_i\mu(A_i)\\$



**Definition (Measurable Function) $f:(E_1,\mathcal{F_1})\to (E_2,\mathcal{F_2})$ is measurable if $\forall A\in\mathcal{F_2},f^{-1}(A)\in\mathcal{F_1}$**

If $(E_2,\mathcal{F_2})=(\mathbb{R},Borel)$, we usally call $f$ a $\mathcal{F_1}$ measurable funtion.

**Definition (Integration)**

**1. $f\geq 0, \int_E f\text{d}\mu =\sup _{h\leq f,h\ simple} \int_E h\text{d}\mu$**

**2. $\int_E f\text{d}\mu=\int_E f^+\text{d}\mu -\int_E f^-\text{d}\mu$**

Remark. Say $f$ integrable if $\displaystyle{\int |f|\text{d}\mu<+\infty}$, then $\displaystyle{\int_E f^+,\int_E f^{-}<+\infty}$ 



**Rimeann Integrable On Closed Interval $\implies$ Measurable and $\int_L=\int_R$**

Proof: $\int_L=\int_R$ if we use step functions as the simple functions. Using Upper sums and Lower sums immediately leads to the result.

For the measurable part, 







### 14. Probability

We use Kolomogrov axiom to define the probability.

A probability space consists of $(\Omega,\mathscr{F},\mathbb{P})$, where $\Omega$ is the hole space, $\mathscr{F}$ is a $\sigma-$algebra, and $\mathbb{P}$ a measure over it such that $\mathbb{P}(\Omega)=1$

**(Independence of events) $\mathbb{P}(E_1\cap E_2)=\mathbb{P}(E_1)\mathbb{P}(E_2)$, then $E_1,E_2$ independent.**

**More generally say a countable family of events $\{E_i\}_{i=1}^{+\infty}$ independent if $\mathbb{P}(\cap E_i)=\prod \mathbb{P}(E_i)$ holds for any sub family $E_i(i\in I)$**

**(Condition Probability) For $A\in\mathscr{F}$, $\mathbb{P}(A)>0$, then for $E\in\mathscr{F}$, define the condition probability $\mathbb{P}(E|A)=\dfrac{\mathbb{P}(E\cap A)}{\mathbb{P}(A)}$**

Through standard checking process this indeed defines a probability on $\mathscr{F}$



Similar to sets, we have Product space by conducting cartesian product.



**(Random Variables) A random variable is a measurable function $X:\Omega\to \mathbb{P}$**

**(Discrete Random Variable) $\mathbb{P}(X=X_i)=P_i$, $X$ ranges on discrete countable points.**

**(Independence of Random Variables) Given a family of random variables $(X_i)_{i\in I}$, they are independent if $\forall \alpha_1,\cdots,\alpha_n\in I$, $\forall F_{\alpha_1},\cdots,F_{\alpha_n}\in B(\mathbb{R})$, we have $\mathbb{P}(\cap \{X_{\alpha_i}\in F_{\alpha_i}\})=\prod\mathbb{P}(\{X_{\alpha_i}\in F_{\alpha_i}\})$**

**(Expectation) $E(X)=\int X\text{d}\mathbb{P}$**

**(Variance) $Var(X)=E((X-E(X))^2)=E(X^2)-E(X)^2$**

**Prop. If $X_1,\cdots,X_n$ are independent random variables, then $Var(\sum X_i)=\sum Var(X_i)$**

Proof: $LHS=E[(\sum x_i)^2]-(\sum E[x_i])^2=\sum(E[x_i^2]-(E[x_i])^2)+\sum (E[x_ix_j]-E[x_i]E[x_j])=RHS$

Examples for discrete random variables.

Bernoulli $X\in\{0,1\}$, $P(X=1)=p;P(X=0)=1-p$

Binomial

 $\mathbb{P}(X=k)={n\choose k} p^k(1-p)^{n-k}$

$\sum^n Bernoulli(p) \sim Binomial(n,p)$, $E(Binomial (n,p))=nE(Bernoulli(p))=np$



Geometry 

$\mathbb{P}(X=k)=(1-p)^{k-1}p$, $E(X)=1/p$

Poisson

$\mathbb{P}(X=k)=e^{-\lambda}\cdot \dfrac{\lambda^k}{k!}$, $E(X)=Var(X)=\lambda$



**Markov Inequality $\mathbb{P}(|x|>\lambda)\leq \dfrac{1}{\lambda}E(|x|)$**

This is exactly same to the Chebyshev inequality in the real analysis case.

**Weak LLN**

$X_i$ i.i.d.$\to X$, $\sum X_n/N\to(under\ probability) E[X]$

Proof: $\mathbb{P}[|S_n-E[X]|\geq\varepsilon]=\mathbb{P}[(S_n-E[S_n])^2\geq \varepsilon^2]\\\leq E[(S_n-E[S_n])^2]/(\varepsilon^2)=(iid)=\sum Var[X_n]/n^2\leq C/n $





### **15. Random Graph & Perrolation**

Graph are defined to be 1-skeleton of a CW complex.

#### 15.1 Erdos-Renyi Graph

Model $G=G(n,P_n)$, with $n$ vertices. Sample i.i.d. Bernoulli random variables of parameter $P_n$. Connect $i,j$ if $X_{i,j}=1$, otherwise 0.

**Connectivity**

$P_n=1$, then $\mathbb{P}(G=K_n)=1$.

**Connectivity Theorem. **

**1. For $P_n\geq \dfrac{(1+\varepsilon)\log n}{n},\varepsilon>0$, then $\mathbb{P}(G(n,p)\ is\ connected)\xrightarrow{n\to+\infty}1$**

**2. For $P_n\leq \dfrac{(1-\varepsilon)\log n}{n},\varepsilon>0$, then $\mathbb{P}(G(n,p)\ is\ connected)\xrightarrow{n\to+\infty}0$**

We call case 1 "supercritical"(超临界), case 2 "subcritical"(次临界)

In this case $\dfrac{\log n}{n}$ here is the critical situation.

Proof:



**Lemma 1. (Isolated point) **

**For $P_n\geq \dfrac{(1+\varepsilon)\log n}{n}$, $\mathbb{P}(G(n,p)\ has\ isolated\ point)\xrightarrow{n\to+\infty}0$**

Lemma 1 Proof:

$\text{\color{red} First\ Moment Method\ (Mean/Expectation): 一阶矩方法}$

$\mathbb{P}(\#isolated\ vertices\ of\ G(n,p)\geq1)\leq \mathbb{E}(\#isolated\ vertices)$

To compute the last term, we observe that $\#isolated\ vertices=\sum_{i=1}^{n}\mathbb{1}_{i\ is\ isolated}$

Thus $\mathbb{E}(\#isolated\ vertices)=\sum_{i=1}^n\mathbb{E}(\mathbb{1}_{i\ is\ isolated})=\sum_{i=1}^{n}\mathbb{P}(i\ is\ isolated)$



Now For any single point $i$, $\mathbb{P}(i\ is\ isolated)=\mathbb{P}(X_{i,t}=0\quad\forall t\neq i)=(1-P_n)^{n-1}$

Hence:

 $\mathbb{E}(\#isolated\ vertices)=n(1-P_n)^{n-1}\leq n(1-\dfrac{(1+\varepsilon)\log n}{n})^{n-1}\\\leq n(e^{-\dfrac{(1+\varepsilon)\log n}{n}})^{n-1}\leq n^{1-(1+\varepsilon)(n-1)/n}\xrightarrow{n\to+\infty}0 $

We get a conclusion $\color{red} n(1-P_n)^n\simeq n^{-\varepsilon}$.



**Lemma 2. (Isolated point)**

**For $P_n\leq \dfrac{(1+\varepsilon)\log n}{n}$, $\mathbb{P}(G(n,p)\ has\ isolated\ point)\xrightarrow{n\to+\infty}1$**

Lemma 2 Proof:

$\text{\color{red} Second\ Moment Method\ (Variance): 二阶矩方法}$

Denote $X=\# \{isolated\ vertices\}$, then $\mathbb{P}(X\geq 1)\geq \dfrac{\mathbb E^2(X)}{\mathbb E(X^2)}$(Cauchy-Schwartz)

Since $\mathbb E(X^2)=\mathbb E\left((\sum\mathbb1_{i\ is\ isolated})^2\right)=\sum\mathbb{E}(\mathbb 1_{i\ is\ iolated})+\sum\mathbb{E}(\mathbb 1_{i,j\ both\ are\ isolated})$

The first sum is $n(1-P_n)^{n-1}$, second sum is $n(n-1)(1-P_n)^{2n-3}$(through elementary combinatorics)

Thus $\dfrac{\mathbb E^2(X)}{\mathbb E(X^2)}=[n^2(1-P_n)^{2n-2}]/[n(n-1)(1-P_n)^{2n-3}+n(1-P_n)^{n-1}]\to 0$



**Main Proof of Part 1.**

$\mathbb{P}(G\ isn't\ connected)=\mathbb{P}(\exists cut\ V_1\sqcup V_2)\\\leq\mathbb{P}\cup_{k=1}^{[n/2]}(\exists cut,|V_1|=k,\ no\ edges\ between\ V_1,V-V_1)\\\leq\sum_{k=1}^{[n/2]}{n\choose k}(1-P_n)^{k(n-k)}$

Since $P_n$ is monotonic w.r.t. $\varepsilon$, it is possible to let $\varepsilon$ be arbitarily small.

Condition: $n>>1$.

Since ${n\choose k}(1-P_n)^{k(n-k)}={\color{red}\dfrac{n!}{(n-k)!}(1-P_n)^{kn}}{\color{blue}\dfrac{1}{k!}(1-P_n)^{-k^2}}\simeq{\color{red}n^{^k}\cdot(1-P_n)^{nk}}{\color{blue}(k/e)^{-k}e^{P_nk^2}}\\\simeq{\color{red}n^{-\varepsilon k}}{\color{blue}(k/e)^{-k}e^{(1+\varepsilon)k^2\log n/n}}\\\leq \exp(-\varepsilon k\log n-k\log (k/e) + (1+\varepsilon)k^2\log n/n)$

$=\exp(-k[\varepsilon \log n+\log(k/e)-(1+\varepsilon)(k/n)\log n])$

If $k\leq \dfrac{\varepsilon}{2}n$, $\varepsilon \log n-(1+\varepsilon )(k/n)\log n\geq \varepsilon/3 \cdot \log n$

If $n/2\geq k\geq \varepsilon n/2$, $\varepsilon \log n+\log(k/e)-(1+\varepsilon )(k/n)\log n\geq\log((\varepsilon n)/(2e))-(1+\varepsilon)/2\cdot\log n\\=(1-\varepsilon)/2\cdot\log n+\log [\varepsilon /(2e)]>(\log n)/3$

Thus $\mathbb P(G\ isn't\ connected)\leq \sum e^{-k[\varepsilon \log n+\log(k/e)-(1+\varepsilon)(k/n)\log n]}\\\leq \sum_{k=1}^{+\infty} n^{-\varepsilon k/3}+\sum_{k=[\varepsilon n/2]}^{+\infty} n^{-k/3}=n^{-\varepsilon/3}/(1-n^{-\varepsilon/3})+n^{-\varepsilon n/6}/(1-n^{-1/3})\xrightarrow{n\to+\infty}0 $



**Proof of Part 2.**

Directlty deduced from Lemma 2.



#### 15.2 Bernoulli Percolation

**Definition. (Bernoulli Percolation: 伯努利渗流模型) Given a graph $G=(V,E)$, associate every $e\in E$ with an independent Bernoulli Random variable $\omega (e)$ with the parameter $p$**.  (This is called the distribution of a percolation configuration)

**Given the percolation configuration distribution, we define a new random graph $G=(V,\mathcal{E})$, where for every $e$, $e\in \mathcal{E}\iff \omega(e)=1$, call the edge open, otherwise closed.**

Erdos-Renyi graph, particularly, is the case when taking $G=K_n$

Remarks: Here the probability space is $(\{0,1\}^E,\mathcal{F}=Events\ generated\ by\ Finite\ Edges\ Events, \mathbb P_p)$



Now we consider the Bernoulli Percolation on $\mathbb{Z}^d$, i.e. take $G=(\mathbb{Z}^d,E(\mathbb{Z^d}))$,  where $E(\mathbb{Z}^d)=\{(x,y)|dist(x,y)=1\}$.

$\theta(p)=\mathbb P(0\longleftrightarrow \infty)=\mathbb P(\{\exists an\ infinite\ component\ containing\ 0\})$, where $(x\longleftrightarrow y)$ denote $x,y$ can be connected by a open path. 

Here $(0\longleftrightarrow \infty)=\cap_{n\geq 1} (0\longleftrightarrow \part\Lambda_n)$, where $\Lambda_n$ is the square $[-n,n]^d$, hence a finite edge event, hence $(0\longleftrightarrow\infty)$ indeed exists in the event domain.

Call the component containg 0 $C(0)$ the cluster containing 0.



We would like to consider the critical probability in which $\theta(p)$ changes from 0 to non-0 values.

**Prop 1.(Lower case) $\forall d\in \mathbb{N}_+, \exists \tilde p(d)$, such that $p\leq \tilde{p}(d)\implies \theta(p)=0$**

Proof: Since $(0\longleftrightarrow\infty)=\cap_{n\geq 1} (0\longleftrightarrow\part\Lambda_n)$, it is also a descending chain, thus $\mathbb P(0\longleftrightarrow\infty)=\lim_{n\to \infty} (0\longleftrightarrow \part\Lambda_n )$

For each $n$,

 $\mathbb{P}(0\longleftrightarrow \part \Lambda_n)\leq \sum_{k\geq n}\mathbb P(\exists length\ k-open\ path:0\longleftrightarrow\part\Lambda_n)\\\leq\sum_{k\geq n}p^k\cdot (\#length\ k-open\ path:0\longleftrightarrow\part\Lambda_n)\\\leq\sum_{k\geq n} p^k\cdot(2d)^k=(2dp)^n\cdot\dfrac{1}{1-2dp}$

Take $p<1/(2d)$, we get the result. Thus $\widetilde p(d)=1/(2d)-\varepsilon$ is a suitable choice. 



**Prop 2.(Upper case) $\forall d\geq 2$, $\exists \tilde{\tilde {p}}(d)\in(0,1), p\geq \tilde{\tilde p}(d)\implies \theta(p)>0$**

Proof: Similarly we have $\mathbb{P}(0\longleftrightarrow\infty)=1-\mathbb{P}(0\not\longleftrightarrow\infty)=1-\lim_{n\to\infty}\mathbb{P}(0\not\longleftrightarrow \part \Lambda_n)$

It suffices to prove that for $p>\tilde{\tilde p}, \mathbb{P}(0\not\longleftrightarrow \part \Lambda_n)\leq c\in (0,1)$

$\mathbb{P}(0\not\longleftrightarrow\part\Lambda_n)=\mathbb{P}(\exists a\ open\ dual\ hyperplane\ separating\ 0\ and\  \part\Lambda_n)\\\leq\sum_{k\geq 2d}\mathbb{P}(\exists a\ size-k\ hyperplane\ separating\ 0\ and\ \part\Lambda_n)\\\leq\sum_{k\geq 2d}c(d)^k(1-p)^k=\dfrac{[c(d)(1-p)]^{2d}}{1-[c(d)(1-p)]}$

Take a rather large $p$, (near to 1), we can let $\mathbb{P}(0\not\longleftrightarrow\part \Lambda_n)$ be controlled by a rather small value.



**Prop 3.(Monotonicity) $\theta(p)$ is increasing.**

Proof: Define a event $A$ is increasing, if $\omega\in A$, $\omega'\geq \omega$, then $\omega'\in A$. Where $\omega,\omega'\in\{0,1\}^{E}$, $\omega'\geq\omega$ if for all components we have the same greater relation.

We claim if $A$ is increasing, $p<p'$, $\mathbb{P}_p(A)\leq \mathbb{P}_p(A')$

Proof: 

$\text{\color{red}Coupling Method:耦合方法}$.

Given 2 probability space $(\Omega_1,\mathcal F_1,\mathbb P_1),(\Omega_2,\mathcal F_2,\mathbb P_2)$

Construct a new probability space $(\Omega_1\times\Omega_2,\mathcal{F_1}\otimes\mathcal{F_2},\tilde{\mathbb{P}})$, such that

 $\tilde{\mathbb{P}}(A_1\times \Omega_2)=\mathbb{P}_1(A_1)$

$\tilde{\mathbb{P}}(\Omega_1\times A_2)=\mathbb P_2(A_2)$.

Note that product space is a coupling space.

$\text{\color{red}Stochastic domination}$

Given 2 real value random variable $X_1\in(\Omega_1,\mathcal F_1,\mathbb P_1),X_2\in(\Omega_2,\mathcal F_2,\mathbb P_2)$

We construct a coupling space such that $\tilde{\mathbb P}(X_1\leq X_2)=1$.



For example, consider 2 coin toss with front face probability $p_1,p_2$, resp.

We sample a uniform distributed random variables $U\stackrel{distribution}\sim Unif([0,1])$

Let $X_1=\mathbb{1}_{U\leq P_1}$, $X_2=\mathbb{1}_{U\leq P_2}$, then $X_1\leq X_2$.



Back to the proposition:

Take i.i.d. random variables which distributed uniformly on $(0,1)$. $\{U_e,e\in E(\mathbb{Z}^d)\}$

Take $\omega_p(e)=\mathbb 1_{\{U_e\leq p\}}$, 

Then clearly $\omega_p\sim \mathbb{P}_p$, $\omega_p\leq \omega_{p'}$ if $p<p'$. Thus $\mathbb{P}_p[A]=\tilde{\mathbb{P}}[\omega_p\in A]\leq \tilde{\mathbb{P}}[\omega_p'\in A]=\mathbb{P}_{p'}[A]$



**Theorem. (Phase Transition) $d\geq 2$, $\exists p_c(d)\in (0,1)$, such that $p<p_c\implies \theta(p)=0;\\p>p_c\implies \theta(p)=1$**. 

More particularly, when $d=2,or \ d\geq 11$, $\theta(p_c)=0$; when $3\leq d\leq10$, determine $\theta(p_c)$ value is a Fields-Medal-Level Work.



**Lem. $p\to\theta(p)$ is right-continuous.**



**Thm. Kolmogrov 0-1 law**



### 16. Markov Chain



**Definition. (Markov Chain) Let $(\Omega,\mathcal F,\mathbb P)$ be a probability space, with a series of random variables $(X_n)_{n\in\mathbb N}$. **

**We call the series a Markov Chain if $\mathbb{P}(X_{n+1}\in E_{n+1}|\cap_{1\leq i\leq n}(X_{i}\in E_i))=\mathbb{P}(X_{n+1}\in E_{n+1}|X_n\in E_n)$ holds for all $E_i\in Borel(\mathbb{R})$. (i.e. only the present state matters)**



E.g. If $\mathbb{P}(X_{n+1}\in E_{n+1}|\cap_{1\leq i\leq n}(X_i\in E_i))=\mathbb{P}(X_{n+1}\in E_{n+1}|(X_n\in E_n)\cap(X_{n-1}\in E_{n-1}))$

Then $Y_n=(X_n,X_{n-1})$ $(\Omega^2\to \R^2)$ is a $\mathbb{R}^2-$valued random variable. 

Hence $\mathbb{P}(Y_{n+1}\in E_{n+1}\times E_n|Y_i)=\mathbb{P}(Y_{n+1}\in E_{n+1}\times E_n|Y_n\in E_{n}\times E_{n-1})$, and indeed the sigma closure of $Borel(\mathbb{R})^2$ is $Borel(\mathbb{R}^2)$,  thus a markov chain.



**Definition. (Homogeneous Markov Chain; Transition Matrix) A countable state markov series is times homogeneous if $\mathbb{P}(X_{n+1}=x_{n+1}|X_n=x_n)=Q_{x_n,x_{n+1}}$ **

Here the matrix $Q$ is a fixed matrix. 

Remark. $\forall x,\sum_y Q_{x,y}=1 $



**Prop. $(X_n)$ times homogeneous Markov Chain with transition matrix $Q$, $X_0\stackrel{d}\sim Q$, then $Q,\mu$ determine the distribution of the markov chain $X_n$**

Proof: By induction and using the transition matrix.

$\mathbb{P}(X_0=x_0,X_1=x_1,\cdots,X_n=x_n)$

$=\mathbb{P}(X_n=x_n|X_0=x_0\cap \cdots\cap X_{n-1}=x_{n-1})\cdot \mathbb{P}(X_0=x_0,\cdots,X_{n-1}=x_{n-1})\\=Q_{x_{n-1},x_n}\cdot\mathbb{P}(X_0=x_0,\cdots,X_{n-1}=x_{n-1})\\=\cdots=\mu_{x_0}\cdot Q_{x_0,x_1}\cdots Q_{x_{n-1},x_n}$

**Corollary. $\mathbb{P}(X_n=x_n)=(\mu Q^n)_{x_n}$**



### Simple Random Walk on Graph

**Definition. (SRW on Graph) $G=(V,E), \deg V<+\infty$, a SRW on $G$ is a markov chain s.t. $\mathbb{P}(X_{n+1}=\nu|X_n=\mu)=\dfrac{1}{\deg (\mu)}\mathbb{1}_{\mu\sim\nu}$**

Note $\mathbb P_x$ denotes the markov chain starting from point $x$.

Prop. $f_n(x)=\mathbb{E}_x[f(X_n)]$, then $f_n(x)=(Q^nf)(x)$

