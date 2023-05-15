# Chapter 7 函数项级数

  本章节主要研究的内容为极限的换序和$$C(X)$$中的一些性质。

##  1. 换序定理

极限过程的可交换性涉及到许多情况，为了统一地处理它们，采用基上极限的语言叙述。

### 1.1 集合的基

给定集合$$X$$，若其子集族$$\mathscr{B}$$满足：

a. $$\phi\notin\mathscr{B}$$   b. $$\forall b_1,b_2\in\mathscr{B}, \exists b_3\in\mathscr{B}$$且$$b_3\subseteq b_1\cap b_2$$

则称为$$X$$的一个基。

例：

a. 给定$$t\in X\subseteq \mathbb{R}$$：$$\mathscr{B}=\{(t-\delta_1,t+\delta_2)\cap X|\delta_1,\delta_2>0\}$$

b. $$X\subseteq\mathbb{R}$$且无上界：$$\mathscr{B}=\{(a,+\infty)\cap X|a\in \mathbb{R}\}$$（这可以看做a.中$$t\rightarrow +\infty$$的情况）

c. $$X$$为$$[a,b]$$上全体带有标记点的分划，对每个$$\delta>0$$：$$\mathscr{B}_\delta=\{P\in X|maxlength(P)<\delta\}$$，取$$\mathscr{B}=\bigcup B_\delta$$（很明显能看出它和Riemann积分的关系）

### 1.2 基上极限

对于实值函数$$f: X\rightarrow \mathbb{R}$$，$$\mathscr{B}$$是$$X$$的一个基。

若：$$\exists a\in\mathbb{R}, s.t. \forall \varepsilon >0, \exists b\in\mathscr{B}$$，只要$$x\in b$$，就有$$|f(x)-a|<\varepsilon$$，则称$$a$$为$$f$$在基$$\mathscr{B}$$上的极限，记作：
$$
\lim_{\mathscr{B}}f(x)=a\ 或\ f(x)\stackrel{\mathscr{B}}{\longrightarrow}a
$$
于是考虑1中的三个例子：

a. $$f$$在$$\mathscr{B}$$上的极限即为：$$\lim_{x\rightarrow t}f(x)$$

b. $$f$$在$$\mathscr{B}$$上的极限即为：$$\lim_{x\rightarrow +\infty}f(x)$$

c. 取函数$$\sigma(P)=\sum f(c_k)\Delta_k$$，那么$$\sigma$$在$$\mathscr{B}$$上的极限即为Riemann积分$$\int_a^b f(x)dx$$

### 1.3 换序定理

这是换序的核心定理，简单说就是一个$$n$$重极限过程可换序可由其中$$n-1$$个极限过程的一致性推出。

**（换序定理）对于$$X$$,$$Y$$上的基$$\mathscr{B}_X,\mathscr{B}_Y$$，它们在$$X\times Y$$上诱导了一组基$$\mathscr{B}_{X\times Y}=\{b_X\times b_Y|b_X\in\mathscr{B}_x, b_Y\in\mathscr{B}_Y\}$$**

**对于$$f:X\times Y\longrightarrow \mathbb{R}$$，若$$f(x,y)\stackrel{\mathscr{B}_X}\rightrightarrows F_1(y)$$**

（即：$$\forall \varepsilon >0, \exists b_X\in\mathscr{B}_X$$，只要$$x\in b_X$$，就有$$|f(x,y)-F_1(y)|<\varepsilon$$对任意$$y\in Y$$成立）

**且：$$f(x,y)\stackrel{\mathscr{B}_Y}\longrightarrow F_2(x)$$，那么：**

**$$\lim_{\mathscr{B}_X}\lim_{\mathscr{B}_Y}f(x,y)=\lim_{\mathscr{B}_Y}\lim_{\mathscr{B}_X}f(x,y)=\lim_{\mathscr{B}_{X\times Y}}f(x,y)$$**

证：

a. $$\lim_{\mathscr{B}_x}F_2(x)$$存在

由于$$f(x,y)\stackrel{\mathscr{B}_X}\rightrightarrows F_1(y)$$：$$\forall \varepsilon >0, \exists b_X\in\mathscr{B}_X,\forall x_1,x_2\in b_X, \forall y\in Y$$:

$$|f(x_1,y)-f(x_2,y)|<\frac{\varepsilon}{3}$$

由于$$f(x,y)\stackrel{\mathscr{B}_Y}\longrightarrow F_2(x)$$：$$\exists b_{Y_1}, b_{Y_2}\in\mathscr{B}_Y, \forall y\in b_Y\subseteq b_{Y_1}\cap b_{Y_2}$$:

$$|f(x_i,y)-F_2(x_i)|<\frac{\varepsilon}{3}\ (i=1,2)$$

于是综合两者，$$|F_2(x_1)-F_2(x_2)|<\varepsilon$$，$$\forall x_1,x_2\in b_X$$，从而由Cauchy准则得证，设这个极限为$$A$$。

b. $$\lim_{\mathscr{B}_Y}F_1(y)=A$$

$$\exists b_X\in\mathscr{B}_X, \forall x\in b_X, y\in Y: |f(x,y)-F_1(y)|<\varepsilon /3$$     ($$f\rightrightarrows F_1$$)

$$\exists b'_X\in\mathscr{B}_X, \forall x\in b'_X: |F_2(x)-A|<\varepsilon /3$$     ($$F_2\rightarrow A$$)

$$\exists \mathscr{B}_X \ni b''_X\subseteq b_X\cap b_{X'}$$，以及某个$$x_0\in b''_X$$，再取$$b_Y\in\mathscr{B}_Y$$，使得$$|F_2(x_0)-f(x_0,y)|<\varepsilon / 3$$   ($$f\rightarrow F_2$$)

综合三者，$$\forall y \in b_Y$$ ：$$|F_1(y)-A|<\varepsilon$$，从而得证。

c. $$\lim_{\mathscr{B}_{X\times Y}}f(x,y)=A$$

这是简单的，各自选取$$X,Y$$的基中的元素，使得$$|f(x,y)-F_1(y)|<\varepsilon/2 \ (\forall y)$$ 且 $$|F_1(y)-A|<\varepsilon/2$$即可。



## 2. 一致收敛

正如前文所述，由换序定理知一个$$n$$重极限过程可换序可由其中$$n-1$$个极限过程的一致性推出（简单归纳），接下来研究函数列的一致收敛性。

**Weierstrass M判别**

**若$$|f_n(x)|\leq M_n$$，且$$\sum M_n$$收敛，则$$\sum f_n$$的部分和构成的函数列一致收敛。**

（考虑Cauchy判别即可）

**A-D判别**

**Abel: a. $$\sum u_n(x)$$一致收敛 b. 对于每个$$x$$，$$v_n(x)$$单调，且一致有界**

**Dirichlet: a. $$\sum u_n(x)$$的部分和一致有界 b. 对于每个$$x$$，$$v_n(x)$$关于$$n$$单调，且$$v_n(x)\rightrightarrows 0$$**

**则$$\sum u_n(x)v_n(x)$$一致收敛**

证明同数列的A-D判别法



前文的换序定理给出了一个直接推论：

**连续函数列$$f_n\rightrightarrows f$$，则$$f$$也连续。**

自然想问逆命题何时成立，紧集上是一个情形。

**（Dini引理）$$K$$是紧拓扑空间，$$\{f_n\}$$是$$K$$上的连续实值函数序列，并且逐点收敛到连续函数$$f$$，并且满足$$f_n$$关于$$n$$逐点单调减，则这个收敛是一致的。**

证：记$$g_n=f_n-f$$，$$g_n(x)$$连续，$$g_n$$关于$$n$$逐点单调减，且$$g_n$$逐点收敛到$$0$$，需证其一致收敛到$$0$$

记$$K_n=\{x\in K|g_n(x)\geq\varepsilon\}$$，那么$$O_n$$闭，从而紧，而$$g_n$$逐点收敛到$$0$$，于是对每个$$x$$能找到充分大的$$N$$使$$n\geq N$$则$$x\notin K_n$$，另一方面有降链$$K_1\supseteq K_2\supseteq \cdots$$，因而$$\bigcap K_n$$是空的。

但是紧空间中满足有限交性质的闭集族的交不空，于是族$$\{K_1,\cdots\}$$不满足有限交性质，从而存在$$K_N=\phi$$，于是$$\forall n>N, g_n(x)<\varepsilon$$，即证。



## 3. 换序定理应用

### 3.1 积分-极限

这个问题在实分析中将会被更加细致地研究，被称之为积分号下取极限，这里只利用换序定理给出一个很弱的结论。

**$$f(x,y): [a,b]\times Y\rightarrow \mathbb{R}$$，且对每个$$y$$，$$f(x,y)$$关于$$x$$在$$[a,b]$$上Riemann可积，对于$$Y$$的基$$\mathscr{B}_{Y}$$，$$f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows F(x)$$**

**则：$$F(x)$$在$$[a,b]$$上Riemann可积，且$$\int_a^b F(X)dx = \lim_{\mathscr{B}_Y}\int_a^b f(x,y)dx$$**

证：在换序定理中，令$$X$$和$$\mathscr{B}_X$$如同1.1.c中那样定义，取换序定理中的函数为$$\sigma(P,f(x,y))$$为Riemann和，于是只需验证$$\sigma(P,f(x,y))\stackrel{\mathscr{B}_Y}\rightrightarrows\sigma(P,F(x))$$

由于：$$f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows F(x)$$

$$\exists b_Y\in\mathscr{B}_Y, \forall y\in b_Y, \forall x\in [a,b], |f(x,y)-F(x)|<\frac{\varepsilon}{b-a}$$

从而：$$|\sigma(P,f(x,y))-\sigma(P,F(x))|\leq \sum |F(c_i)-f(c_i,y)|\Delta_i \leq \frac{\varepsilon}{b-a}\cdot (b-a)=\varepsilon$$，于是得证。

另外可以看出这个证明可以推广到Riemann-Stieltjes积分。



来看一个稍微强一些的定理：

**较弱的Lebesgue控制收敛定理**

**$$g$$与$$\{f_n\}$$定义在$$(0,+\infty)$$上，并且它们在每个内闭区间上Riemann可积，且$$|f_n|\leq g$$，$$\int_0^{+\infty}g(x)dx<+\infty$$**

**且$$\{f_n\}$$在每个$$(0,+\infty)$$的紧子集上一致收敛到$$f$$，那么：**

**$$\lim _{n\rightarrow+\infty}\int_0^{+\infty}f_n(x)dx=\int_0^{+\infty}f(x)dx$$**

证：这事实上是反常积分-极限换序，为了方便叙述，我们不妨将$$(0,+\infty)$$拆成两个半开半闭区间，先用基的语言对一个半开半闭区间（不妨$$[1,+\infty)$$）叙述结论，然后再将两段结果综合即证。

对于$$f(x,y):[1,+\infty)\times Y\rightarrow \mathbb{R}$$

对任何$$y$$，$$f(x,y)$$关于$$x$$在任何$$[1,+\infty)$$内闭区间上Riemann可积，且控制函数保证了反常积分$$\int_1^{+\infty}f(x,y)dx$$收敛。

现取$$Y=\mathbb{Z}_{> 0}$$，基$$\mathscr{B}_Y$$如同1.1.b那样选取，这样就将原定理转换为基的语言。

记：$$I(y,u)=\int_1^u f(x,y)dx$$ ，其中$$u\in S \stackrel{\triangle}=[1,+\infty)$$，$$S$$中基$$\mathscr{B}_S$$如同1.1.b那样选取。

则：控制函数保证了$$I(y,u)$$在基$$\mathscr{B}_S$$上一致地收敛到$$I(y,+\infty)$$ 

从而由换序定理，只需验证$$I(y,u)\stackrel{\mathscr{B}_y}\rightarrow\int_1^b f(x)dx$$，但这是常义积分-极限换序的结果，于是定理得证。



### 3.2 求导-极限

****

**$$f(x,y): [a,b]\times Y\rightarrow \mathbb{R}$$，且对每个$$y$$，$$f(x,y)$$在$$[a,b]$$连续，在$$(a,b)$$可导，且$$\exists x_0\in [a,b]$$使得$$\lim_{\mathscr{B}_Y}f(x_0,y)$$存在。**

**且$$\frac{\partial}{\partial x}f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows \varphi(x)$$**

**则：存在$$F(x):[a,b]\rightarrow\mathbb{R}$$满足$$f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows F(x)$$，且$$F'(x)=\varphi(x)$$**

证：思路是在换序定理中取函数$$d(h,y)=\frac{f(x+h,y)-f(x,y)}{h}$$，为证一致收敛性，需先证明$$f(x,y)$$一致收敛。

由于在点$$x_0$$，$$\lim_{\mathscr{B}_Y}f(x_0,y)$$存在，故$$\exists b_Y\in\mathscr{B}_Y, \forall y_1,y_2\in b_y, \ |f(x_0,y_1)-f(x_0,y_2)|<\varepsilon/2$$

而$$\frac{\partial}{\partial x}f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows \varphi(x)$$，于是$$\exists b'_Y\in\mathscr{B}_Y, \forall y_1,y_2\in b'_Y, \forall x,\ \ \  |\frac{\partial}{\partial x}f(x,y_1)-\frac{\partial}{\partial x}f(x,y_2)|<\frac{\varepsilon}{2(b-a)}$$

那么对于$$y_1,y_2\in b_{Y0}\subseteq b_Y\cap b'_Y$$

$$|f(x,y_1)-f(x,y_2)|\leq|[f(x,y_1)-f(x.y_2)]-[f(x_0,y_1)-f(x_0,y_2)]|+|f(x_0,y_1)-f(x_0,y_2)|\\=|\frac{\partial}{\partial x}(f(x,y_1)-f(x,y_2)|_{x=c\in[x.x_0]}|\cdot|x-x_0|+|f(x_0,y_1)-f(x_0,y_2)|\\<\varepsilon$$

于是可设$$f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows F(x)$$

接下来运用换序定理，取函数$$d(h,y)=\frac{f(x+h,y)-f(x,y)}{h}$$，$$d:H\times Y\rightarrow \mathbb{R}$$，其中$$H=\{h\in\mathbb{R}|x+h\in(a,b)\}$$，取其基为$$\mathscr{B}_H={(-\delta,\delta)\cap H|\delta>0}$$

那么自然$$d(h,y)\stackrel{\mathscr{B}_H}\rightarrow \frac{\partial}{\partial x}f(x,y)$$，只需$$d(h,y)\stackrel{\mathscr{B}_Y}\rightrightarrows \frac{F(x+h)-F(x)}{h}$$，但这由$$f(x,y)\stackrel{\mathscr{B}_Y}\rightrightarrows F(x)$$保证，从而得证。



### 3.3 重积分

**$$f(x,y): D=[a,b]\times[c,d]\rightarrow\mathbb{R}$$ 连续，则$$\int_a^b \int_c^d f(x,y)dydx=\int_c^d\int_a^b=f(x,y)dxdy$$**

证：同3.1一样定义Riemann和函数$$\sigma_x(P,f(x,y)),\sigma_y(Q,f(x,y))$$

然后在换序定理中取$$X,Y$$分别为$$[a,b],[c,d]$$的带标记点的分划构成的集合，基的取法如同1.1.c。取换序定理中的函数为：$$\sigma_x(P,\sigma_y(Q,f(x,y)))$$，于是由换序定理，只需验证：

$$\sigma_x(P,\sigma_y(Q,f(x,y)))\stackrel{\mathscr{B}_Y}\rightrightarrows\sigma_x(P,\int_c^df(x,y)dy)$$

但$$f(x.y)$$一致连续，于是存在$$\delta$$，只要$$|(x_1,y_1)-(x_2,y_2)|<\delta$$，就有$$|f(x_1,y_1)-f(x_2,y_2)|<\varepsilon$$

故可取$$b_Y\in\mathscr{B}_Y$$，使得$$\forall Q\in b_Y, maxlength(Q)<\delta$$

从而，$$\forall Q\in b_Y, P\in b_X$$

$$|\sigma_x(P,\sigma_y(Q,f(x,y)))-\sigma_x(P,\int_c^df(x,y)dy)|\\=|\sigma_x(P,\sigma_y(Q,f(x,y)-\int_c^df(x.y)dy))|\leq(b-a)(d-c)\varepsilon$$

于是得证。

## 4. $$C(X)$$中函数列的收敛子列: Arzela-Ascoli定理

仿照$$\mathbb{R}$$中情况，希望知道实值函数列的收敛子列乃至一致收敛子列的性质，而后者与$$C(X)$$中子集的紧性有关。

### 4.1 $$C(X)$$、上确范数

首先明确研究对象：对于度量空间$$X$$，记$$C(X)$$为全体$$X$$上连续实值函数构成的集合，若需要区分实值函数和复值函数时分别用$$C^{\mathbb{R}}(X)$$和$$C^{\mathbb{C}}(X)$$表示，否则默认为实值函数。

$$C(X)$$首先有着明显的线性结构，同时可以赋予很多种度量结构。本章中赋予的是上确范数从而形成度量空间，这里上确范数是指$$||f||=\sup_{x\in X} |f(x)|$$，从而诱导了度量$$d(f,g)\stackrel{\triangle}=||f-g||$$

当$$X$$是紧度量空间时，上述定义良好，并且$$(C(X),d)$$构成完备空间。



**$$(C(X),d)$$构成完备空间**

证：设$$\{f_n\}$$ 是$$C(X)$$中Cauchy列，于是由一致收敛的Cauchy准则，$$f_n\rightrightarrows f$$ ，那么$$f$$连续，从而得证。



研究上确范数诱导的度量的原因是$$C(X)$$中序列$${f_n}$$在度量$$d$$意义下收敛于$$f\iff$$$$f_n$$在$$X$$上一致收敛于$$f$$。

同时$$C(X)$$的闭子集称为一致闭的，$$C(X)$$的子集的闭包称为一致闭包。



### 4.2 Helly选择定理

首先从一个特例开始，这个特例的证明使用的对角线法将会被反复使用。

**$$\{f_n\}$$在可数集$$E$$上逐点有界，则其有子列$$\{f_{n_k}\}$$在$$E$$上逐点收敛**

证：设$$\{x_i\}$$为$$E$$的一个列举，由于$$\{f_n(x_1)\}_{n=1}^{+\infty}$$有界，于是有子列收敛，设为$$\{f_{1,k}(x_1)\}_{k=1}^{+\infty}$$

那么在函数列$$S_1:f_{1,1},f_{1,2},\cdots$$中考虑数列$$f_{1,1}(x_2),f_{1,2}(x_2),f_{1,3}(x_3),\cdots$$，也能找到一个子列收敛，设它们所对应的函数列为：$$S_2:f_{2,1},f_{2,2}\cdots$$ ，这样归纳地构造。

那么$$S_n$$是$$S_{n-1}$$的子列，且$$\{f_{n,k}(x_n)\}_{k=1}^{+\infty}$$收敛，并且保持先后顺序。

于是$$f_{1,1},f_{2,2},f_{3,3}\cdots$$即为满足要求的函数列。



**（Helly选择定理）$$\{f_n\}$$是$$\mathbb{R}$$上单调增函数的序列，且$$\forall x,n: \ f_n(x)\in[0,1]$$，则：$$\{f_n\}$$有一个逐点收敛的子列。**

证：由前述结论，有子列$$\{f_{n_i}\}$$在有理数点收敛，设收敛值为$$f(r)$$，那么$$f$$是单调增的。对任意$$x$$，记$$f(x)=\sup_{\mathbb{Q}\ni r\leq x}f(x)$$，从而这个$$f$$是良定义且单调增的。

于是若$$f$$在点$$x$$处连续，可选择$$r\leq x\leq s, \ r,s\in\mathbb{Q}$$，使$$f(r)\in[f(x)-\varepsilon,f(x)],f(s)\in[f(x),f(x)+\varepsilon]$$

另外，对于充分大的$$i$$，$$|f_{n_i}(r)-f(r)|\leq \varepsilon ,|f_{n_i}(s)-f(s)|\leq \varepsilon $$，于是$$f_{n_i}(r)\in[f(x)-2\varepsilon,f(x)+\varepsilon]$$，对于$$s$$对称同理。

从而$$|f_{n_i}(x)-f(x)|\leq 2\varepsilon$$，故$$f_{n_i}$$在点$$x$$逐点收敛至$$f$$

而单调有界函数的不连续点至多可数，故再次运用前述结论，在$$\{f_{n_i}\}$$继续选出子列在不连续点集上逐点收敛，从而在$$\mathbb{R}$$上逐点收敛，得证。



### 4.3 等度连续，Arzela-Ascoli定理

度量空间$$X$$上实值函数族$$\mathscr{F}$$在$$x$$点等度连续，若$$\forall \varepsilon>0, \exists\delta>0 , s.t. \forall f\in \mathscr{F}$$，只要$$d(x,x')<\delta$$，就有$$|f(x)-f(x')|<\varepsilon$$.

若$$\mathscr{F}$$在$$X$$中每一点都等度连续，则称$$\mathscr{F}$$在$$X$$上等度连续。



与4.2类似地有：

**（Arzela-Ascoli引理）X为可分度量空间，$$\{f_n\}$$为$$C(X)$$中逐点有界且等度连续的函数列，则$$\{f_n\}$$有一子列逐点收敛到$$X$$上的实值函数。**

证：对于$$X$$的可数稠密子集$$D$$，由4.2中结论，存在子列$$\{f_{n_i}\}$$在$$D$$上逐点收敛到$$f$$，不妨记这个子列为$$\{f_n\}$$.

对于每个$$x_0\in X$$，存在$$\delta$$使得$$\forall x \ \ s.t. d(x_0,x)<\delta, |f_n(x_0)-f_n(x)|<\varepsilon/3$$对所有指标$$n$$满足。而$$D$$稠密，于是$$\exists d\in D, d(x_0,d)<\delta$$。同时选择充分大的$$n,m$$使$$|f_n(d)-f_m(d)|<\varepsilon/3$$

于是$$|f_n(x_0)-f_m(x_0)|<\varepsilon$$，故逐点收敛，得证。



**紧度量空间$$X$$上$$\{f_n\}\subseteq C(X)$$若逐点收敛，则：$$\{f_n\}$$一致收敛$$\iff$$$$\{f_n\}$$在$$X$$上等度连续**

证：（$$\implies$$) 存在$$N$$使得$$n>N$$则$$||f_n-f_N||<\varepsilon$$，而紧集上连续函数一致连续，于是存在$$\delta$$，只要$$d(x,y)<\delta$$且$$i=1,\cdots,N$$，就有$$|f_i(x)-f_i(y)|<\varepsilon$$.

若$$n>N$$ : $$|f_n(x)-f_n(y)|\leq|f_n(x)-f_N(x)|+|f_N(x)-f_N(y)|+|f_N(y)-f_n(y)|<3\varepsilon$$

于是综合两者就得到等度连续。

（$$\Longleftarrow$$）紧集上等度连续则一致等度连续，于是$$\exists \delta>0\ s.t. \ \forall n\ \forall d(u,v)<\delta,$$ 有$$|f_n(u)-f_n(v)|<\varepsilon$$

紧度量空间是全有界的，从而能被有限$$\delta$$-网覆盖，设为$$B(x_i,\delta)$$

则对于每个$$i$$，$$\{f_n(x_i)\}$$是Cauchy的，于是充分大的$$n,m$$，有$$|f_n(x_i)-f_m(x_i)|<\varepsilon$$。

那么对每个$$x$$，$$|f_n(x)-f_m(x)|\leq|f_n(x)-f_n(x_i)|+|f_n(x_i)-f_m(x_i)|+|f_m(x_i)-f_m(x)|<3\varepsilon$$

于是它一致收敛。



**紧度量空间$$X$$上$$\{f_n\}\subseteq C(X)$$逐点有界且等度连续$$\implies\{f_n\}$$一致有界**

证：紧集上等度连续则一致等度连续，于是$$\exists \delta>0\ s.t. \ \forall n\ \forall d(u,v)<\delta,$$ 有$$|f_n(u)-f_n(v)|<\varepsilon$$

紧度量空间是全有界的，从而能被有限$$\delta$$-网覆盖，设为$$B(x_i,\delta)$$，不妨$$|d(x,x_i)|<\delta$$，于是取$$|f_n(x)|\leq M+\varepsilon$$



综合4.2的第一个命题（对角线）；A-A引理；紧度量空间上逐点收敛时一致收敛和等度连续的等价性；以及有界性的等价命题 可以得到：

**（Arzela-Ascoli定理）$$X$$是紧度量空间，$$\{f_n\}$$是$$X$$上一致有界，等度连续的实值函数，于是$$\{f_n\}$$有子列一致收敛到某个$$X$$上连续函数，条件改为逐点有界且等度连续仍然成立。**



同时这个定理的逆定理能帮助判断$$C(X)$$中子集的紧性。

**$$X$$是紧度量空间，$$\mathscr{F}\subseteq C(X)$$，则：$$\mathscr{F}$$紧$$\iff\mathscr{F}$$闭，一致有界且等度连续**

证：（$$\Longleftarrow$$）设$$\{f_n\}$$是$$\mathscr{F}$$中序列，则由Arzela-Ascoli定理，存在子列收敛到$$C(X)$$，而$$\mathscr{F}$$闭，从而这个子列也收敛到$$\mathscr{F}$$。于是$$\mathscr{F}$$序列紧，从而紧。

（$$\implies$$) 设$$\mathscr{F}$$紧，则$$\mathscr{F}$$完备，从而闭。$$\mathscr{F}$$全有界，从而一致有界。

若$$\mathscr{F}$$在点$$x\in X$$处不等度连续，则$$\exists \varepsilon>0 \ s.t.\ \forall n, \exists f_n\in \mathscr{F},\ x_n\in X$$，使得$$d(x_n,x)<\frac{1}{n}$$但$$|f_n(x_n)-f_n(x)|\geq\varepsilon$$

但是$$\mathscr{F}$$紧从而序列紧，于是上述定义的$$\{f_n\}$$存在子列$$\{f_{n_k}\}$$一致收敛到$$f\in C(X)$$

于是对于充分大$$k\geq K$$，$$||f-f_{n_k}||< \varepsilon/3$$

即：$$|f(x)-f_{n_k}(x)|< \varepsilon/3$$

$$|f(x_{n_k})-f_{n_k}(x_{n_k})|< \varepsilon/3$$

但是$$|f_{n_k}(x_{n_k})-f_{n_k}(x)|\geq\varepsilon$$且$$d(x_{n_k},x)<1/n_k$$

从而$$|f(x)-f(x_{n_k})|>\varepsilon/3$$但$$d(x_{n_k},x)<\frac{1}{n_k}$$，与$$f$$连续性矛盾，得证。



## 5. Weierstrass逼近、Stone-Weierstrass定理

### 5.1 Dirac函数列：Weierstrass逼近、Fejer定理 

Dirac函数列（也称Delta函数列）指一族非负实值连续函数$$\varphi_n$$，满足：

a. 对于每个$$n$$，$$\int_{\mathbb{R}^m}\varphi_n(x)dx=1$$  

b. 对于每个$$\delta>0$$, $$\lim_{n\to+\infty}\int_{|x|>\delta}\varphi_n(x)dx=0$$

**（Dirac列卷积逼近）若$$f$$是$$\mathbb{R}^m$$上连续有界的函数，则$$\varphi_n * f$$在$$\mathbb{R}^m$$的每个紧子集上一致收敛到$$f$$**

证：设紧集$$\Omega\subseteq\mathbb{R}^m$$，对于$$x\in\Omega$$：
$$
|f(x)-(f*\varphi_n)(x)|\\=|\int_{\mathbb{R}^m}[f(x)-f(x-t)]\varphi_n(t)dt|\\
\leq|\int_{|t|\leq\delta}[f(x)-f(x-t)]\varphi_n(t)dt|+|\int_{|t|\geq\delta}[f(x)-f(x-t)]\varphi_n(t)dt|
$$
对于第一项，由于$$f$$连续，且$$\Omega$$紧从而有界，于是可以取充分小$$\delta$$使得对每个$$x\in\Omega$$，$$|f(x)-f(x-t)|<\varepsilon/2$$，于是第一项$$\leq \frac{\varepsilon}{2}\int_{|t|\leq\delta}\varphi_n(t)dx\leq\varepsilon/2$$

对于第二项，$$|f(x)-f(x-t)|$$一致有界，于是可取充分大$$n$$，从而使第二项小于$$\varepsilon/2$$

于是完成了证明。



那么Weierstrass逼近定理就几乎完成了。

**（Weierstrass逼近定理，$$\mathbb{R}^1$$版本）定义在 $$\mathbb{R}^1$$中紧集上的连续函数可以被多项式一致逼近**

证：不妨$$\Omega\subseteq[-\frac{1}{2},\frac{1}{2}]$$，取Dirac函数列为：$$\varphi_n(x)=\left\{ \begin{aligned} \frac{1}{I_n}(1-x^2)^n \quad |x|\leq1\\ 0 \quad otherwise\\ \end{aligned} \right.\ \ \ (Landau) $$

其中归一化系数$$I_n=\int_{-1}^{1}(1-x^2)^ndx$$，可以验证它的确是一个Dirac函数列。

将$$f$$连续延拓到整个$$\mathbb{R}$$上，由Tietze延拓，可以使$$f$$有界（当然$$\mathbb{R}^1$$的情况下完全不用考虑Tietze延拓）

那么$$f*\varphi_n$$在紧集$$[-\frac{1}{2},\frac{1}{2}]$$上一致收敛到$$f$$上，而且$$f*\varphi_n$$事实上是常义积分（充分大后则为0），于是可知每个$$f*\varphi_n$$都是多项式，从而得证。



**（Weierstrass逼近定理，$$\mathbb{R}^m$$版本）定义在 $$\mathbb{R}^m$$中紧集上的连续函数可以被多项式一致逼近**

证：同样，不妨$$\Omega\subseteq[-\frac{1}{2},\frac{1}{2}]^m$$，取Dirac函数列为$$\varphi_n(x)=\left\{ \begin{aligned} \frac{1}{I_n}\prod^m_{i=1}(1-x_i^2)^n \quad |x|\leq1\\ 0 \quad otherwise\\ \end{aligned} \right.\ \ \ (Landau) $$

接下来证明同前，值得注意的是这里Tietze延拓发挥了作用。



同样，Fourier分析中重要的定理：Fejer定理也可以被如此证明。

这里的Dirac函数列被定义为：一族非负实值连续周期函数$$\varphi_n$$，满足：

a. 对于每个$$n$$，$$\frac{1}{2\pi}\int_{-\pi}^{\pi}\varphi_n(x)dx=1$$  

b. 对于每个$$\delta>0$$, $$\lim_{n\to+\infty}\int_{\delta\leq|t|\leq\pi}\varphi_n(x)dx=0$$

c. 周期$$T=2\pi$$

那么有类似的卷积逼近定理：

**（Dirac列卷积逼近，三角版本）若$$f$$是$$\mathbb{R}$$上连续复值函数，且有周期$$2\pi$$，则$$\varphi_n * f$$在$$\mathbb{R}$$上一致收敛到$$f$$**

（这里的卷积指：$$f*g(x)\stackrel{\triangle}= \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x-t)g(t)dt$$）

证：设紧集$$\Omega\subseteq\mathbb{R}^m$$，对于$$x\in\Omega$$：
$$
|f(x)-(f*\varphi_n)(x)|\\
=\frac{1}{2\pi}|\int_{-\pi}^{\pi}[f(x)-f(x-t)]\varphi_n(t)dt|\\
\leq\frac{1}{2\pi}|\int_{|t|\leq\delta}[f(x)-f(x-t)]\varphi_n(t)dt|+|\int_{\delta\leq|t|\leq\pi}[f(x)-f(x-t)]\varphi_n(t)dt|
$$
对于第一项，由于$$f$$连续，从而在$$[-\pi,\pi]$$上一致连续，又有周期性，于是可以取充分小$$\delta$$使得对每个$$x\in\Omega$$，$$|f(x)-f(x-t)|<\varepsilon/2$$，于是第一项$$\leq \frac{1}{2\pi}\cdot\frac{\varepsilon}{2}\int_{|t|\leq\delta}\varphi_n(t)dx\leq\varepsilon/2$$

对于第二项，$$|f(x)-f(x-t)|$$一致有界，于是可取充分大$$n$$，从而使第二项小于$$\varepsilon/2$$

于是完成了证明。



对于$$\mathbb{R}$$上连续复值函数$$f$$，且有周期$$2\pi$$，记：

$$D_n(x)=\begin{aligned}\sum_{k=-n}^{n} e^{ikx}\end{aligned}$$$$=1+2\begin{aligned}\sum_{k=1}^n \cos kx\end{aligned}=\frac{\sin\frac{2n+1}{2}x}{\sin\frac{x}{2}}(x\in2\pi\mathbb{Z}时延拓为2n+1)$$

$$K_m(x)=\frac{1}{m}\begin{aligned}\sum_{n=0}^{m-1} D_n(x)\end{aligned}$$$$=\begin{aligned}\frac{1}{m{\sin\frac{x}{2}}}\sum_{n=0}^{m-1}{\sin\frac{2n+1}{2}x}=\frac{1-\cos mx}{2m{\sin^2\frac{x}{2}}}=\frac{1-\cos mx}{m(1-\cos x)} \end{aligned}(x\in2\pi\mathbb{Z}时延拓为m) $$

$$S_n(x)=\begin{aligned}\sum_{k=-n}^n c_k e^{ikx}\end{aligned}$$， 其中$$\begin{aligned}c_k=\frac{1}{2\pi}\int_{-\pi}^{\pi}f(t)e^{-ikt}dt\end{aligned}$$

可以验证$$K_m(x)$$是一组Dirac函数列，于是$$K_m*f$$在$$\mathbb{R}$$上一致收敛到$$f$$.

而$$(D_n*f)(x)=\begin{aligned}\sum_{k=-n}^{k=n} \frac{1}{2\pi}\int_{-\pi}^{\pi}f(t)e^{ik(x-t)}dt=\sum_{k=-n}^nc_ke^{ikx}=S_n(x)\end{aligned}$$，同理$$(K_n*f)(x)=\begin{aligned}\frac{1}{n}\sum_{i=0}^{n-1}S_n(x)\end{aligned}$$

那么就得到了：**（Fejer定理）$$\begin{aligned}\frac{1}{n}\sum_{i=0}^{n-1}S_n(x)\end{aligned}\rightrightarrows f(x)$$**

同时作为推论：$$\mathbb{R}$$上连续复值函数$$f$$，且有周期$$2\pi$$，能被三角多项式一致逼近。



### 5.2 Stone-Weierstrass定理

现在回来继续研究$$C(X)$$中的逼近，5.1的定理告诉我们多项式集合是一个可行的逼近集合，自然想考虑它的推广，这正是Stone推广的Weierstrass定理的内容。

考虑最一般的情况：$$X$$是紧Hausdorff空间，$$C(X)$$意义同前。



**（引理1）$$X$$至少两个元素，$$H\subseteq C(X)$$，且：**

**$$a. \forall u,v\in H, \ \max\{u,v\},\ \min\{u,v\}\in H$$**

**$$b. \forall x_1\neq x_2\in X,\ c_1,c_2\in\mathbb{R},\ \ \exists u \in H: \ s.t. u(x_1)=c_1,\ u(x_2)=c_2$$**

**则：$$H$$在$$C(X)$$中稠密**

证：设$$f\in C(X)$$，固定某个$$x\in X$$，则对每个$$y\neq x$$，$$\exists u_y\in H, \ u_y(x)=f(x),\ u_y(y)=f(y)$$

记$$O_y=\{x'|f(x')-u_y(x')<\varepsilon\}$$，那么这是一个包含$$x,y$$的开集，从而$$X=\bigcup_{y\neq x} O_y$$

于是存在有限开覆盖，设为$$O_{y_1},\cdots O_{y_r}$$

令$$v_x=\max\{u_{y_1},\cdots u_{y_r}\}\in H$$，那么$$v_x(x)=f(x)$$且$$\forall x'\in X,\ f(x)-f(x')<\varepsilon$$

现在让$$x$$变动，同样地，记$$P_x=\{x'|f(x')-v_x(x')>-\varepsilon\}$$

同理，存在有限开覆盖，设为$$P_{x_1},\cdots P_{x_s}$$

令$$v=\min\{v_{y_1},\cdots v_{y_s}\}\in H$$，那么$$||f-v||<\varepsilon$$，得证。



下面阐述几个定义：

a. $$H\subseteq C(X)$$，若$$\forall x_1\neq x_2\in X, \exists h \in H , h(x_1)\neq h(x_2)$$，则称$$H$$是分离的。

b. 若$$\forall f,g \in H, \max\{f,g\}, \min\{f,g\}\in H$$，则称$$H$$是一个格。

（$$C(X)$$的线性子空间是一个格$$\iff$$ 若$$h\in H$$则$$|h|\in H$$）

c. $$C(X)$$的线性子空间称为一个子代数，若它在乘法下封闭。



**（引理2）若$$H$$是$$C(X)$$一个分离的线性子空间，并且包含常值函数，且是一个格，则$$H$$在$$C(X)$$中稠密。**

证：$$|X|=1$$时平凡，否则应用引理1，只需验证b条件。

由于$$H$$分离，$$\exists h, h(x_1)\neq h(x_2)

则$$\left\{ \begin{aligned} \lambda h(x_1)+\mu=c_1\\ \lambda h(x_2)+\mu=c_2\\ \end{aligned} \right.$$有解，从而$$\lambda h+\mu$$即满足b的要求。



于是综合几个引理：

**（Stone-Weierstrass定理，实版本，条件1）$$C(X)$$每个包含常值函数的分离子代数在$$C(X)$$中稠密。**

证：设这个子代数为$$H$$，那么它的闭包$$\bar{H}$$也是一个包含常值函数的子代数（只需验证子代数，而有界函数的一致收敛保持乘积，故的确是子代数）

因此只需证明$$\bar{H}$$是一个格，然后运用引理2即证。

由于存在一列多项式$$\{p_n\}$$在$$[-1,1]$$上一致地收敛到$$|x|$$，那么$$\{p_n(\frac{f(x)}{||f(x)||})\}\rightrightarrows \frac{|f(x)|}{||f(x)||}$$在$$X$$上。

于是$$\{||f(x)||\cdot p_n(\frac{f(x)}{||f(x)||})\}\rightrightarrows |f(x)|$$，但前者的每一项都是$$\bar{H}$$中元素，于是若$$f(x)\in H$$，$$|f(x)|\in H$$

从而说明$$H$$是格，得证。



这个定理条件还存在变体。

**（Stone-Weierstrass定理，实版本，条件2）$$C(X)$$每个不在$$X$$中点消失的分离子代数在$$C(X)$$中稠密。**

证：我们说明这样的子代数$$H$$满足引理1.

首先同理条件1中的证明知$$H$$是格，只需验证b.

由于$$H$$分离且在每点都不消失，则$$\exists g,h,k\in H,\ s.t. \ g(x_1)\neq g(x_2), h(x_1)\neq 0 ,k(x_2)\neq0$$

取$$u(x)=[g(x)-g(x_1)]k(x),\ \ v(x)=[g(x)-g(x_2)]h(x)$$

那么$$f(x)=c_1v(x)/v(x_1)+c_2u(x)/u(x_2)$$满足要求。



自然的想法是这个结论能否推广到复值函数，然而不加强一些条件是不行的。

下文中$$C(X)$$指$$C^{\mathbb{C}}(X)$$

**（Stone-Weierstrass定理，复版本反例，条件1&2）$$C(X)$$每个不在$$X$$中点消失的且包含常值函数的分离子代数在$$C(X)$$中可能不稠密。**

设$$X$$为复平面上单位圆，$$H$$为全体形如$$f(e^{i\theta})=\begin{aligned}\sum_{n=0}^{N} c_ne^{in\theta} \end{aligned}$$的函数，它满足条件1和2，

于是$$\forall h\in H,\ \begin{aligned}\int_0^{2\pi}h(e^{i\theta})e^{i\theta}d\theta=0\end{aligned}$$，从而这对于闭包$$\bar{H}$$中每个元素都成立，但是考虑$$g(e^{i\theta})=e^{-i\theta}$$，$$\begin{aligned}\int_0^{2\pi}g(e^{i\theta})e^{i\theta}d\theta=2\pi\end{aligned}$$，于是$$g\notin \bar{H}$$，从而$$H$$在$$C(X)$$中不稠密。



然而加上自共轭条件后定理就可以推广了：

**（Stone-Weierstrass定理，复版本，条件1或2）$$C(X)$$每个满足条件1或2且自共轭的子集都在$$C(X)$$中稠密。**

证：

条件1：记$$H_0$$为$$H$$中全体实值函数，那么$$H_0$$在$$C^{\mathbb{R}}(X)$$中满足条件1：$$f\in H$$则$$\Re(f),\Im(f)\in H_0$$（考虑$$(f+\bar{f})/2$$等即可），那么分离性由$$H$$的分离性即可推出（复数不同则实部虚部至少有一不同）

从而$$H_0$$在$$C^{\mathbb{R}}(X)$$中稠密，于是$$H=H_0+i\cdot H_0$$自然在$$C(X)$$中稠密。

条件2的情况是同理的。





参考：

W.Rudin. Principles of Mathematical Analysis

H.L.Royden, P.M.Fitzpatrick Real Analysis

GTM192 Elements of Functional Analysis