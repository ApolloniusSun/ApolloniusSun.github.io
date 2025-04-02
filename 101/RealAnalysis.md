接下来内容假定9～12章的基础点集拓扑是熟知的。

## 2. Lebesgue测度

### 2.1 Lebesgue外测度

对于每个实数集合$A$，定义一个外测度函数$m^*(A)=\inf\sum l(I_k)$，其中$\cup I_k$是覆盖$A$的可数开区间。

性质：

0. 空集外测度为$0$

1. 单调：$A\subseteq B\implies m^*(A)\leq m^*(B)$：因为后者的可数开区间覆盖一定能覆盖前者。
1. $m^*([a,b])=b-a$：因为它的任何可数开区间覆盖都有有限的子开区间覆盖。子开区间且覆盖自然能说明其长度和大于$b-a$
1. $m^*((a,b))=b-a$：因为开区间能被闭区间两侧逼近，且由外测度的单调性就得到结论。
1. 平移不变：两者的可数开区间覆盖也可以用平移建立一一对应。
1. 可数**次**可加：对于任意可数集族$\{E_k\},m^*(\cup E_k)\leq\sum m^*(E_k)$

证：只要有一个$E_k$外测度无穷，不等式就成立了。下设所有集的外测度都是有限的。

对于每个$E_k$，存在可数开有界区间族$\{I_{n,k}\}$使得$m^*(E_k)\geq\sum_n l(I_{n,k})-\varepsilon/2^k$

于是$m^*(\cup E_k)\leq\sum_{n,k}l(I_{n,k})\stackrel{?}=\sum_k\sum_nl(I_n,k)\leq\sum_k [m^*(E_k)+\varepsilon/2^k]=\sum m^*(E_k)+\varepsilon$

令$\varepsilon\to 0$则得证。

自然能够得到有限次可加性。

6. (等价定义) 即使在外测度的定义中要求每个开区间的长度小于$\delta$，这样得到的集函数$m^*_\delta$依然与$m$相同。

证：首先当然有$m_\delta^*(E)\geq m^*(E)$，不妨两个函数的值都不是正无穷。

于是存在可数开区间族覆盖$E$，且$\sum l(I_n)\leq m^*(E)+\varepsilon$

那么将每个开区间分割成不相交的长度不超过$\delta/2$的开区间，使得新的分割与原来的开区间最多相差可数个孤立点。然后再将这些新的开区间固定中心延伸$\lambda\in (1,2)$倍，于是这些新开区间族可数，每个开区间长度不超过$\delta$，并且构成对$E$的覆盖。并且它们的长度和$\sum l(I'_n)=\lambda \cdot \sum l(I_n)\leq \lambda\cdot (m^*(E)+\varepsilon)$

于是$m^*_\delta(E)\leq \lambda\cdot(m^*(E)+\varepsilon)$，令$\lambda\to 1,\varepsilon \to 0$即证。



结论与例子：

1. 可数集外测度为0：每个点周围赋予开区间$(x_k-\varepsilon/2^k,x_k+\varepsilon/2^k)$即可。
2. 对于区间$[0,1]$中的全体无理数构成的集合$A,\ m^*(A)=1$

证：设区间$[0,1]$中的全体有理数构成的集合为$B$，有限次可加性：$1=m^*(A\cup B)\leq m^*(A)+m^*(B)=m^*(A)$

单调性：$m^*(A)\leq m^*(A\cup B)=1$

实际上，若两个集合包含，且相差（甚至可以去掉包含关系变为对称差）一个零外测度的集合，那么这两个集合的外测度相同。

即：$m^*(A)=0\implies m^*(A\cup B)=m^*(B)$

3. 对于任何有界集$E$，存在$G_\delta$集$G$：$E\subseteq G$且$m^*(E)=m^*(G)$

证：$\forall \varepsilon,\ \exists{I_k}\ cover\ E,\sum l(I_k)\leq m^*(E)+\varepsilon$

记$O=\cup I_k$是开集。则$m^*(O)\leq \sum m^*(I_k)=\sum l(I_k)\leq m^*(E)+\varepsilon$

那么对于每个$\varepsilon=1/n$，就能决定一个开集$O_n$使得$m^*(O_n)\leq m^*(E)+1/n$

于是取$G=\cap O_n$，那么$m^*(G)\leq m^*(O_n)\leq m^*(E)+1/n$, however n is arbitrary, which implies: $m^*(G)\leq m^*(E)$

但另一方面$E\subseteq G$，于是$m^*(E)\leq m^*(G)$，这样就得到了证明。

4. （分离条件下可加）$A,B$有界，且$\forall a\in A,b\in B,|a-b|\geq\alpha>0$，那么$m^*(A\cup B)=m^*(A)+m^*(B)$

证：应用性质6. 对于任何一族长度小于$\alpha$的可数开区间族覆盖$A\cup B$，满足$\sum l(I)\leq m^*(A\cup B)+\varepsilon$.这些开区间中没有一个能够同时与$A,B$相交，并且不妨它们每个都至少与$A,B$中的一个相交，于是可将这些开区间分成与$A$或$B$相交两类，并且这两类各自是$A,B$的可数开区间覆盖，于是$m^*(A\cup B)\geq \sum l(I)-\varepsilon\geq m^*(A)+m^*(B)-\varepsilon$，令$\varepsilon \to 0$即得证。

5. （介值性）集合$E$有界，且有正外测度，对于任意$c\in(0,m^*(E))$，则存在有界集$A\subseteq E$使得$m^*(A)=c$

证：设$E\subseteq [a,b]$，记$f(x)=m^*([a,x]\cap E)$，$f(a)=0,f(b)=m^*(E)$

且$f(x+\delta)\stackrel{次可加}\leq f(x)+m^*([x,x+\delta])=f(x)+\delta\ \ (\delta>0)$

同样地反过来考虑，左侧连续也可同理完成，于是$f$连续，则由介值定理自然成立。

### 2.2 Lebesgue可测

外测度的次可加性并不令人满意：它甚至不能做到不交集合的有限可加。但是有一个$\sigma$代数：它包含所有开集且支持可数可加。下面给出这个可测族的构造定义；

**(Caratheodory: Lebesgue可测) 集合$E$可测，若$\forall A$, $m^*(A)=m^*(A\cap E)+m^*(A\cap E^c)$**

首先能够直观看出一个可测集能够支持有限可加：

**(有限可加) 若$A$可测，$B$是任何与$A$不交的集合，那么$m^*(A\cup B)=m^*(A)+m^*(B)$**

证：$m^*(A\cup B)=m^*([A\cup B]\cap B)+m^*([A\cup B]\cap B^c)=m^*(A)+m^*(B)$

于是自然有分割性质$m^*(B-A)=m^*(B)-m^*(A); \ A\ finitely\ measurable,A\subseteq B$

### 2.2a Lebesgue可测集构成$\sigma$代数，部分性质

我们自然好奇什么样的集合是Lebesgue可测的，接下来的一系列命题都是为了刻画这个性质的。

**1. (补集) $E$可测$\implies E^c$可测**

**2. 外测度为0的集合可测**

证：设$m^*(E)=0$，则$\forall A, \ m^*(A\cap E)+m^*(A\cap E^c)\leq m^*(E)+m^*(A)=m^*(A)$而左侧大于右侧是有限次可加性的推论，于是立刻有两侧相等。

**3. (有限并) 可测集族的有限并可测**

证：只需证明$E_1, E_2\ measurable\implies E_1\cup E_2\ measurable$

$\forall A, \ m^*(A)=m^*(A\cap E_1)+m^*(A\cap E_1^c)=m^*(A\cap E_1)+m^*([A\cap E_1^c]\cap E_2)+m^*([A\cap E_1^c]\cap E_2^c)$

$=m^*(A\cap E_1)+m^*([A\cap E_1^c]\cap E_2)+m^*(A\cap [E_1\cup E_2]^c)$

$\geq m^*([A\cap E_1]\cup\{A\cap [E_1^c\cap E_2]\})++m^*(A\cap [E_1\cup E_2]^c)$

$=m^*([A\cap[E_1\cup E_2])+m^*([A\cap[E_1\cup E_2]^c)$

同样反方向自然成立，于是立刻有两侧相等。



利用de Morgan律，自然也对有限交成立类似命题。从而可测集的对称差，相对补（也称差集）也成立类似命题。

**4. (可数并) 可测集的可数并可测**

证：每个可测集的可数并$\cup E_i$当然可以写成若干可测集的不交并：$E'_k=E_k - \cup^{k-1} E_i,\ E'_1=E_1$

于是不妨假设这里的可数并是不交可数并：$E=\coprod_1^\infty E_k,\ F_k=\coprod_1^n E_k$，那么每个$F_k$可测。

于是对任意集合$A,\ m^*(A)=m^*(A\cap F_k)+m^*(A\cap F_k^c)\geq m^*(A\cap F_k)+m^*(A\cap E^c)$

但是对于不交有限可测族$\{E_k\}$，$m^*(A\cap[\coprod_1^n E_k])=\sum_1^n m^*(A \cap E_k)$（归纳可证, See P.31）

（简单证明：$m^*(A\cap[\coprod_1^n E_k])=m^*([A\cap[\coprod_1^n E_k]]\cap E_n)+m^*([A\cap[\coprod_1^n E_k]]\cap E_n^c)=m^*(A\cap E_n)+m^*(A\cap[\coprod_1^{n-1}E_k])$

$\xlongequal{Induction}\sum_1^n m^*(A \cap E_k)$，另外注意到取$A=\coprod_1^n E_k$就有一般的有限可加性）

于是$m^*(A)\geq \sum m^*(A\cap E_k)+m^*(A\cap E^c)$

利用可数次可加，并令$k\to\infty$，有$m^*(A)\geq m^*(A\cap E)+m^*(A\cap E^c)$

得证。

**4alt-a. (有限) 对于不交有限可测族$\{E_k\}$，对任意集合$A$，$m^*(A\cap[\coprod^k E_k])=\sum^k m^*(A \cap E_k)$**

**4alt-b. (可数可加性) $\{E_k\}$是可测集的可数不交族，则$\coprod E_k$可测（4）且$m^*(\coprod E_k)=\sum m^*(E_k)$**

证：只需$m^*(\coprod E_k)\geq\sum m^*(E_k)$，但是$m^*(\coprod E_k)\geq m^*(\coprod_1^n E_k)=\sum^n_1 m^*(E_k)$，令$n\to \infty$即证。

**4col. (容斥原理) $E_1,E_2$可测，那么$m(E_1\cap E_2)+m(E_1\cup E_2)=m(E_1)+m(E_2)$**

证：由4中结论，取$LHS=m(E_1\cap E_2)+m([E_1-E_2]\cup[E_1\cap E_2]\cup[E_2-E_1])$

$=[m(E_1\cap E_2)+m(E_1-E_2)]+[m(E_1\cap E_2)+m(E_2-E_1)]=m(E_1)+m(E_2)=RHS$

**4col. (a: 可数情况) 对于不交可数可测族$\{E_k\}$，对任意集合$A$，$m^*(A\cap[\coprod_1^\infty E_k])=\sum_1^\infty m^*(A \cap E_k)$**

证：只需$m^*(A\cap[\coprod_1^\infty E_k])\geq\sum_1^\infty m^*(A \cap E_k)$。由外测度的单调性，$m^*(A\cap[\coprod_1^\infty E_k])\geq m^*(A\cap[\coprod_1^n E_k])=\sum_1^n m^*(A \cap E_k)$，这个不等式对全体$n$成立，令$n\to\infty$即证。

**5. 区间可测**

证：每个开区间都是闭区间的可数并，闭区间的补是两个无限开区间的并，并且一个区间关于原点反射后可测性不变（将A一起反射即可，外测度不变的原因与平移不变相同），因此只需$(a,+\infty)$可测。

对于任意集合$A$，不妨$a\notin A$，否则去掉这样一个点不会改变外测度。

存在一个可数开区间族$\{I_k\}$覆盖$A$，使得$\sum l(I_k)\leq m^*(A)+\varepsilon$

于是只需$m^*(A\cap(a,+\infty))+m^*(A\cap(-\infty,a))\leq m^*(A)$

$m^*(A\cap(a,+\infty))=m^*(\cup(I_k\cap(a,+\infty)))\leq\sum m^*(I_k\cap(a,+\infty))=\sum l(I_k\cap(a,+\infty))$，最后一个等号是外测度退化为了区间长度。

同样地，$m^*(A\cap(-\infty,a))\leq \sum l(I_k\cap(-\infty,a))$

于是$m^*(A\cap(a,+\infty))+m^*(A\cap(-\infty,a))\leq \sum l(I_k\cap(a,+\infty))+\sum l(I_k\cap(-\infty,a))=\sum l(I_k)\leq m^*(A)+\varepsilon$

令$\varepsilon\to 0$得证。

**6. 可测集的平移、反射、缩放可测**

**7. 开集可测**：开集是可数开区间的并（有可数拓扑基：有理开球）

**8.($\sigma$代数) 可测集族是一个包含Borel集的$\sigma$代数，于是每个区间、开集、闭集、$G_\delta,F_\delta$集都是可测的。 **



接下来想问在Carathedory的定义中，集合$A$是否能限制在一些别的集合上且保持定义等价性，答案是可以的，将$A$限制为区间仍然是成立的。

只需说明所有区间$I$，$m^*(I)=m^*(I\cap E)+m^*(I\cap E^c)$成立能够推出$\forall A$, $m^*(A)=m^*(A\cap E)+m^*(A\cap E^c)$

**9. (Lebesgue可测的等价定义) 集合$E$可测，若$\forall I\ open\ interval $, $m^*(A)=m^*(A\cap E)+m^*(A\cap E^c)$**

证：由之前的讨论，设$A$有可数开区间族$\{I_k\}$覆盖$A$，使得$\sum l(I_k)\leq m^*(A)+\varepsilon$

从而同理5. $m^*(A\cap E)+m^*(A\cap E^c)\leq \sum m^*(I_k\cap E)+\sum m^*(I_k\cap E^c)=\sum m^*(I_k)\leq m^*(A)+\varepsilon$

令$\varepsilon\to 0$得证。

（反向的论证是显然的，从而自然是等价的定义）



### 2.2b Lebesgue可测集的逼近，Littlewood第一原理

**1. （外逼近：开集或$G_\delta$集）**

**以下结论与$E$可测等价：**

**a. 每个$\varepsilon>0$，存在包含$E$的开集$O$使$m^*(O-E)<\varepsilon$**

**b. 存在包含$E$的$G_\delta$集$G$使得$m^*(G-E)=0$**

证：（可测$\implies a.$）

如果$E$外测度有限：

存在$E$的可数开区间族$\{I_k\}$，使得$\sum l(I_k)< m^*(E)+\varepsilon$

于是记$O=\cup I_k, m^*(O)-m^*(E)<\varepsilon$

但是由$E$可测，$m^*(O-E)=m^*(O)-m^*(E)<\varepsilon$

如果$E$外测度无限：

$E$一定能够写成可数个有限外测度的可测集族的无交并（$E_n=E\cap([n-1,n]\cup[-n,-n+1])$），设为$\{E_k\}$，于是利用有限测度时已经完成的结论，存在开集$O_k$包含$E_k$且$m^*(O_k-E_k)< \varepsilon/2^k$

于是$m^*(O-E)\leq m^*(\cup[O_k-E_k])\leq\sum m^*(O_k-E_k)<\varepsilon$

（$a.\implies\ b.$）

对每个$k$，选取开集$O_k$包含$E$，且$m^*(O_k-E)<1/k$

于是取$G=\cup O_k, m^*(G-E)\leq m^*(O_k-E)<1/k$，那么$m^*(G-E)=0$

（$b.\implies$可测）

$G,G-E(0\ outer\ measure) \ measurable\implies E\ measurable$



于是同理$1.$有内逼近结果：闭集和$F_\sigma$集。



另外有限外测度的可测集与有限个开区间的不交族相差无几：

**2. （$Littlewood$第一原理：开区间的有限不交族逼近）$E$为外测度有限的可测集，$\forall\varepsilon>0,\exists$开区间的有限不交族$I_k$。记$O=\coprod I_k$，则$m^*(E-O)+m^*(O-E)<\varepsilon$**

证：由外逼近定理，存在一个包含$E$的开集$U$，使得$m^*(U-E)<\varepsilon/2$

令$U=\cup I_k$为开区间的可数不交族，于是$\sum^n l(I_k)\xlongequal{See 2.2a-4.}m^*(\cup^n I_k)\leq m^*(U)<\infty$

于是由于$m^*(U)$的控制，$\sum l(I_k)<\infty$

从而可以选取自然数$n$使得$\sum_{n+1}^\infty l(I_k)<\varepsilon/2$

取$O=\cup ^n I_k$，于是$O-E\subseteq U-E$，从而$m^*(O-E)\leq m^*(U-E)<\varepsilon/2$

且$m^*(E-O)\leq m^*(U-O)=\sum_{n+1}^{\infty} l(I_k)<\varepsilon/2$，综合两者即证。



### 2.2c Lebesgue测度性质

定义在可测集上的外测度赋予了任何区间它的长度，平移不变且可数可加。

**（连续性）若$\{A_k\}$是上升的可测可数集族，则$m(\cup A_k)=\lim m(A_k)$**

**若$\{B_k\}$是下降的可测可数集族，且$m(B_1)<\infty$，则$m(\cap B_k)=\lim m(B_k)$ **

证：（上升）只需要考虑所有$k$，$m(A_k)<\infty$，记$C_k=A_k-A_{k-1}$，那么$m(\cup A_k)=m(\cup C_k)=\sum[m(A_k)-m(A_{k-1})]=\lim m(A_k)$

（下降）考虑$D_k=B_1-B_k$，同理。

当然同理$4col.$中的做法，这有推广的结论：

条件同上，$m^*(A\cap[\cup^\infty A_k])=\lim m^*(A\cap A_k);\ m^*(A[\cap^\infty B_k])=\lim m^*(A\cap B_k)$



**(Borel-Canteli引理) 若$\sum m(E_k)<\infty$，$\{E_k\}$为可测集的可数族，则几乎所有$x$属于至多有限个$E_k$**

（我们称一个性质几乎处处成立如果其不成立的点集外测度为0）

证： 由于$m(\cup_1^\infty E_k)\leq\sum m(E_k)<\infty$，于是由连续性有$m(\cap_{n=1}^\infty[\cup_{k=n}^\infty E_k])=\lim_{n\to\infty} m(\cup_{k=n}^{\infty}E_k)\leq\lim_{n\to\infty}\sum_{k=n}^{\infty}E_k=0$

于是几乎所有$x$不属于$\cap_{n=1}^\infty[\cup_{k=n}^\infty E_k]$，从而属于至多有限多个$E$。



### 2.3 不可测集

自然提问：是否存在不可测集？我们来说明Vitali的重要结果：正外测度的实数集一定存在不可测子集。

**(Vitali) 正外测度的实数集一定存在不可测子集。**

我们首先给出一个引理：

**(不可测集构造) 引理：$E$为有界的可测实数集，假定存在有界、可数无穷的实数集$\Lambda$，使得平移族$\{E+\lambda\}_{\lambda\in\Lambda}$不交，那么$m(E)=0$**

证：首先$\coprod \{E+\lambda\}$有界，由可数可加性：$\infty>m(\coprod \{E+\lambda\})=\sum_\lambda m(E+\lambda)$，而$m(E+\lambda)=m(E)$

故只能$m(E)=0$



回到Vitali定理的证明：设这个正外测度的实数集是$E$，于是有界。考虑$E/\Q\sim$的任意一组代表元构成的选择出来的集合$C_E$（这要求选择公理！），我们说明$C_E$不可测。如果它可测：

那么$E\subseteq\bigcup_{\lambda\in \Q}\{\lambda+C_E\}$，但是由于$E$有界，上述并集的指标$\lambda$范围可以修改到有理数集并上一个有限区间。于是自然有界，可数无穷。由引理$m(C_E)=0$，从而$m(E)\leq \sum_{\lambda\in\Lambda_0}m(\lambda+C_E)=0$，矛盾！

（自然的推论是这个$C_E$必然不可数无穷，否则就可测了）

于是自然我们终于可以回答，$m^*(A\coprod B)<m^*(A)+m^*(B)$是能够成立的：如果对于所有的$A,B$, $m^*(A\coprod B)= m^*(A)+m^*(B)$，那么每个$A,B$可测，于是和Vitali定理矛盾。



### 2.4 Cantor集，Cantor-Lebesgue函数

我们将利用Cantor集说明外测度零不一定意味着可数，可测集合也不一定是Borel集。

**(Cantor集) 取$C_1=[0,1/3]\cup[2/3,1], C_n=C_{n-1}/3\cup[C_{n-1}/3+2/3]$，这样得到可数集族$\{C_k\}$，定义Cantor集$C=\cap_{k=1}^{\infty} C_k$**

于是容易验证：$\{C_k\}$是下降的闭集族，并且对于每个$k$, $C_k$是$2^k$个不交闭区间的并集，每个区间长度为$1/3^k$。

性质：$C$是闭的零测度的不可数集。

证：由于闭集族的交是闭的，从而$C$闭，于是可测。利用$m(C)\leq m(C_k)=(2/3)^k$知它零测。

对于任意$C$中元素$x$，$x\in C_k\iff x$的三进制表示中第$k$位为$0\ or\ 2$

于是Cantor集中的元素与一列$0,2$构成的可数无限长的序列基数相同，但后者利用对角线法可以说明是不可数的，于是$C$不可数。

于是这就说明了外测度为0不代表着可数。



（Cantor集的构造中相当于挖去正中间的$3^{-n}$，如果更改成$\alpha \cdot 3^{-n},0<\alpha<1$，那么这样得到的集合$C$可测且测度为$1-\alpha$（利用测度的连续性），称为广义Cantor集。那么它关于$[0,1]$的补集（作为开集）是一个具有正测度边界的开集。）



同样，我们利用Cantor集构造出的Cantor-Lebesgue函数说明可测集合不一定是Borel集。

**(Cantor-Lebesgue函数) 定义函数$f_0(x)=x$, $f_{n+1}(x)= \left\{\begin{aligned}\frac{1}{2}f_n(3x)\quad x\in[0,1/3)\\\frac{1}{2}\quad x\in [1/3,2/3)\\\frac{1}{2}+f_n(3x+2)\quad x\in[2/3,1] \end{aligned}\right.$**

由于$\max_{x\in[0,1]}|f_{n+1}(x)-f_n(x)|=\max_{x\in[0,1/3]}|\frac{1}{2}f_n(3x)-f_n(x)|=\frac{1}{2}\max_{x\in[0,1]}|f_n(x)-2f_n(\frac{x}{3})|$

$=\frac{1}{2}\max_{x\in[0,1/3]}|f_n(x)-f_{n-1}(x)|$

于是$\{f_n\}$一致收敛到某个函数$f$上，称它为$Cantor-Lebesgue$函数。

**(Cantor-Lebesgue函数性质) Cantor-Lebesgue函数$\varphi$是递增的连续函数，将$[0,1]$映到$[0,1]$，导数在$[0,1]-C$，即Cantor集的补集上存在，并且在这个开集上导数恒为0。**

证：递增是因为每一项$f_n(x)$都是递增的，连续则是因为它是连续函数的一致收敛函数。

由上述构造很容易发现$f$的确在Cantor集的补集上分段为常数，从而就能说明结论，值域由介值定理推出。



接下来指出映射$\psi=\varphi(x)+x$有着很独特的性质。

**$\psi:[0,1]\to[0,2]$是严格递增的连续函数，且将Cantor集$C$映为正测度的可测集，但能够将Cantor集$C$的某个子集映为不可测集。**

证：严格递增和连续性显然。并且显然这个函数映满了$[0,2]$

记$O=[0,1]-C$，现在说明$m(\psi(O))=1$（我们能采用$m$是因为下面讨论能够蕴含可测性）

当然$O=\coprod I_k$，而$\psi$保持了每个$I_k$长度不变，且$\psi(C)=\coprod\psi(I_k)$（保长的$x$和映出常数只有平移效果的$\varphi$）

于是$m(\psi(O))=\sum l(I_k)=m(O)=1$，从而$m(\psi(C))=1$

由Vitali定理，$\psi(C)$有不可测子集$W$，从而$\psi^{-1}(W)$是Cantor的子集。



最后我们说明$Cantor$集有一个不是$Borel$集的可测子集。

由于严格递增连续函数将Borel集映为Borel集（这不难验证），$W$不可测，从而$\psi^{-1}(W)$不是Borel集。



接下来总结一些映射对集合性质的保持：

1. 连续函数可测集的像和原像都不一定可测。

证：像不可测已经在$Cantor-Lebesgue$函数的结论中证明过了。

对于原像，只需要考虑函数的反函数即可。



2. $Lipschitz$函数$f$将零测集映为零测集，$F_\sigma$集映为$F_\sigma$集，将可测集映为可测集。

证：

a. 设$E$零测，于是$\forall \varepsilon>0,\ \exists L-cover\{I_k\}\ s.t.\ \sum l(I_k)<\varepsilon,\ $

而设$I_k=(a_k,b_k)$，就有$f(I_k)\subseteq(f(a_k)-L\cdot l(I_k),f(a_k)+L\cdot l(I_k))$

而后者当然也构成了$f(E)$的L-覆盖，从而$\exists L-cover\ \ of\ \ f(E)\ s.t.\sum l<2L\cdot\varepsilon$，这就说明$f(E)$零测。

b. 这只需要证明闭集被映成了闭集，而这是Lipschitz连续的自然推论。

c. 利用$F_\sigma$集对可测集的逼近即证。



## 3. Lebesgue可测函数

### 3.1 可测函数

本节的函数都是扩充实值函数

**（Lebesgue可测函数）设函数$f$有可测定义域$E$，以下四个命题等价：**

**1) 对每个实数$c$，$f^{-1}((c,+\infty))$可测**

**2) 对每个实数$c$，$f^{-1}([c,+\infty))$可测**

**3) 对每个实数$c$，$f^{-1}((-\infty,c))$可测**

**4) 对每个实数$c$，$f^{-1}((-\infty,c])$可测**

**满足这个性质的函数称为Lebesgue可测函数，并且这$\implies f^{-1}(c)$可测**

证：$2\iff 3,1\iff4$显然

$1\implies 2$，因为$f^{-1}([c,+\infty))=\bigcap_{k} f^{-1}((c-1/k,+\infty))$

$2\implies 1$，因为$f^{-1}((c,+\infty))=\bigcup_{k} f^{-1}([c+1/k,+\infty))$

$Lebesgue\ measurable\implies f^{-1}(c)\ measurable$因为$f^{-1}(c)=f^{-1}([c,+\infty))\cap f^{-1}((-\infty,c])$

（其实对于扩充实数$c$，$f^{-1}(c)$依然可测，用若干无限开区间的原像取交即可）

（对每个实数$c$,$f^{-1}(c)$可测并不能反向推出$f$可测：因为取）



**（判定）$f$条件同上，则$f$可测$\iff$每个开集$O$的原像可测**

证：$\Leftarrow$显然，$\Rightarrow$是因为可以将$O$表示为有界开区间的可数并，而每个这样的区间当然可以表示为$(c,+\infty)\cap (-\infty,d)$

于是自然说明了$O$可测

（实际上：具有性质$f^{-1}(A)$可测的集合$A$构成了$\sigma$代数，于是自然这里$O$还可以换成Borel集）



下面来看可测函数的性质：

1. 连续函数可测

证：每个开集在连续函数下的原像是开集和定义域的交，自然可测，由前述得证。

2. 定义在区间上的单调函数可测

证：显然

3. 若$f$在$E$上可测，且$f=g\ a.e.$，则$g$可测。

证：设$f,g$不相同的点集为$A$，$g^{-1}((c,+\infty))=\{x\in A|g(x)>c\}\cup(\{x\in E|f(x)>c\}\cap[E-A])$

当然可测。

4. $E$的可测子集$D$，$f$在$E$上可测$\iff$ $f$在$D,E-D$上可测。

证：$\{x\in E|f(x)>c\}=\{x\in D|f(x)>c\}\cup\{x\in E-D|f(x)>c\}$

$\implies$方向只需要注意到$\{x\in D|f(x)>c\}=\{x\in E|f(x)>c\}\cap D$



我们自然想问可测函数是否能够通过代数运算导出可测函数。

但在这之前我们需要明确扩充实值函数的运算到底是如何进行的，因为异号无穷的和不恰当定义。我们假定两个函数在$E$上$f,g\ a.e.finite$，设$E_0$是使得$f,g$均有限的集合。那么$f+g$在$E_0$上如果可测，自然延拓在$E$上后可测。对于乘积结果同样成立。



**（线性与乘积）令$f,g$为$E$上可测函数，在$E$上$a.e.\ finite$，那么对于任何$\alpha,\beta,\ \ \alpha\cdot f+\beta\cdot g$在$E$上可测；$fg$在$E$上可测。**

证：线性：

很容易注意到$f$可测$\implies\alpha\cdot f$可测。于是只需$f,g$可测$\implies f+g$可测。

$f(x)+g(x)<c\implies\exists q\in\mathbb{Q},\ f(x)<q<c-g(x)$

于是$\{x\in E|f(x)+g(x)<c\}=\bigcup_{q\in\mathbb{Q}}[\{x\in E|g(x)<c-q\}\cap\{x\in E|f(x)<q\}]$

自然说明了可测。

乘积：

由于$fg=\frac{1}{2}[(f+g)^2-f^2-g^2]$，于是只需说明$f$可测$\implies f^2$可测。

对于$c>0$，$\{x\in E|f^2(x)>c\}=\{x\in E|f(x)>\sqrt{c}\}\cup\{x\in E|f(x)<-\sqrt{c}\}$

对于$c\leq 0$，这个集合就是$E$，于是说明了可测。



尽管可测已经有了如上的好性质，但是可测函数的复合依然可能不是可测的。

由于$\psi=x+\varphi(x)$，这个递增连续函数将可测集映为不可测集，于是$\psi^{-1}$将不可测集映为可测集，再考虑这个可测集的指示函数$\chi$，于是$\chi\circ \psi^{-1}$尽管两者都是可测函数，但它们的复合并不可数：$1$的原像上不可测集。

尽管有了这个令人沮丧的反例，只要再加强一下条件，复合的命题就能成立了：

**（复合）$g$为$E$上的可测实值函数，$f$为$\R$上的连续实值函数，那么$f\circ g$可测**

证：

$\forall O\stackrel{open}\subseteq\R$，$(f\circ g)^{-1}(O)=g^{-1}(f^{-1}(O))$

但$f^{-1}(O)$定义在$\R$上且连续，于是$f^{-1}(O)$开，自然就有$(f\circ g)^{-1}(O)$可测。



（可以看到可测集的原像不一定可测是一般版本复合命题的本质困难，但是如果我们放宽到$f$可测，$g$为$\R\to \R$的双射且有Lipschitz逆。那么$f\circ g$，这源于先前已经证明的Lipschitz函数的性质。）



**（有限max,min）有共同定义域$E$的可测实数函数的有限族$\{f\}_{k=1}^n$，那么对它们作用$max\ or\ min$得到的函数依然可测。**

这是很容易的，$(\max{f})^{-1}((c,+\infty))=\cup f((c,+\infty))$

于是自然$f\ measurable\implies |f|,f^+,f^-\ measurable$

这里的取最大最小值可以推广到上下确界（可数情况）

**有共同定义域$E$的可测函数序列$\{f_n\}，\inf f_n, \lim\inf f_n$都可测（自然sup情况同理。）**

证：同样地，这是由于可测集的可数并（交）仍然可测。

### 3.2 逐点收敛，简单逼近，有界控制

本章节接下来的小节都在描述逼近性质。

在称一个函数列收敛到某个函数时，接下来都假定它们有着共同的定义域。

我们首次看到可测函数相比之前的Riemann可积函数性质好在哪里：

**(逐点收敛保持可测) $measurable\ sequence\{f_n\}\ a.e.\ pointwise \to f$，$f$可测**

证：设$E_0$零测，且$E-E_0$上$\{f_n\}\ pointwise\to f$

我们当然可以不妨$E=E-E_0$，因为它们的可测性一样（零测集的子集一定可测）

对于点$x$，$f(x)<c\iff\exists n,k\in\N,s.t.\forall j>k, f_j(x)<c-1/n$

于是$\{x\in E|f(x)<c\}=\begin{aligned}\bigcup_{1\leq k,n<\infty}[\bigcap_{j>k} \{x\in E|f_j(x)<c-1/n\}]\end{aligned}$

但是可测集的可数交和并都可数，于是得证。



类似Riemann理论中的阶梯函数，Lebesgue理论中也有对应对应概念：简单函数。

**（简单函数，典范表示）称一个可测集上实值函数简单，若它可测且仅取有限个值，于是每个简单函数可以表示为可测集的指示函数的线性组合。**

实际上，简单函数和阶梯函数是“差不多的”：**闭有界区间$I$上的简单函数$\psi$，对每个$\varepsilon>0$，存在$I$上阶梯函数$h$和$I$的可测子集$F$使得$F$上$\psi=h$，且$m(I-F)<\varepsilon$**

证：我们先来证明$\psi$是某个可测子集$E$的特征函数这一情况：这是由可测集被开区间的有限不交族逼近保证的。再对简单函数的典范表示中的每个分量应用这一结果，选出若干有限的$F$。取交即证。



接下来的内容是可以预见的：逼近。

**（简单逼近引理）$f$为$E$上可测实值函数，且在$E$上有界（已经蕴涵了$E$的可测性），则存在$E$上简单函数$\varphi,\psi$使得$\varphi\leq f\leq\psi,\ 0\leq\psi-\varphi<\varepsilon$**

证：设$f(E)\subseteq(c,d)$

考虑对$(c,d)$的一个分划$c=y_0<y_1<\cdots<y_{n-1}<y_n=d$，我们取充分小的分划长度$\varepsilon$

定义$E_k=[y_k,y_{k+1})$可测，以及它们对应的指示函数$\chi_k$

取$\varphi=\sum y_k\chi_{k},\psi=\sum y_{k+1}\chi_{k}$

它自然满足$\varphi\leq f\leq\psi$，并且$0\leq \psi-\varphi<\varepsilon$



于是有一个利用简单逼近刻画可测的结果：

**（简单逼近定理）定义在可测集$E$上的扩充实值函数$f$是可测的$\iff$存在$E$上简单函数序列$\varphi_n \ pointwise\to f$，且$\forall n,|\varphi_n|\leq |f|$，另外如果$f$非负，这个简单函数列可以递增。**

证：$(\Longleftarrow)$简单函数可测，可测函数序列的逐点极限依然可测。

对于$(\implies)$，可以假定$f$非负，一般情况利用$f=f^+-f^-$且简单函数的和与差仍为简单函数完成。

我们这里先选出一个简单函数列$\{\varphi_n\}$

记$E_n=\{x\in E|f(x)\leq n\}$

于是可以将简单逼近引理应用在$f|_{E_n}$上，得到一组简单函数$\varphi_n,\psi_n,s.t.\  on\ E_n,\ 0\leq\varphi_n\leq f\leq \psi_n, 0\leq\psi_n-\varphi_n<1/n$

在$E_n$外将$\varphi_n$延拓为常值函数$\varphi_n|_{E-E_n}=n$，这样得到了一个$E$上的简单函数。且$0\leq\varphi_n\leq f$.

我们来说明$\varphi_n \ pointwise\to f$，如果$f(x)<+\infty$，设有自然数$N$使得$f(x)<N$，那么对于$n\geq N$有$f(x)-\varphi_n(x)<1/n$，自然收敛。

如果$f(x)=+\infty$，则$\varphi_n(x)=n$，结论自然成立。

将$\varphi_n$替换为$\max\{\varphi_1,\cdots\varphi_n\}$，即得递增函数列。



**（简单序列一致逼近）条件同简单逼近引理，存在$E$上得简单函数序列$\{\varphi_n\},\{\psi_n\}$，使得前者递增，后者递减并且它们都在$E$上一致收敛于$f$**

证：一致性可以同样利用简单逼近引理，递增只需取$\max\{\varphi_1,\cdots,\varphi_n\}$，递减同理。

**（半简单序列一致逼近）称实值可测函数半简单，如果其仅取可数个值，对于任意$E$上可测函数$f$，证明存在$E$上半简单函数序列$\{f_n\}$，在$E$上一致收敛于$f$**

证：简单逼近引理中将区间的有限分划修改为可数的分划，并且保证分划最大长度得到控制，接下来的证明是相同的。



**（有界控制）如果$E$上可测函数$f\ a.e.\ finite$，那么对每个$\varepsilon>0$，存在$measurable\ set\ F\subseteq E$，使得$f$在$F$上有界，且$m(E-F)<\varepsilon$**

证：设$f$在$E'$上有限，$m(E-E')=0$

记$F_n =f^{-1}([-n,n])$可测，并且$E'=\cup_{n=1}^{\infty} F_n$，且$F_n$上升、可测，于是由测度连续性$\lim m(F_n)=m(E')$，那么当然能够使得$m(E'-F_n)<\varepsilon$，于是$m(E-F)<\varepsilon$



### 3.3 Littlewood第二原理（Lusin）；第三原理（Egroff）

我们先说明Littlewood所总结的三个原理的内容：

第一原理：每个可测集接近于开区间的有限并

第二原理：每个可测函数接近于连续函数

第三原理：每个逐点收敛的可测函数序列接近于一致收敛的函数序列。



**（第二原理：Lusin定理）$f$为$E$上定义在$E$上的实值可测函数，对每个$\varepsilon>0$，存在$\R$上连续函数$g$和闭集$F\subseteq E$，使得$F$上$f=g$，$m(E-F)<\varepsilon$**

证：

a. $E$测度有限，且$f$为简单函数。

设$f$在$E_k$上取到$a_k$（$1\leq k \leq n$），由可测集的内逼近知存在$F_k\subseteq E_k$，$m(E_k-F_k)<\varepsilon/n$

选取$F=\coprod_{k=1}^n F_k$，于是$m(E-F)=m(\coprod[E_k-F_k])=\sum m(E_k-F_k)<\varepsilon$，于是由Tietze延拓可以将$f|_F$延拓到$\R$上

b. $E$测度有限，且$f$ $a.e.$有限

由有界控制，可以选出与$E$相差无几的可测子集$E'$使得$f$限制在其上成为有界函数。于是直接假设$f$有界是合理的，从而简单逼近引理：$f$被简单函数一致逼近，对于每个简单函数$\varphi_k$，由a存在一个闭集$F_k\subseteq E$使得存在一个连续函数$f_k$，$f_k|_{F_k}=\varphi_k|_{F_k}$，且$m(E-F_k)<\varepsilon/2^k$。

于是$m(E-\cap F_k)<\varepsilon$，$\cap F_k$上连续函数$f_k$自然一致收敛到$f$，从而$f$在$\cap F_k$上连续，于是利用Tietze延拓，命题自然成立。

c. $E$无限测度，且$f$ $a.e.$有限

设$E_k=E\cap \{[k,k+1)\cup(-k-1,k]\}$

对每个$E_k$利用b，选出闭集$F_k,m(E_k-F_k)<\varepsilon/2^{k+1}$，尽管它们的交$\cap F_k$不一定闭，但由于它可测，再使用闭集内逼近，使得最终的$F$与$E$相差无几，于是命题自然成立。



第二原理的闭集可以换为紧集：只需要将$E$替换为某个有界集合：考虑$E_k=E\cap[-k,k]$，由测度的极限，当然有$E_k$使得它和$E$相差无几（差集测度可控），于是在$E_k$中应用Lusin定理，由于有界自然得到了紧集。



然后是第三原理：我们现在对它的思路详细叙述。

第三原理希望告诉我们对于性质不错的函数逐点收敛行为和一致收敛行为相差无几。

这让人回想起分析中的：

**Dini定理：紧集上的连续函数逐点单调地收敛到一个连续函数，那么这个收敛是一致的**（但很可惜，单调收敛要求还是比较高的）

**Arzela-Ascoli定理，partial form：紧度量空间上等度连续的函数列逐点收敛则一致收敛**

但是等度连续依旧要求很高，我们现在说明将逐点收敛则一致收敛放宽为逐点收敛“差不多”一致收敛则可以将函数列的要求放宽，这也是第三原理的动机。

**（第三原理：Egroff定理）有限测度集合$E$，设可测函数列$\{f_n\}$在$E$上逐点收敛到实值函数$f$，则对每个$\varepsilon>0,\ \exists closed\ set\ F\subseteq E$且在$F$上$f_n\rightrightarrows f$，$m(E-F)<\varepsilon$**

证：

（方法1.）

自然的一个思路是能不能找到一个单调收敛的函数列然后应用Dini定理呢？（既然写在这里了那的确是可以的）

取$g_k(x)=\sup_{k\geq n}|f_k(x)-f(x)|$

逐点收敛告诉我们$g_k(x)\searrow 0$，而$g_k$是可测的。

由Lusin定理：对于每个$g_k$，取紧集$F_k\subseteq E$，使得有$\R$上连续函数$h_k$限制在$F_k$上时和$g_k$相等，并且$m(E-F_k)<\varepsilon/2^{k+1}$

取$F_k$的交得到紧集$F'=\cap F_k, m(E-F')<\varepsilon$

然后应用Dini定理：$h_k$在$F'$上逐点收敛到$0$，于是一致收敛到$0$于是$f_n\stackrel{F'}\rightrightarrows f$

（方法2.）

夹层控制：非常雷同Dini定理的证明。

取$E_k^n=\{x\in E||f_j(x)-f(x)|<1/n,\forall j\geq k\}$

那么有升链$E_k^n\subseteq E_{k+1}^n\cdots \subseteq E$（最后一个包含号的意思是这个升链的并最终成为$E$

以及降链$E_k^n\supseteq E_{k}^{n+1} \supseteq\cdots$

思路是增大$n$，保证一致收敛，增大$k$调节测度。



## 4. Lebesgue积分

### 4.1 Riemann积分的缺陷

我们重述上下Riemann积分的定义：(阶梯函数的Riemann积分略)

$\begin{aligned}(R)\underline{\int_a^b}f=\sup\{(R)\int_a^b\varphi|\varphi是阶梯函数且[a,b]上\varphi\leq f\}\end{aligned}$

$\begin{aligned}(R)\overline{\int_a^b}f=\inf\{(R)\int_a^b\varphi|\varphi是阶梯函数且[a,b]上\varphi\geq f\}\end{aligned}$

然而积分号下取极限在这种积分下需要很强的条件（一致性），而一般的逐点收敛不一定能够满足保持Riemann积分值，甚至不能够保持Riemann可积性（Dirichlet函数）！另一方面考虑到微积分基本定理，大跌眼镜的是存在一些函数的导数不能Riemann可积（即使导数有界），同样Riemann可积的函数也不一定是某个函数的导数。



### 4.2 Lebesgue积分：有限测度集上的有界可测函数

接下来三节我们将爬坡式地建立Lebesgue积分理论

首先是有限测度集上的简单函数的积分：

$\begin{aligned} \int_E\psi=\sum_{i=1}^n a_i\cdot m(E_i)\end{aligned}$，其中右侧部分记号同简单函数$\psi$的典范表示。

很容易注意到即使$\psi$有非典范表示$\begin{aligned}\sum_{i=1}^n a_i \chi_{E_i}\end{aligned}$，只要$E_i$是可测子集的有限不交族，就有$$\begin{aligned}\int_E\psi=\sum_{i=1}^n a_i \cdot m(E_i)\end{aligned}$$

然后是第一个性质：

**（线性与单调性：有限测度集上简单函数）$\varphi,\psi$为有限测度集$E$上的简单函数，则：**

**对于任何$\alpha,\beta$，$\begin{aligned}\int_E (\alpha\varphi+\beta\psi)=\alpha\int_E\varphi+\beta\int_E\psi\end{aligned}$**

**如果在$E$上$\varphi\leq\psi$，$\begin{aligned}\int_E\varphi\leq\int_E\psi\end{aligned}$**

证：对于线性，只需说明$\begin{aligned}\int_E(\varphi+\psi)=\int_E\varphi+\int_E\psi\end{aligned}$

这是很显然的。对于单调，只需利用线性性质考虑$\begin{aligned}\int_E(\psi-\varphi)\geq0\end{aligned}$



然后是有限测度集上的有界函数：同样，类似Riemann积分的做法，定义上下Lebesgue积分为：

$\begin{aligned}\inf\{\int_E \psi|\psi简单且在E上f\leq\psi\}\end{aligned}$

$\begin{aligned}\sup\{\int_E\varphi|\varphi简单且在E上\varphi\leq f\}\end{aligned}$

**（Lebesgue积分：有限测度集上的有界函数）如果有限测度集$E$上的有界函数$f$满足其上下Lebesgue积分相同，则称这个公共值为$f$在$E$上的Lebesgue积分：$\begin{aligned}\int_E f\end{aligned}$**



自然，闭有界区间上的有界函数如果Riemann可积就一定Lebesgue可积（注意阶梯函数简单）



**（可测函数可积）$f$为有限测度集$E$上的有界可测函数，则$f$在$E$上可积。**

证：根据简单逼近引理取简单函数使得$\sup-\inf\leq (1/n)\cdot m(E)$ 即可。（注意：这里运用了简单函数Lebesgue积分的单调性）

实分析的一个核心结果就是上述命题的逆也是正确的，这样就完全建立了可积性的刻画（这比Riemann积分做的要好得多！）



于是自然有线性与单调性

**（线性与单调性：有限测度集上有界可测函数）$\varphi,\psi$为有限测度集$E$上的有界可测函数，则：**

**对于任何$\alpha,\beta$，$\begin{aligned}\int_E (\alpha\varphi+\beta\psi)=\alpha\int_E\varphi+\beta\int_E\psi\end{aligned}$**

**如果在$E$上$\varphi\leq\psi$，$\begin{aligned}\int_E\varphi\leq\int_E\psi\end{aligned}$**

证：可积性显然，利用简单函数逼近取极限即可。

单调性同样利用线性考虑差的下积分即可。



**（区域可加性：有限测度集上有界可测函数）$f$为有限测度集$E$上的有界可测函数，$A,B$为$E$的不交可测子集，则：$\begin{aligned}\int_{A\coprod B}f=\int_A f+\int _B f\end{aligned}$**

证：只需$\begin{aligned}\int_A f=\int_E f\cdot\chi_A\end{aligned}$，其中$A$是可测集$E$的可测子集。

$\inf\{\begin{aligned}\int_A\psi|\psi\geq f\ on\ A\end{aligned}\}$与$\begin{aligned}\inf\{\int_E\psi'|\psi'\geq f\cdot\chi_A\}\end{aligned}$是一一对应的，下积分的情况同理。



**（绝对值不等式：有限测度集上有界可测函数）$f$为有限测度集$E$上的有界可测函数，则$\begin{aligned}|\int_E f|\leq\int_E|f|\end{aligned}$**

证：利用单调性，以及$-|f|\leq f\leq |f|$即证。



**（积分-极限换序，一致收敛条件：有限测度集上有界可测函数序列）$\{f_n\}$为有限测度集$E$上的有界可测函数序列，且一致地收敛到有界可测函数$f$，则$\begin{aligned}\lim\int_E f_n=\int_E f\end{aligned}$**

证：取$N\ s.t. \forall n\geq N,\sup|f-f_n|<\varepsilon/m(E)$

利用绝对值不等式和单调性即证。



沮丧的是即使在$Lebesgue$积分中，逐点收敛依然不能够保证积分号下取极限是合法的，但是回想Littlewood第三原理：Egroff定理，我们知道可测函数的逐点收敛实际上与一致收敛相差无几，于是利用它能够给出分析学中第一次出现的，条件更弱的积分-极限换序定理。

**（积分-极限换序，有界收敛定理：有限测度集上有界可测函数序列）有限测度集$E$上的一致有界的逐点收敛函数列$\{f_n\}$能够完成积分号下取极限：$\begin{aligned}\lim\int_E f_n=\int_E  f\end{aligned}$**

证：右侧积分号合法性源于可测函数的逐点极限依然可测，由于一致有界，可设$|f_n|\leq M$

$\begin{aligned}\int_E f_n-\int_E f=\int_A(f_n -f)+\int_{E-A}f_n+\int_{E-A} f\leq\int_E|f_n-f|+2M\cdot m(E-A)\end{aligned}$

Egroff定理保证可以选取$A$使得$A$上$f_n\rightrightarrows f,m(E-A)<\varepsilon/(4M)$

再取$N$使得$\forall n\geq N,|f_n-f|<\varepsilon/(2\cdot m(E))\ on\ A$

得证。



### 4.3 Lebesgue积分：非负可测函数

具有有限测度支撑$\text{supp} f$的函数的Lebesgue积分是可以被显然定义的：取为$\begin{aligned}\int_{ E_0} f\end{aligned}$，只要$\text{supp}f\subseteq E_0$.（良定义性是显然的）

于是：

**（Lebesgue积分：非负可测函数）$E$上非负可测函数$f$，其在$E$上的积分被定义为：$\begin{aligned}\int_E f :=\sup\{\int_E h|h有界，可测，有限支撑，且非负，0\leq h\leq f\}\end{aligned}$**



利用定义可以得到**Chebyshev不等式：$f$为$E$上非负可测函数，$\lambda\geq 0$，则$\begin{aligned}m(f^{-1}([\lambda,+\infty))\leq (\int_E f)/\lambda\end{aligned}$**

证：取$E_\lambda=f^{-1}([\lambda,+\infty))$，



如果$m(E_\lambda)=\infty$，取$\psi_n=\lambda\cdot\chi_{E_\lambda\cap[-n,n]}$

(Motive: 经典套路：利用测度连续性质)

$\lambda\cdot m(E_\lambda\cap[-n,n])=\int_E\psi_n$，且$0\leq\psi\leq f$，是具有有限支撑的有界可测函数。

两侧取$n\to\infty$，不等式两侧都是无穷于是成立。



如果$m(E_\lambda)<\infty$， 同样取$h=\lambda\cdot\chi_{E_\lambda}$

于是$\lambda\cdot m(E_\lambda)=\begin{aligned}\int_E h\leq\int_E f\end{aligned}$，得证。



**（零性质）$f$为$E$上非负可测函数，则$\begin{aligned}\int_E f=0\iff f=0\ a.e.\end{aligned}$**

证：

$(\implies)$ 由Chebyshev不等式，$m(f^{-1}[\lambda,+\infty))=0$，由测度的连续性，$m(f^{-1}(0,+\infty))=0$，于是$f=0\ a.e.$

$(\Longleftarrow)$ $\begin{aligned}\int_E f :=\sup\{\int_E h|h有界，可测，有限支撑，且非负，0\leq h\leq f\}\end{aligned}$这个定义式中，一定有$h=0\ a.e.$，从而自然有$\begin{aligned}\int_E f=0\end{aligned}$



**（可积性，无穷性质）$f$为$E$上非负可测函数，则称$f$可积，若$\begin{aligned}\int_E f<+\infty\end{aligned}$，这$\implies\ f\ finite\ a.e.$**

证：考虑Chebyshev不等式，可知（由测度的连续性）$m(f^{-1}(\infty))=0$



接下来有一些dirty work：

**（线性与单调性：非负可测函数）$\varphi,\psi$为$E$上的非负可测函数，则：**

**对于任何$\alpha,\beta>0$，$\begin{aligned}\int_E (\alpha\varphi+\beta\psi)=\alpha\int_E\varphi+\beta\int_E\psi\end{aligned}$**

**如果在$E$上$\varphi\leq\psi$，$\begin{aligned}\int_E\varphi\leq\int_E\psi\end{aligned}$**

证：线性性需要仔细检验。

单调性考虑有序关系成立集合的上确界也有序关系

以及类似的区域可加性性质依然成立。



再次回到积分号下取极限：

**（Fatou引理：非负可测函数）$\{f_n\}$为$E$上的非负可测函数序列，如果在$E$上$f_n\ a.e.\ pointwise\ \rightarrow f$，则$\begin{aligned}\int_E f\leq\lim\inf\int_E f_n\end{aligned}$**

证：$a.e.$是可以去掉的，因为零积分值性质向我们保证了改变函数在一个零测度集合上的取值不会对积分结果有任何影响，因此假定$f_n\ pointwise\rightarrow f$是合理的。

于是这样的情况下$f$是非负可测的。

那么只需要说明对于每个有界可测非负有限支撑且满足$0\leq h\leq f$的函数，$\begin{aligned}\int_E h\leq\lim\inf\int_E f_n\end{aligned}$

（Motive: 我们希望应用有限测度集上有界可测函数的有界收敛定理，这里的条件$h$的选取已经非常良好）

记$E_0=\text{supp} h$，$h_n=\min\{f_n,h\}$

于是$h_n\leq h$，从而一致有界，并且在$E_0$外消失，并且每个$h_n$都是可测的。于是由$f_n\ point wise\ \rightarrow f$, $h_n\ pointwise\ \rightarrow \ h$

于是利用有界收敛定理，$\begin{aligned}\lim\int_E h_n=\lim\int_{E_0} h_n=\int_{E_0} h=\int_E h\end{aligned}$

但是另一方面，对于每个$n$，$h_n\leq f_n\ on\ E$, 于是$\begin{aligned}\int_E h=\lim\int_E h_n\leq\lim\inf\int_E f_n\end{aligned}$

（严格成立的例子是取$f=n\cdot\chi_{(0,1/n)}$）

**（Fatou引理：推广）$\{f_n\}$为$E$上的非负可测函数序列，那么$\begin{aligned}\int_E\lim\inf f_n\leq\lim\inf\int_E f_n\end{aligned}$**

证：我们在Fatou引理中取函数列为$\inf_{i\geq n} f_i$，那么结论自明。

**（单调收敛定理：非负可测函数）令$\{f_n\}$为$E$上非负可测函数的递增序列，且在$E$上$a.e.\ pointwise\ \{f_n\}\rightarrow f$，则$\begin{aligned}\lim\int_E f_n=\int_E f\end{aligned}$**

证：由递增性，$f_n\leq f$

根据Fatou引理，$\begin{aligned}\int_E f\leq\lim\inf\int_E f_n\leq\lim\sup\int_E f_n\leq\int_E f\end{aligned}$

（这相当于完成了非负可测函数项级数的换序）

（注意：递减序列是不能使命题成立的：取$f_n=1/(nx^2)$）



**（Beppo-Levi定理：非负可测函数）令$\{f_n\}$为 $E$上非负可测函数的递增序列，如若积分序列$\begin{aligned}\{\int_Ef\}\end{aligned}$是有界的，那么$f_n\ pointwise\to E$上$a.e.$有限的可测函数$f$，且$\begin{aligned}\lim\int_E f_n=\int_E f<+\infty \end{aligned}$**

证：取$f$为逐点极限（递增列当然存在扩充实数极限），由于单调收敛定理$\begin{aligned}\int_E f<+\infty\end{aligned}$，自然$f\ a.e.\ finite$



### 4.4 一般Lebesgue积分

从非负进入一般的道路是考虑$f^+=\max\{f,0\},f^-=\max\{-f,0\}$

于是$f\ measurable\iff f^+,f^-\ measurable$

自然就有在$f$可测的前提下：$|f|\ 可积\iff f^+,f^-可积$

**（Lebesgue积分：一般）称$E$上可测函数$f$在$E$上可积，如果$|f|$在$E$上可积，此时记积分$\begin{aligned}\int_E f=\int_E f^+-\int_E f^-\end{aligned}$**

当$f$退化到非负可测函数时，这个定义是一致的。

于是4.3中的零性质（改变零测集上的函数值不影响积分）和无穷性质（可积$\implies\ a.e.\ finite$）在这里依然成立。



为了处理线性性质和单调性质，回想起分析中我们对级数讨论的类似结果是有用的。

**（比较判别法）$f$为$E$上可测函数，如果非负函数$g$在$E$上可积且控制了$f$的绝对值：$|f|\leq g$，就有$f$在$E$上可积且$\begin{aligned}|\int_E f|\leq\int_E|f| \end{aligned}$**

证明是利用非负可测函数上我们已经建立的积分理论。其中最后一个不等式是利用$\begin{aligned}|\int_Ef|=|\int_Ef^+-\int_Ef^-|\leq\int_E f^++\int_E f^-=\int_E |f|\end{aligned}$



为了说明线性性质，我们面临了和函数可测性讨论中出现的一样的问题：异号无穷点如何相加。但是这里可积性保证了无穷函数值的点集是零测的，自然我们可以定义和函数的积分是除去这样的点的集合上的积分。

于是接下来线性性质和单调性质以及区域可加性就显然了。



继续回到积分号下取极限的课题，这次我们有了：

**（Lebsegue控制收敛定理：ver.1 - 恒定控制函数）令$\{f_n\}$为$E$上的可测函数序列，假定存在$E$上的可积函数$g$，且在$E$上$|f_n|\leq g$，那么如若$f_n\ a.e.\ pointwise\to f$，则$f$在$E$上可积，且$\begin{aligned}\lim\int_E f_n=\int_E f\end{aligned}$**

证：

我们现在是可以讨论$g-f$和$g-f_n$的。那么由$Fatou$引理，$\begin{aligned}\int_E(g-f)\leq\lim\inf\int_E (g-f_n)\end{aligned}$

于是$\begin{aligned}\int_Eg-\int_Ef\leq\int_Eg-\lim\sup\int_Ef_n\implies\lim\sup\int_E f_n\leq\int_Ef\end{aligned}$

同样地，讨论$g+f$和$g+f_n$

有：$\begin{aligned}\int_E f\leq\lim\inf\int_E f_n\end{aligned}$

**（Lebesgue控制收敛定理：ver.2 - 逐点收敛的控制函数）令$\{f_n\}$为$E$上的可测函数序列，假定存在$E$上的非负可测函数列$\{g_n\}$，且在$E$上$|f_n|\leq g_n$，且在$E$上$a.e.\ pointwise\to g$。那么如若$f_n\ a.e.\ pointwise\to f$，$\begin{aligned}\lim\int_Eg_n=\int_Eg<+\infty\end{aligned}$，则$f$在$E$上可积，且$\begin{aligned}\lim\int_E f_n=\int_E f\end{aligned}$**

证：将ver.1的证明中的$g$修改为$g_n$.

即：$\begin{aligned}\int_E(g-f)\leq\lim\inf\int_E(g_n-f_n)=\int_E g-\lim\sup\int_E f_n\end{aligned}$

（等号成立的原因是著名的不等式：$\lim\inf A_n+\lim\inf B_n\leq\lim\inf(A_n+B_n)\leq\lim\sup A_n+\lim\inf B_ n$）

于是接下来的讨论就和之前一样是自然的了。



### 4.5 来换序吧！

1. **（$L^1$空间的收敛）$\{f_n\}$是$E$上的可积函数序列，使得$E$上$f_n\ a.e.\to f$，且后者可积。那么$\begin{aligned}\int_E|f-f_n|\to 0\iff\lim\int_E|f_n|=\int_E|f|\end{aligned}$**

 证：

$(\implies)$

$ \begin{aligned}\lim\int_E|f-f_n|=0\implies\lim\int_E||f|-|f_n||=0\\\implies|\lim\int_E (|f|-|f_n|)|=0\implies\lim\int_E|f|=\lim\int_E|f_n|\end{aligned}$



$(\Longleftarrow)$

考虑Lebesgue控制收敛定理，$|f_n-f|$被$g_n=|f_n|+|f|$在绝对值意义下控制。

但是$g_n\ a.e.\ pointwise\to 2|f|$且当然满足Lebesgue控制收敛定理使用的条件，于是结论自明。



2. **（实轴上反常积分）$f$为$\R$上非负可测函数，则$\begin{aligned}\lim\int_{-n}^{n}f=\int_\R f\end{aligned}$**

证：由于$f\cdot\chi_{[-n,n]}$被恒定的控制函数$|f|$控制，于是由Lebesgue控制收敛定理结论自明。

3. **（积分 - 极限换序）$f$为$[0,1]\times[0,1]$上的双变量实值函数$f(x,y)$，且固定每个$y$得到的关于$x$的函数是可测的。并且对于每个$x$，$\lim_{y\to 0}f(x,y)=f(x)$，且对每个$y$，有控制函数$|f(x,y)|\geq g(x)$，其中$g$在$[0,1]$上可积。**

**$\begin{CD}g(x)\\@VcontrolingVV\\f(x,y)@>\lim>> f(x)\\@VVV@VVV\\\int_{[0,1]} f(x,y)@>\lim>>\int_{[0,1]} f(x)\end{CD}$**

**那么$\begin{aligned}\lim_{y\to 0}\int_0^1 f(x,y)dx=\int_0^1 f(x)dx\end{aligned}$**

并且，如果$f(x,y)$对每个$x$在$y$连续，那么积分函数$h(y)=\begin{CD}\int_0^1 f(x,y)dx\end{CD}$是关于$y$的连续函数。

证：

