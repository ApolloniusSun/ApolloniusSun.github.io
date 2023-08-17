# 几何长跑：从流形到代数

## 0. 概述

本文的写作动机原本只是想对PMA第10章进行一点总结，但是在学习过程中接触到了更为一般的结果，而PMA对外微分式以及相关内容讨论的过于局限，因此这份笔记可以看做是一次“几何长跑”。

首先从传统的微分几何视角出发，以流形为切入点论述了流形的Stokes定理（当然也提供了多重线性代数的预备知识）；然后进入同调的领域，着重介绍了奇异同调以及de Rham上同调，并且最终给出了沟通两者的桥梁：de Rham定理。

值得注意的是介绍同调时由于篇幅限制，并未像部分代数拓扑教材那样直接从同调论公理开始，也没有很详细地去验证同调是否满足所有的同调论公理，仅仅对需要使用的部分性质进行了记录。因此如若需要详细了解这一部分的细节，可以阅读参考书目。

## 1. 预备知识

### 1.1 微分流形

首先是流形相关的预备知识。

**设$M$是Hausdorff的$C_2$空间，且对任一点$x\in M$，都有一个包含它的开邻域同胚于$\mathbb{R}^m$的开集，则称$M$为一个m维流形。**

那么对于每个同胚映射$\varphi_U:U\rightarrow \varphi_U(U)\stackrel{open}\subseteq\mathbb{R}^m$，那么称$U$中点在$\varphi_U$的像为其局部坐标，$(U,\varphi_U)$称为一个坐标卡。

自然想问不同坐标卡之间的交上如何过渡：若$U\cap V\neq \phi$，那么$\varphi_V^{-1}\circ \varphi_U$和$\varphi_U^{-1}\circ\varphi_V$是$U\cap V$在两个坐标卡下坐标之间的过渡映射（它们是互逆的同胚映射）

如果给予过渡映射以微分性质，这就能够在流形上定出微分结构。

**m维流形$M$上若有一组坐标卡$\mathscr{A}$满足：**

**a. 坐标卡的定义域是$M$的一个开覆盖**

**b. 任意两个坐标卡之间的过渡映射是$C^r$的**

**c. $\mathscr{A}$是极大的，即若有一个坐标卡与$\mathscr{A}$中每个坐标卡之间都满足条件b.，则它自身也必定在$\mathscr{A}$中**

**则称$\mathscr{A}$是一个$C^r$-微分结构，$M$是一个$C^r$-微分流形，$\mathscr{A}$中坐标卡称为容许的坐标卡，某点附近的局部坐标指包含该点的容许坐标卡给出的坐标系。**

若将上述定义中$C^r$换为$C^{\infty}$，则称为光滑流形，简称流形。



**（局部紧致性）拓扑空间$X$在点$x$处局部紧致，若存在$x$的开邻域$U$和紧集$C$，使得$x\in U\subseteq C$，若$X$在每点局部紧致，则称$X$局部紧致。**

拓扑流形的一个重要性质是局部紧致。这是由于$\mathbb{R}^m$的开集是局部紧的，而局部紧致性在同胚映射下保持。

对于Hausdorff空间，局部紧致性有一个重要的等价表述。

**（Hausdorff空间的局部紧致性）Hausdorff空间$X$在点$x$处局部紧致$\iff\forall U\ni x \ open,\ \exists V\ni x \ open,\ \bar{V}\subseteq U, \bar{V} \ compact$**

证：只需证明$\implies$

 存在$x$的开邻域$W$和紧集$C$，$x\in W\subseteq C$，那么$C$闭。对于任意$x$的开邻域$U$，$C\backslash U=C\cap(X\backslash U)$是闭的，从而紧。那么存在两个开集$V_1,V_2$将$x,C\backslash U$分离。（将紧集中每个点取出来，用$T_2$公理得到许多组分离开邻域，利用紧性选出有限组，将紧集中点的开邻域取并，单点的开邻域取交就满足要求）

从而$V_1\subseteq X\backslash V_2$进而$\bar{V_1}\subseteq X\backslash V_2$。再取$V=V_1\cap W$，$V$是$x$的开邻域，则$\bar{V}\subseteq\bar{V_1}\cap\bar{W}\subseteq(X\backslash V_2)\cap C=C\backslash V_2\subseteq U$，而上一等式还能说明$\bar{V}\subseteq C$，从而是$C$的相对闭集，从而$\bar{V}$紧，得证。



### 1.2 切空间，余切空间

切空间和余切空间的核心是对一个双线性映射取不同的视角，这个双线性映射在更为熟悉的情况下正是方向导数，下面来详细阐述。

我们研究的对象是m维光滑流形上一定点$p$的邻域上的$C^{\infty}$实值函数，记这个集合为$C_p^{\infty}$。$C_p^{\infty}$中两不同元素的定义域可能不同，但它们的交仍然是包含$p$的开集，因此空间$C_p^{\infty}$就有了加法和乘法结构。

同时，设$C$设$M$上过点$p$的一段光滑参数曲线，即有$\delta>0$，光滑映射$\gamma: (-\delta,\delta)\longrightarrow M$，并且$\gamma(0)=p$，所有这样的参数曲线的集合称为$\Gamma_p$。

那么就有映射$<\  ,\ >:\Gamma_p\times C_p^{\infty}\rightarrow\mathbb{R}$，$\begin{aligned}<\gamma,f>=\frac{d(f\circ\gamma)}{dt}|_{t=0}\end{aligned}$

那么余切向量是指映射$<-,f>:\Gamma_p\rightarrow \mathbb{R}$ ，当然我们知道不同的$f$可能诱导出相同的映射，经过计算知：设$(U,\varphi_U)$为包含$p$的容许坐标卡，那么$f,g$所诱导出的余切向量相同（即对每条曲线，其方向导数相同），当且仅当$f$和$g$属于同一个函数芽，或$f\circ \varphi_U^{-1}, \ g\circ \varphi_U{^-1}$在点$\varphi_U(p)$处的一阶Taylor展开相同。

而这是一个等价关系，$C_p^{\infty}$商掉这一等价关系后得到的空间正是全体余切向量构成的空间（并且事实上是线性空间），称为余切空间$T_p^*$。

容易验证$\dim T_p^{*}=m$，$<,u^i>$（$u_i$为容许坐标卡下的第i个局部坐标）是$T_p^*$的一组基。



对偶地：切向量是指映射$<\gamma,->:C_p^{\infty}\rightarrow\mathbb{R}$

同样地我们知道不同$\gamma$可能诱导出相同的映射，同样地计算表明：不同曲线诱导出相同的切向量当且仅当两条曲线在点$p$处关于局部坐标的切向量相同，同样地商掉这一等价关系后得到了全体切向量构成的一个线性空间，称为切空间。

于是考虑$<,>:\Gamma_p/ \sim_T \times C_p^{\infty}/\sim_{T^{*}}\rightarrow\mathbb{R}$，其中两个等价关系就是上述讨论中出现的等价关系，这是一个双线性映射$<,>:T_p\times T_p^*\rightarrow\mathbb{R}$，于是$T_p,\ T_p^*$对偶。

### 1.3 张量积，张量

多重线性代数中张量积等概念引入方式多样，这里采用线性代数方式引入。



下文所有线性空间都是在域$F$上的。

线性空间的张量积被定义为$V\otimes W = \text{Hom}(V^*,W^*;F)$

对于$V,W$中的元素$v,w$，这两个元素的张量积$v\otimes w$表示映射$(v^*(-),w^*(-))\rightarrow v^*(v)\cdot w^*(w)$

可以验证元素的张量积是双线性的，满足结合律，并且它们张成的线性空间正是$\text{Hom}(V^*,W^*;F)=V\otimes W$


同样地，由于每个多重线性函数都对应了线性空间张量积中的一个元素，因而结合律保证了两个多重线性函数之间的张量积是有意义的，举例来说：

$f\in\text{Hom}(V_1,...,V_s;F)$，于是它对应了$\begin{aligned}\bigotimes_{i=1}^sV_i^*\end{aligned}$中的某个元素。而这个张量积自身也是一个线性空间，于是对于另外一个$g\in\text{Hom}(W_1,...W_t;F)$，它也对应了$\begin{aligned}\bigotimes_{i=1}^tW_i^*\end{aligned}$的某个元素，那么称$f,g$的张量积是它们作为$\begin{aligned}\bigotimes_{i=1}^sV_i^*\end{aligned}$和$\begin{aligned}\bigotimes_{i=1}^tW_i^*\end{aligned}$的元素进行张量积后所对应的函数，而事实上这个张量积正是$f(v_1,...,v_s)g(w_1,...w_t)$。

线性空间的张量积还保持了对偶关系：$V^*\otimes W^*\cong(V\otimes W)^*$

张量积的基为其因子的基的张量积，于是$\dim(V\otimes W)=\dim V\cdot\dim W$



另外一个引入张量积的方法是泛性质：$M_1,M_2,...,M_n$是交换幺环$R$上的模，那么$M_1,\cdots M_n$的张量积指的是一个模$T$以及一个n重线性映射：$\mathbb{R}ho:M_1\times\cdots\times M_n\rightarrow T$，满足：对于任一$R$模$N$，以及$M_1\times\cdots\times M_n$到$N$的n重线性映射$f$，存在唯一的$R$模同态$\varphi$，使得$f$是$\varphi\circ\mathbb{R}ho=f$

（它与前文定义的等价性是显然的）

并且它指出了$\text{Hom}(V_1,\cdots,V_n;W)\cong\text{Hom}(V_1\otimes\cdots\otimes V_n;W)$



接下来引入张量的概念。

**$V$是域$F$上的n维线性空间：**

**称张量积：$V^r_s=\bigotimes^r V\bigotimes^sV^*$的元素为$(r,s)$型张量，其中$r$为反变阶数，$s$为协变阶数。**

特别地：$V_0^r$的元素称为$r$阶反变张量，$V_s^0$的元素称为$s$阶协变张量。约定$V^1_0=V,V^0_1=V^*,V^0_0=F$。

$\dim V^r_s=n^{r+s}$，因此$(r,s)$型张量可以看做定义在$\stackrel{r个}{V^*\times\cdots\times V^*}\times\stackrel{s个}{V\times\cdots\times V}$上的$F-$值$(r+s)$重线性映射。



那么全体$(r,s)$型张量有形式：$x=\begin{aligned}\sum_{i_1,\cdots i_r\atop j_1,\cdots,j_s} x^{i_1\cdots i_r}_{j_1\cdots j_s}(e_{i_1}\otimes\cdots\otimes e_{i_r})\otimes(e^{*k_1}\otimes\cdots\otimes e^{*k_s})\end{aligned}$

其中分量$x^{i_1\cdots i_r}_{j_1\cdots j_s}$是$x$作用在对应的对偶基上得到的值。

当$V$的基发生变化时，基底和对偶基底的过渡矩阵变化方向是相反的，这也是反变和协变名称的由来。



**张量的运算：**

**$V^r_s$本身作为一个$F-$线性空间，自然有加法和数乘。**

**张量的张量积就是它们作为多重线性映射的张量积，新分量就是原分量的积，从而符合分配律和结合律。**



记：$V^r=T^r(V)$，接下来讨论张量的对称性，以$r$阶反变张量为例。

设$S_r$为$\{1\cdots r\}$的置换群，那么其任意元素$\sigma$决定了$T^r(V)$的一个自同态：$\sigma x(v^{*1},\cdots, v^{*r})=x(v^{*\sigma(1)},\cdots,v^{*\sigma(r)})$

自然地：$\sigma(v_1\otimes\cdots\otimes v_r)=v_{\sigma^{-1}(1)}\otimes\cdots\otimes v_{\sigma^{-1}(r)}$

称$x\in T^r(V)$对称，若对所有置换：$\sigma x= x$；称它反对称，若对所有置换：$\sigma x=\text{sgn}\  \sigma\cdot x$

容易验证$x$对称（反对称）当且仅当其分量关于各个指标对称（反对称）

全体对称$r$阶反变张量的集合记为$P^r(V)$，全体反对称$r$阶反变张量的集合记为$\Lambda^r(V)$，

称$S_r(x)=\frac{1}{r!}\sum \sigma x$为对称化子，$A_r(x)=\frac{1}{r!}\sum \text{sgn}\ \sigma\cdot\sigma x$为反对称化子，不难验证$P^r(V)=S_r(T^r(V)), \Lambda^r(V)=A_r(T^r(V))$



以上讨论对于协变张量也成立，只不过所有记号由$V$修改为$V^*$

### 1.4 反对称张量：外矢量和外形式

反对称张量在接下来的讨论中有着重要地位。

首先从反对称$r$阶反变张量开始，它被称为外$r$次矢量，它们构成外$r$次矢量空间$\Lambda^r(V)$。

同样地研究这个空间里的运算：由于$\Lambda^r(V)$是线性空间，加法和数乘都得以保持。但是张量积则不一定了，两个外矢量的张量积并不一定仍然是一个外矢量。

自然的想法是将反对称化子作用在张量积上，这也就构成了称为外积的运算。

**（外积）$x\in\Lambda ^k(V),y\in\Lambda^l(V)$，则定义其外积：$x\wedge y=\begin{aligned}\frac{(k+l)!}{k!l!}A_{k+l}(x\otimes y)\end{aligned}$**

可以验证它满足分配律、结合律和反交换律（这里反交换律指$x\wedge y=(-1)^{kl}y\wedge x$），并且在$r\leq n$时，$\{e_{i_1}\wedge\cdots\wedge e_{i_r},1\leq i_1<\cdots<i_r\leq n\}$构成了$\Lambda^r(V)$的一组基，次数大于$n$的外矢量都是$0$（由反交换律，对于一次外矢量$x$，$x\wedge x=0$）

（基的证明）只需验证线性无关性。

对于$V^*$中任$r$个元素$v^{*1},\cdots v^{*r}$，有求值公式：

$(e_{i_1}\wedge\cdots\wedge e_{i_r})(v^{*1},\cdots v^{*r})=\sum\text{sgn}\ \sigma\cdot<e_{i_1},v^{*\sigma(1)}>\cdots<e_{i_r},v^{*\sigma(r)}>= \begin{array}  |<e_{i_1},v^{*1}>\ \cdots\ <e_{i_1},v^{*r}>\\<e_{i_2},v^{*1}>\ \cdots\ <e_{i_2},v^{*r}>\\\cdots\\<e_{i_r},v^{*1}>\ \cdots\ <e_{i_r},v^{*r}> \end{array}$

若它们线性相关，设某个值为$0$的线性组合的任意一项为$a^{i_1i_2\cdots i_r}e_{i_1}\wedge\cdots\wedge  e_{i_r}$，设$\{k_1,\cdots k_{n-r}\}$与$\{i_1,\cdots i_{r}\}$相补，于是在线性组合式两侧外积$e_{k_1}\wedge\cdots\wedge e_{k_{n-r}}$，得到：

$a^{i_1i_2\cdots i_r}e_{1}\wedge\cdots\wedge e_{n}=0$

但是由求值公式：$(e_{1}\wedge\cdots\wedge e_{n})(e^{*1},\cdots e^{*n})=1$，于是只有$a^{i_1i_2\cdots i_r}=0$，从而证明了线性无关性。



现在考虑所有$V$上的外矢量空间的直和，即：$\Lambda(V)=\Lambda^0(V)+\Lambda^1(V)+\cdots+\Lambda^n(V)$，那么$\Lambda(V)$中元素自然有加法和数乘，外积按照分配律那样进行定义，于是$\Lambda(V)$成为代数，称为外代数。



同样地，上述所有讨论都对外形式$\Lambda^r(V^*)$适用，另外它表示的是$V$上反对称的$F-$值$r$重线性映射。

需要注意：在对$r$次外矢量和$r$次外形式讨论配合时，有$<v_1\wedge\cdots\wedge v_r,v^{*1}\wedge\cdots\wedge v^{*r}>=\text{det} (<e_{i_\alpha},e^{*j_{\beta}}>)$

但是如果考虑一般的张量积所诱导出的配合，会发现二者之间差一数量因子，因此默认在讨论外代数相关时采用这里的配合，其余情况则采用一般的配合。

## 2. 张量丛

### 2.1 丛结构

<img src="/Users/wanglijun/Downloads/fiber-bundle.png" alt="fiber-bundle" style="zoom:25%;" />

丛结构能够很好地引入流形上的外微分式。

目前先讨论张量丛而非一般的矢量从。

丛结构的本质是对于流形上每一个点都赋予了一个线性空间，然后将这些线性空间（形象地视为一根根纤维）并起来得到丛空间，然后考虑这之上的拓扑。

对于$m$维光滑流形$M$，$p\in M$，记$T^r_s(p) = \bigotimes^r T_p \bigotimes^r T^*_p$，那么要考虑的丛空间即为$E=T^r_s=\begin{equation}\bigcup_{p\in M}T^r_s(p)\end{equation}$，我们希望它能够成为一个光滑流形。



思路是将流形$M$的若干局部积粘合起来。

对于流形$M$的一个局部坐标域$U$，局部坐标函数为$u^i$，$V$是$m$维实线性空间。

取映射：$\varphi_U: U\times V^r_s\rightarrow \bigcup_{p\in M}T^r_s(p)$，使得$\varphi_U(p,V^r_s)\subseteq T^r_s(p)$，并且对每个$p$，$V^r_s$到$T^r_s(p)$的对应方式就取为将$V$视作$T_p$（$e_i\rightarrow (\frac{\partial}{\partial u_i})_p$）所诱导的对应。

（这相当于丛空间在局部$\bigcup_{p\in U}T^r_s(p)$中的坐标）



现在取$M$的一组坐标覆盖$\{U_1,U_2,\cdots\}$，以及它们对应的$\{\varphi_{U_1},\varphi_{U_2},\cdots\}$，取丛空间$T^r_s$的拓扑基为$U_i\times V^r_s$在

$\varphi_{U_i}$下的像。（它是拓扑基是因为，若两者有交，取$U'\subseteq U_1\cap U_2$也为一坐标域，然后得到的像也是拓扑基的元素，并且满足要求）

这样丛空间成为了有可数基的Hausdorff空间，并且$\varphi_{U_i}$是同胚，这样就成为了流形。

下面考虑微分结构，这只需要指出一组相容的坐标覆盖。

对于一点$p\in U_1\cap U_2$，取$\varphi_{U_i,p}(y)=\varphi_{U_i}(p,y)$，这样就给出了一个$V^r_s\rightarrow T^r_s(p)$的映射，它们描述的是不同局部坐标到丛上的映射方式。

记$g_{12}(p)(y)=\varphi_{U_2,p}^{-1}\circ \varphi_{U_1,p}(y)$，则这是$V^r_s$上的自同态。

那么$\varphi_{U_1}(p,y_1)=\varphi_{U_2}(p,y_2)\iff y_2=y_1\cdot g_{12}(p)$（将$y$视为行向量，变换记为右乘）

因此对每个点$p$都有一个映射$g_{12}(p)$以及逆$g_{21}(p)$，于是有$g_{12}: U_1\cap U_2 \rightarrow \text{GL}(V^r_s)$

为了简单，这里讨论$r=s=1$的情况。

在$U_1\cap U_2$上，每个$T_p, T^{*}_p$的自然基底有着关系$\begin{aligned}{du}_1^i=\frac{\partial u_1^i}{\partial u_2^j}du_2^j,\frac{\partial}{\partial u_1^i}=\frac{\partial u_2^j}{u_1^i}\frac{\partial}{\partial u_2^j}\end{aligned}$

并且$\varphi_{U_i}(p,y)=\varphi_{U_i}(p,y^\alpha_\beta \cdot e_\alpha\otimes e^{*\beta})=y^\alpha_\beta(\frac{\partial}{\partial u_i^\alpha})_p\otimes(du_i^\beta)_p$

于是可知$g_{12}=J_{12}\otimes J_{21}$即两Jacobi矩阵的张量积，而Jacobi矩阵的每一项都是光滑的，从而$g_{12}$光滑。

那么回到$T^r_s$，有一组开覆盖$\{\varphi_{U_i}(U_i\times V^r_s)\}$。并且点$\varphi_{U_i}(p,y)$的坐标为$(u^i(p),y^{i_1i_2\cdots i_r}_{j_1j_2\cdots j_s})$

于是$\varphi_{U_1}(p,y_1)=\varphi_{U_2}(p,y_2)\iff y_2=y_1\cdot g_{12}(p)$保证了这个开覆盖是$C^{\infty}-$相容的，从而成为了一个光滑流形。



投影$\pi:T^r_s\rightarrow M$把$T^r_s(p)$中元素映为$p$，这当然是光滑满射。

**称$T^r_s$为流形$M$上的$(r,s)$型张量丛，$\pi$为丛投影，$T^r_s(p)$为丛在$p$点上的纤维。**

上述构造对外矢量和外形式丛依然成立，记为$\Lambda^r(M)$和$\Lambda^r(M^*)$



若有一个光滑映射$f:M\rightarrow T^r_s$，且$\pi\circ T^r_s =\text{id}_M$，即对流形上每一点指定纤维上一个点，就称$f$是丛的一个光滑截面，很自然地也称为$M$上的一个$(r.s)$型光滑张量场，退化到$r=1,s=0,$和$r=0,s=1$的情况时立刻变为切矢量场和余切矢量场。另外丛空间取为$\Lambda^r(M^*)$时则光滑截面称为流形$M$上光滑的$r$次外微分式。

### 2.2 外微分

正如之前对外矢量进行直和从而形成代数那样，这个过程也可以在外形式丛上进行：**取$\Lambda(M^*)=\bigcup_{p\in M} \Lambda(T_p^*)$，它的光滑截面称为流形$M$上光滑的$r$次外微分式。全体外微分式，即全体光滑截面的空间记为$A(M)$。**

同样$A(M)$中也有自然的外积：$(\omega_1\wedge\omega_2)(p)=\omega_1(p)\wedge\omega_2(p)$



外形式的重要性源于$A(M)$中有外微分运算。

**（外微分）$M$是m维光滑流形，那么存在唯一的映射$d:A(M)\rightarrow A(M)$，使得：**

**a. $d(A^r(M))\subseteq d(A^{r+1}(M))$**

**b. 任两外微分式：$d(\omega_1+\omega_2)=d\omega_1+d\omega_2$**

**c. $\omega_1\in A^r(M)$，则：$d(\omega_1\wedge\omega_2)=d\omega_1\wedge \omega_2+(-1)^r\omega_1\wedge d\omega_2$**

**d. $f\in A^0(M)$，即$f$是$M$上光滑实值函数，则$df$是$f$的微分。**

**e. $f\in A^0(M)$ ，则：$d(df)=0$** 

**称这个映射$d$为外微分。**

事实上：外微分的唯一性其实是同调中Eilenberg-Steenrod公理的推论：满足一系列（上）同调公理的（上）同调有且只有一个。

证：

首先证明：

若存在这样的映射$d$，且外微分式$\omega_1,\omega_2$在流形的某个开集$U$上相等，那么$d\omega_1, d\omega_2$在$U$上也相等，即$d$是局部的。

这相当于证明$\omega|_U=0\implies d\omega|_U=0$. 任取$U$中一点$p$，由Hausdorff空间的局部紧致性，存在包含$p$的开邻域$W$，使得闭包$\bar{W}$是紧的，那么存在一个光滑函数将$\bar{W}$和$U^c$分离（Urysohn引理，光滑版本）

关于光滑版本Urysohn引理的一个简单证明（详细讨论见3.1）：同胚映射保证了可以在$\mathbb{R}^m$上考虑。紧致性保证有限组同心开球的覆盖的存在。然而对于同心开球时命题是简单的（命题：在较小开球的闭包上取1，较大开球的补上取0），将这些光滑函数相乘即可。



设这个光滑函数为$h$，$h$在$\bar{W}$上取1，$U^c$上取0。于是$h\omega\in A(M)$，并且$h\omega\equiv 0$，则$dh\wedge \omega + hd\omega=0$，则在$W$上，$dh=0\implies hd\omega=0\implies d\omega|_W\equiv0 $，但$p$任意选取，于是得证。



然后考虑一个局部坐标域内的外微分算子$d$：

如果这样的算子存在，那么由b.只需考虑单项的外微分式$\omega=a \ du^1\wedge\cdots\wedge du^r$，利用c.~e.知：必有$d\omega = da\wedge du^1\wedge\cdots\wedge du^r$，对于多项外微分式，只要使得它保持加法，就完成了局部坐标域上外微分算子的定义。

a,b,d条件是显然的，只需验证c,e：

c: 只需考虑两个单项外微分式$\omega_1=a \ du^{i_1}\wedge\cdots\wedge du^{i_r}, \omega_2=b \ du^{j_1}\wedge\cdots\wedge du^{j_s}$，那么：

$d(a\wedge b)=d(ab \ du^{i_1}\wedge\cdots\wedge du^{i_r}\wedge  du^{j_1}\wedge\cdots\wedge du^{j_s})=\\(b\ da+a\ db)\wedge du^{i_1}\wedge\cdots\wedge du^{i_r}\wedge  du^{j_1}\wedge\cdots\wedge du^{j_s}=da \wedge b+(-1)^ra\wedge db$

e: $f$作为$M$上光滑函数，限制在$U$上则有$df = \frac{\partial f}{\partial u^i}du^i$

那么$d(df)=d(\frac{\partial f}{\partial u^i})\wedge du^i=\frac{\partial^2 f}{\partial u^i\partial u^j}du^j\wedge du^i = 0$

这就证明了局部坐标域上的存在和唯一性。



对于另一局部坐标域$W$，利用局部性就可以说证明$d$在$U\cap W$上以两种方式的定义是一致的，从而$d$在大范围的流形$M$上是存在且唯一的。



作为外微分的性质，立刻得到：

**（Poincare）$d(d\omega)=0$**

证：只需验证单项外微分式$\omega = a \ du^1\wedge\cdots\wedge du^r$

$d\omega = da \wedge du^1\wedge\cdots\wedge du^r$，$d(d\omega)=d(d(a))\wedge du^1\wedge\cdots\wedge du^r - da\wedge d(du^1\wedge\cdots\wedge du^r)$

而$d(du^1\wedge\cdots\wedge du^r)=d(du^1)\wedge(du^2\wedge\cdots\wedge du^r)+du^1\wedge d(du^2\wedge\cdots\wedge du^r)$，因此对$r$归纳即有$d(du^1\wedge\cdots\wedge du^r)=0$，从而$d(d\omega)=0$



## 3. 外微分式的积分

### 3.1 流形的拓扑性质

现在对流形的拓扑性质做一些总结：

**1. 局部紧性：这在1.1中已经讨论过了**

**2. 预紧集：闭包为紧集的子集**

1.1中得到的结论相当于：**Hausdorff空间在点$x$处局部紧，若每个开邻域都包含一个预紧的开邻域**

**Hausdorff空间局部紧$\iff$ 它有一组预紧开集构成的拓扑基**

证：考虑到拓扑基生成拓扑的判定：$(X,\tau)$为拓扑空间，$\mathcal{B}$为$X$的一个开集族，那么$B$生成拓扑$\tau$，当且仅当：对$X$中任何开集$U$，对$U$中任意一点$x$，存在$\mathcal{B}$中的开集$V$，使得$x\in V\subseteq U$。那么利用1.1得到的结论这个命题就显然了。

**3. 紧穷尽(exhaustion by compact sets)：拓扑空间$X$的一个紧穷尽指一列紧子集$\{K_n\}$，且$\cup K_n=X, K_{i}\subseteq \text{Int} K_{i+1}$**

**$C_2$的局部紧Hausdorff空间$X$存在紧穷尽**

证：$X$有一组预紧开集拓扑基$\mathcal{K}$，以及一个可数拓扑基$\mathcal{B}$，先来说明$\mathcal{B}$有一个预紧的子拓扑基。

取至多可数子集族$\mathcal{B}'=\{B\in\mathcal{B}|B\subseteq \exists K\in\mathcal{K} \}$，这样，对于每一个$B\in \mathcal{B}'$，对于$X$中每一点$x$，自然有$\mathcal{K}$中元素$K$满足$K\ni x$，而$\mathcal{B}$是拓扑基，于是自然有某个$B\in\mathcal{B}$使得$x\in B \subseteq K$（因为$K$开集，必然能表示成若干拓扑基中元素的并）。但这样的$B\in\mathcal{B}'$，从而说明$\mathcal{B}'$是开覆盖。但是对每个$\mathcal{B'}$中的元素，其闭包都在紧集$\bar{K}$中，于是自然$\mathcal{B'}$由预紧开集构成。

$\mathcal{B'}$能够成为生成原有拓扑的子拓扑基是因为对于任意开集$U$，它可表示为若干$K\subseteq\mathcal{K}$的并，对$U$中任意一点$x$，设$x\subseteq K_\alpha$，那么自然有某个$B\in\mathcal{B}$使得$x\in B \subseteq K_\alpha$（原因同上）。于是这就自动满足拓扑基生成拓扑判定定理的条件了，从而$\mathcal{B'}$使一个预紧开集构成的拓扑基。



设$\{U_i\}$为一组可数预紧开集构成的拓扑基（上述讨论保证了存在性），下面选取紧穷尽：

$K_1=\bar{U_1}$，自然$K_1\subseteq \bar{U_1}\cup\cdots\cup\bar{U_{i_2}}$，紧性保证$i_2$存在，我们选取最小的使这个式子成立的指标$i_2$，且$i_2>1=i_1$。取$K_2=\bar{U_1}\cup\cdots\cup\bar{U_{i_2}}$。这样$K_{1}\subseteq \text{Int} K_{2}$。反复构造下去并且保证指标序列$\{i_n\}$严格增。那么这就是满足要求的紧穷尽。



称子集族**局部有限**，若对于每点，存在开邻域与子集族中至多有限个子集相交。

对于两个开覆盖$\mathcal{U,V}$，若每个$\mathcal{V}$中的开集$V$都能找到一个$\mathcal{U}$中开集$U$使得$V\subseteq U$，则称$\mathcal{V}$为$\mathcal{U}$的**加细**。

**4. 仿紧性：若拓扑空间$X$的每个开覆盖都有局部有限的开覆盖加细，则称$X$仿紧。**

重要的结论是：

**拓扑流形仿紧。**

证：设$M$是一个拓扑流形，$\mathcal{U}$为一个开覆盖，$\{K_i\}$为一个紧穷尽。

记$V_i=K_{i+1}-\text{Int}\ K_i$，$W_i=\text{Int} \ K_{i+2}-K_{i-1}$（指标超出定义域时按空集理解）

那么$V_i$紧，$W_i$开，且$V_i \subseteq W_i$

对于$M$上每点$x$，取$\mathcal{U}$中元素$U_x\ni x $，那么对于每个指标$i$可以取一个$x$处的局部坐标系$\{V^{pre}_{xi},\varphi_{xi}\}$，使得$x\in V^{pre}_{xi}\subseteq U_x\cap W_i$。由于局部紧，可以选出一个$x\in V_{xi}\subseteq V^{pre}_{xi}$，且$V_{xi}$是一个预紧开邻域，那么自然它也是坐标域，并且沿用同样的同胚$\varphi_{xi}$。

（接下来做一些很小的加强，这是为了后续Urysohn引理和单位分拆定理叙述方便）

取适当的$\varphi_{xi}$使得$\varphi_{xi}(x)=0,\varphi_{xi}(V_x)=B(0,3)$

记$T_{xi}=\varphi_{xi}^{-1}(B(0,1))$，当然存在有限个$T_{xi}$覆盖了$V_i$，设为$T_{x1_{i}},\cdots,T_{xn_{i}}$，于是它们对应着$V_{x1_{i}},\cdots,V_{xn_{i}}$

于是对于每一个$i$如此操作，就得到若干$V_{xn_{i}}$，这是一个开覆盖加细（开覆盖是因为它们覆盖了$V_i$），并且满足局部有限性：取点$x$的开邻域为任一$V_{xi}$即可（不妨$i=1$）。

这是因为对于任意$V_{xi}\subseteq W_i$，$V_{xn_j}\cap V_{xi}\neq\phi\implies W_i\cap W_j\neq\phi\implies j\in[i-2,i+2]$。而这种情况当然是有限的。





接下来，在这里详细描述2.2中使用过的光滑版本的Urysohn引理。

（利用磨光得到的更一般的结论见：[https://www.cnblogs.com/XiongRuiMath/p/9514946.html](https://www.cnblogs.com/XiongRuiMath/p/9514946.html)）

**（Urysohn引理，流形，光滑版本）$U,V$是光滑流形$M$的两个非空开集，且$\bar{V}$紧致，$\bar{V}\subseteq U$，则流形$M$上存在光滑函数$h:M\rightarrow [0,1]$，使得：$h(V)=1, h(U^c)=0$**

证：对于任一$\bar{V}$中的点$q$，取其局部坐标$(U_q,\varphi_q)$使得$U_q\subseteq U$，自然可以选取一个恰当的同胚$\varphi_q$，使得$\varphi_q(U_q)=B(0,3)$，设$V_q=\varphi_{-1}(B(0,1))$。

取$f:\mathbb{R}^m\rightarrow \mathbb{R}$，$f(\{|x|\leq 1\})=1,f(\{|x|\geq 2\})=0$，并且$f$光滑（利用$e^{-\frac{1}{x}}$，这被称为所谓鼓包函数）

再取$h_q(p)=\left\{f\circ \varphi_q(p)\ \ p\in U_q \atop0\ \ \ \ \ \ otherwise\right.$，那么$h_q(V_q)=1,h_q(U^c_q)=0$

而$\cup V_q$构成了$\bar{V}$的开覆盖，于是可选出有限子覆盖$V_{q_1}\cdots V_{q_n}$。取$h_0=\sum h_{q_i}$，那么当$p\in \bar{V}$时，$h_0(p)\geq 1$，且$h_0$是光滑的。那么再复合上一个$\mathbb{R}\rightarrow\mathbb{R}$的光滑函数$g$，且使$x\leq0, g(x)=0; x\geq1, g(x)=1$即可。



**（支集）对于$M$上实函数$f$，其支集为非零点集的闭包：$\text{supp} \ f=\overline{\{p\in M|f(p)\neq 0\}} $**

**同样，对于$M$上的外微分式$\varphi$，$\text{supp} \ \varphi=\overline{\{p\in M|\varphi(p)\neq 0\}} $**



以上是所有有关这个重要定理所需的内容。

**（单位分拆定理）对于光滑流形$M$上的任一开覆盖$\{U_{\alpha}\}$，存在一组光滑函数$\{g_\alpha\}$满足：**

**a. $g_\alpha(M)\subseteq [0,1]$，且$\text{supp}\  g_\alpha$紧致，并且能被开覆盖中某个开集$U_\alpha$包含。**

**b. 支集$\text{supp}\  g_\alpha$局部有限，即对每一个点$x$，存在开邻域仅与有限多个支集相交。**

**c. 由于条件b，和式$\sum g_\alpha$有意义，且它为1。**

证明的梗概是简单的：紧穷尽$\implies$仿紧性$\implies$局部有限开覆盖加细$\implies$在开覆盖加细的每个开集上应用Urysohn引理，局部有限性保证和式有意义。

证：

前置准备已经说明了光滑流形$M$上任一开覆盖$\{U_{\alpha}\}$有着局部有限的开覆盖加细。

设这个开覆盖加细为$\{V_{i},\varphi_{i}\}$​，并且满足之前构造时的$\varphi_{i}(V_i)=B(0,3)$，以及$\bar{V_i}$紧致。同样地，记$T_{i}=\varphi_{i}^{-1}(B(0,1))$，并且在流形仿紧的证明中说明了$\{T_i\}$是一个开覆盖。

现在同Urysohn引理完全一样地构造出$h_i(p)=\left\{f\circ \varphi_i(p)\ \ p\in U_q \atop0\ \ \ \ \ \ otherwise\right.$，那么$\text{supp}\ h_i\subseteq V_i\subseteq U_\alpha$

记$g(p)=\sum h_i(p)$，由于$V_i$局部有限，所以这个和式总是表示一个有限和。

另一方面$\{T_i\}$是一个开覆盖，且$T_i\subseteq \text{supp}\ h_i$，于是$g(p)\geq1$处处成立。

从而取$g_i(p)=h_i(p)/g(p)$满足要求：条件b,c是显然的，对于a，只需验证紧致性。而$\text{supp}\ g_i=\text{supp}\ h_i$，后者是紧集$\bar{V_i}$的闭子集，从而也是紧的，这就完成了证明。



单位分拆定理的证明思路是直接了当的，但是其严格的证明细节需要反复利用流形的局部紧和仿紧性质，在这里也看到假定流形$C_2$的重要性。

利用单位分拆，就可以在流形上大范围地进行定义：将$1$分拆，每一个部分只在一个很小的邻域上非$0$，从而能够从局部定义推及到整个流形上的定义，关于这一点我们已经在外微分算子的定义时领略过了。

### 3.2 重积分换元

在直接引入流形上的积分之前，先从流形退回到熟悉的$\mathbb{R}^m$中来。

为了简便起见，这里只讨论连续函数的换元（从而尽管思路与微分同胚相同，但是换元映射只是连续可微的单射）。

完整的讨论参见：https://zhuanlan.zhihu.com/p/303511620

首先给出核心的换元定理：

**$T$是将开集$E\subseteq \mathbb{R}^m$映入$\mathbb{R}^m$的连续可微单射，并且对于一切$\pmb{x}\in E$，$J_T(\pmb{x})\neq 0$. 如果$f$是$\mathbb{R}^m$上的连续函数，且具有紧支集，并且位于$T(E)$内，那么：**

**$\begin{aligned}\int_{\mathbb{R}^m} f(\pmb{y})d\pmb{y}=\int_{\mathbb{R}^m}f(T(\pmb{x}))|J_T(\pmb{x})|d\pmb{x}\end{aligned}$**

（反函数定理保证$T^{-1}$连续，从而$\text{supp} \ (f\circ T)$也是紧的）



证：

1. 每个连续可微映射在点$x_0$，若$\pmb{F'}(x_0)$可逆，$F(x_0)=0$，则存在某个邻域使得在这个邻域上映射能拆成若干本原映射（只改变一个坐标）以及坐标对换的复合。

对被改变坐标数进行归纳：假设命题对被改变至多$k-1$个坐标的连续可微映射成立，那么对于被改变至多$k$个坐标的连续可微映射$f$：不妨它在某个邻域有形式$y^i=\left\{f^i(x^1,\cdots x^m)\quad i\in\{1,\cdots,k\}\atop x^i\quad otherwise\right.$。

$\pmb{F'}$不是退化的：于是计算行列式知$\{\frac{\partial f^i}{\partial x^j}\}_{k\times k}$构成的行列式非0，于是这个行列式至少有一个$k-1$阶子式非0。由于坐标顺序在这里已经不重要，不妨其$k-1$顺序主子式非0。

那么：$g:y^i=\left\{f^i(x^1,\cdots x^m)\quad i\in\{1,\cdots,k-1\}\atop x^i\quad otherwise\right.$在点$x_0$的某个邻域成立，于是$\pmb{G'}$不退化，从而由反函数定理在某个邻域内存在逆映射$g^{-1}$

于是$h=f\circ g^{-1}$是本原映射（只有第$k$个坐标发生了变化），而$f=h\circ g$，应用归纳假设即证。

2. 对于本原映射，命题成立

这是一维情况的直接推论

3. 对于坐标对换，命题成立

这是重积分换序的推论：将紧支集被某个$m-$方格包含，然后应用重积分换序。

4. 如果有两个变换$P,Q$使得命题成立，那么它们的复合$P\circ Q$作为变换也能使命题成立。

$\begin{aligned}\int f(\pmb{z})d\pmb{z}=\int f(P(\pmb{y}))\cdot|J_P(\pmb{y})|d\pmb{y}=\int f(P\circ Q(\pmb{x}))\cdot|J_P(Q(\pmb{x}))|\cdot|J_Q(\pmb{x})|d\pmb{x}\end{aligned}$

而$J_{P\circ Q}(\pmb{x})=\det ({P\circ Q})'=\det P'(Q)\cdot Q'=\det P'(Q)\cdot\det Q'=J_P(Q(\pmb{x}))\cdot J_Q(\pmb{x})$，于是得证。

5. 综合1~4. 知对于每点$\pmb{a}\in E$，存在一个开邻域$U_a$使得在其中变换$T$可拆成1.中所述的形式与一个平移的复合。那么设$V_a=T(U_a)$，于是当$\text{supp}\ f \in V$ 时命题成立。



那么对于具有紧支$K\sube T(E)$的任意连续函数$f$，$\{V_a\}$是一组$K$上开覆盖，于是应用单位分拆（紧致版本，证明完全相同）可知$f=\sum g_\alpha\cdot f$，并且每个$g_\alpha$的支集都在某个$V_i$内，于是对于每个$g_\alpha\cdot f$，命题成立，从而原命题成立。

### 3.3 流形上的积分

单位分拆的最直接的应用就是外微分式在定向流形上的积分。

**（定向流形）$n$维光滑流形$M$称为可定向的，若存在一个处处非0的$n$次外微分式（注意外微分式已经蕴含了光滑从而蕴含了连续条件）。**

那么就可以定义外微分式的积分。

$M$是$m$维定向的光滑流形，$\varphi$是$M$上的$m$次外微分式，且具有紧致的支集$\text{supp}\ \varphi$。取一组符合定向（即$du^1\wedge\cdots du^m$与定向的外微分式仅相差一个正因子）的坐标覆盖$\{U_i\}$。

那么有从属于$\{U_i\}$的单位分拆$\{g_\alpha\}$，自然$\varphi = \sum (g_\alpha \varphi)$。于是支集$\text{supp}\ g_\alpha\varphi\subseteq\text{supp}\ \varphi\subseteq U_i$

从而定义$\begin{aligned}\int_Mg_\alpha\cdot\varphi=\int_{U_i}g_\alpha\cdot\varphi\end{aligned}$

右端的定义是：若$g_\alpha\cdot\varphi$在局部坐标下表示为$f(u_i^1,\cdots u_i^m)du_i^1\wedge\cdots\wedge du_i^m$，则$\begin{aligned}\int_Mg_\alpha\cdot\varphi=\int_{U_i}g_\alpha\cdot\varphi=\int_{U_i}f(u_i^1,\cdots u_i^m)du_i^1\cdots du_i^m\end{aligned}$

最后一式即为普通的Riemann积分。

这个定义是良好的是因为若$\text{supp}\ g_\alpha\varphi\subseteq U_i\cap U_j$，利用重积分换元可以验证选取$U_i$或$U_j$不会影响结果（这里符合定向的重要性就体现出来了）。

那么外微分式在整个流形上的积分被定义为$\begin{aligned}\int_M\varphi=\sum\int_Mg_\alpha\cdot\varphi\end{aligned}$（局部有限性保证右端和式有意义）

还需要证明这与单位分解的选取方式无关。

若$\{g'_\beta\}$是另一组从属于$\{U_i\}$的单位分拆，则：

$\begin{aligned}\sum_{\beta}\int_M g'_\beta\cdot\varphi=\sum_\beta\sum_\alpha\int_M g_\alpha\cdot g'_\beta \cdot\varphi=\sum_\alpha\sum_\beta\int_M g'_\beta\cdot g_\alpha \cdot\varphi=\sum_{\alpha}\int_M g_\alpha\cdot\varphi\end{aligned}$

从而说明了定义是良好的。

不难验证流形上的积分依然有线性关系，且当$\text{supp}\ \varphi$落在某个坐标域内时退化成普通的Riemann积分。



### 3.4 Stokes公式 - 流形

Stokes公式指出的是区域和边界上积分的关系，但是为了说明边界的具体定义，首先定义带边区域。

一个最简单的例子就是闭圆盘，其边界点的邻域无论如何也不能与$\mathbb{R}^2$中的开集同胚，但是能够和上半平面的同胚。于是就引出带边区域的定义：

**（带边区域）光滑流形$M$的一个带边区域指流形的一个闭子集$D$，其中的点要么为内点：有一个邻域包含在$D$内；要么为边界点：设这个点为$p$，则存在一个局部坐标系$(U,u^i)$，使得$u^m(p)=0,U\cap D=\{q|q\in U,u^m(q)\geq 0\}$，称这个坐标系为适用坐标系（同胚于上半平面的某个开集）**

全体边界点称为$D$的边缘（为了与拓扑的边界区分，尽管它们在大多数应用场景下是一样的），记作$B$。

那么首先有$B$是闭的，这是因为一个点不能同时为内点和边界点（$\mathbb{R}^m$与$\H^m$不同胚，有关带边流形的详细论述见4.4），而内点构成的集合是开的，则边界是闭的（闭集减去开集还是闭集）

为了引入Stokes公式，还要考虑边界上的定向：

若$M$是定向的，对于边缘$B$上的每一点，可以取符合定向的坐标系$(U,u^i)$，使得$U\cap B=\{q|q\in U, u^m(q)=0\}$，这是因为如果$u^m(q)>0$，那么就有一个$D$内的开邻域了。

即：全体边缘点在坐标卡的同胚变换下落在了$\H^m$的边缘上。

于是将$B$在$p$点的局部坐标取为$(U;u^1,\cdots,u^{m-1})$，然后给出$U\cap B$的定向：$(-1)^m du^1\wedge\cdots\wedge du^{m-1}$，下面说明这样取出来的$B$的坐标系给出的定向相容。

设有另一个符合定向的坐标系$(V,v^i)$，并且给出了$V\cap B$的一个局部坐标。由于$v^m$和$u^m$的符号相同，且$u^m=0\iff v^m=0$，那么$\frac{\partial v^m}{\partial u^m}>0$。那么可以假设$u^m=v^m$，于是$U,V$定向相容自然说明边缘上的定向是相同的。从而边缘的定向被流形的定向决定了。

记这个继承了流形定向的边界为$\partial D$。



**（Stokes公式）$D$是$m$维定向流形$M$中的带边区域，$\omega$是$M$上有紧支的$m-1$次外微分式，则：**

**$\begin{aligned}\int_D d\omega=\int_{\partial D}\omega \end{aligned}$**

（若$\partial D=\phi$，则规定右侧积分为0）

证：设$U_i$是一组符合定向的坐标覆盖，以及从属的单位分解$\{g_\alpha\}$

那么只需说明对于每个分解：$\begin{aligned}\int_D d(g_\alpha\cdot\omega)=\int_{\partial D}g_\alpha\cdot\omega \end{aligned}$

于是恒可假定$\text{supp} \ \omega$被某个符合定向的坐标域$U$包含（将$g_\alpha\cdot\omega$视作$\omega$）

那么设$\omega=\begin{aligned}\sum_{j=1}^m (-1)^{j-1}a_j du^1\wedge\cdots\wedge \overline{du^j}\wedge\cdots\wedge du^m\end{aligned}$（$a_j$是$U$上光滑函数）

于是$d\omega=\begin{aligned}(\sum_{j=1}^m \frac{\partial a_j}{\partial u^j})du^1\wedge\cdots\wedge du^m\end{aligned}$

1. $U\cap\partial D=\phi $，于是$\begin{aligned}\int_{\partial D}\omega=0 \end{aligned}$

此时$U\subseteq M-D$或$D$的内部。对于前者当然$\begin{aligned}\int_D d\omega=0 \end{aligned}$，对于后者：

$\begin{aligned}\int_D d\omega=\sum_{j=1}^m\int_U\frac{\partial a_j}{\partial u^j}du^1\cdots du^m \end{aligned}$

那么在$\mathbb{R}^m$中可以将$a_j$延拓到某个m-方格$|u^i|\leq T$上

于是$\begin{aligned}\int_U\frac{\partial a_j}{\partial u^j}du^1\cdots du^m =\int_{|u_i|\leq T\atop i\neq j } (\int_{-T}^T\frac{\partial a_j}{\partial u^j}du^j)du^1\cdots\overline{du^j}\cdots du^m\end{aligned}=0$

2. $U\cap\partial D\neq\phi $

不妨$U$是边界上适用的坐标系（适当地选取坐标映射）

于是取一个m-方格$[-T,T]^{m-1}\times[0,T]$使得$U\cap D$的同胚像落在 这个方格的内部并上边界$u^m=0$中，当然可以对$a_j$作延拓。

于是：

$\begin{aligned}\int_{\partial D}\omega= \int_{U\cap \partial D}\omega=\sum_{j=1}^m (-1)^{j-1}\int_{U\cap\partial D}a_jdu^1\wedge\cdots\wedge \overline{du^j}\wedge\cdots\wedge du^m \\\xlongequal[]{u^m=0}(-1)^{m-1}\int_{U\cap\partial D}a_mdu^1\wedge\cdots\wedge du^{m-1}\\=-\int_{|u^i|\leq T\atop 1\leq i\leq m-1}a_m(u^1,\cdots,u^{m-1},0)du^1\wedge\cdots\wedge du^{m-1}\end{aligned}$

（最后一个等号源于边缘的定向）

$\begin{aligned}\int_D d\omega=\int_{D\cap U}d\omega=\sum_{j=1}^m \int_{D\cap U}\frac{\partial a_j}{\partial u^j}du^1\wedge\cdots\wedge du^m \end{aligned}$

而对于$1\leq j\leq m-1$：

$\begin{aligned}\int_{D\cap U}\frac{\partial a_j}{\partial u^j}du^1\wedge\cdots\wedge du^m =\int_{|u^i|\leq T(i\neq j,m)\atop 0\leq u^m\leq T} (\int_{-T}^T\frac{\partial a_j}{\partial u^j }du^j)du^1\cdots\overline{du^j}\cdots du^m\end{aligned}=0$

于是：

$\begin{aligned}\int_D d\omega=\int_{D\cap U}\frac{\partial a_m}{\partial u^m}du^1\wedge\cdots\wedge du^m=\int_{|u^i|\leq T \atop i\neq m}[a(u^1,\cdots,u^{m-1},T)-a(u^1,\cdots,u^{m-1},0)]du^1\cdots du^{m-1}\\=-\int_{|u^i|\leq T\atop 1\leq i\leq m-1}a_m(u^1,\cdots,u^{m-1},0)du^1\wedge\cdots\wedge du^{m-1}  \end{aligned}$

这样就完成了证明。

另外，当$D$是紧的，不必假定$\omega$有紧致的支集，因为此时上述结论都自动成立。



## 4. 同调

第四节和第五节是代数拓扑的内容。

代数拓扑的基本观点：几何对象的代数照相。这种照相是用范畴与函子的语言来表达的。



在本节，主要考虑两件事：1. 奇异链上导出的Stokes公式，2. 奇异同调群

我们考虑流形上的积分不再如同上一节那样通过一个坐标域上的自然基实现了，转而考虑链上作积分。这就引出了链：它是对于流形的分割。

这样的分割方式多种多样：最简单的一种是单纯复形（这是遵循直觉的）：考虑多面体到流形上的同胚，拓扑上有许多手段来完成单纯复形；而进一步则是奇异复形：这比单纯复形的要求更低。

### 4.1 单形与单纯复形

**（单形）对于$\mathbb{R}^n$中$m+1$个点$\{a_0,\cdots,a_m\}$，若$a_i-a_0$线性无关，则将包含着$m+1$个点的凸包称为一个$m$维单形。**

**（定向）**对于单形的一个顶点排列，称$[a_0,\cdots,a_m]$给出了单形的一个定向，并且两个排列给出定向相同当且仅当它们之间相差一个偶置换。这样每个单形都存在两种定向。

**（面）若对于单形$A,B$，后者的顶点集是前者的子集，则称$B$为$A$的一个面：$B<A$**

正如流形上已经做过的那样，单形也可以被定义一个边缘算子：

$\partial [a_0,a_1,\cdots,a_m]=\sum_i (-1)^i[a_0,a_1,\cdots,\overline{a_i},\cdots,a_m]$（其实在这里就已经能从形式上看出$\partial$和$d$的对偶性了）

其中$(-1)^i$表示了定向是否反转。

特殊地：0维单形的边缘是0.

当然希望若干单形能够“完美地”进行拼接，这种完美性称为规则相处。

**（规则相处）称两个单形规则相处，若它们不交或其交为它们的公共面**

于是这种拼接的结构称为：

**（单纯复形）若$\mathbb{R}^n$中有限个单形构成的集合$K$满足：a. 每个$K$中单形的面也在$K$中；b. $K$中任意两个单形是规则相处的。称复形的维数为其中包含单形的最高维数。**

那么将一个复形$K$中的所有单形对应的集合并起来称为$\mathbb{R}^n$的一个子集，称这个子集$|K|$为一个多面体，而$K$则为一个单纯剖分。

于是这给出了一个本节开头提及的单纯剖分：

若一个拓扑空间$X$，存在复形$K$，使得有同胚$h:X\rightarrow |K|$，则称这个拓扑空间是可单纯剖分的，并且定义这个单纯剖分为复形和同胚组成的偶对$(K,h)$

### 4.2 链群，单纯同调群

单形的重要性源于它可以将整个问题转化到代数上来，在对单形进行研究时已经出现了单形的加法，这已经暗示了Abel群要在这里闪亮登场。

对于一个复形$K$，定义一个$q$维链为$K$中包含的全体$q$维（定向）单群的一个整系数线性组合，其中符号表示定向的反转。于是这些形式和（链）自然地构成了一个Abel群，称为复形$K$的$q$维链群$C_q(K)$。

于是对于一个链，也可以定义它被边缘算子作用后的像：按照线性组合方式定义即可。

于是对于作用在$q$维链上的边缘算子，这事实上是一个群同态：$\partial:C_q(K)\rightarrow C_{q-1}(K)$（特殊地：$C_{-1}(K)=0$）



接下来阐明一个事实（尽管从几何直觉来看是显然的）

**$\partial^2=0$**

证明就是利用定义验算，此处略去。



于是在所有被边缘算子作用为0的链中，有些自身也作为某个链的边缘，但是有更重要的一部分是：尽管自己不是某个链的边缘，但自己被边缘算子也作用成0。即：圈是不是边？这一部分用群的语言叙述就是：

**（闭链群，边缘链群，同调群）**

**同态$\partial:C_q(K)\rightarrow C_{q-1}(K)$的核称作$q$维闭链群$Z_q(K)$，称其元素为圈。**

**同态$\partial:C_{q+1}(K)\rightarrow C_{q}(K)$的像称作$q$维边缘链群$B_q(K)$，称其元素为边界。**

**定义$q$维单纯同调群为：$H_q(K)=Z_q(K)/B_q(K)$**（子群由$\partial^2=0$保证）

那么前文中描述的重要的那一部分就相当于$H_q(K)$.



当然以后的结论指出了$H_q(K)$是拓扑不变量，但这目前不是重点。介绍单形的目的是为了更好地解释奇异单形以及奇异链。

### 4.3 奇异单形，奇异链

同样地，从与单纯形几乎相同的标准单形开始：

**（标准单形）一个$q-$标准单形$\Delta^q$被定义为零点和q个标准正交基张出的凸包。**

边缘算子的定义方式和4.1中相同。

那么对于$\mathbb{R}^n$中的$n-$微分形式$\omega=a(\pmb{x})dx^1\wedge\cdots\wedge dx^n$，定义它在单形上的积分为对应的Riemann积分$\int a(x_1,\cdots,x_n)dx^1dx^2\cdots dx^n$

一定的计算（其实和流形上Stokes定理的证明时计算相仿）表明了标准单形的Stokes定理成立：

**（Stokes定理，标准单形）$\omega$是一个$r-1$微分形式，则：$\int_{\Delta^r}d\omega=\int_{\partial \Delta^r}\omega$**



正如之前对单纯复形讨论链群一样，这里也有类似的结果。

首先定义奇异单形：在这里可以看到这节走上了和4.2完全不同的道路。

**（奇异单形）流形$M$的一个奇异单形指一个连续映射$T:\Delta^r\rightarrow M$的像，称为$r-$奇异单形。奇异单形的边缘被定义为标准单形边缘的像。（这里的流形可以放宽至任何拓扑空间$X$，在那里将奇异单形直接看作这里的连续映射$T$，二者没有本质差别）**

全体$q$维奇异单形的$G-线性组合$构成的群称为其奇异链群$S_q(M,G)$，（对于$G=\mathbb{Z}$的情况仍记为$S_q(M)$）每个元素称为奇异链。于是同样地可以定义$r-$形式在奇异链上的积分（按照线性组合相加即可）

**（奇异链复形）一个奇异链复形$S_*(X)$是群$S_q(X)$和同态$\partial:S_q(X)\rightarrow S_{q-1}(X)$构成的族。**

仿照单纯形的情况，这个链复形也可以定义出**奇异同调群$H_q(X)=Ker \partial_q/Im\partial_{q+1}$**

自然地有奇异链的Stokes定理（奇异链上的积分被定义为$\int_\Delta f^*\omega$，其中$f^*$为拉回映射：$T^*_M\rightarrow T^*_\mathbb{R}$，这和后文de Rham同调中的拉回相似）

**（Stokes定理，光滑奇异链）$\omega$是一个$r-1$微分形式，C是一个r维光滑奇异链，则：$\int_{C}d\omega=\int_{\partial C}\omega$**

证：自然可以假设$C$是光滑奇异单形$\sigma$。

那么$\int_\sigma d\omega=\int_{\Delta^r}f^*(d\omega)=\int_{\Delta^r}d(f^*\omega)\xlongequal{带角流形的Stokes定理，证明同Stokes定理} \int_{\partial\Delta^r}f^*\omega=\int_{\partial\sigma}\omega$

于是这样就说明了光滑奇异链的Stokes定理。

### 4.4 奇异同调

下文的所有同调群指奇异同调群。

首先说明奇异同调群为什么是几何对象的“代数照相”：



拓扑空间上的每个连续映射$f:X\rightarrow Y$都诱导了奇异链群的同态：$f_{\#}:S_p(X)\rightarrow S_p(Y),T\mapsto f\circ T$

简单的计算指出$f_{\#}与$$\partial$可交换。于是在同调群$H_p(X),H_p(Y)$上，定义$f_{*}([c])=[f_{*}(c)]$。

这个定义是良好的，因为若$c,c'$同调，即$c-c'\in B_p(X), [c]=[c']$，那么$f_{*}(c)-f_{*}(c')=f_{\#}(c-c')=f_{*}(\partial d)=\partial(f_{*}(d))$，从而$[f_{*}(c)]=[f_{*}(c')]$

并且，很容易验证恒等映射诱导了同调群的恒等映射，并且保持了结合律，保持了零元。

于是自然有$f$是同胚时，诱导出的群同态变为群同构，从而说明了奇异同调群是拓扑不变量。



接下来介绍奇异同调的几个性质（但不予以证明，其证明可在任何代数拓扑参考书中找到）

有关同伦的结果被放在上同调的部分中介绍。

**（同伦不变量）若$X,Y$同伦等价，则$X,Y$上同调群同构。**

**（相对同调群）$A$是$X$的子拓扑空间，则相对奇异链群$S_p(X,A)=S_p(X)/S_p(A)$，并且可以验证边缘算子$\partial$也在$S_p(X,A)$上诱导了同态。将群$S_p(X,A)$和边缘同态组成的族称为空间偶$(X,A)$的奇异链复形，这个链复形上自然也可以定义出同调群$H_p(X,A)$**

**（星凸）关于某点星凸的欧氏空间子空间$X$在奇异同调中是零调的，自然地单形、圆盘都是零调的。**

**（切除定理）$A\subseteq X,\bar{U}\subseteq \text{Int}A$，则包含映射$j:(X-U,A-U)\rightarrow (X,A)$在奇异同调中诱导出了一个同构：$S_p(X,A)\cong S_p(X-U,A-U)$**

几何意义是极其直观的：切掉同一块不会改变相对同调群。

**（单纯同调和奇异同调相容）$K$是单纯复形，则其单纯同调群与$|K|$的奇异同调群同构，并且这个同构与边缘同态，单纯映射诱导的同态都交换，这就说明两种同调理论是相容的。**



接下来回到流形，利用局部同调给出带边流形一个严格的说明（它和带边区域是相仿的）。

**（局部同调群）Hausdorff空间$X$在某点$x$处的局部同调群定义为相对同调群$H_p(X,X-x)$**

**（局部性）令$A\subseteq X$，且包含一个$x$点的邻域，则：$H_p(X,X-x)\cong H_p(A,A-x)$**

证：记$U=X-A$，则$\bar{U}\subseteq X-x=\text{Int}(X-x)$，第一个包含是因为$A$包含$x$的一个邻域。

于是$H_p(X,X-x)\stackrel{切除定理}\cong H_p(X-U,X-x-U)=H_p(A,A-x)$

**（带边流形，弱）非空Hausdorff空间$X$每一点都有一个邻域与Euclid半空间$\H^m$的开集同胚，则称为$m$维带边流形。（这里标记了“弱”是因为没有要求$C_2$或可度量化）**

之前在处理带边区域的时候已经遇到了一些区分边界和内部的困难。在这里我们利用局部同调群能够很好的解决它。

$X$中的点$x$可能被同胚映射到$\mathbb{R}^{m-1}\times\mathbb{R}^+$内，也可能被映射到边界$\mathbb{R}^{m-1}\times 0$上

于是利用4.5中的结果可以知道，前者会使得局部同调群$H_m(X,X-x)$成为无限循环的，而后者使其成为零群。这样局部同调群可以用来帮助区分边界和内部：

**（边界与内部，带边流形版本）若带边流形$X$中的一个点$x$在所有坐标卡中都被映到了$\text{Bd}\H^m=\mathbb{R}^{m-1}\times 0$中的点，则称为边界点，边界点构成的集合记为$\text{Bd}X$，$X-\text{Bd}X$称为$X$的内部。**

使得$H_m(X,X-x)$能够非平凡的指数$m$是唯一的，于是这个维数的定义也是良好的。

这样，代数拓扑帮助完成了带边流形的严格定义。

### 4.5 长正合列，一些计算

将计算相关的部分内容放到此节介绍：

**（约化同调群）一个链复形可以被增广为$\cdots\rightarrow S_1(X)\stackrel{\partial}\rightarrow S_0(X)\stackrel{f}\rightarrow \mathbb{Z}\rightarrow 0$，其中$f(\sum n_i \sigma_i)=\sum n_i$，这个增广的链复形的同调群记作约化同调群：$\widetilde{H}_n(X)=\left\{H_n(x)\quad n\neq 0\atop Ker\ f/Im\ \partial_1\right.$**

对于相对链复形，同样可以进行增广，只不过此时$\widetilde{H}_n(X,A)=H_n(X,A)$。

并且对于合适的$(X,A)$，有长正合列。

**若$A$是$X$的非空闭子集，且为$X$中的某个邻域的形变收缩，则有长正合列：**

**$\cdots\longrightarrow\widetilde{H}_n(A)\stackrel{i_*}\longrightarrow\widetilde{H}_n(X)\stackrel{j_*}\longrightarrow \widetilde{H}_n(X/A)\stackrel{\partial}\longrightarrow\widetilde{H}_{n-1}(A)\stackrel{i_*}\longrightarrow\widetilde{H}_{n-1}(X)\longrightarrow\cdots$**

**其中$i$是包含映射，$j$则是商映射：将$A$映成一个点，其余保持不动。**

映射$\partial$将在证明中指出。

证：

首先说明在满足定理的条件下，商映射$j:(X,A)\rightarrow (X/A,A/A)$诱导了同构$q_*:H_n(X,A)\rightarrow H_n(X/A,A/A)$，而后者就是$\widetilde{H}_n(X/A)$

对于$X$的邻域$V$形变收缩到$A$，则$A\subseteq V\subseteq X$，有交换图：

$\begin{CD} H_n(X,A)@>>> H_n(X,V)@<<<H_n(X-A,V-A)\\ @Vq_*VV@Vq_*VV@Vq_*VV\\ H_n(X/A,A/A)@>>>H_n(X/A,V/A)@<<<H_n(X/A-A/A,V/A-A/A) \end{CD}$

由于$(V,A),(A,A)$同伦，从而$H_n(V,A)=H_n(A,A)=0$，于是$H_n(X,A)\cong H_n(V,A)$，即左上水平箭头是同构。同样地有形变收缩将$V/A$变为$A/A$，于是左下水平箭头也是同构。切除定理保证了右侧的两个水平箭头也是同构。

而最右侧的竖直箭头是同构的，因为$X-A\cong X/A-A/A$，对$V$同理。

于是由交换图得出最左侧的箭头是同构。



于是需要证明的内容变成了：

（长正合列定理）$\cdots\longrightarrow{H}_n(A)\stackrel{i_*}\longrightarrow{H}_n(X)\stackrel{j_*}\longrightarrow {H}_n(X,A)\stackrel{\partial}\longrightarrow{H}_{n-1}(A)\stackrel{i_*}\longrightarrow{H}_{n-1}(X)\longrightarrow\cdots$是一个长正合列。

注意到短正合列$0\longrightarrow S_n(A)\longrightarrow S_n(X)\longrightarrow S_n(X,A)\longrightarrow 0$，这个命题可以变成如下的一般形式：

（Zig-Zag引理）若对于链复形有如下交换图成立，每个竖列为短正合列，这也被称为链复形的短正合列：

$\begin{CD} @. 0@.0@.0@. \\@.@VVV@VVV@VVV\\ \cdots@>>>A_{n+1}@>\partial>>A_n@>\partial>>A_{n-1}@>>>\cdots\\@.@ViVV@ViVV@ViVV@.\\\cdots@>>>B_{n+1}@>\partial>>B_n@>\partial>>B_{n-1}@>>>\cdots\\@.@VjVV@VjVV@VjVV@.\\\cdots@>>>C_{n+1}@>\partial>>C_n@>\partial>>C_{n-1}@>>>\cdots\\@.@VVV@VVV@VVV@.\\ @.0@.0@.0@.\end{CD}$

那么对于其同调群$H_n(S)=Ker\partial_n/Im\partial_{n+1}$，有长正合列$\cdots\longrightarrow H_n(A)\stackrel{i_*}\longrightarrow H_n(B)\stackrel{j_*}\longrightarrow H_n(C)\stackrel{\partial}\longrightarrow H_{n-1}(A)\stackrel{i_*}\longrightarrow H_{n-1}(B)\longrightarrow \cdots$

由于$i,j$与边缘算子$\partial$可交换，故它们自然地诱导了同调群的同态。

这其中需要定义长正合列中的$\partial$：

若$c\in C_n$，且为$Ker\partial_n$的元素：记$a=\partial(c)=i^{-1}\circ\partial\circ j^{-1}(c)\ (C_n\longrightarrow A_{n-1})$（注意第一个$\partial$是长正合列当中的，而第二个则是边缘同态）（即：先向上再向右再向上的之字形路线）

设$j(b)=c$，则由于$j(\partial b)=\partial(j(b))=\partial c=0$，由正合性，存在仅由$\partial b$决定的$a$，使得$\partial b=i(a)$，那么对于这个$a$，$i(\partial a)=\partial(i(a))=\partial \partial b=0$

于是在同调群中，定义$\partial [c]=[a]$

欲说明其良定义性，只需说明结果和$c,b$的选取无关：

若有$b'\ s.t. j(b')=j(b)=c$，则$b'-b\in Ker\ j=Im\ i$，于是可设$i(a')=b'-b$。而$i(a+\partial a')=i(a)+i(\partial a')=\partial b+\partial(i(a'))=\partial b+\partial(b'-b)=\partial b'$，但$[a+\partial a']=[a]$，从而说明与$b$的选取无关。

若有另一$c+\partial c'$，设$c'=j(b')$，则$j(b+\partial b')=j(b)+\partial(j(b'))=c+\partial c'$，但$\partial b=\partial(b+\partial b')$，从而说明与$c$的选取无关。

$\partial$是同态可自然地验证。



接下来验证长正合列。

$H_n(B)$处正合：

$Im\ i_*\subseteq Ker\ j_*$：由$ji=0$得出。

$Ker\ j_*\subseteq Im\ i_*$：$Ker j_*$中的等价类的元素$b_n$为圈，而$j(b_n)$为边界。于是可设$c_{n+1}\in C_{n+1}, \partial c_{n+1}=j(b_n)$。而$j$是满射保证存在$b_{n+1}\in B_{n+1},c_{n+1}=j(b_{n+1})$，于是$j(b_n-\partial b_{n+1})=j(b_n)-\partial c_{n+1}=0$。而(A-B-C)的正合性保证了存在$a_n\in A_n,i(a_n)=b_n-\partial b_{n+1}$。而$i(\partial a_n)=\partial(i(a_n))=\partial(b_n)=0$，又$i$是单射，于是$a_n$是圈。从而$i_*[a]=[b_n-\partial b_{n+1}]=[b_n]$

$H_n(C)$处正合：

$Im\ j_*\subseteq Ker\ \partial$：对于$\partial\circ j_*([b])$，由于$\partial\circ j(b)=i^{-1}\circ \partial b$。但是$[b]$在同调群中于是$\partial b=0$，从而$\partial\circ j_*=0$

$Ker\ \partial\subseteq Im\ j_*$：若$[c_n]$是$Ker\partial$中的等价类，于是$[i^{-1}\circ\partial\circ j^{-1}(c_n)]=[0]$，从而$i^{-1}\circ\partial\circ j^{-1}(c_n)$是边界。不妨记前者为$a_{n-1}$，记$j^{-1}(c_n)=b_n$。则存在$a_n\in A_n, \partial a_n=a_{n-1}$。于是$\partial (b_n-i(a_n))=\partial b_n-i(\partial a_n)=\partial b_n-i(a_{n-1})\xlongequal[]{def\ of\ \partial}\partial b_n-\partial b_n=0$，并且$j(b_n-i(a_n))=j(b_n)-(j\circ i)(a_n)=j(b_n)=c_n$，综合有$j_*[b_n-i(a_n)]=[c_n]$

$H_{n-1}(A)$处正合：

$Im\ \partial\subseteq Ker\ i_*$：这和$Im\ j_*\subseteq Ker \partial$的情况类似：$[c_n]$被映到$[\partial b_n]=[0]$

$Ker\ i_*\subseteq Im\ \partial$：若$[a_{n-1}]$是$Ker\partial$中的等价类，即$i(a)=\partial b_n$，那么$\partial j(b_n)=j(\partial b_n)=(j\circ i)(a_{n-1})=0$并且$(i^{-1}\circ \partial \circ j^{-1})(j(b_n))=a{n-1}$，于是$[j(b_n)]$被映到$a_{n-1}$.



综上所述，$\cdots\longrightarrow H_n(A)\stackrel{i_*}\longrightarrow H_n(B)\stackrel{j_*}\longrightarrow H_n(C)\stackrel{\partial}\longrightarrow H_{n-1}(A)\stackrel{i_*}\longrightarrow H_{n-1}(B)\longrightarrow \cdots$构成了一个长正合列。

从而完成了定理的全部证明。



1. 单点空间的$P$的同调群$H_n(p)$在$n=0$时为$\mathbb{Z}$，其余情况时为零。

证：每一个非负维数$n$有一个奇异单形$T_n:\Delta^n\rightarrow P$，于是$S_n(P)$是无限循环的。

计算知：$n\ odd,\partial T_n=0;n\ even,\partial T_n=T_{n-1}$，于是同调群的结果得证。



作为推论，由于$B^m$和单点同伦等价，因此$H_n(B^m)$在$n=0$时为$\mathbb{Z}$，其余情况时为零。



2. $x\in\mathbb{R}^m$，则$H_i(\mathbb{R}^m,\mathbb{R}^m-x)$在$i=m$时无限循环，其余情况时为零。

证：设$B$为一个以$x$为中心的球，于是$H_i(\mathbb{R}^m,\mathbb{R}^m-x)\cong H_i(B,B-x)\cong H_i(B^m,B^m-0)\cong H_i(B^m,S^{m-1})$

对于最后一个群，在长正合列中取$X=B^m,A=S^{m-1}$，知$H_i(B^m,S^{m-1})\cong \widetilde{H}_{i-1}(S^{m-1})$（$\widetilde{H}_i(B^m)=0$）



而只需计算：$\widetilde{H}_k(S^n)$。在长正合列中取$X=B^n,A=S^{n-1}$，于是$X/A=S^n$。于是由长正合列，有$H_i(S^n)\stackrel{\partial}\cong H_{i-1}(S^{n-1})$。如此下降指标，就得到了结论。



3. $x\in\H^m$，$H_i(\H^m,\H^m-x)$：

若$x\notin\text{Bd}\H^m$，则该群在$i=m$时的$i$维局部同调无限循环，其余情况时为零。

若$x\in \text{Bd}\H^m$，则该群为零。

证：前者即为2的直接结果。

对于后者，不妨$x=0$，记上半球$D^m=B^m\cap\H^m$，于是$H_i(\H^m,\H^m-x)\cong H_i(D^m,D^m-0)$

而$D^m-0$能连续变形到上半球面$E^{m-1}_+=S^{m-1}\cap \H^m$。

$H_i(\H^m,\H^m-x)\cong H_i(D^m,D^m-0)\cong H_i(D^m,E^{m-1}_+)$

而两者都是零调的，于是得证。



## 5. de Rham上同调

在第四节的讨论中已经能够注意到外微分算子和边缘算子令人惊异的对偶性，本节的目标是证明de Rham定理。

### 5.1 de Rham 上同调

首先将注意力放到$\mathbb{R}^n$中的开集而非一般的流形。自然地，这个开集上可以定义一个$p-$微分形式。这与流形上的微分形式完全相同，也遵循相同的运算律。记全体$p-$微分形式构成的群为$\Omega^p(U)$。于是外微分算子$d:\Omega^p(U)\rightarrow \Omega^{p+1}(U)$是一个群同态，并且满足性质$d^2=0$.

于是当然可以定义一个上链复形，称为de Rham复形。

**（de Rham复形，de Rham上同调）对于复形$\Omega^0(U)\stackrel{d}\rightarrow\cdots\stackrel{d}\rightarrow \Omega^n(U)$（两端可以扩展为0）：同样地定义闭形式$Z^n(U)=Ker\ d_n$，恰当形式$B^n(U)=Im\ d_{n-1}$，de Rham上同调群$H^n(U)=Z^n(U)/B^n(U)$**

于是类似同调中的情况，两个开集之间的光滑映射$f:U_1\rightarrow U_2$诱导出了拉回映射（群同态）：$\Omega^0(U_2)\rightarrow\Omega^0(U_1): f^*(g)=g\circ f$。然后利用与外微分算子可交换延展到$\Omega^k(U_2)\rightarrow\Omega^k(U_1)$上去。并且可以验证这个同态与外微分算子，外积均相容。这个映射可以进一步诱导出上同调群的同态。

接下来回到主线：流形。同样地，有流形上的全体$p-$微分形式构成群$\Omega^p(M)$，以及对应的de Rham上同调的概念，外积仍然存在，并且形成了分次代数。而链映射也诱导了上同调群的同态。

自然，对于上同调，之前在同调中有关长正合列，相对同调的一切结果都可以平行地搬到此处。

**（加性定理）$\{M_j\}$是可数个流形，且$M=\coprod M_\alpha$，则$\prod H^k_{dR}(M_\alpha)\cong H^k_{dR}(M)$**

证：包含映射$i_\alpha: M_\alpha\rightarrow M$诱导了拉回映射$i_\alpha^*$，于是它们的积$\prod i_\alpha^*$是同构。



接下来详细论述同伦对于上同调群的影响。

**（链同伦）两个上链复形$A^*,B^*$之间的两个链映射$f,g$被称为链同伦的，如果存在一个群同态$s:A^n\rightarrow B^{n-1}$满足$d_B\circ s+s\circ d_A = f-g$（这里$d_A,d_B$是指上链复形中的外微分映射）**

同伦的链映射诱导出上同调群的同构：

$(f^*-g^*)[a]=[f(a)-g(a)]=[d_B\circ s(a)+s\circ d_A(a)]=0$

**（同伦等价）连续映射$f:X\rightarrow Y$称为同伦等价映射，如果存在映射$g:Y\rightarrow X$，使$X\circ Y,Y\circ X$都同伦于对应的恒等映射。称$X,Y$同伦等价。**

**两个同伦的光滑映射$f,g:U\rightarrow V$诱导出了两个相同的上同调群同态$f^*,g^*:H^k(V)\rightarrow H^k(U)$**

证：

只需要说明$f,g$诱导出了链同伦的映射。

设$H:M\times\mathbb{R}\rightarrow N$是描述$f$到$g$的同伦的映射，即$H(x,0)=f(x),H(x,1)=g(x)$，Whitney逼近保证我们可以假定$H$是光滑的。

记$i_t:M\rightarrow M\times\mathbb{R}$将$x$映为$(x,t)$，则$F\circ i_0=f,F\circ i_1=g$

于是只需要说明$i_0,i_1$在上链上诱导出的映射是链同伦的。这样自然有$f^\#=F^\#\circ i_0^\#=F^\#\circ i_1^\#=g^\#$



因此需要说明$M\times\mathbb{R}$上的微分形式是如何定义的：

对于某族坐标卡$\{U_\alpha,\varphi_\alpha\}$，从属的一个单位分拆$\{\rho_\alpha\}$，Urysohn定理保证的一族函数$\{g_\alpha\}$使得$g_\alpha(\text{supp}\ \mathbb{R}ho_\alpha)=1$且$\text{supp}\ g_\alpha\subseteq U_\alpha$，以及投影函数$\pi:M\times\mathbb{R}\rightarrow M$。

那么$\{\pi^{-1}(U_\alpha)\}$是$M\times \mathbb{R}$的开覆盖，并且其上也有一族诱导出的单位分拆$\{\pi^*\mathbb{R}ho_\alpha\}$从属于开覆盖$\{\pi^{-1}(U_\alpha)\}$

下文中所有$\pi^*h$都是指对应的$M\times\mathbb{R}$上的函数。

设$\omega$是$M\times\mathbb{R}$上的（光滑）微分形式，则$\omega=\sum(\pi^*\mathbb{R}ho_\alpha)\cdot\omega$，记和式中的每一项$(\pi^*\mathbb{R}ho_\alpha)\cdot\omega$为$\omega_\alpha$，单位分拆保证了和式是有限的。

于是$\text{supp}\ \omega_\alpha\subseteq\text{supp}\ (\pi^*\mathbb{R}ho_\alpha)\subseteq\pi^{-1}(U_\alpha)$

而$\pi^{-1}(U_\alpha)$有局部坐标$(x^1,\cdots,x^n,t)$（当然前n者是$M$自身的局部坐标），于是在$\pi^{-1}(U_\alpha)$上，$\omega_\alpha$可以被表为$\sum a_Idx^I+\sum b_Jdt\wedge dx^J$

而$a_I,b_J$的支集当然都在$\text{supp}\ (\pi^*\mathbb{R}ho_\alpha)$中，于是可以延拓到整个流形（外部取0）

另一方面：对$g_\alpha$，也有一族对应的函数$\{\pi^*g_\alpha\}$使得其在$\text{supp}\ \pi^*\mathbb{R}ho_\alpha$上恒为1，$\text{supp}\ \pi^*g_\alpha\subseteq \pi^{-1}(U_\alpha)$

于是在$\pi^{-1}(U_\alpha)$上：$\omega_\alpha=(\pi^*g_\alpha)\cdot\omega_\alpha=\sum a_I\pi^*(g_\alpha dx^I)+\sum b_Jdt\wedge \pi^*(g_\alpha dx^J)$，而这里不光是$a_I,b_J$，$g_\alpha dx^I$也可以延拓。（其实就是坐标域内取，外部不要）



现在回来看上链映射$i_0^*,i_1^*$，同样地可以只考虑一个坐标域内的形式。我们取链同伦中的映射$s:\Omega^*(M\times\mathbb{R})\rightarrow\Omega^{*-1}(M)$为：

$s(\omega_\alpha)=\sum(\int_0^1b_J(x,t)dt)g_\alpha dx^J$（$a_I$部分消失），再线性地得出$s(\omega)$

接下来只需验证$d\circ s+s\circ d = i_1^*-i_0^*$，而这只需计算即可。



于是有重要的推论，其在分析中也经常出现：

**（Poincare引理）若$U$是与单点同伦的空间（例如星凸），那么$p>0$时$H^p(U)=0$，$p=0$时$H_p(U)=\mathbb{R}$**

### 5.2 Mayer-Vietoris长正合列

正如同调中的情况（尽管在第四节中我们没有讲这个结果），M-V序列是切除定理的直接推论。不过在de Rham上同调有着更直接的证明。

首先：包含映射给出了如下所诱导出的链映射交换图（$M=U\cup V$）：

$\begin{CD}\Omega^*(U\cap V)@<j^*_U<<\Omega^*(U)\\@Aj_V^*AA@Ai_U^*AA\\\Omega^*(V)@<i_V^*<<\Omega^*(M)\end{CD}$

那么自然地有列$0\longrightarrow\Omega^*(M)\stackrel{i^*=(i_U^*,i_V^*)}\longrightarrow \Omega^*(U)\oplus\Omega^*(V)\stackrel{j^*=j^*_V-j^*_U}\longrightarrow \Omega^*(U\cap V)\longrightarrow0$

可以验证它是一个链复形之间的短正合列：在第四项正合是因为对于$U\cap V$上的任意微分形式$\omega$，把它（以0）延拓到整个流形上，然后限制在$U,V$从而成为$\Omega^*(U),\Omega^*(V)$的元素，然后利用$(U,V)$诱导的一个单位分拆$g_1+g_2=1$，那么考虑$(g_1\omega_V,-g_2\omega_U)$的像即成为$\omega$。

于是利用长正合列的Zig-Zag引理（同样地，使用图追踪）

我们得到了M-V长正合列：

$0\longrightarrow H^0_{dR}(M)\stackrel{i^*}\longrightarrow H^0_{dR}(U)\oplus H^0_{dR}(V)\stackrel{j^*}\longrightarrow H^0_{dR}(U\cap V)\stackrel{d^*}\longrightarrow H^1_{dR}(M)\stackrel{i^*}\longrightarrow\cdots$

### 5.3 奇异上同调

首先，流形上的光滑奇异同调和奇异同调实质上是同构的，这一点在Whitney逼近定理中就已经给予了足够的暗示。

**光滑流形$M$上，链群的包含映射$i:C^{sm}_k(M)\longrightarrow C_k(M)$诱导了同调群$H^{sm}_k(M)\cong H_k(M)$的同构。**

证：Whitney逼近定理保证了奇异单形总是和某个光滑奇异单形是同伦的，因此这样诱导出的一个链映射$C_k(M)\longrightarrow C_k^{sm}(M)$，继而诱导出同调群的同态$H_k(M)\longrightarrow H_k^{sm}(M)$，而这就是$i^*$的逆映射。

因此我们知道了：在同调的层面上，流形的光滑奇异同调和奇异同调本质上是一件事。



通过对奇异链群取对偶，我们能够得到实系数的奇异上链群：$C^k(M,\mathbb{R})=\text{Hom}(C_k(M);\mathbb{R})$

同样地，群同态$A\longrightarrow B$在对偶中诱导了$\text{Hom}(B,\mathbb{R})\longrightarrow\text{Hom}(A,\mathbb{R})$

于是边缘同态诱导出了一个上链群的同态：$\delta:C^k(M,\mathbb{R})\longrightarrow C^{k+1}(M,\mathbb{R})$，从而有上链复形$\cdots\longrightarrow C^k(M,\mathbb{R})\longrightarrow C^{k+1}(M,\mathbb{R})\longrightarrow\cdots$，于是有奇异上同调群$H^k(M,\mathbb{R})=Ker\delta_k/Im\delta_{k-1}$

自然地，利用对偶函子，奇异同调的同伦不变性，长正合列，M-V序列，加性定理等等一系列结论都可以搬运到奇异上同调。（并且我们已经发现它们和de Rham上同调有着一样的形式）



另外，奇异同调群和光滑奇异同调群的同构保证了它们的上同调群也是同构的。

### 5.4 de Rham定理

微分形式和光滑奇异上链群之间有自然的同态：$\Psi:\Omega^k(M)\rightarrow C^k_{sm}(M,\mathbb{R}):\ \ \omega\mapsto(c\mapsto\int_c\omega)$

由于Stokes定理，这个同态是一个链映射$\Omega^*(M)\rightarrow C^*_{sm}(M,\mathbb{R})$，那么自然能诱导出上同调群的同态$\Psi^*:H^k_{dR}(M)\rightarrow H^k(M,\mathbb{R})$

de Rham定理指出：这个同态是同构，从而架起了光滑结构（de Rham上同调）和拓扑结构（奇异上同调）的桥梁。

**（de Rham定理）对于光滑流形$M$，$\Psi^*:H^k_{dR}(M)\rightarrow H^k(M,\mathbb{R}):\ \ [\omega]\mapsto([c]\mapsto \int_c\omega)$**是同构。

流形自然是不好直接处理的，于是在这里采用一个很类似归纳的做法：

引理：对于流形$M$，如果有一个命题$P(U),U\stackrel{open}\subseteq M$满足：

a. $P(U)$对所有与$\mathbb{R}^n$中的某个凸集微分同胚的开集$U$成立

b. (M-V) $P(U),P(V),P(U\cap V)\ true \implies P(U\cup V)\ true$

c. 对于不教的开集族$\{U_\alpha\}$，$P(U_\alpha)$对每个$\alpha$成立$\implies P(\bigcup U_\alpha)$成立。

引理证明：

首先假定$M$和$\mathbb{R}^n$的某个开集微分同胚，来证明$P(M)$成立。不失一般性，可直接令$M$为$\mathbb{R}^n$的某个开集。由于流形上存在可数预紧拓扑基$\{V_n\}$，设它们诱导出一族单位分拆$\{\rho_i\}$

记$f:M\rightarrow \mathbb{R}:\ \  x\mapsto \sum i\rho_i(x)$

由于$f^{-1}[-N,N]\subseteq\cup^N_{i=1} \overline{V_i}$，且$f$连续，紧子集的闭子集是紧的，于是一切闭区间的原像都是紧的。

那么记$A_n=f^{-1}[n,n+1]$是紧的，于是所有$f^{-1}[n-\frac{1}{2},n+\frac{3}{2}]$中的凸开集能够覆盖$A_n$（例如：取开球）。那么紧性要求存在一个有限覆盖，设这个覆盖中这些有限开集的并为$U_n$，那么只有$n_1,n_2$奇偶性相同，$U_{n_1},U_{n_2}$就不相交。

那么a,b条件保证只要$U$是有限个凸开集的并，$P(U)$成立。于是$P(U_n)$成立。

由条件c. $P(\cup U_{2n}),P(\cup U_{2n+1})$成立。

而$(\cup U_{2n})\cap(\cup U_{2n+1})=\cup(U_{2i}\cap U_{2j+1})$，最后一式是无交并。

而$U_{2i}\cap U_{2j+1}$同样是有限个凸开集的并（将组成$U_{2i},U_{2j+1}$的有限开集对应地作交即可）

于是$P(U_{2i}\cap U_{2j+1})\ true$，从而$P((\cup U_{2n})\cap(\cup U_{2n+1}))=P(\cup(U_{2i}\cap U_{2j+1}))\ true$

再由b. 知$P(M)=P(\cup U_n)=P((\cup U_{2n})\cup(\cup U_{2n+1}))\ true$，从而得到证明。



对于一般的流形$M$，考虑覆盖的坐标卡，那么命题对每个坐标域成立。将上文的证明重新运用一次即可，只不过覆盖$A_n$的集合不选取凸开集，而是选取坐标域。（后续证明是一样的，因为我们已经证明了命题对一个坐标域成立）

引理得证。



因此想要证明主定理，只需说明定理满足引理的条件。

de Rham定理的证明：

1. 条件a.

奇异上同调群和de Rham上同调群都具有同伦不变性，于是与$\mathbb{R}^n$中的某个凸集微分同胚的开集$U$和单点集同伦。从而其上同调群在$k>0$时均为0，则此时$\Psi^*$当然是同构。对于$k=0$，计算知$\Psi^*[1]=1$，从而说明同态是同构。

2. 条件b.

两个上同调都有各自的M-V序列，并且$\Psi^*$与它们都有交换性（Stokes定理）

$\begin{CD}H_{dR}^{k-1}(U)\oplus H_{dR}^{k-1}(V)@>{j^*}>>H_{dR}^{k-1}(U\cap V)@>d^*>>H_{dR}^k(M)@>i>>H_{dR}^{k}(U)\oplus H_{dR}^{k}(V)@>{j^*}>>H_{dR}^{k}(U\cap V)\\@V\Psi^*VV@V\Psi^*VV@V\Psi^*VV@V\Psi^*VV@V\Psi^*VV\\H_{}^{k-1}(U,\mathbb{R})\oplus H_{}^{k-1}(V,\mathbb{R})@>{j^*}>>H_{}^{k-1}(U\cap V,\mathbb{R})@>d^*>>H_{}^k(M,\mathbb{R})@>i>>H_{}^{k}(U,\mathbb{R})\oplus H_{}^{k}(V,\mathbb{R})@>{j^*}>>H_{}^{k}(U\cap V,\mathbb{R})\end{CD}$

而第1，2，4，5列的同态都是同构，由5引理立刻得出第3列的同态也是同构。

3. 条件c.

利用加性定理：$\Psi^*:H^k_{dR}(\coprod M_\alpha)\rightarrow H^k(\coprod M_\alpha,\mathbb{R})$同构当且仅当诱导出的$\prod H^k_{dR}(M_\alpha)\rightarrow\prod H^k(M_\alpha,\mathbb{R})$同构，但这正是条件c的前提。



综上我们成功说明了de Rham定理的正确性。



**参考：**

1. 陈省身, 陈维恒. 微分几何讲义
2. W.Rudin. *Principles of Mathematical Analysis*
3. H.L.Royden, P.M.Fitzpatrick. *Real Analysis*
4. Raoul Bott, Loring W.Tu. *Differential Forms in Algebraic Topology* : Graduate Texts in Mathematics, Vol. 82.
5. John M.Lee. *Introduction to smooth manifolds*

5. J.R.Munkres. *代数拓扑基础*
