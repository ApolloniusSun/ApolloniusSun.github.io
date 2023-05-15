# Introduction to Commutative Algebra - Part1.

## 1. 环和理想

### 1.1 基本概念

本书中所有讨论的环$A$都是指交换幺环。

环同态是指保持环运算的环之间的映射。

理想是环作为加群的子群且对乘法封闭：$R\mathfrak{a}\subseteq\mathfrak{a}$

于是商群上也有环结构$A/\mathfrak{a}$，称为商环（$(r+\mathfrak{a})(s+\mathfrak{a})=rs+\mathfrak{a}$）

**（1.1：对应定理）**环$A$到商环$A/\mathfrak{a}$有典范同态，并且如同群中那样，$A$中包含$\mathfrak{a}$的理想与$A/\mathfrak{a}$的理想在典范同态下一一对应（前者为后者的完全逆像）

特殊地，任何环同态$A\to B$，核是$A$的理想，像是$B$的子环。

（**1.1a：即使对于一般的环同态，理想的逆像仍然是理想**：$\mathfrak{b}$是$B$中的理想$\implies (A/\mathfrak{a})\cap \mathfrak{b}$是$A/\mathfrak{a}$中的理想，验证即可）

零因子$x$是指满足$\exists y\neq 0\ s.t. \ xy=0$ 的元素$x$. 如果一个环没有这样的零因子，那么称它为整环。

幂零元$x$是指满足$\exists n>0\ s.t.\ x^n=0$的元素$x$. 于是幂零元是零因子。

单位$x$是指满足$\exists y\ s.t.\ xy=1$的元素$x$，记这样的$y$为$x^{-1}$：这个$y$是唯一确定的，因为如若$xy=xy'=1,y=y(xy')=(yx)y'=y'$

全体单位在乘法下构成了Abel群。

主理想$(a)=aA$是一个元素生成的理想，特别地$(0)=0,(1)=A$

域是满足每个非零元素都是单位的环（交换幺环），于是每个域都是整环：$xy=0\and xy'=1\implies 0=y'xy=y$



**（1.2：域）$A$是非零环，则以下等价**

**i. $A$是域	ii. $A$中的理想只有平凡理想	iii. 每个$A$到非零环$B$的环同态是单的**

证：$1\to 2$ 注意到非零元素都是单位，于是每个非零理想都包含1.

$2\to 3$ 考虑$\ker$即可。

$3\to 1$ 如果$A$中元素$x$不是一个单位，那么$(x)\neq(1)$，考虑$A\to A/(x)$的典范同态，后者不是零环，并且由单性，$(x)=(0)$，即$x=0$.



素理想$\mathfrak{p}$是一个非$(1)$的理想，且$xy\in\mathfrak{p}\implies x\in\mathfrak{p}\or y\in\mathfrak{p}$

极大理想$\mathfrak{m}$是一个理想，且满足不存在理想$\mathfrak{a}\ s.t.\ \mathfrak{m}\subset\mathfrak{a}\subset (1)$

于是自然可以验证：

$\mathfrak{p}$素$\iff A/\mathfrak{p}$是整环；$\mathfrak{m}$极大$\iff A/\mathfrak{m}$是域。

那么极大理想是素理想。零理想是素理想$\iff$环$A$是整环。

#### 极大理想的存在性

极大理想的存在性不是一个显然的结果。

**（1.3：极大理想的存在性 - Zorn引理）每个环$A\neq 0$至少有一个极大理想**

证：记全体非$A$的理想构成的集合为$\Sigma$，其上的偏序关系被定义为包含关系。

$0\in \Sigma$，于是$\Sigma\neq \empty$. 由Zorn引理，需证每条（全序）链在$\Sigma$中有上界。

设这条链是$(\mathfrak{a_\alpha})$，于是这个链实际上就是集合的升链，取$\mathfrak{a}=\cup \mathfrak{a}_\alpha$是一个理想，并且$1\notin\mathfrak{a}$，于是$\mathfrak{a}\in\Sigma$，并且是上界。从而运用Zorn引理即证。

自然有推论：

**（1.4: 包含特定理想的极大理想）如果$A$的理想$\mathfrak{a}\neq(1)$，那么存在一个包含$\mathfrak{a}$的极大理想。**

证：对$A/\mathfrak{a}$运用1.3，同时考虑对应定理（1.1）即证。

**（1.5: 包含特定元素的极大理想）每个$A$中的非单位元素被某个极大理想包含。**

证：考虑非单位元素生成的主理想即可。



同样地，值得考虑的是极小素理想。

**（1.E8: 包含特定理想的极小素理想）如果$\mathfrak{p}$是$A$中的素理想，$\mathfrak{a}$是理想，那么存在一个极小素理想使得$\mathfrak{p}\supseteq\mathfrak{q}\supseteq \mathfrak{a}$**

证：类似1.4化归到1.3的方法，同理1.3只需说明素理想降链的交还是素理想。

任意$yz\in\cap\mathfrak{p}$，存在$y,z$之一使得有无穷个$\mathfrak{p_i}$包含它，不妨设为$y$，由降链性质立刻$y\in\cap \mathfrak{p}$，从而交仍然是素理想，于是应用Zorn引理即证。

#### 局部环

一个环如果恰好仅有一个极大理想（例如：域）则称为局部环，那么域$k=A/\mathfrak{m}$称为剩余域。

**（1.6: 局部环的判定）**

**i. $A$是环且理想$\mathfrak{m}\neq(1)$，并且$\forall x\in A-\mathfrak{m}$是$A$的单位，则$A$是局部的，并且$\mathfrak{m}$是极大理想。**

**ii. $A$是环且$\mathfrak{m}$是极大理想，并且$1+\mathfrak{m}$的每个元素都是单位，那么$A$是局部环。**

证：

i. 每个非$(1)$理想都是由非单位元素组成的，于是在$\mathfrak{m}$中，从而$\mathfrak{m}$是唯一的极大理想。

ii. $\forall x\in A-\mathfrak{m}$，由于$\mathfrak{m}$极大，那么$(x,\mathfrak{m})=(1)$，即$\exists y\ s.t.\ xy+t=1(t\in\mathfrak{m})$

即$xy=1-t\in 1+\mathfrak{m}$是单位，从而$x$是单位：$(xy)z=1\implies x(yz)=1$.

即$\forall x\in A-\mathfrak{m}$，$x$是单位，由i.即证。



（有着有限个极大理想的环称为半局部环）

#### **素理想的拉回**

对于环同态$f:A\to B$，$B$中的素理想$\mathfrak{q}$拉回到$A$中仍然是素理想，因为$ A/f^{-1}(\mathfrak{q})\lesssim B/\mathfrak{q}$，且整环的子环仍然是整环。

Rmk. 极大理想的拉回不一定极大：$f: \Z\hookrightarrow\Q, \mathfrak{q}=0$. 原因是域的子环不一定还是域。

素理想的这个性质奠定了它在整个交换代数的重要地位。



### 1.2 幂零根和Jacobson根

**（1.7: 幂零根 - 小根）全体幂零元构成了$A$的理想$\mathfrak{R}$，且$A/\mathfrak{R}$中没有非零幂零元。这个理想称为幂零根。**

证：$x\in\mathfrak{R}\implies ax\in\mathfrak{R}$，$x\in\mathfrak{R}, y\in\mathfrak{R}$，设$x^m=y^n=0$，则$(x+y)^{m+n}=0$，于是$x+y\in\mathfrak{R}$，从而$\mathfrak{R}$是一个理想。

若$(a+\mathfrak{R})^n=\mathfrak{R}$，即$a^n+\mathfrak{R}=\mathfrak{R}$，于是$a^n\in \mathfrak{R}$，从而$(a^n)^k=0\ \exists k>0$，于是$a^{nk}=0\implies a\in \mathfrak{R}$，即$a+\mathfrak{R}=\mathfrak{R}$



**（1.8: 幂零根 - 等价定义）幂零根$\mathfrak{R}$是全体素理想的交。**

证：

设$\mathfrak{R}'=\cap_{prime} \mathfrak{p}$

对于幂零根中元素$f^n=0\in\mathfrak{p}$，那么$f\in\mathfrak{p}$。于是$\mathfrak{R}\subseteq\mathfrak{R'}$

反过来，我们证明：**1.8a: 对于一个不是幂零的元素$f$，存在一个素理想$\mathfrak{p}$使得它不包含任何$f$的幂。**

1.8a：记全体满足不包含任何$f$的幂的理想构成的集合为$\Sigma$，那么$0\in\Sigma$非空，应用Zorn引理，取偏序为包含关系，那么每个链有上界，从而$\Sigma$有极大元，设为$\mathfrak{p}$，我们说明$\mathfrak{p}$是素的。

任取$x,y\notin \mathfrak{p}$，那么理想$(x)+\mathfrak{p}, (y)+\mathfrak{p}$都是严格包含$\mathfrak{p}$的理想，从而都不在$\Sigma$内，于是对于$f,\exists m,n\ s.t. f^m\in (x)+\mathfrak{p}; f^n\in(y)+\mathfrak{p}$

从而$f^{m+n}\in (xy)+\mathfrak{p}$，于是$(xy)+\mathfrak{p}\notin\Sigma$，$xy\notin \mathfrak{p}$，从而$\mathfrak{p}$是素的。

于是对每个非幂零的元素$f$，找到了一个素理想不包含它，从而$\mathfrak{R}^c\subseteq\mathfrak{R'}^c$

于是$\mathfrak{R}=\mathfrak{R'}$



类似地，定义Jacobson根$J(A)$为全体极大理想的交，以及它的等价刻画：

**（1.9: Jacobson根 - 等价定义）$x\in J(A)\iff \forall y\in A,1-xy$是$A$中的单位。**

证：

$(\implies)$ 如果$1-xy$不是单位，设它被极大理想$\mathfrak{m}$包含，同时$x\in J(A)\subseteq \mathfrak{m}$，于是$1\in \mathfrak{m}$，矛盾。

$(\Longleftarrow)$  如果对于某个极大理想$\mathfrak{m}\ s.t.\ x\notin\mathfrak{m}$，那么$\mathfrak{m},x$生成了理想$(1)$，即$\exists u\in\mathfrak m, y\in A,\ s.t.\ u+xy=1$，那么条件：$1-xy$是单位就导出了矛盾。



### 1.3 理想的运算

#### 和、积、交

和：理想的和$\mathfrak{a+b}$仍然是理想，并且是$\mathfrak{a,b}$生成的理想。

对于无限个理想$\mathfrak{a}_i$，它们的直和被定义为全体$\sum_{finite\ non-zero\ terms}x_i $构成的集合，这也是理想，并且是包含诸理想的最小理想。

交：理想的交仍然是理想，并且全体理想构成了完备格。

积：理想$\mathfrak{a,b}$的积是全体$ab,a\in\mathfrak{a}.b\in\mathfrak{b}$生成的理想，于是归纳地定义了有限个理想的积。特殊地，我们定义了幂$\mathfrak{a}^n$，记$\mathfrak{a}^0=(1)$.



这三个运算都是交换且结合的，并且也有分配律$\mathfrak{a(b+c)}=\mathfrak{ab+ac}$.

对于另外运算组合的结合律，尽管在$\Z$中有较好的结果：$(m)+(n)=(gcd(m,n)), (m)\cap(n)=(lcm(a,b)), (m)(n)=(mn)$

对于一般的环上，最好的结果是：

**（Modular Law）$\mathfrak{a\cap(b+c)=a\cap b+a\cap c}$ 如果$\mathfrak{b\subseteq a}$.**

以及$\mathfrak{(a+b)(a\cap b)\subseteq ab}$ （因为$\mathfrak{(a+b)(a\cap b)=a(a\cap b)+b(a\cap b)\subseteq ab}$

以及$\mathfrak{ab}\subseteq \mathfrak{a\cap b}$

于是$\mathfrak{a\cap b=ab}\Longleftarrow \mathfrak{a+b=(1)}\iff \mathfrak{a,b}$互素。

（注意反方向不一定成立：取$\mathfrak{a}=0$，当然$\mathfrak{a\cap b=ab}=0$，但$\mathfrak{a+b}$当然不一定为$1$.）



对于一族有限个数的理想$\mathfrak{a_1\cdots a_n}$，有典范同态$\phi:A\to\prod(A/\mathfrak{a}_i)$

那么有：

**（1.10: 中国剩余定理）**

**a. 如果$\mathfrak{a_i,a_j}$两两互素，那么$\prod \mathfrak{a_i}=\cap \mathfrak{a_i}$**

**b. $\phi$是满射$\iff$ 理想$\mathfrak{a_i}$两两互素**

**c. $\phi$是单射$\iff \cap\mathfrak{a_i}=0$**

证：

a. 对理想个数$n$归纳，奠基已证。假定$n-1$成立，记$\mathfrak{b}=\cap ^{n-1}\mathfrak{a_i}=\prod^{n-1}\mathfrak{a_i}$

那么$\mathfrak{a_i}+\mathfrak{a_n}=(1)\implies x_i+y_i=1(x_i\in\mathfrak{a_i},y_i\in\mathfrak{a_n})$

于是$\prod x_i=\prod (1-y_i)\equiv1\mod\mathfrak{a}_n$

于是$\mathfrak{a_n+b}=(1)$.

应用奠基即证。

b. $(\implies)$ $\exists x\ s.t. \phi(x)=(1,0,\cdots,0)$ 

即$x\equiv 1\mod\mathfrak{a_1};x\equiv0\mod \mathfrak{a_2}$

于是$1=(1-x)+x\in\mathfrak{a_1+a_2}$，从而说明了$\mathfrak{a_1,a_2}$互素。

$(\Longleftarrow)$ 同样只需说明存在$\phi(x)=(1,0,\cdots,0)$有解，这将前述证明颠倒即可。

c. 显然$\ker \phi=\cap \mathfrak{a_i}$

（结合b,c就得到了中国剩余定理）



**（1.11: 回避引理、包容引理）**

Rmk. Atiyah中的回避引理和包容引理并非最强版本。

**（1.11a：回避引理）$\mathfrak{a_1,\cdots,a_n}$是环$R$的理想，且至多有2个不是素理想。如果理想$\mathfrak{b\subseteq\cup a_i}$，那么$\mathfrak{b}$被包含在某个$\mathfrak{a_i}$中。**

证：归纳：$n=1$显然。

$n=2$时，设$\mathfrak{b}\subseteq \mathfrak{a_1\cup a_2}$

若结论不成立，$\exists b_1\in \mathfrak{b}$，且$b_1\in \mathfrak{a_1-a_2}$；$\exists b_2\in \mathfrak{b}$，且$b_2\in \mathfrak{a_2-a_1}$

则$b_1+b_2\notin \mathfrak{a_i},i=1,2$，矛盾。

假设$n-1$时成立，$n(\geq3)$时：

记$\mathfrak{d_i}=\cup \mathfrak{a_i}$，若$\mathfrak{b}$不在任何一个$\mathfrak{d_i}$中，取$b_i\in \mathfrak{b-d_i}$，自然$b_i\in \mathfrak{a_i}$

设$\mathfrak{a_1}$素，令$y=b_1+b_2b_3\cdots b_n\in \mathfrak{b}$

若$y\in \mathfrak{a_1}$，则$b_2\cdots b_n\in\mathfrak{a_1}$，与$\mathfrak{a_1}$素理想矛盾。

若$y\in\mathfrak{a_i}(i\geq 2)$，$b_1\in \mathfrak{a_i}$，矛盾。

综上$y\notin \cup \mathfrak{a_i}$，矛盾。

从而$\mathfrak{b}$含于某个$\mathfrak{d_i}$，应用归纳假设即证。



**（1.11b：包容引理）$\mathfrak{a_1\cdots a_n}$是环$R$的理想，如果素理想$\mathfrak{p}\supseteq\prod \mathfrak{a_i}$（或特别地 $\mathfrak{p}\supseteq\cap\mathfrak{a_i}$）**

**那么$\mathfrak{p}$包含某个$\mathfrak{a_i}$。**

证：若结论不真，则$\forall i,\exists x_i\in \mathfrak{a_i}-\mathfrak{p}$，取$y=x_1\cdots x_n\in \prod\mathfrak{a_i}\in\mathfrak{p}$，与$\mathfrak{p}$素理想矛盾。

特别地，如果$\mathfrak{p}=\cap\mathfrak{a_i}$，由包容引理存在$\mathfrak{p\supseteq \mathfrak{a_i}}$，即$\mathfrak{a_i}\subseteq \cap \mathfrak{a_i}$，于是只有$\mathfrak{p=a_i}$

（当然$p=\prod \mathfrak{a_i}$时这个取等依然能够成立）



#### 商理想、零化子、根理想

对于环$A$中的理想$\mathfrak{a,b}$，其商理想定义为$(\mathfrak{a:b})=\{x\in A|x\mathfrak{b}\subseteq \mathfrak{a}\}$

（自行验证这的确是理想）

**（1.12: 商理想性质）**

**1. $\mathfrak{a}\subseteq\mathfrak{(a:b)}$** （显然）

**2. $\mathfrak{(a:b)b\subseteq a}$**（定义）

**3. $\mathfrak{((a:b):c)=(a:bc)=((a:c):b)}$**（只需证明左侧等号）

**4. $\mathfrak{(\cap a_i:b)=\cap(a_i:b)}$**（显然）

**5. $\mathfrak{(a:\sum b_i)=\cap (a:b_i)}$**

证：

3.  $\mathfrak{((a:b):c)}=\{x|\mathfrak{(}x\mathfrak{c)b\subseteq a}\}=\{x|x\mathfrak{bc\subseteq a}\}=\mathfrak{(a:bc)}$

5. $\mathfrak{(a:\sum b_i)}=\{x|x\sum \mathfrak{b_i\subseteq a}\}\xlongequal[\rightarrow take\ element\ from \mathfrak\ {b_{j\neq i}}\ as\ 0]{\leftarrow x\sum\mathfrak{b_i}\subseteq\sum\mathfrak{a=a}}\mathfrak{\cap (a:b_i)}$



特别地，在$\mathfrak{a}=0$时，$\mathfrak{(a:b)=(0:b)}=Ann(\mathfrak b)$



对于环$A$中的理想$\mathfrak{a}$，它的根理想$r(\mathfrak{a})$为$\{x\in A|x^n\in \mathfrak{a}\}$.

对于典范同态$\phi:A\to A/\mathfrak{a}$，$r(\mathfrak{a})=\phi^{-1}(\mathfrak{R}_{A/\mathfrak{a}})$. 即商模的幂零根的原像。

**（1.13: 根理想性质）**

**1. $r(\mathfrak{a})\supseteq \mathfrak{a}$** （显然）

**2. $r(r(\mathfrak{a}))=r(\mathfrak{a})$**

**3. $r(\mathfrak{ab})=r(\mathfrak{a\cap b})=r(\mathfrak{a})\cap r(\mathfrak{b})$**

**4. $r(\mathfrak{a})=(1)\iff \mathfrak{a}=(1)$**

**5. $r(\mathfrak{a+b})=r(r(\mathfrak{a})+r(\mathfrak{b}))$**

**6. 若$\mathfrak{p}$素，那么$r(\mathfrak{p}^n)=\mathfrak{p}$**

证：

2. $r(r(\mathfrak{a}))=\{x|x^n\in r(\mathfrak{a})\}=r(\mathfrak{a})$

3. $r(\mathfrak{ab})=\{x|x^n\in \mathfrak{ab}\}\xlongequal[\to this\ way\ trivial]{\leftarrow x^m\in\mathfrak{a}\cap\mathfrak{b},hence\ x^{2m}\in\mathfrak{ab}}r(\mathfrak{a\cap b})\xlongequal[trivial]{}r(\mathfrak{a})\cap r(\mathfrak{b})$

4. 只需证明向右的情况：

$r(\mathfrak{a})=(1)\implies \exists n,1^n\in  \mathfrak{a}\implies1\in\mathfrak{a}\implies  \mathfrak{a}=(1)$

5. $r(\mathfrak{a+b})=\{x|x^n\in\mathfrak{a+b}\}\xlongequal[\rightarrow\ trivial]{\leftarrow x^n\in r(\mathfrak{a})+r(\mathfrak{b}),say\ x^n=y+z,where\ y^p\in\mathfrak{a},z^q\in\mathfrak{b},x^{n(p+q)}\in\mathfrak{a+b}}r(r(\mathfrak{a})+r(\mathfrak{b}))$

6. $r(\mathfrak{p}^n)=\{x|x^t\in\mathfrak{p}^n\}\xlongequal[\to x^t\in\mathfrak{p},hence\ x\in\mathfrak{p}]{\leftarrow  trivial}\mathfrak{p}$



利用幂零根的等价性质，那么$r(\mathfrak{a})$是全体包含$\mathfrak{a}$的素理想之交。



**（1.16：根理想互素性质）$\mathfrak{a,b}$互素$\iff r(\mathfrak{a}),r(\mathfrak{b})$互素。**

证：$r(\mathfrak{a+b})=r(r(\mathfrak{a})+r(\mathfrak{b}))$，于是显然。



### 1.4 理想的扩张与局限

尽管有了对应定理，但是在一般的环同态下理想的像并不一定是理想（$\Z\hookrightarrow \Q$），1.1a保证了理想的拉回还是理想，基于这两个事实，定义出以下运算。

对于环同态$f:A\to B$，$A$中的理想$\mathfrak{a}$的扩张$\mathfrak{a}^e$定义为$f(\mathfrak{a})$生成的理想，$B$中理想$\mathfrak{b}$的局限定义为$f^{-1}(\mathfrak{b})$. 

前文已经说明了素理想的局限仍然是素的，但极大理想并不一定保持，另外素理想的扩张一般不是素的（$\Z\hookrightarrow \Q$）

导致扩张和局限的这些复杂情况的是环同态中的嵌入部分，即以下分解的后半部分：$A\twoheadrightarrow f(A)\hookrightarrow B$

（经典例子：$\Z\hookrightarrow\Z[i]$，实际上素理想在这样嵌入下诱导的扩张是代数数论的中心问题之一）



**（1.17: 扩张与局限的性质）记号同前，则：**

**1. $\mathfrak{a\subseteq a^{ec}, b\supseteq b^{ce}}$**

**2. $\mathfrak{a^e=a^{ece},b^c=b^{cec}}$**

**3. $C$是全体局限理想的集合，那么$C=\{\mathfrak{a}|\mathfrak{a=a^{ec}}\}$，$E$是全体扩张理想的集合，那么$E=\{\mathfrak{b}|\mathfrak{b=b^{ce}}\}$，于是自然$C,E$之间产生了双射：$\mathfrak{a\mapsto a^e,b\mapsto b^c}$**

证：1,2显然。

3. 设局限理想$\mathfrak{a=b^c,a^{ec}=b^{cec}=b^c=a}$，反过来如果$\mathfrak{a=a^ec}$，取$\mathfrak{b=a^e}$即说明$\mathfrak{a}$是局限理想。

对于$E$的讨论是完全同理的，从而自然有了双射。



**（1.18: 扩张、局限与其他运算的性质）$\mathfrak{a_1,a_2}$是$A$中的理想，$\mathfrak{b_1,b_2}$是$B$中的理想，那么：**

**1. $( \mathfrak{a}_1 + \mathfrak{a}_2)^{e}= \mathfrak{a}_1^{e}+ \mathfrak{a}_2^{e}\quad( \mathfrak{b}_1 + \mathfrak{b}_2)^{c}\supseteq \mathfrak{b}_1^{c}+ \mathfrak{b}_2^{c}$**

**2. $( \mathfrak{a}_1 \cap \mathfrak{a}_2)^{e}\subseteq \mathfrak{a}_1^{e} \cap \mathfrak{a}_2^{e}\quad ( \mathfrak{b}_1 \cap \mathfrak{b}_2)^{c}=\mathfrak{b}_1^{c}\cap \mathfrak{b}_2^{c}$**

**3. $( \mathfrak{a}_1 \mathfrak{a}_2)^{e}= \mathfrak{a}_1^{e}\mathfrak{a}_2^{e}\quad ( \mathfrak{b}_1 \mathfrak{b}_2)^{c}\supseteq \mathfrak{b}_1^{c} \mathfrak{b}_2^{c}$**

**4. $( \mathfrak{a}_1 : \mathfrak{a}_2)^{e}\subseteq \mathfrak{a}_1^{e}: \mathfrak{a}_2^{e}\quad( \mathfrak{b}_1 : \mathfrak{b}_2)^{c}\subseteq \mathfrak{b}_1^{c}: \mathfrak{b}_2^{c}$**

**5. $( r (\mathfrak{a}) )^{e}\subseteq r( \mathfrak{a}^{e})\quad ( r (\mathfrak{b}) )^{c}= r( \mathfrak{b}^{c})$**

**6. $E$对和与积封闭，$C$对交、商、根封闭**



### 1.5(E) 交换环的基本性质以及特殊例子

1. $x$是环$A$的幂零元，则$1+x$是单位；由此推出幂零元和单位的和还是单位。

证：如$x^n=0, (1+x)(1+(-x)+\cdots+(-x)^{n-1})=1-(-x)^n=1$

对于一般的情况，$u+x=u(1+u^{-1}x)$，而$(u^{-1}x)^n=u^{-n}x^n=0$

#### 多项式环$A[x]$的性质

2. 对于环上的多项式环$A[x]$，取$f=a_0+a_1x+\cdots+a_nx^n\in A[x]$

**2.1 $f$是单位$\iff a_0$是单位，且$a_1,\cdots, a_n$幂零**

**2.2 $f$幂零$\iff a_0,a_1,\cdots,a_n$幂零 **

**2.3 $f$是零因子$\iff\exists a\neq0,a\in A,af=0$**

**2.4 称$f$是本原的，若其系数生成了整个环。那么$fg$本原$\iff f,g$本原**

证：

2.1 $(\implies)$ $a_0$是单位显然。设$(a_0+a_1x+\cdots +a_nx^n)(b_0+b_1x+\cdots+b_mx^m)=1$

归纳说明$a_n^{r+1}b_{m-r}=0$，$r=0$显然。

假定$\leq r$成立，对于$r+1$，由于$a_nb_{m-r}+a_{n-1}b_{m-r+1}+\cdots=0$

于是$a_n^{r+1}b_{m-r}+a_{n-1}b_{m-r+1}a^{r}+a_{n-2}b_{m-r+2}a^r+\cdots=0$

即$a_n^{r+1}b_{m-r}=0$，取$r=m$，此时$a_n^{m+1}b_0=0$，但$b_0$是单位，于是$a_n^{m+1}=0$

从而由1.E1，$a_0+a_1x+\cdots+a_{n-1}x^{n-1}$是单位，于是递归下去即证。

$(\Longleftarrow)$ 由1.E1，$f=(a_0)+(a_1x+\cdots+a_nx^n)$是单位和幂零元的和，因此还是单位。

2.2 $(\implies)$ $f$幂零$\implies 1+f$单位，于是$1+a_0$单位，其余系数幂零。考虑0次项显然有$a_0$幂零。

$(\Longleftarrow)$ 设$a_t^{i_t}=0$，则$f^{\max{i_t}\cdot (n+1)}=0$

2.3 $(\implies)$ 选取$g=b_0+b_1+\cdots+b_mx^m$是最低次数满足$fg=0$的多项式

此时$a_nb_m=0$，那么$(a_n g)f=0$，而$a_n g$次数比$g$低，于是只能有$a_ng=0$，从而归纳下去证明$a_{n-r}g=0$

（例如$r:0\to 1$, $a_{n-1}b_m+a_{n}b_{m-1}=0\implies a_{n-1}b_m=0\implies(similarly) a_{n-1} g=0$）

于是考虑$b_0$，自然有$b_0a_{n-r}=0$，即$b_0f=0$。

（$\Longleftarrow$）显然。

2.4 $(\implies ) $ 如果$fg$本原，但$f$不本原，设$\mathfrak{a}=(a_0,\cdots,a_n)$，且$fg$的系数生成的理想被包含在了$\mathfrak{a}$当中，得到了矛盾。

$(\Longleftarrow)$ 如果$fg$不本原，设其系数生成的理想为$\mathfrak{I}$，那么考虑$A/\mathfrak{I}[x]$ 以及$f,g$在这之中的像$f^*,g^*$，则有$f^*g^*=0$，于是都是零因子。由2.3，存在一个$\overline{a}\in A/\mathfrak{I}, \overline{a}f^*=0$

即（设$f$系数为$a_0,\cdots$）$\exists a\notin \mathfrak{I}$，但$aa_i\in\mathfrak{I}$。即$(aa_0,\cdots,aa_n)\subseteq \mathfrak{I}$，但是$a\in(aa_0,\cdots,aa_n)$（因为$(a_0,\cdots,a_n)=(1)$），于是有$a\in\mathfrak{I}$，立刻得到矛盾。





3. 对于环上的多元多项式环$A[x_1,\cdots,x_n]$，取$f\in A[x_1,\cdots,x_n]$，且常数项为$a_0$，其余非零系数为$a_1,\cdots ,a_n$

**3.1 $f$是单位$\iff a_0$是单位，且$a_1,\cdots, a_n$幂零**

**3.2 $f$幂零$\iff a_0,a_1,\cdots,a_n$幂零** 

**3.3 $f$是零因子$\iff\exists a\neq0,a\in A,af=0$**

**3.4 $fg$本原$\iff f,g$本原**



**4. $A[x]$中小根（幂零根）和大根（Jacobson根）相同**

证：如果$f\in J(A[x])$，则$\forall g, 1-fg$是单位。设$f=a_0+a_1x+\cdots +a_nx^n$，取$g=-x$，$1-fg=1+a_0x+\cdots+a_nx^{n+1}$，那么$a_0,\cdots ,a_n$幂零，从而说明了$f$幂零，于是$f\in\mathfrak{R}$

而小根当然包含于大根，于是得证。

#### 形式幂级数环$A[[x]]$的性质

**5. 对于形式幂级数环$A[[x]]$，$f=\sum a_nx^n$**

**5.1 $f$是单位$\iff a_0$是单位**

**5.2 $f$幂零$\implies$每个系数幂零**

**5.3 $f\in J(A[[x]])\iff a_0\in J(A)$**

**5.4 对于嵌入$f:A\hookrightarrow A[[x]]$，极大理想的局限还是极大的，并且这个极大理想$\mathfrak{m}$由$\mathfrak{m}^c,x$生成。**

**5.5 $A$中的每个素理想都是$A[[x]]$中某个素理想的局限。**

证：

5.1 $(\implies)$显然

$(\Longleftarrow)$ $a_0$可逆，于是取$b_0=a_0^{-1}$，归纳地可以显式写出所有$b_i$

5.2 比较常数知$a_0$幂零，于是$f-a_0$幂零，比较一次项知$a_1$幂零，归纳即证。

反方向不成立（Noether环中成立）

5.3 $f\in J(A[[x]])\iff \forall g, 1-fg$是单位$\iff \forall b,1-a_0b$是单位$\iff a_0\in J(A)$

5.4 这只需证明$A[[x]]$中的极大理想形如$\mathfrak{m}_0+Ax+Ax^2+\cdots$，其中$\mathfrak{m}_0$是$A$的极大理想。

首先具有这样形式的理想当然是极大的。对于$A[[x]]$中的任意一个理想$\mathfrak{n}$，$\mathfrak{n}^c$当然还是理想，设包含$\mathfrak{n}^c$的$A$中的极大理想为$\mathfrak{m}_0$，那么理想$\mathfrak{n}\subseteq \mathfrak{m}_0+Ax+\cdots$，这就说明了极大理想只有如上形式。

5.5 $\mathfrak{p}=(\mathfrak{p}+Ax+Ax^2+\cdots)^c$

#### 幂零根、Jacobson根；素理想，极大理想

**6. 如果一个环$A$满足每个不被包含在某个幂零根的理想都包含了某个幂等元，那么这个环的幂零根和Jacobson根相同。**

证：设$x\in J(A)$，当然$(x)\neq (1)$。若$x\notin \mathfrak{R}_A$，那么$(x)$不被某个幂零根包含，于是包含了某个非零幂等元，设为$ax$。那么$a^2x^2=ax$，当然$1-ax$是单位。

又$1-ax=(1-ax)(1+ax)$，两侧乘上逆就有$1+ax=1\implies ax=0$，矛盾！



**7. 如果一个环$A$满足其每个元素都是幂等的，那么每个$A$中的素理想都是极大的。**

证：对于$A$中任一素理想$\mathfrak{p}$，商环$A/\mathfrak{p}$是整环，欲说明其为域，只需说明任意非零元素$a+\mathfrak{p}$有逆。设$a^n=a$，并且$n\geq 2$，那么$(a+\mathfrak{p})(a^{n-1}+\mathfrak{p})=(a+\mathfrak{p})$，于是$a^{n-1}+\mathfrak{p}=1+\mathfrak{p}$

从而$a+\mathfrak{p}$的逆取为$a^{n-2}+\mathfrak{p}$即可，于是得证。



**8. 极小素理想：See Previous Context**



**9. 设$\mathfrak{a}\neq(1)$是$A$的理想，则$\mathfrak{a}=r(\mathfrak{a})\iff\mathfrak{a}$是素理想的交。**

证：$(\Longleftarrow)$显然

$(\implies)$ 在$A/\mathfrak{a}$中，不存在非零幂零元，于是$A/\mathfrak{a}$的全体素理想的交是0. 拉回到$A$中即有$\mathfrak{a}$是某些素理想的交。



**10. 设$\mathfrak{R}$是环$A$的幂零根，那么以下三者等价：**

**1. $A$只有一个素理想**

**2. $A$中每个元素要么是单位，要么是幂零元。**

**3. $A/\mathfrak{R}$是域。**

证：

$1\to2$：条件指出仅有一个极大理想，那么这个极大理想一定包含了全体非单位元，但是这个极大理想（素理想）也正是幂零根。

$2\to 3:$ 显然

$3\to 1:$ 幂零根是极大理想，且为全体素理想的交，于是只能有素理想都是$\mathfrak{R}$，即只有一个素理想。



**11. 称一个环是布尔环如果$x^2=x,\forall x\in A$，那么在布尔环$A$中：**

**11.1 $2x=0\forall x\in A$**

**11.2 每个素理想$\mathfrak{p}$都是极大的，且$A/\mathfrak{p}$是2个元素构成的域。**

**11.3 每个有限生成的理想都是主理想。**

证：

11.1 $x^2=x,(x+1)^2=x+1\implies 2x=0$

11.2 前半部分是1.E7，后半部分只需发现$A/\mathfrak{p}$只有两个元素$0+\mathfrak{p},1+\mathfrak{p}$即可（考虑关系$(x+\mathfrak{p})^2=x+\mathfrak{p}$，以及这个商环是整环)

11.3 只需证明两个主理想生成了一个主理想。

这是因为$(x)+(y)=(x+y-xy)$，（注意到$x=x(x+y-xy)$ etc.）



**12. 每个局部环没有除$0,1$之外的幂等元。**

证：

若否，设为$a$，极大理想包含了所有的非单位。

如果$a$是单位，那么$1=a^{-1}a=a^{-1}a^2=a$，矛盾。于是$a$在极大理想$\mathfrak{m}$中。从而在Jacobson根中，于是$1-ax$是单位，特别地，取$a=1$。设$u(1-a)=1$，则$au(1-a)=a$，即$a=0$，矛盾。

#### 域的代数闭包构造(Artin.)

**13. 设$K$是域，$\Sigma$是全体$K$上首一的一元不可约多项式构成的集合。对于每个$f\in\Sigma$，指定一个元$x_f$，用$A$表示它们在$K$上生成的多元多项式环，设$\mathfrak{a}$是全体$f(x_f)$生成的理想，证明$\mathfrak{a}\neq (1)$**

**设$\mathfrak{m}$是包含$\mathfrak{a}$的极大理想，令$K_1=A/\mathfrak{m}$，于是$K_1$是$K$的扩域，且在其中每个$f\in\Sigma$都有根。对$K_1$重复以上操作，得到了一系列$K$，取$L=\cup K_i$是域，在其中的每个多项式$f\in\Sigma$都可分解成线性因式之积。用$\bar{K}$表示$L$中在$K$上代数的那些元素的集合，那么$\bar{K}$是$K$的代数闭包。**

证：如果$\mathfrak{a}=(1)$，那么存在某些多项式的线性组合为$1$，在分裂域中指定左侧的$x_f$为对应的根，即$0= 1$，矛盾。



**14. 取$\Sigma$为$A$中仅由零因子构成的理想的集合，那么$\Sigma$有一个极大元，并且每个这样的极大元都是素理想，从而说明$A$中零因子的集合可表示为素理想的并。**

证：极大元存在性是Zorn引理的直接推论（全序链上选取理想的并即可）

对于$\Sigma$的极大元$\mathfrak{p}$，$xy\in\mathfrak{p}$，那么$((x)+\mathfrak{p})((y)+\mathfrak{p})\subseteq \mathfrak{p}$

如果$((x)+\mathfrak{p}),((y)+\mathfrak{p})$均不在$\mathfrak{p}$中，那么一定存在$k_1,k_2\in A,p_1,p_2\in\mathfrak{p}\ s.t. k_1x+p_1,k_2y+p_2$均非零因子。

但是$(k_1x+p_1)(k_2y+p_2)\subseteq \mathfrak{p}$，于是是零因子。但两个非零因子不能乘出零因子，矛盾，于是必定存在一个理想（不妨为$((x)+\mathfrak{p})$）全部由零因子构成，从而属于（进而等于$\mathfrak{p}$）

于是$x\in\mathfrak{p}$，进而$\mathfrak{p}$素。

推论是显然的。



#### 素谱

**15.（Zariski拓扑：闭集） 设$A$是环，$X$是全体$A$中素理想构成的集合，称为素谱，记做$Spec(A)$。对于每个$E\subseteq A$，记$V(E)$为全体包含$E$的素理想构成的集合。**

**证明：**

**15.1 $\mathfrak{a}$是$E$生成的理想，那么$V(E)=V(\mathfrak{a})=V(r(\mathfrak{a}))$**

**15.2 $V(0)=Spec(A),V(1)=\varnothing$**

**15.3 $(E_i)_{i\in I}$是$A$的子集族，那么$V(\cup E_i)=\cap V(E_i)$**

**15.4 $\mathfrak{a,b}$是两个理想，$V(\mathfrak{a}\cap\mathfrak{b})=V(\mathfrak{ab})=V(\mathfrak{a})\cup V(\mathfrak{b})$**

**从而在$Spec(A)$中指定全体$V(E)$形式的集合为闭集，这样就生成了素谱上的拓扑，称为Zariski拓扑。**

证：

15.1 第一个等号显然，只需证明$V(\mathfrak{a})=V(r(\mathfrak{a}))$

考虑$A/\mathfrak{a}$，包含$0$的全体素理想当然是包含全体素理想的交的素理想。

15.2 显然

15.3 $\mathfrak{p}\in V(\cup E_i)\iff\mathfrak{p}\supseteq E_i \ (\forall i\in I)\iff \mathfrak{p}\in\cap V(E_i)$

15.4 $\mathfrak{p}\in V(\mathfrak{a\cap b})$，由包容引理立刻知道$\mathfrak{p}\in V(\mathfrak{a})\cup V(\mathfrak{b})$，即$V(\mathfrak{a\cap b})=V(\mathfrak{a})\cup V(\mathfrak{b})$

而$V(\mathfrak{ab})=V(r(\mathfrak{ab}))=V(r(\mathfrak{a})\cap r(\mathfrak{b}))=V(r(\mathfrak{a}))\cup V(r(\mathfrak{b}))=V(\mathfrak{a})\cup V(\mathfrak{b})$



**16.（例）$Spec(\Z),Spec(\R),Spec(\C[x]),Spec(\R[x]),Spec(\Z[x])$**

$Spec(\Z)$为全体$p_i\Z$构成的集合，其中的闭集为全体$p\Z$以及$\varnothing$和$Spec(\Z)$

$Spec(\R)=\{(0)\}$，于是闭集只能为$(0),\varnothing$

$Spec(\C[x])$是全体形如$(x-a)$或$(0)
$的理想，其中闭集为全体有限个$(x-a)$构成的集合以及$\varnothing$和$Spec(\C[x])$

$Spec(\R[x])$是全体0，一次多项式和二次不可约多项式生成的理想。其中闭集同样为全体一次多项式、二次不可约多项式生成的理想以及$\varnothing$和$Spec(\R[x])$

$Spec(\Z[x])$

$\Z[x]$素谱的Zariski拓扑是一个极其有趣的例子的特例，我们不妨考虑更一般的情况：$A$是一个Noether环，那么$Spec(A)$上的Zariski拓扑有着如下构造。

**Claim. Noether环$A$的Zariski拓扑中的每个闭集都可以表示成有限不可约闭集的并。**

利用Noetherian归纳。注意Noether环的素谱满足良基性，但一般情况不一定。

但是$Spec(A)$上的不可约闭集只能是单点的闭包，于是全体（真）闭集是素理想的闭包的有限并。

应用结果在$\Z[x]$上即可。



**17. （Zariski拓扑：开集）对于每个$f\in A$，取$X_f$为$V(f)$的补，那么这些集合都是Zariski拓扑的开集（称为主开集），则：**

**17.0 这些开集是Zariski拓扑的一组拓扑基。**

**17.1 $X_f\cap X_g= X_{fg}$**

**17.2 $X_f=\varnothing\iff f$是幂零**

**17.3 $X_f=X\iff f$是单位**

**17.4 $X_f=X_g\iff r((f))=r((g))$**

**17.5 $X=Spec(A)$是紧的拓扑空间**

**17.6 每个$f$，$X_f$都是紧的**

**17.7 对于任意开集$U$，$U$是紧的$\iff U$是$X_f$的有限并。**

（Rmk. Atiyah书中的quasi-compact（拟紧）对应着通常意义下的紧；书中的compact则指紧且Hausdorff的）

证：

17.0 对于每个开集$U=Spec(A)-V(E)$

取$Spec(A)-V(E)=\cup_{x\in E}(Spec(A)-V(x))$。于是每个开集都能被这一组开集生成，自然是拓扑基。

17.1 只需$V(f)\cup V(g)=V(fg)$，这正是1.E15.4.

17.2 $X(f)=\varnothing \iff V(f)=Spec(A)\iff f\in r(A)$

17.3 $X_f=X\iff V(f)=\varnothing\stackrel{非单位被极大理想包含}{\iff} f$是单位。

17.4 $X(f)=X(g)\iff V(f)=V(g)$，

但是$r((f))=\cap _{\mathfrak{p}\in V(f)}\mathfrak{p}$，于是得证。

17.5 只需说明对于任何一组拓扑基的开覆盖$(X_{f_i})_{i\in I}\supseteq X=Spec(A)$，存在一个有限子覆盖$(X_{f_i})_{i\in J}$

对于每个素理想$\mathfrak{p}$，都存在一个$f_i$不被$\mathfrak{p}$包含。

因此不存在包含$(f_i)_{i\in I}$的素理想（更进一步地，极大理想），于是只能有$(f_i)_{i\in I}=(1)$

于是自然有一个有限子族$J$使得$(f_i)_{i\in J}=(1)$，于是自然我们找到了这样的有限子覆盖。

17.6 只需说明对于任何一组拓扑基的开覆盖$(X_{f_i})_{i\in I}\supseteq X_f$，存在一个有限子覆盖$(X_{f_i})_{i\in J}$

对于每个素理想$\mathfrak{p}\not\supseteq f$，都存在一个$f_i$不被$\mathfrak{p}$包含。

因此不存在包含$(f_i)_{i\in I}$的素理想$\mathfrak{p}$满足$\mathfrak{p}\supseteq f$，于是只能有$((f_i)_{i\in I},f)=(1)$

于是自然有一个有限子族$J$使得$((f_i)_{i\in J},f)=(1)$，于是自然我们找到了这样的有限子覆盖。

17.7 $\Longleftarrow$方向是显然的，对于$\implies$方向：

对于任意开集$U=Spec(A)-V(E)$，如果它不能表示成有限开集的并，则覆盖$U=\cup _{x\in E} X_x$不存在有限子覆盖，从而不紧。



**18. （Zariski拓扑：$T_0$空间）记号方便起见，记Zariski拓扑空间$X=Spec(A)$中的点为$x$，如果它们被视作环中的素理想，就记这个素理想为$\mathfrak{p}_x$。那么：**

**18.1 单点集$\{x\}$是闭的$\iff\mathfrak{p}_x$极大。**

**18.2 $\overline{\{x\}}=V(\mathfrak{p}_x)$**

**18.3 $y\in\overline{\{x\}}\iff\mathfrak{p}_x\subseteq \mathfrak{p}_y$**

**18.4 $X$是$T_0$空间(Kolomogorov Space)。**

证：

18.1 1.E18.2的直接推论

18.2 注意到全体包含点$x$的闭集$V(E)$等价于$E\subseteq \mathfrak{p}_x$，即$\overline{\{x\}}=\bigcap_{E\subseteq\mathfrak p_x} V(E)=V(\mathfrak p_x)$

18.3 1.E18.2的直接推论

18.4 由于$x\neq y$，$\mathfrak p_x\not\subseteq\mathfrak p_y,\mathfrak p_y\not\subseteq\mathfrak p_x$至少有一成立，不妨前者成立。那么$x\in X-\overline{\{y\}},y\notin X-\overline{\{y\}}$，且$X-\overline{\{y\}}$是开的。



**19.（不可约空间） 称一个拓扑空间不可约，如果它不空且每对非空开集都有交；或等价地，每个非空开集都是稠密的。证明$Spec(A)$不可约$\iff A$的幂零根是素理想。**

证：前两个关于不可约叙述的等价性是显然的（若满足交性质但若不稠密，考虑补集的一个内点；若稠密，但不满足交性质，矛盾显然）

$(\Longleftarrow)$方向是显然的，因为这意味着$A$只有唯一的一个素理想。

$(\implies)$ 不可约要求非全集的闭集的并不是全集。即$V(x)\cup V(y)\neq X$，如果$x,y\notin r(A)$

那么$V(xy)\neq X$（由1.E17.1），即$xy\notin r(A)$，这说明$r(A)$是素的，从而得到了结论。



**20.（不可约分支） 对于拓扑空间$X$：**

**20.1 如果$Y$是$X$的不可约子空间，那么$Y$在$X$中的闭包$\overline{Y}$也是不可约的。**

**20.2 每个$X$不可约子空间都被某个极大不可约子空间包含。**

**20.3 所有$X$的极大不可约子空间都是闭的，并且它们覆盖了$X$，它们被称为不可约分支，Hausdorff空间的不可约分支是什么样的？**

**20.4 对于环$A$以及素谱$X=Spec(A)$，那么$X$的不可约分支是闭集$V(\mathfrak p)$，其中$\mathfrak p$是$A$中的极小素理想。**

证：

20.1 任一$\overline{Y}$中的非空开集$U$在$\overline{Y}$中的闭包是$\overline{U}\cap \overline{Y}$，但是$U\cap Y$作为$Y$中开集在$Y$中稠密，即$\overline{U\cap Y}\cap Y=Y$，即$Y\subseteq \overline{U\cap Y}$，于是$\overline Y\subseteq\overline{U\cap Y}$，于是只有$\overline{U\cap Y}=\overline{Y}$，从而$U$在$\overline{Y}$中稠密。

20.2 应用Zorn引理，只需证明对于一个不可约子空间的全序链$Y_1\subseteq Y_2\subseteq\cdots$，有上界。取上界$Y=\cup Y_n$，需要说明$Y$也是一个不可约子空间。

若否，即存在于$Y$相交的开集$U,V$使得$(U\cap Y)\cap (V\cap Y)=\varnothing$

由于$U$与$Y$相交，自然存在一个$i$使得$Y_i\cap U\neq\varnothing$，对$V$也可以同理找到这样的一个指标，取指标大者，仍设为$i$，那么$Y_i\cap U,Y_i\cap V$均非空。

但是$(U\cap Y_i)\cap (V\cap Y_i)=(U\cap V)\cap Y_i\subseteq (U\cap V)\cap Y\\=(U\cap Y)\cap (V\cap Y)=\varnothing$，与$Y_i$不可约矛盾。

20.3 1.E20.1保证了闭，1.E20.2中取不可约子空间遍历单点子空间保证了覆盖。

Hausdorff空间的不可约分支是全体单点集（实际上是全体不可约子空间，因为若有子空间$|X|\geq 2$，设$u\neq v\in X$，考虑分离它们的两个邻域$U,V$，于是在子空间中$U\cap X,V\cap X$是分离的并且非空，自然不交，矛盾。）

20.4

**Claim: 不可约闭子空间是全体形如$V(\mathfrak{p})$的闭集，其中$\mathfrak{p}$是素理想。**

C1. 如果$\mathfrak{p}$素，那么$V(\mathfrak{p})$不可约。

若否，则$\exists a,b$使得$X_a\cap V(\mathfrak{p})\neq\varnothing\and X_b\cap V(\mathfrak{p})\neq\varnothing$，但$(X_a\cap X_b)\cap V(\mathfrak{p})=\varnothing$，即$X_{ab}\cap V(\mathfrak{p})=\varnothing$，即$ab\in\mathfrak{p}$，即$a\in\mathfrak{p}\or b\in\mathfrak{p}$

但是$a\in\mathfrak{p}\implies \forall \mathfrak{I}\in V(\mathfrak{p}),a\in\mathfrak{I}\implies\mathfrak{I}\notin X_a\implies X_a\cap V(\mathfrak{p})=\varnothing$，矛盾。

C2. 如果$V(E)=V((E))\xlongequal{(E)=\mathfrak{a}}V(r(\mathfrak{a}))$不可约，那么$r(\mathfrak{a})$素。

若否，则$\exists a,b:ab\in r(\mathfrak{a})\and a\notin r(\mathfrak{a})\and b\notin r(\mathfrak{a})$

那么考虑$X_a\cap V(r(\mathfrak{a})),X_b\cap V(r(\mathfrak{b}))$不空（取$r(\mathfrak{a}),r(\mathfrak{b})$即可），但是$X_{ab}\cap V(r(\mathfrak{a}))$空（同前C1），与不可约矛盾。



由Claim，接下来结论显然，如果$V(\mathfrak{p})$极大，但$\mathfrak{p}$不极小，取更小的素理想$\mathfrak{q}$即矛盾；如果$\mathfrak{p}$极小，但$V(\mathfrak{p})$不极大，设有$V(\mathfrak{q})$包含它，那么$\mathfrak p\supset\mathfrak q$即矛盾。

综上得到结论。



**21.（环同态到素谱的推前）设$\phi:A\to B$是环同态，那么它自然诱导出了素谱（赋予Zariski拓扑）之间的映射$\phi^*:Y=Spec(B)\to X=Spec(A)$ ，**

$\begin{CD}A@>\phi>>B\\\\Spec(A)@<\phi^*<<Spec(B)\end{CD}$

**那么：**

**21.1 $f\in A$，$\phi^{*-1}(X_f)=Y_{\phi(f)}$，从而$\phi^*$连续。**

**21.2 $\mathfrak{a}$是$A$的理想，那么$\phi^{*-1}(V(\mathfrak a))=V(\mathfrak a^e)$**

**21.3 $\mathfrak b$是$B$的理想，那么$\overline{\phi^*(V(\mathfrak{b}))}=V(\mathfrak{b}^c)$**

**21.4 如果$\phi$是满射，那么$\phi^*$是$Y$到$V(\ker\phi)$的同胚（于是$Spec(A)$和$Spec(A/\mathfrak{R})$之间有自然同胚）**

**21.5 如果$\phi$是单射，那么$\phi^*(Y)$在$X$中稠密，更进一步地，$\phi^*(Y)$在$X$中稠密$\iff\ker\phi\subseteq\mathfrak{R}$**

**21.6 $\psi:B\to C$也是一个环同态，那么$(\psi\circ\phi)^*=\phi^*\circ\psi^*$**

**21.7 $A$是一个整环，且只有一个非零素理想$\mathfrak{p}$，$K$是$A$的分式域。取$B=(A/\mathfrak{p})\times K$，定义$\phi:A\to B:x\mapsto (\bar{x},x)$，其中$\bar{x}$是$x\in A$在自然同态下映到$A/\mathfrak{p}$中的像。那么$\phi^*$是双射但不是同胚。**

证：

21.1 $\mathfrak{b}\in \phi^{*-1}(X_f)\iff \phi^{-1}(\mathfrak{b})\in X_f\\\iff \phi^{-1}(\mathfrak b)\not\supseteq f\iff \phi(f)\not\subseteq \mathfrak{b}\iff\mathfrak{b}\in Y_{\phi(f)}$

21.2 $\mathfrak{q}\in\phi^{*-1}(V(\mathfrak a))\iff \phi^*(\mathfrak q)\in V(\mathfrak a)\iff\mathfrak a\subseteq \phi^*(\mathfrak q)\iff \mathfrak{q}\supseteq\mathfrak{a}^e$

21.3 $\overline{\phi^*(V(\mathfrak b))}\subseteq V(\mathfrak b^c)$是显然的，另一方向，由于$\overline{\phi^*(V(\mathfrak b))}=\overline{C\cap V(\mathfrak b^c)}=\overline{(C\cap X)}\cap\overline{V(\mathfrak b^c)}=\overline{(C\cap X)}\cap V(\mathfrak b^c)$

（$C$是全体局限理想）

因此只需说明$\overline{(C\cap X)}=V(0_B^c)$

即只需$V(0_B^c)\subseteq \overline{C\cap X}$

若$\exists x\in V(0_B^c)$，$f\in A$，$x\in X_f, X_f\cap C\cap X=\varnothing$，即$X_f\cap C=\varnothing$，那么$C\subseteq V(f)$。但是$B$中零理想的拉回$0_B^c\in C$，即$0_B^c\subseteq V(f)$，只能有$f\subseteq 0_B^c$，那么$X_f\cap V(0_B^c)=\varnothing$，这和$x$的存在矛盾。于是就说明了$V(0_B^c)\subseteq \overline{C}$

21.4 首先$\phi^*$是$Y\to V(\ker\phi)$的双射是显然的（对应定理，并且素理想的像还是素理想：$(A/\ker)/(\mathfrak{p/}\ker)\cong A/\mathfrak{p}$）

此时逆映射$\phi^{*-1}:\mathfrak p\mapsto\mathfrak p/\ker\phi$，那么开集$Y_{\mathfrak p/\ker\phi}$的原像正是$X_{\mathfrak p}$，于是说明了这是双连续映射，从而同胚。

21.5 由1.E21.3，$\overline{\phi^*(Y)}=\overline{\phi^*(V(0_B))}=V(0_B^c)$

那么原命题等价于$V(0_B^c)=X$，即$0_B^c$幂零，即$\ker \phi\subseteq \mathfrak{R}$

21.6 显然。

21.7 注意到$B=(A/\mathfrak p)\times K$是两个域（作为环）的直积，不妨记为$F\times K$

它的素理想有且仅有$(F,0);(0,K)$

这源于以下结论：

**Claim（环直积的理想结构）: $S=\prod^n R_i$（有限直积），那么$S$的理想一定是如下形式：$\prod^n P_i$，其中$P_i$是$R_i$的理想或者是$R_i$自身。**

证：

由归纳，只需$n=2$，考虑$R_1\times R_2\to R_1$，那么积环中的某个理想$I$在像下是$R_1$的理想$I_1$，同样有$I_2$。于是$\forall x_1\in I_1,\exists y_1\in R_2\ s.t. (x_1,y_1)\in I$，同样我们也能找到$(x_2,y_2)\in I$，那么$(x_1,y_2)=(1,0)(x_1,y_1)+(0,1)(x_2,y_2)\in I$，于是只有$I=I_1\times I_2$

**Claim（环直积的素理想结构）：$S=\prod^n R_i$，那么$S$的素理想一定是如下形式：$\mathfrak{p_i}\times\prod_{j\neq i}R_j$，其中$\mathfrak{p_i}$是$R_i$中的一个素理想。**

证：

由归纳，只需$n=2$，设$P$为$S$的素理想，则一定由形式$P=P_1\times P_2$。那么$S/P\cong R_1/P_1\times R_2/P_2$。此时$(\overline{1},0)(0,\overline{1})=(0,0)$，于是必须（事实上，不可能两个都是$0$）有一个$\overline{1}=0$，设为第一个，那么$R_1/P_1=0$，那么$S/P\cong R_2/P_2$，于是$P_2$是$R_2$的素理想，那么就证明了结论。



于是$(F,0)$和$(0)$对应；$(0,K)$和$\mathfrak{p}$对应。然而$(F,0)$闭，$(0)$开，从而$\phi^{*-1}$并不是连续映射，不是同胚。



**22.（环直积与连通分支） 设$A=\prod A_i$是环直积，那么$Spec(A)$是与$Spec(A_i)$自然同胚的空间$X_i$的不交并。**

**反之，对于任一环$A$，以下三者等价。**

**1. $X=Spec(A)$不连通。**

**2. $A\cong A_1\times A_2$，其中没有一个直因子是零环。**

**3. $A$有非$0,1$的幂等元。**

证：

对于同态$A\to A/\prod_{j\neq i} A_j\cong A_i$，由1.E21.4，它诱导了$Spec(A_i)$到$V(\prod_{j\neq i}A_j)$的同胚。

很容易验证$V(\prod_{j\neq i}A_j)$对不同的$i$是不交的。并且$A$的每个素理想都有结构$\mathfrak p_i\times\prod _{j\neq i}A_j$（**直积的素理想结构定理**）

那么就说明了这样的$V(\prod_{j\neq i}A_j)$的确覆盖了整个素谱。



接下来证明反过来的等价命题。

$1\implies 3$，若否，设$X=S_1\coprod S_2$，其中$S_1,S_2$是两个闭集，不妨设为具有形式$V(r(\mathfrak a)),V(r(\mathfrak b))$.

由于$V(r(\mathfrak{a}))\cap V(r(\mathfrak{b}))=\varnothing $，那么$r(\mathfrak{a})+r(\mathfrak{b})=(1)$

而$X=V(r(\mathfrak a))\coprod V(r(\mathfrak b))=V(r(\mathfrak a)\cap r(\mathfrak b))$，那么$r(\mathfrak a)\cap r(\mathfrak b )=\mathfrak R$

取$a\in\mathfrak a,b\in\mathfrak b$，且$a+b=1$，那么$a,b$不幂零（首先二者不可同时幂零，其次如果有一者幂零，那么另一者是单位，矛盾。），但是$ab$幂零。

设$a^nb^n=0$，那么$(a+b)^n=1\implies a^n+b^n=1+abf$是单位，设其逆位$g$，那么$a^ng+b^ng=1$。

如果$a^ng,b^ng$有平凡的情况，不妨$a^ng=0,b^ng=1$，就有$a^n=0$，矛盾。

于是它们不平凡，而$a^ng(1-a^ng)=a^ngb^ng=(ab^n)g^2=0$，从而$a^ng$是幂等的。

$3\implies 2$

对于这个非平凡幂等元$e$，$A=eA\oplus (1-e)A$

$2\implies 1$

$A$中素理想为$(A_1,\mathfrak{p_2})$或$(\mathfrak{p_1},A_2)$

那么全体包含了$A_1$的素理想和全体包含了$A_2$的素理想就是$Spec(A)$的两个连通分支，从而说明了$Spec(A)$不连通。



#### Stone定理

**23.（Boolean环$\to$紧Hausdorff空间）**

**$A$是Boolean环，$X=Spec(A)$**

**23.1 对每个$f\in A$，主开集$X_f$既开又闭。**

**23.2 对于$f_1,\cdots, f_n\in A$，$X_{f_1}\cup\cdots\cup X_{f_n}=X_f$对某个$f\in A$成立。**

**23.3 $X_f$是$X$中仅有的既开又闭的集合**

**23.4 $X$是紧致Hausdorff空间**

证：

23.1 只需说明闭，那么$V((f))\coprod V((1-f))=0$，于是$X_f=V((1-f))$从而闭。

23.2 $X_{f_1}\cup\cdots\cup  X_{f_n}=X-\cap V(f_i)=X-V(\cup f_i)\xlongequal[1.E11.3]{}X-V((f))=X_{1-f}$

23.3 如果$Y\subseteq X$既开又闭，$Y$开说明它是若干主开集的并，$Y$是闭的而$X$是紧的，于是$Y$也是紧的，那么$Y$一定是有限主开集的并，利用1.E23.2即证

23.4 对于任意素理想$f_1\neq f_2$，不妨$f_2\not\supseteq f_1$，那么$f_2\in X_{f_1}$，$f_1\in V_{f_1}$，被两个开集分离，于是Hausdorff。紧致性已证：1.E17.7。



**24. （Boolean环$\leftrightarrow$Boolean格）**

**Boolean格：指满足以下三个条件的格$L$。**

**1. $L$有最小元和最大元，记为$0,1$。**

**2. $\and,\or$之间相互有分配律**

**3. 对于每个$a\in L$，存在唯一的补元素$a'$使得$a\or a'=1,a\and a'=0$**



**对于一个Boolean格$L$，定义$L$上的运算为$a+b=(a\and b')\or(a'\and b), ab=a\and b$，可以验证这样得到的结构是一个Boolean环，记为$A(L)$**

**相反地，对于一个Boolean环$A$定义环中元素的需关系为$a\leq b\iff a=ab$，验证在这个序关系下得到的格是Boolean格。**

需要注意到$a\and b=ab,a\or b=a+b+ab$（若$a=ac,b=bc$，那么$(a+b+ab)c=a+b+ab$，并且$a+b+ab\geq a,b$的确成立，补元素定义为$a'=1-a$）

**于是我们建立起了Boolean格和Boolean环的一一对应（商去同构的情况）。**



**25. （Stone定理）每个Boolean格与一个紧Hausdorff空间的既开又闭集在包含关系下构成的格同构。**

证：只需要验证Boolean格$L$与$Spec(A(L))$中的开闭集在包含关系下构成的格同构。

Boolean格中的每个元素$f$对应着主开集 $X_f$

只需验证序关系仍然相同。

在格$L$中$a\leq b\iff a=ab\implies V(a)\supseteq V(b)\implies X_a\subseteq X_b $

在$Spec(A(L))$中，$X_a\subseteq X_b\implies V(a)\subseteq V(b)\implies V(1-a)\cap V(b)=\varnothing\\ \implies ((1-a),b)=(1)\stackrel{1.E11.3}\implies(1-a+b+(1-a)b)=(1)\\1-a+b+(1-a)b=1-a-ab单位$

设单位为$u$，则：

$b(1-a-ab)u=b\implies bu=b$

$a(1-a-ab)u=a\implies a(bu)=a\implies ab=a\implies a\leq b$



#### 极大谱，函数环

**26.（极大谱） 环$A$中$Spec(A)$有由全体极大理想构成的子空间，其上的拓扑定义为继承的子空间拓扑，称为极大谱，记为$Max(A)$，很显然极大谱没有1.E21中那样好的性质，因为极大理想拉回并不一定是极大理想。**

**（函数环）$X$是紧Hausdorff空间，$C(X)$是其上所有实值连续函数构成的环。对于每一点$x\in X$，取$\mathfrak{m}_x$为$C(X)$中全体在该点取值为0的函数构成的集合。这个理想$\mathfrak{m}_x$是一个极大理想，因为考虑赋值函数$C(X)\to \R:f\mapsto f(x)$，这个理想是环同态的核，而像集是域$\R$。**

**记$\widetilde{X}=Max(C(X))$，我们有了一个映射$\mu:X\to\widetilde{X}:x\mapsto \mathfrak{m}_x$**

**目标是证明$\mu$是一个$X$到$\widetilde{X}$的同胚。**

**26.1 对于$C(X)$的任意一个极大理想$\mathfrak{m}$，取公共零点集$V=V(\mathfrak{m})=\{x\in X|f(x)=0\forall f\in \mathfrak{m}\}$**

**如果公共零点集$V(\mathfrak{m})$是空的，那么$\forall x\in X,\exists f_x\in\mathfrak{m}$使得它在这一点不消失。由于连续性，可以保证扩展到$x$的某个邻域$U_x$，而$f_x$在$U_x$上不消失。由于紧性，开覆盖$\cup_{x\in X} U_x$存在有限子覆盖$U_{x_i}$，那么$f=f_{x_1}^2+\cdots+f_{x_n}^2$处处非零，从而在函数环$C(X)$中存在逆，即为单位。而$f\in \mathfrak m$，与极大理想矛盾。**

**因此$V(\mathfrak m)$不空。**

**对于任意一点$x\in V(\mathfrak m)$，$\mathfrak m\subseteq \mathfrak m_x$，由极大性只有$\mathfrak{m}=\mathfrak{m}_x$，从而$\mu$是满射。**

**26.2 由于紧致T2空间是T4的，从而可以应用Urysohn引理，存在一个连续实值函数将$X$中的点分离，于是$x\neq y\implies \mathfrak m_x\neq\mathfrak m_y$。（考虑分离函数$f:f(x)=0,f(y)=1$即可）从而$\mu$是单射。**

**26.3 对于$f\in C(X)$，取$U_f=\{x\in X|f(x)\neq 0\}=\text{supp}f$，$\widetilde{U}_f=\{\mathfrak{m}\in \widetilde{X}|f\notin \mathfrak{m}\}$，那么$\mu(U_f)=\widetilde{U}_f$，并且它们分别是$X,\widetilde{X}$的一组拓扑基，于是$\mu$是同胚。$X$可以从环$C(X)$中重建。**

26.3证：

$\mu (U_f)=\widetilde{U}_f$是显然的。

$U_f$构成$X$上拓扑的一组拓扑基是因为任何$X$中开集$U$，和$x\in U$，由Urysohn引理都存在连续函数$f_x$使得$f(X-U)=0,f(x)=1$，那么$x\in \text{supp} f_x\subseteq U$，现在让$x$遍历$U$，得到的$U_f$的并自然为$U$。

函数环$C(X)$的极大谱$\widetilde{X}$中的开集$U$一定能写成$(\cup X_f)\cap \widetilde{X}$的形式。而$U_f=X_f\cap \widetilde{X}$，于是立刻得证。



#### 仿射代数簇

**27. （仿射代数簇）设$k$是代数闭域，那么所有同时满足$f_\alpha(t_1,\cdots,t_n)=0(\forall\alpha)$的点$x\in k^n$称为一个仿射代数簇，记为$X$。**

**全体在$X$上消失的多项式构成了$k[t_1,\cdots,t_n]$的一个理想，记为$I(X)$。称它为簇$X$的理想。那么商环$P(X)=k[t_1,\cdots,t_n]/I(X)$是$X$上的多项式环。因为$k[t_1,\cdots,t_n]$中两个多项式$g,h$限制在$X$上诱导出了相同的多项式环$\iff (g-h)|_X\equiv 0\iff g-h\in I(X)$。**

**于是取$\xi_i$为$t_i$在典范映射$k[t_1,\cdots,t_n]\to P(X)$下的像，它称为坐标函数，因为$x\in X$则$\xi_i(x)$正是$x$的第$i$个坐标。$P(X)$作为$k-$代数由$\xi_i$生成。**

**如同1.E26中那样，对于每一个$x\in X$，$\mathfrak m_x=\{f\in P(X)|f(x)=0\}$是极大理想，于是有了映射$\mu:X\to\widetilde{X}:x\mapsto\mathfrak m_x$。**

**$\mu$是单射是因为如果$x\neq y$，一定有一个$i$使得$x_i\neq y_i$，于是$\xi_i -x_i\subseteq \mathfrak m_x$但$\not\subseteq \mathfrak m_y$**

**$\mu$是满射也是正确的，但是这是Hilbert Nullstellensatz的结果。**



**28. （多项式映射）设$f_1,\cdots, f_m\in k[x_1,\cdots,x_n]$，那么它们决定了一个多项式映射$\phi:k^n\to k^m: x\mapsto (f_1(x),\cdots, f_m(x))$**

**对于$k^n,k^m$中各自一个代数簇$X,Y$，称映射$\phi:X\to Y$是正则的，如果它是某个多项式映射$k^n\to k^m$在$X$上的限制。**

**对于$Y$上的任一多项式$\eta\in P(Y)$，$\eta\circ\phi$当然是$X$上的一个多项式。于是正则映射$\phi$诱导出了代数同态$P(Y)\to P(X)$，证明这是一个一一对应。**

证：只需考虑坐标函数在代数同态下仍然被映到坐标函数的多项式函数。

### 1.6 节末笔记



## 2. 模

### 2.0 引言

在交换代数中我们更多地考虑模而非理想是因为模给出了一些额外的操作空间，并且真正地将子结构（理想）和商结构（商环）放在了同一个层面上进行操作。

### 2.1 模和模同态

**定义：模**

**一个$A-$模是一个Abel群$M$，且$A$线性地作用在其上。即是一个偶对$(M,\mu)$，其中$M$是Abel群，$\mu:A\times M\to M$，满足$a(x+y)=ax+ay;(a+b)x=ax+bx;(ab)x=a(bx);1x=x$**

（亦即$M$和一个$A\to End(M)$的环同态）

例：

$A$是域$k$时成为$k-$线性空间。

$A=k[G]=k$上群代数时，$A-$模是一个$G$的$k-$表示。

**定义：模同态**

**称$A-$模$M,N$之间的映射$f:M\to N$是一个$A-$模同态，如果$f(x+y)=f(x)+f(y);f(ax)=af(x)$**

显然$A-$模同态的复合还是$A-$模同态。

全体$M\to N$的$A-$模同态可以构成一个$A-$模。

其中$(f+g)(x)=f(x)+g(x);(af)(x)=a\cdot f(x)$，记这个模为$Hom_A(M,N)$。

于是很自然地$u:M'\to M$；和$v:N\to N'$各自诱导了$\bar{u}:Hom_A(M,N)\to Hom_A(M',N)$；$\bar{v}:Hom_A(M,N)\to Hom_A(M,N')$两个$A-$模同态。

同样；每个$A-$模$M$都有一个自然同态$Hom(A,M)\cong M$，因为$A\to M$的$A-$模同态被$f(1)$唯一的确定了，但后者可以在$M$中任意选取。

**定义：子模，商模**

**$A-$模$M$的子模是一个$M$的子群$M'$且在$A$作用下封闭。商群$M/M'$上也有模结构：$a(x+M')=ax+M'$，称为商模。于是典范映射$M\to M/M'$是一个$A-$模同态。**

当然依然有对应定理和同构基本定理成立。

**核、余核：**

核的定义是自然的，余核可以看作满足以下正合列的模（于是在这里立刻看到来对称性）。

$\begin{CD}0@>>>\ker f@>>>A@>f>>B@>>>\text{coker} f@>>>0\end{CD}$

### 2.2 子模的运算

#### 和、交、积

和：$\sum M_i=\{\sum_{finite\ non-zero\ terms} x_i\}$仍然是子模，并且是包含诸$M_i$的最小的子模。

交：子模的交仍然是子模。（于是全体子模构成了完备格）

积：一般情况下并不能定义，但是可以定义$\mathfrak{a}M=\sum_{finite\ sum}a_ix_i$，其中$\mathfrak{a}$是$A$的理想。

类似群和环中的那样，依然有：

**（2.1：模同构定理）**

**1. $L\supseteq M\supseteq N$是$A-$模，那么$(L/N)/(M/N)\cong L/M$**

**2. $M_1,M_2$是$M$的子模，那么$(M_1+M_2)/M_1\cong M_2/(M_1\cap M_2)$**

证：

1. $L/N\to L/M:x+N\mapsto x+M$

2. $M_2\to M_1+M_2\to (M_1+M_2)/M_1$



#### 商理想，零化子，生成子模

对于$A-$模$M$中两个子模$N,P$，商理想被定义为$\{a\in A|aP\subseteq N\}$，是$A$的理想，依然记为$(N:P)$。特殊地$(0:M)$是全体使得$aM=0$的元素，称为模$M$的零化子，记为$Ann(M)$。

如果$\mathfrak{a}\subseteq Ann(M)$，$A-$模$M$也可以视作$A/\mathfrak{a}-$模：$\overline{x}m:=xm$

即，将$A\to End(M)$分解为$A\to A/\mathfrak a\to End(M)$

称一个$A-$模忠实，如果$Ann(M)=0$；$A-$模$M$作为$A/Ann(M)-$模一定是忠实的。

**（2.2: 零化子性质）**

1. **$Ann(M+N)=Ann(M)\cap Ann(N)$**

2. **$(N:P)=Ann((N+P)/N)$**

证：

1. 显然。
2. $x\in (N:P)\iff xP\subseteq N\iff x(N+P)\subseteq N\\\iff x[(N+P)/N]\subseteq\bar{0}\iff x\in Ann((N+P)/N)$



对于$x\in M$，$Ax:=\{ax|a\in A\}$是$M$的子模。如果$M=\sum Ax_i$，则称$(x_i)_{i\in I}$是一组生成元，即$M$的每个元素都可以表示为$x_i$的$A$有限线性组合。如果这个模有有限生成元，则称为有限生成模。



### 2.3 直和、直积

略，环直和、直积相关的内容已经介绍过了。

如果$A=\mathfrak{a_1}\oplus\cdots\oplus \mathfrak{a_n}$，那么$A\cong \prod (A/\mathfrak{b_i})$，其中$\mathfrak{b_i}=\oplus_{j\neq i}A_j$

于是$\mathfrak{a_i}\cong A/\mathfrak{b_i}$，并且其对应的单位元$e_i$（商环中单位元的同构像）在$A$中是幂等元，并且$\mathfrak{a_i}=(e_i)$

### 2.4 有限生成模

自由$A-$模是指形如$\oplus M_i$的模，其中每个$M_i\cong A$。因此有限生成模一定同构于$A\oplus\cdots\oplus A=A^n$。

**（2.3）$M$是有限生成模$\iff M$同构于某个$A^n$的商模。**

证：

$\implies$方向是因为考虑一组生成元$x_1,\cdots,x_n$，当然有同态$\phi:A^n\to M:(a_1,\cdots,a_n)\mapsto a_1x_1+\cdots+a_nx_m$。并且这个映射是满的。

$\Longleftarrow$ 方向是显然的：$\phi(0,\cdots,1,\cdots,0)$生成了$M$



**Rmk. Caution! 有限生成模的商模是有限生成的，但是子模不是！**

有限生成模的子模不有限生成的反例：

令$A=\{f|f\in \Q[x],且常数项为整数\}$是$\Q[x]$的子环，于是它作为$A-$模自然是有限生成的。

考虑子模$I=\{f|f\in\Q[x],且常数项为0\}$，它不有限生成。

若否，设生成元组为$f_1,\cdots,f_n$，则$I$中任意元素可表示成$g_1f_1+\cdots +g_n f_n,g_i\in A$。

考虑一次项，这相当于要求每个有理数可以被有限个有理数的$\Z-$线性组合表出，而这当然是不可能的。



**（2.4）$M$是有限生成$A-$模，$\mathfrak a$是$A$的理想，且某个$\phi\in End_A(M)=Hom_A(M,M)$满足$\phi(M)\subseteq \mathfrak aM$，那么$\phi$在$\mathfrak a$中有零化多项式。**

证：

设$M=<x_1,\cdots,x_n>$，由于$\phi(M)\subseteq \mathfrak aM$，$\phi(x_i)=\sum_{j=1}^na_{ij}x_j$，其中系数$a_{ij}\in \mathfrak a$

于是$\begin{pmatrix}\phi(x_1)\\\cdots\\\phi(x_n)\end{pmatrix}=A\begin{pmatrix}x_1\\\cdots\\x_n\end{pmatrix}$

即$(\phi I-A)\begin{pmatrix}x_1\\\cdots\\x_n\end{pmatrix}=O_{n\times 1}$

于是$\det (xI-A)$就是一个$\phi$的零化多项式。

**（2.5）$M$是有限生成 $A-$模，$\mathfrak a$是满足$\mathfrak aM=M$的理想。那么存在$x\equiv1 \mod\mathfrak a$且$xM=0$**

证：在2.4中取$\phi=id$，那么立刻就有$(a_n+\cdots+a_1+1)\cdot id=0$，即取$x=a_n+\cdots+a_1+1$满足要求。

**（2.6：Nakayama引理）$M$是有限生成$A-$模，$\mathfrak{a}\subseteq J(A)$，则$\mathfrak{a}M=M\implies M=0$**

证：由2.5，存在$x =1+a$满足$xM=0$，其中$a\in\mathfrak a\subseteq J(A)$。于是由Jacobson根的等价刻画，$x$是单位。

从而$M=x^{-1}xM=0$

2.6Rmk. Nakayama引理中有限生成的条件是必要的。

对于一个非域的局部整环$A$，$\mathfrak{m}$为其极大理想，$K$为分式域是$A-$模，则有非零的$x\in\mathfrak m$。但是$\forall z\in K, z=x(z/x)$，即$K=\mathfrak m K$，但是后者不为0。

**（2.7: 推论）$M$是有限生成$A-$模，$N$是$M$的子模，$\mathfrak a\subseteq J(A)$，那么$M=\mathfrak aM+N\implies M=N$**

证：

首先说明$\mathfrak a(M/N)=(\mathfrak a M+N)/N$

左侧元素形式均为$\sum_{finite}a_i (m_i+N)=\sum_{finite}a_im_i +N$

右侧元素形式均为$(\sum_{finite} a_im_i+n_i)+N=\sum_{finite} a_im_i+N$

从而的确是相等的。

在$M/N$上应用2.6Nakayama引理，它确实是有限生成的，且$\mathfrak a(M/N)=(\mathfrak aM+N)/N=M/N$，于是$M/N=0$，从而$M=N$。



对于一个局部环$A$，极大理想$\mathfrak m$，剩余域$k=A/\mathfrak m$。对于任何一个有限生成$A-$模$M$，商模$M/\mathfrak m M$由于被$\mathfrak m$零化，自然可以作为$A/\mathfrak m=k$上的模，从而成为了$k$上的线性空间，于是它是有限维的（因为它可以被有限生成：有限生成模的商模还是有限生成的）。

接下来的命题告诉我们这个线性空间上的基可以被提升回模的生成元。

**（2.8 局部环上模$M/\mathfrak m M$的性质）如果$x_i\in M$在$M/\mathfrak m M$中的像构成了$M/\mathfrak m M$的一组基，那么$x_i$生成了$M$。**

或者进一步地：$x_1,\cdots,x_n$生成了模$M\iff$ 其在$M/\mathfrak m M$中的像$\overline{x}_1,\cdots,\overline{x}_n$生成了$M/\mathfrak m M$

证：

当然核心部分还是$\Longleftarrow$，我们只需证明2.8中的情况。

设$N$是$x_1,\cdots,x_n$生成的子模，考虑$N\to M\to M/\mathfrak mM$复合出的映射，则$N+\mathfrak m M=M$

（Note：

$\forall x\in M, x=y+z,z\in \mathfrak mM, \overline{y}=a_1\overline{x}_1+\cdots+a_n\overline{x}_n,\\y=\overbrace{a_1x_1+\cdots+a_nx_n}^{y'}+z',z'\in\mathfrak mM,thus\ x=y'+(z'+z)\subseteq N+\mathfrak m M$）

于是由2.7，$N=M$。



### 2.5 正合序列，同态函子

（因为不是同调代数，不讨论Abel范畴，耶！）

称由$A-$模和$A-$模同态组成的序列：

$\begin{CD}\cdots@>>>M_{i-1}@>f_i>>M_i@>f_{i+1}>> M_{i+1}@>>>\cdots\end{CD}$

在$M_i$处正合，如果$Im f_i=Ker f_{i+1}$。 称一个序列是正合序列，如果它处处正合。正合序列可以两端没有尽头，也可以长度有限。

形如$\begin{CD}0@>>>M'@>f>>M@>g>>M''@>>>0\end{CD}$的正合列称为短正合列。它正合，当且仅当$g$诱导了$Coker(f)=M/f(M')$到$M''$的同构。

每个长正合列都能分裂成若干短正合列：记$N_i=Im(f_i)=Ker(f_{i+1})$，那么长正合列在$M_i$处分裂为$\begin{CD}0@>>>N_i@>>>M_i@>>>N_{i+1}@>>>0\end{CD}$。



对于（左）模范畴，有一个共变函子$Hom(M,\bullet):Mod\to Mod$（注意Hom自身也是一个模）：

它将$N$映到$Hom(M,N)$这个集合；将态射$N\stackrel{f}\to P$映到态射$Hom(M,N)\stackrel{f^*}\to Hom(M,P):r\mapsto f^*\circ r$上。

同样地也有反变函子$Hom(\bullet,M)$。



**（2.9 Hom函子的左正合性）**

**$A-$模序列$M'\stackrel{u}\longrightarrow M\stackrel{v}\longrightarrow M''\longrightarrow 0$正合$\iff$对于任何$A-$模$N$，序列$0\longrightarrow Hom(M'',N)\stackrel{v^*}\longrightarrow Hom(M,N)\stackrel{u^*}\longrightarrow Hom(M',N)$正合。**



**$A-$模序列$0\longrightarrow N'\stackrel{u}\longrightarrow N\stackrel{v}\longrightarrow N''、$正合$\iff$对于任何$A-$模$N$，序列$0\longrightarrow Hom(M,N')\stackrel{u^*}\longrightarrow Hom(M,N)\stackrel{v^*}\longrightarrow Hom(M,N'')$正合。**

（Rmk. 一般地，这两个函子并不一定是右正合的）



**（2.10: Zig-zag引理）对于一个行正合的交换图：**

$\begin{CD}@.M'@>u>>M@>v>>M''@>>>0\\@.@Vf'VV@VfVV@Vf''VV\\0@>>>N'@>>u'>N@>>v'>N''\end{CD}$

**有这样的蛇形正合列：**

$\begin{CD}@.Ker(f')@>>>Ker(f)@>>>Ker(f'')\\@.@VVV@VVV@VVV\\@.M'@>u>>M@>v>>M''@>>>0\\@.@Vf'VV@VfVV@Vf''VV\\0@>>>N'@>>u'>N@>>v'>N''\\@.@VVV@VVV@VVV\\@.Coker(f')@>>>Coker(f)@>>>Coker(f'')\end{CD}$

（这立刻让人回想起同调代数里的长正合列引理）

其中从右上到左下的同态称为边缘同态$d$，定义为$x''\in Ker(f''),\exists v(x)=x'',v'(f(x))=f''(v(x))=f''(x'')=0;\\f(x)\in Ker(v')=Im(u'),\exists u'(y')=f(x)$

$d(x'')$取为$y'$在$Coker(f')$里的像。（实际上边缘同态就是沿着对角线上的5个态射进行定义的）



**（2.11: 加性赋值）**

**一个加性赋值$\lambda$是模范畴到Abel群$G$的映射，满足，对于任意一个短正合列$0\to M'\to M\to M''\to 0$，$\lambda(M')-\lambda(M)-\lambda(M'')=0$**

**则对于任意一个长正合列$0\to M_0\to M_1\to\cdots\to M_n\to 0$，$\sum_{i=0}^n (-1)^i\lambda(M_i)=0$**

证：考虑长正合列的分裂即可。

Rmk. 自行回想同调代数中的例子。

### 2.6 模的张量积

**（2.12: 张量积）$A-$模$M,N$的张量积被定义为一个偶对$(T,g)$。其中$T$是一个$A-$模，$g:M\times N\to T$是双线性映射，满足泛性质：**

$\xymatrix{M\times N\ar[r]^-g\ar[dr]_{\forall f}& T\ar@{-->}[d]|{\exists !}\\&P}$

**那么张量积存在，并且在同构意义下唯一。**

证：

唯一性显然：

$\xymatrix{M\times N\ar[r]^-g\ar[rd]_{g'}& T\ar@<.5ex>[d]^f\\&T'\ar@<.5ex>[u]^{f'}}$

存在性只需要考虑全体$\sum_{finite} a_i(x_i,y_i)$形式的元素构成的模$C$（完全自由），然后商去全体$(x+x',y)-(x,y)-(x',y);(x.y+y')-(x,y)-(x,y')\\(ax,y)-a(x,y);(x,ay)-a(x,y)$生成的子模$D$

得到了一个商模$T=C/D$。

对于每个$(x,y)$，记$x\otimes y$为其像，于是$T$由$x\otimes y$生成，$g(x,y):=x\otimes y$。

当然可以迅速验证泛性质，任何一个双线性映射要求至少商去上述关系。



这样的模$T$记为张量积$M\otimes_A N$，如果$M$有生成元组$(x_i)$，$N$有生成元组$(y_i)$，那么张量积由$x_i\otimes_A y_j$生成。

注意：元素的张量积记号$x\otimes _A y$如果不指明所属的模是存在歧义的。

例如$2\otimes_\Z x$作为$\Z\otimes_\Z \Z/2\Z$的元素时为0，但是作为$2\Z\otimes_\Z \Z/2\Z$的元素时不是。

尽管如此，有这样的结果。

**（2.13）$x_i\in M,y_i\in N$满足在$M\otimes N$中$\sum_{finite} x_i\otimes y_i=0$，那么存在有限生成子模$M_0\leq M;N_0\leq N$使得在$M_0\otimes N_0$中$\sum_{finite} x_i\otimes y_i=0$**

证：

沿用2.12中的记号，$\sum_{finite } (x_i,y_i)\in D$；即为$D$生成元的有限和，设它们构成的集合为$S$

取$M_0$为$x_i$以及全体$S$中元素的第一个分量上的元素生成的子模；同样取$N_0$为$y_i$以及全体$S$中元素的第二个分量上的元素生成的子模。

那么在$M_0\otimes N_0$中$\sum_{finite} x_i\otimes y_i=0$



Note：**(2.13 alt.) 在子模$M_0,N_0$的情况中，如果在$M_0\otimes N_0$中$\sum_{finite}x_i\otimes y_i=0$，那么在$M\otimes N$中$\sum_{finite} x_i\otimes y_i=0$**

证：

考虑张量积的构造，$M_0\otimes N_0\cong (M_0*N_0)/R_0$，于是$\sum(x_i,y_i)\in R_0 $

那么由于$M\otimes N\cong (M*N)/R$，且$R_0\subseteq R$，自然$\sum (x_i,y_i)\in R$，于是在$M\otimes N$中$\sum x_i\otimes y_i=0$.





多重张量积也可以同样由多重线性映射构造得到（完全类似的泛性质）

$\xymatrix{M_1\times\cdots\times M_r\ar[r]^-g\ar[dr]_{\forall f}& T\ar@{-->}[d]|{\exists !}\\&P}$



**（2.14: 张量积的运算律）**

**对于$A-$模$M,N,P$，以下模之间存在唯一的自然同构。**

**1. $M\otimes N\to N\otimes M:x\otimes y\mapsto y\otimes x$**

**2. $(M\otimes N)\otimes P\to M\otimes (N\otimes P)\to M\otimes N\otimes P:\\(x\otimes y)\otimes z\mapsto x\otimes(y\otimes z)\mapsto x\otimes y\otimes z$**

**3. $(M\oplus N)\otimes P\to (M\otimes P)\oplus (N\otimes P):(x,y)\otimes z\mapsto (x\otimes z,y\otimes z)$**

**3alt. $(\oplus M_i)\otimes N\cong \oplus ( M_i\otimes N)$**

**4. $A\otimes M\to M:a\otimes x\mapsto ax$**

证：

这只需要验证即可：构造出两个方向的同态，以及说明它们的复合是恒等映射。

注意，3alt的证明略有不同，具体如下：

3alt: 

给定双线性映射：$f:(\oplus M_i)\times N \to \oplus (M_i\otimes N):(\cdots,m,\cdots),n\mapsto(\cdots,m\otimes n,\cdots)$

对于任意模$P$，每个双线性映射$h:(\oplus M_i)\times N\to P$限制在$M_i$上得到$h_i:M_i\times N\to P$，于是存在$g_i: M_i\oplus N\to P, h_i=f_i\circ g_i$.

将$g$定义为$(\oplus M_i)\otimes N\to P:(\cdots,m_i,\cdots)\otimes n\mapsto\sum g_i(m_i\otimes n)$

由泛性质，得证。



**（2.15：双模的张量积）$A,B$是环，$M$是$A-$模，$P$是$B-$模，$N$是$(A,B)-$双模（即两个模结构相容：$(ax)b=a(xb)$），那么$M\otimes_A N$是一个$B-$模：$(m\otimes n)b=m\otimes(nb)$，同理$N\otimes_B P$是一个$A-$模。**

**那么$(M\otimes_A N)\otimes_B P\cong M\otimes_A(N\otimes_B P)$**

证：

这只需要验证即可：构造出两个方向的同态，以及说明它们的复合是恒等映射。



自然地，模同态之间也有张量积：$f\otimes g(x\otimes y)=f(x)\otimes g(y)$

$\xymatrix{M\ar[d]\ar[r]^-f\ar@/^1.5pc/[rr]^{f'\circ f}& M'\ar[d]\ar[r]^-{f'}&M''\ar[d]\\M\otimes N\ar@/_1pc/[rr]_{(f'\circ f)\otimes (g'\circ g)}\ar[r]^-{f\otimes g} & M'\otimes N'\ar[r]^-{f'\otimes g'} &M''\otimes N''\\N\ar@/_1.5pc/[rr]_{g'\circ g}\ar[u]\ar[r]^-g&N'\ar[u]\ar[r]^-{g'}&N''\ar[u]}$

当然也有$(f'\circ f)\otimes (g'\circ g)=(f'\otimes g')\circ(f\otimes g)$

（如上交换图说明了一切：其实只是练习一下使用xymatrix）



### 2.7 纯量局限和扩充

回想起我们曾经将$A-$模视作$A/\mathfrak a-$模，它可以推广为：

**定义：纯量局限**

给定环同态$f:A\to B$，$B-$模可以视作$A-$模：$ax:=f(a)x$

这实际上相当于将$B\to End(M)$变为了$A\to B\to End(M)$

**（2.16: 局限保持有限生成性）$f:A\to B$是环同态。$N$是有限生成$B-$模；环$B$作为$B-$模当然也可以看作$A-$模，如果它作为后者有限生成，那么$N$纯量局限为$A-$模后也是有限生成的。**

证：设$y_i$生成$B-$模$N$，$x_i$生成$A-$模$B$，那么$x_iy_j$生成$A-$模$N$。

因为$x\in N$，$x=\sum_i b_iy_i=\sum_i(\sum_j a_{ij}x_i)y_j=\sum_{i,j}a_{ij}x_iy_j$



我们自然想问上述操作反过来是否能够进行，即给定环同态：$f:A\to B$和一个$A-$模$M$，能否构出一个$B-$模？

首先显而易见的是肯定不能够直接将$M$视作一个$B-$模。回想起在定义双模张量积时所做的，自然可以用张量积来完成构造。

**定义：纯量扩充**

给定环同态$f:A\to B$，那么$B$作为$A-$模可以得到$A-$模：$M_B=B\otimes_A M$，它可以视作一个$B-$模：$b(b'\otimes m)=(bb')\otimes m$

**（2.17：扩充保持有限生成性）$M$是有限生成$A-$模，那么$M_B$是有限生成$B-$模**

证：如果$x_1,\cdots,x_m$生成了$M$

$x\in M_B,\ x=\sum b_i\otimes m_i=\sum b_i(1\otimes m_i)\\=\sum b_i\left[1\otimes(\sum a_{ij} x_j)\right]=\sum a_{ij}b_i (1\otimes x_j)=\sum f(a_{ij}b_i)(1\otimes x_j)$

于是$1\otimes x_1,\cdots,1\otimes x_m$生成了$M$。



### 2.8 张量函子

首先可以看出同态函子和张量函子$\bullet\otimes N$互为伴随：

$Hom(M\otimes N,P)\cong Hom(M,Hom(N,P))$（回想一下双线性映射的定义即可）

张量函子当然是共变的：$M\to M'\implies M\otimes N\to M'\otimes N$：通过张量积。

**（2.18: 张量函子的右正合性）**

**$\xymatrix{M'\ar[r]^f& M\ar[r]^g&M''\ar[r]&0}$是$A-$模的正合列，那么：**

**$\xymatrix{M'\otimes N\ar[r]^{f\otimes 1}& M\otimes N\ar[r]^{g\otimes 1}&M''\otimes N\ar[r]&0}$也是正合列。**

证：

利用同态函子的左正合性：

$\xymatrix{0\ar[r]&Hom(M'',Hom(N,P))\ar[r]&Hom(M,Hom(N,P))\ar[r]&Hom(M',Hom(N,P))}$正合，于是：

$\xymatrix{0\ar[r]&Hom(M''\otimes N,P)\ar[r]&Hom(M\otimes N,P)\ar[r]&Hom(M'\otimes N,P)}$正合。

由于$P$的选取是任意的，利用同态函子的左正合性：$\xymatrix{M'\otimes N\ar[r]^{f\otimes 1}& M\otimes N\ar[r]^{g\otimes 1}&M''\otimes N\ar[r]&0}$是正合的。



正如同态函子中出现的那样，张量函子也不一定是左正合的。

如果张量函子$\bullet \otimes N$总是正合的，那么称$N$是平坦模。



**（2.19: 平坦模）对于$A-$模$N$，以下等价：**

**1. $N$是平坦的。**

**2. 对于任何正合列$0\to M'\to M\to M''\to 0$，$0\to M'\otimes N\to M\otimes N\to M''\otimes N\to 0$**

**3. 如果$f:M'\to M$单射，那么$f\otimes 1: M'\otimes N\to M\otimes N$是单射**

**4. 如果$f:M'\to M$单射且$M,M'$有限生成，那么$f\otimes 1: M'\otimes N\to M\otimes N$是单射**

证：

$1\iff 2$ 将正合列分裂。

$2\iff 3$ 3实际上就是左正合性。

$3\implies 4$ 显然。

$4\implies 3$ 

设$u=\sum x'_i\otimes y_i\in \ker (f\otimes 1)$，即在$M\otimes N$中$\sum f(x'_i)\otimes y_i=0$

由2.13，存在$M,N$的有限生成子模$M_0,N_0$，在$M_0\otimes N_0$中$\sum f(x_i')\otimes y_i=0$

设$M_0'$是由$x_i'$生成的子模，那么$u_0=\sum x_i'\otimes y_i$作为$M'_0\otimes N$的元素。

回想2.13的证明，当然可以使$M_0$包含$f(M'_0)$，于是由2.13alt，$M_0\otimes N$中$\sum f(x_i')\otimes y_i=0$。

设$f_0=f|_{M_0'}:M_0'\to M_0$，那么由条件（4)，$(f_0\otimes 1)(u_0)=0$且是单射，于是$u_0=0$，自然（2.13alt）$u=0$.



**（2.20: 扩充保持平坦性）$f:A\to B$是环同态，$M$是平坦$A-$模，那么$M_B=B\otimes_A M$是平坦$B$模。**

证：

只需说明对于任意$B-$模：$f:N'\to N$单射，则$f\otimes 1:N'\otimes_B M_B\to N\otimes_B M_B$是单射。

那么由于$N'\otimes_B(B\otimes_A M)=(N'\otimes_B B)\otimes _A M=N'\otimes_A M$

以及$M$的平坦性立刻得证。



**Rmk. 自由模$A^n$是平坦的：$M'\otimes N\to M\otimes N=\oplus(M'\otimes A\to M\otimes A)=\oplus (M\to N)$当然单。**



### 2.9 代数

**定义：$A-$代数**

对于环$A$，一个$A-$代数是一个环$B$和一个环同态$f:A\to B$。由纯量局限，这个环$B$当然具有了$A-$模结构。

例：

当$A$是域的时候。环同态当然是单射，因此$B$是包含域$K$的环。

每个环$B$都自动成为一个$\Z-$代数（$n\mapsto n\cdot 1$



**定义：$A-$代数同态**

对于$A-$代数$B,C$（其中对应的环同态分别为$f:A\to B;\ g:A\to C$）

称$B,C$之间的代数同态为映射$h:B\to C$，且它既是环同态，也是$A-$模同态。

**$h$是代数同态$\iff h\circ f=g$ **

证：

只需验证$(\implies)$

这要求$a h(b)=h(ab)\iff g(a)h(b)=h(f(a)b)\\\stackrel{Ring\ Hom.}\iff g(a)h(b)=h(f(a))h(b)$

最后一式取$b=1$即得$h\circ f=g$。



**定义：代数的有限；有限生成**

称一个$A-$代数有限，如果它作为$A-$模有限生成，此时称对应的环同态$f:A\to B$有限。

称一个$A-$代数有限生成，如果存在一组元素$x_1,\cdots,x_n$，使得代数中每个元素都可以写成它们$f(A)$系数的多项式形式，亦即存在一个$A[t_1,\cdots,t_n]\to B$的$A-$代数同态，此时称对应的环同态$f:A\to B$是有限型的。



### 2.10 代数的张量积

对于$A-$代数$B,C$，定义它们的张量积是$D=B\otimes _A C$.

定义$D$上的乘法$\mu:D\times D\to D:\mu(b\otimes c,b'\otimes c')=bb'\otimes cc'$，并将其按线性扩展到整个张量积$D=B\otimes_A C$

它良定义是因为：

4-线性映射$B\times C\times B\times C\to D:(b,c,b',c')\mapsto bb'\otimes cc'$诱导了$A-$模同态$B\otimes C\otimes B\otimes C\to D$；由自然同构，诱导了$A-$模同态$D\otimes D\to D$；于是诱导了双线性映射$D\otimes D\to D$。它正是具有上面所给出的形式的映射。



$D$在这个乘法下构成了交换幺环是因为取零元$0\otimes 0$，幺元$1\otimes 1$即可，于是$D$是一个$A$代数，其中环同态$A\to D: a\mapsto f(a)\otimes g(a)$。

事实上有交换图：

$\xymatrix{&B\ar[rd]^u&\\A\ar[dr]_g\ar[ur]^f&&D\\&C\ar[ur]_v}$，其中$u(b):=b\otimes 1$.

由于 $u\circ f(a)=f(a)\otimes 1$, $v\circ g(a)=1\otimes g(a)$

而$f(a)\otimes 1=a(1_B\otimes 1_C)=1\otimes g(a)$，交换性立刻得证。



### 2.11(E)

#### 模的性质

**1. $(\Z/m\Z)\otimes_\Z (\Z/n\Z)= \Z/(m,n)\Z$**

证：

有双线性映射$(\Z/m\Z)\times (\Z/n\Z)\to \Z/(m,n)\Z:(x,y)\mapsto xy$，容易验证良定义。

由泛性质，自然有模同态$f$：$(\Z/m\Z)\otimes_\Z (\Z/n\Z)\to \Z/(m,n)\Z:x\otimes_\Z y\mapsto xy$

而还有模同态$g：\Z/(m,n)\Z\to(\Z/m\Z)\otimes_\Z(\Z/n\Z):1\mapsto a$

那么$g\circ f(x\otimes_\Z y)=1\otimes_\Z xy=x(1\otimes_\Z y)=x\otimes_Z y$

$f\circ g(x)=x$

于是这是模同构，从而得证。



**2. $\mathfrak a$是$A$的理想，$M$是$A-$模，那么$(A/\mathfrak a)\otimes_A M\cong M/\mathfrak aM$**

证：

由于张量函子是右正合的，对于正合列：

$\mathfrak a\to A\to A/\mathfrak a\to 0$

有正合列：

$\xymatrix{\mathfrak a\otimes_A M\ar[r]&A\otimes_A M\ar[r]&(A/\mathfrak a)\otimes_A M\ar[r]&0}$

而第二项正是$M$，因此只需说明$\mathfrak a\otimes_A M\cong \mathfrak aM$

而这是显然的：$\mathfrak a\otimes_A M=1\otimes_A(\mathfrak aM)\cong \mathfrak a M$

于是就得到了结论。



**3. $A$是局部环，$M,N$是其上的有限生成$A-$模，那么$M\otimes_A N=0\implies M=0\ or\ N=0$**

证：

考虑极大理想$\mathfrak m$，和剩余域$k=A/\mathfrak m$，$M_k=k\otimes _A M\cong M/\mathfrak m M$。由Nakayama引理，$M_k=0\implies M/\mathfrak m M=0\implies \mathfrak m M=M\implies M=0$



但是$M\otimes_A N=0\implies \overbrace{k\otimes_A (M\otimes_A N)}^{as\ a\ k-module}=0\implies \overbrace{M\otimes_A(k\otimes_A N)}^{as\ a\ k-module}=0\\\implies \overbrace{(k\otimes_AM)}^{as\ a\ k-module}\otimes_k\overbrace{(k\otimes_A N)}^{as\ a\ k-module}= \overbrace{(M\otimes_A\underbrace {k}_{as\ a\ A,k-bimodule})}^{as\ a\ k-module}\otimes_k\overbrace{(k\otimes_A N)}^{as\ a\ k-module}\\=M\otimes_A\overbrace{\left[\underbrace{k}_{as\ a\ A,k-bimodule}\otimes_k(\overbrace{k}^{as\ a\ A,k-bimodule}\otimes_A N)\right]}^{as\ a\ A-module}=M\otimes_A \left[ \overbrace{(k\otimes_k k)}^{as\ a\ A-module}\otimes_A N\right]\\=\overbrace{M\otimes_A(k\otimes_A N)}^{as\ a\ k-module}=0$

即$M_k\otimes_k N_k=0$，但是这是线性空间的张量积，于是至少有一者为0，不妨$M_k=0$，于是由前述$M=0$。



**4. （模直和的平坦性）对于一族$A-$模$M_i(i\in I)$，$M=\oplus M_i$，则$M$平坦$\iff M_i$平坦$\forall i\in I$ **

证：

Claim $N\otimes(\oplus M_i)\cong \oplus (N\otimes M_i)$

（See. 2.14.3alt）

那么$M$平坦$\iff$ 对每个单射$f:N\to N'$，$f\otimes1:N\otimes M\to N'\otimes M$单射 $\iff$ $\oplus(N\otimes M_i)\to \oplus(N'\otimes M_i)$单射$\iff$对每个$i$，$N\otimes M_i\to N'\otimes M_i$单射$\iff M_i $平坦$\forall i$  



**5. $A[x]$是$A$上的一元多项式环，则$A[x]$是平坦$A-$代数。**

证：

由于$A[x]\cong \oplus A$, 且$A$是平坦$A-$模：$M\otimes_A A=M$，结合2.E4得到结果。



**6. $M[x]$是全体$M$系数的一元多项式构成的集合，自然是一个Abel群。$A[x]$中元素以多项式乘法的形式作用在$M[x]$上，于是$M[x]$成为$A[x]-$模。**

**那么$M[x]\cong A[x]\otimes_A M$**

证：对于双线性映射$A[x]\times M\to M[x]: (f,m)\mapsto fm$

自然诱导出了模同态$A[x]\otimes _A M\to M[x]: x^n\otimes_A m\mapsto mx^n$

另一方面取同态$M[x]\to A[x]\otimes_A M:mx^n\mapsto x^n\otimes_A m$

即说明了是同构，从而得到结果。



**7. $\mathfrak p$是$A$的素理想，则$\mathfrak p[x]$是$A[x]$的素理想；上述结论对极大理想不再成立。**

证：考虑系数的投影映射$\pi: A[x]\to (A/\mathfrak p)[x]$，后者作为域上多项式环是整的。而$\ker \pi=\mathfrak p[x]$，由基本定理得$A[x]/\mathfrak p[x]=(A/\mathfrak p)[x]$是整环，从而是素理想。

极大理想不成立，因为$\mathfrak{m}[x]\subset <\mathfrak m,x>$



**8. （平坦性的保持）**

**8.1 如果$M,N$是平坦$A-$模，那么$M\otimes_A N$也是平坦$A-$模。 **

**8.2 如果$B$是平坦$A-$代数（纯量局限）且$N$是平坦$B-$模，那么$N$是平坦$A-$模。**

证：

8.1

对于任意一个单的模同态$T\to T':injective$

$N\otimes T\to N\otimes T'$是单的，于是$M\otimes(N\otimes T)\to M\otimes (N\otimes T')$是单的，即$(M\otimes N)\otimes T\to (M\otimes N)\otimes T'$是单的，于是$M\otimes N$平坦。

8.2

对于任意一个单的模同态$T\to T':injective$

$B\otimes_A T\to B\otimes_A T'$是单的，于是$N\otimes_B(B\otimes_AT)\to N\otimes_B(B\otimes_A T')$是单的，于是$(N\otimes_BB)\otimes_A T\to(N\otimes_BB)\otimes_A T'$是单的，即$N\otimes_AT\to N\otimes_AT'$是单的，从而$N$是平坦$A-$模。



**9. 给定$A-$模正合列$\xymatrix{0\ar[r]&M'\ar[r]^f&M\ar[r]^g&M''\ar[r]&0}$，$M',M''$有限生成，则$M$有限生成。**

证：

设$M'$的生成元组为$j_1,\cdots,j_s$；$M''$的生成元组为$k_1,\cdots, k_t$。并且在$M$中选取出一组元$l_1,\cdots,l_t$使得$g(f_i)=d_i$.

那么$\forall m\in M,m=m_1+m_2$，其中$m_1\in <l_1,\cdots,l_t>,m_2\in \ker g$（考虑$g(m)\in <k_1,\cdots,k_t>$即可。

然而$m_2\in \ker g=im f,m_2=f(m')=\sum a_if(j_i)$

于是$f(j_i);l_i$构成了$M$的生成元，从而证明了有限生成。



**10. $A$是环，$\mathfrak{a}\in J(A)$。$M$是$A-$模，$N$是有限生成$A-$模，以及模同态$u:M\to N$。 如果诱导出的$M/\mathfrak aM\to N/\mathfrak aN$是满射，那么$u$是满射。**

证：

由于$M/\mathfrak aM\to N/\mathfrak aN$是满射，$\forall n,\exists m \ s.t. \ f(m)-n\in\mathfrak aN$。于是$N/imu\subseteq \mathfrak (a N+imu)/imu=\mathfrak a(N/imu)$

反向包含是显然的，于是$N/imu=\mathfrak a(N/imu)$

由Nakayama引理，只有$N/imu=0$，即$N=imu$，$u$是满射。



**11. **

**11.1 $A\neq 0$, $A^m\cong A^n\implies m=n$**

**11.2 $\phi:A^m\to A^n$ 是满射，那么 $m\geq n$.**

**11.3 $\phi:A^m\to A^n$ 是单射，那么 $m\leq n$ 是否一定成立？**

证：

11.1 设同构$\phi:A^m\to A^n$，以及$A$中极大理想$\mathfrak m$，那么$1\otimes \phi:(A/\mathfrak m)\otimes_{A/\mathfrak m} A^m\to (A/\mathfrak m)\otimes_{A/\mathfrak m} A^n$是同构，而这事实上是$k=A/\mathfrak m$上的$m,n$维线性空间之间的同构，即$m=n$.

11.2 由张量积的右正合性质，给定满射$\phi:A^m\to A^n$，有$1\otimes \phi:(A/\mathfrak m)\otimes_{A/\mathfrak m} A^m\to (A/\mathfrak m)\otimes_{A/\mathfrak m} A^n$是满射，于是$m\geq n$.

11.3 不一定。

取$A$为可数个$\Z$的直积，即形如$\{(e_1,\cdots,e_n,\cdots)|e_i\in \Z\}$的元素构成的集合，其上的运算定义为对应分量之间的运算。

定义$\phi:A\oplus A\to A: \big( (e_1,,e_2,\cdots),(e'_1,e'_2,\cdots)\big)\mapsto (e_1,e_1',e_2,e_2',\cdots)$

验证它的确是一个环同态，并且是单射。但是$2>1$.



**12. 设$M$是有限生成$A-$模，且$\phi:M\to A^n$是满同态，那么$\ker \phi$有限生成。**

证：

设$e_1,\cdots, e_n$是$A^n$的基，选出$u_i\in M,\phi(u_i)=e_i$。设这些$U_i$生成了$U$。显然$U\cap \ker\phi=0$，并且对于任意$\phi(x)=\sum a_ie_i,\phi(x-\sum a_i u_i)=0$，即$x\in U+\ker\phi$，这就说明了$M=\ker\phi\oplus U$.

因此考虑$M$的有限生成元，它们顺着$U$到$\ker\phi$的投影生成了$\ker\phi$。



**13. $f:A\to B$是环同态，$N$是$B-$模。由纯量局限，$N$也可看作$A-$模。于是再作纯量扩张有$N_B=B\otimes_A N$。证明$g:N\to N_B:y\mapsto 1\otimes_A y$是单的且$g(N)$是$N_B$的一个直和项。**

证：单性显然：$1\otimes N\subseteq A\otimes N\cong N$.

考虑投影映射$p:N_B\to N:b\otimes_A y\mapsto by$

显然$im(g)\cap\ker p=0$

且$\forall x\in N_B,x=g(p(x))+(x-g(p(x)))$，第一项是$im(g)$中元素，第二项是$ker(p)$中元素，于是$N_B=im(g)\oplus\ker p$.



#### 正向极限

首先明确几个概念的名称。

正向极限是正向系统的余极限；滤过余极限是滤过系统的余极限；更一般地余极限不要求Index范畴具有任何性质。

（正向系统是滤过系统的特例）

注意：尽管在现代正向极限被视作与余极限等价的概念，在这里的正向局限均指正向系统的余极限。（若要描述没有任何约束的index范畴对应的极限时才使用余极限）

但是无论三者中的哪一个，一般都以$\begin{aligned}\lim_{\longrightarrow}\end{aligned}$记号表示，接下来的讨论如果没有特殊指明，均指正向极限。

**14. （$A-$模范畴中的正向极限）我们接下来讨论$A-$模范畴的正向极限。对于正向系统$(M_i,\mu_{ij})$（或者函子$X:I\to Mod_A$，其中$I$是正向集作为偏序集带来的index范畴）**

**那么直接从极限的定义验证知$M=\oplus M_i/\left<x_i-\mu_{ij}(x_i),i\leq j\right>$，以及对应的映射族$\mu_i=\mu|_{M_i},\mu:\oplus M_i\to M$的确是函子$X:I\to Mod_A$的余极限。**

验证：

需要验证泛性质。

首先$M=\oplus M_i/\left<x_i-\mu_{ij}(x_i),i\leq j\right>$的确满足$\mu_i=\mu_j\circ\mu_{ij}(i\leq j)$，我们验证它的确满足泛性质。

对于任何满足$\mu'_i= \mu'_j\circ\mu'_{ij}$的模$N$，由2.E15.1，$M$中每个元素都可以写作$\mu_i(x_i)$的形式，很容易验证$M\to N$且满足$\mu'_i=f\circ\mu_i$的同态的至多唯一性：$f(\mu_i(x_i))=\mu_i'(x_i)$。

欲说明这样的态射的确存在，需要说明它是良定义的。如若$\mu_i(x_i)=\mu_j(x_j)$

设$i\leq k,j\leq k$，那么$\mu_k(\mu_{ik}(x_i))=\mu_k(\mu_{jk}(x_j))$，即$\mu_{ik}(x_i)-\mu_{jk}(x_k)\in \ker\mu_k=\left<x_c-\mu_{cd}(x_c),c\leq d\right>\cap M_k$

不妨设$\mu_{ik}(x_i)-\mu_{jk}(x_j)=\overbrace{\sum\big[ x_{c_i}-\mu_{c_id_i}(x_{c_i})\big]}^{as\ an\ element \ in\ D.S.\oplus M_i}$，那么$\mu_i'(x_i)-\mu_i'(x_j)=\mu_k'(\mu_{ik}(x_i)-\mu_{jk}(x_k))=\sum{\mu'_t(\overbrace{\sum\big[ x_{c_i}-\mu_{c_id_i}(x_{c_i})\big]}^{as\ an\ element \ in\ D.S.\oplus M_i}\cap M_t)}$（这当然是对的，因为除非$t=k$，否则$\mu_t'()$中的项应该是0）$=\sum\big[\mu_{c_i}(x_{c_i})-\mu_{c_id_i}(x_{c_i})\big]=0$，于是良定义性成立，从而验证了泛性质的确成立。

（事实上，良定义可以由2.E15.2直接推出）

$\xymatrix{M_i\ar[r]^{\mu_{ik}}\ar@/_/[rdd]\ar@/^/[rd]_{\mu_i'}&M_k&M_j\ar[l]_{\mu_{jk}}\ar@/_/[ld]^{\mu_{j}'}\ar@/^/[ldd]\\&M&\\&N&}$





**15. $M$中每个元素都能写成$\mu_i(x_i)$的形式，并且如果$\mu_i(x_i)=0$，那么存在$j\geq i,\mu_{ij}(x_i)=0$**

证：

对$M$中任一元素，设为$\overline{\sum_{i\in I'} x_i}$，由于$I'$有限，存在一个$s,s.t. i\leq s\quad\forall i \in I'$

于是$\overline{\sum x_i}=\overline{\sum \mu_{is}(x_i)}$，从而是$\mu_s(x_s)$的形式。

若$\mu_i(x_i)=0$，$x_i\in \left<x_h-\mu_{hk}(x_h),h\leq k\right>\cap M_i$，即由$x_h-\mu_{hk}(x_h)$生成，于是由正向系统，一定存在$j,\mu_{ij}(x_i)=0$



**16. 已在14中验证**

**17. （和）设$M_i$是一族$A-$模的子模，且对于每个$i,j$，$\exists k\in I$，$M_i+M_j\subseteq M_k$。定义$I$上的偏序$\leq:i\leq j\iff M_i\subseteq M_j$，并且取态射$\mu_{ij}$是$M_i$嵌入到$M_j$。**

**证明正向极限$\varinjlim M_i=\sum M_i=\cup M_i$**

**作为特殊结果，每个$A-$模都是其全体有限生成子模（在如上定义的正向系统下）的正向极限。**

证：条件$M_i+M_j\subseteq M_k$ 保证了这是一个正向系统，于是可以谈论正向极限。

由于$\cup M_i$以及映射族$\mu_i$（嵌入）满足$\mu_{ij}\circ \mu_i=\mu_j$，于是存在唯一的态射$f:\varinjlim M_i\to \cup M_i$

反过来也可以定义$g:\cup M_i\to \varinjlim M_i$：设$x\in \cup M_i$，若$x\in M_i$，定义$g(x)=\mu_i(x)$，容易验证良定义性。当然$f\circ g=id,g\circ f=id$，于是同构，从而得证。



**18. （正向系统间的态射）设$\mathbf{M}=(M_i,\mu_{ij}),\mathbf{N}=(N_i,\nu_{ij})$是同一个正向集$I$上的两个$A-$模正向系统。记$M,N$为对应的正向极限，以及其对应的映射族$\mu_i:M_i\to M,\nu_i:N_i\to N$。**

**定义正向系统之间的模同态为一族模同态$\phi_i: M_i\to N_i$，且满足它和所有正向系统中的态射都交换，即$\phi_i\circ\mu_{ij}=\nu_{ij}\circ \phi_j$。**

**证明这族模同态定义出了正向极限之间的唯一态射$\phi:M\to N$，满足$\phi\circ \mu_i=\nu_i\circ \phi_i$。**

证：

只需注意到$N$上也有映射族$\nu_i\circ\phi_i$满足泛性质的要求：下图的实线箭头均交换。于是存在唯一的映射$\phi$满足下图的虚线箭头加入后仍然交换。

$\xymatrix{M_i\ar[rr]^{\mu_{ij}}\ar[rd]_{\mu_i}\ar[ddd]_{\phi_i}&&M_j\ar[ld]^{\mu_j}\ar[ddd]^{\phi_j}\\&M\ar@{-->}@/^0.5pc/[ddd]^{\exist!\phi}&\\\\N_i\ar[rr]^{\nu_{ij}}\ar[rd]_{\nu_i}&&N_j\ar[ld]^{\nu_j}\\&N&}$



**19. （正向系统间态射的正合列）称正向系统及其态射组成的序列$\mathbf{M}\to\mathbf{N}\to \mathbf{P}$正合，如果对每个$i\in I$，$M_i\to N_i\to P_i$正合。**

**证明：正向极限的序列（态射即为2.E18中诱导出的）$M\to N\to P$也是正合的。**

证：

$\xymatrix{M_i\ar[rr]^{\mu_{ij}}\ar[rd]_{\mu_i}\ar[ddd]_{\phi_i}&&M_j\ar[ld]^{\mu_j}\ar[ddd]^{\phi_j}\\&M\ar@/^0.5pc/[ddd]^{\phi}&\\\\N_i\ar[rr]^{\nu_{ij}}\ar[rd]_{\nu_i}\ar[ddd]_{\psi_i}&&N_j\ar[ld]^{\nu_j}\ar[ddd]^{\psi_j}\\&N\ar@/_0.5pc/[ddd]_{\psi}&\\\\P_i\ar[rd]_{\pi_i}\ar[rr]^{\pi_{ij}}&&P_j\ar[ld]^{\pi_j}\\&P&}$

对于$m\in M$，设$m=\mu_i(m_i)$，那么$\psi\circ\phi(m)=\pi_i\circ\psi_i\circ\phi_i(m)=0$

则$Im\phi\subseteq\ker \psi$

对于$n=\nu_i(n_i)$，若$\psi(n)=0$，即$\pi_i(\psi_i(n_i))=0$，那么由2.E15.2，$\exists j\geq i,\pi_{ij}(\psi_i(n_i))=0$

于是$\psi_j(\nu_{ij}(n_i))=0$，即$\exists m_j, \phi_j(m_j)=\nu_{ij}(n_i)$

于是$\phi(\mu_j(m_j))=\nu_j(\phi_j(m_j))=\nu_j(\nu_{ij}(n_i))=\nu_i(n_i)=n$

则$\ker\psi\subseteq Im\phi$，从而正合性得证。



#### 张量函子保持正向极限

**20. 对于$A-$模的正向系统$(M_i,\mu_{ij})$，张量积上一个$A-$模$N$后得到了另一个正向系统$(M_i\otimes N,\mu_{ij}\otimes 1)$。记$P=\varinjlim (M_i\otimes N)$**

**证明：$\varinjlim (M_i\otimes N)\cong (\varinjlim M_i)\otimes N$**

由于存在映射族$\mu_i\otimes 1:M_i\otimes N\to (\varinjlim M_i)\otimes N$（满足余锥）。于是由正向极限的泛性质，存在一个同态$\psi:\varinjlim (M_i\otimes N)\to (\varinjlim M_i)\otimes N$



$\xymatrix{&\varinjlim(M_i\times N)\ar[ld]_g&\\\varinjlim(M_i\otimes N)\ar@<0.5ex>[r]^\psi&M\otimes N\ar@<0.5ex>[l]^\phi&M_i\times N\ar[ld]^{g_i}\ar@{~>}[lu]_{}\\&M_i\otimes N\ar@{~>}[ul]^{\mu_i^*}\ar[u]|{\mu_i\otimes 1}&}$

同样由于存在$M_i\times N\to M_i\otimes N$的双线性映射（如图），于是诱导出了双线性映射$g:\varinjlim(M_i\times N)\to \varinjlim (M_i\otimes N)$。而$\varinjlim (M_i\times N)=(\varinjlim M_i)\times N$（考虑直和商去某些关系这个定义），由张量积的性质，这诱导出了$\phi:(\varinjlim M_i)\otimes N\to \varinjlim(M_i\otimes N)$

（再继续讨论之前，需要详细解释$g$：这是由对正向系统间的同态$g_i:(M_i\times N)\to(M_i\otimes N)$取极限得到。双线性性源于交换图中的外周菱形除$g$外均为双线性映射。）

接下来只需验证复合为恒等映射。

？



**21. $A_i$是正向集上的一族环，将其视作$\Z-$模得到正向极限$\varinjlim A_i=A$。**

**证明$A$上的环结构使得$\mu_i:A_i\to A$成为环同态。**

**如果$A=0$，那么存在某个$A_i=0$。**

证：

定义乘法为$\mu_i(a_i)\cdot \mu_j(a_j)=\mu_k(\mu_{ik}(a_i)\cdot\mu_{jk}(a_j))$，其中$(i\leq k,j\leq k)$

若不存在$A_i=0$，那么每个环中幺元$e_i$被映到到0. 由2.15.2，存在$j\geq i$, $\mu_{ij}(e_i)=0$，即$e_j=0$，矛盾。



**22. 证明幂零根在正向极限下保持。证明整环在正向极限下保持。**

证：

前者显然：$x\in\varinjlim \mathfrak R_i\implies x=\mu_i(x_i),x^r=\mu_i(x_i^r)=0$

$x^r=0\implies \mu_i(x_i)^{r_i}=0\implies \mu_i(x_i^{r_i})=0\implies \mu_{ij}(x_i)^{r_i}=0$

即$\mu_j(\overbrace{x_i^{r_i}}^{\in \mathfrak R_i})=x$。于是$\varinjlim \mathfrak R_i=\mathfrak R$

整环的保持性显然。



**23. 设$B_\lambda$是一族$A-$代数，对于指标集$\Lambda$的有限子集$J$，设$B_J$为$A-$上张量积：$B_J=\otimes^{j\in J}_A B_j$。对于另一个有限子集$J'\supseteq J$，有自然的代数同态$B_J\to B_{J'}$。设全体这样的$J$构成出了正向系统，$B$存在$A-$代数结构，并且$B_J\to B$是代数同态，那么$A$称为$(B_\lambda)_\Lambda$的张量积。**



#### Tor函子与平坦性

**24. 对于$A-$模$M$，证明以下三者等价：**

**1. $M$平坦**

**2. 对所有$n>0$，$A-$模$N$，$Tor^A_n(M,N)=0$**

**3. 对所有$A-$模$N$，$Tor^A_1(M,N)=0$**

证：

$1\implies 2$.

对于$N$的投射解消$\cdots\to F_2\to F_1\to F_0\to N\to 0$，得到了复形$\cdots\to M\otimes F_2\to M\otimes F_1\to M\otimes F_0\to M\otimes N\to 0$

由于$M$平坦，且解消列是正合的，那么复形也是正合的，于是$Tor_n^A(M,N)=0$

$2\implies 3$.

显然

$3\implies1$.

由同调群的长正合列，对于短正合列$0\to N'\to N\to N''\to 0$

得到了长正合列$\cdots\longrightarrow Tor_2^A(M,N'')\longrightarrow Tor_1^A(M,N')\longrightarrow Tor_1^A(M,N)\longrightarrow Tor_1^A(M,N'')\\\longrightarrow M\otimes_A N''\longrightarrow M\otimes_A N\longrightarrow M\otimes_AN'\longrightarrow 0$

由于$Tor_1^A(M,N'')=0$，得到了正合列$0\longrightarrow M\otimes_A N''\longrightarrow M\otimes_A N\longrightarrow M\otimes_AN'\longrightarrow 0$

从而说明了平坦性。



**25. 对于短正合列$0\longrightarrow N'\longrightarrow N\longrightarrow N''\longrightarrow 0$，$N''$平坦，那么$N$平坦$\iff N'$平坦。**

证：由长正合列：

$Tor_2^A(N'',M)\longrightarrow Tor_1^A(N',M)\longrightarrow Tor_1^A(N,M)\longrightarrow Tor_1^A(N'',M)$

那么由2.E24，$Tor_2^A(N'',M)=Tor_1^A(N'',M)=0$，于是结论自明。



**26. $N$是一个$A-$模，$N$平坦$\iff Tor_1(A/\mathfrak a,N)=0$对全体有限生成理想$\mathfrak a$成立。**

$\implies$是2.E24的直接推论。

$\Longleftarrow$  

$Tor_1(A/\mathfrak a,N)=0\implies 0\longrightarrow \mathfrak a\otimes N\longrightarrow A\otimes N\longrightarrow (A/\mathfrak a )\otimes N\longrightarrow0$正合，对每个有限生成理想$\mathfrak a$。

进一步，同理2.19(4$\to$3)，对每个理想$\mathfrak a$都有上述序列正合，于是对于每个循环模$C$都有$Tor_1(C,N)=0$。从而由2.E25每个有限生成模$M$都满足$Tor_1(M,N)=0$ （一个个商去生成元）

再次同理2.19(4$\to$3)，对于每个模都有$Tor_1(M,N)=0$从而说明了平坦。



**27. 称一个环$A$绝对平坦，如果其上的每个模都是平坦的。证明下述三者等价：**

**1. $A$绝对平坦**

**2. 每个主理想是幂等的**

**3. 每个有限生成的理想是$A$的直和因子**

证：

$1\implies 2$

由题，$A/(x)$是平坦模。而$(x)\otimes A\to A:a'x\otimes a\mapsto a'xa$是单射，于是$(x)\otimes A\otimes A/(x)=(x)\otimes A/(x)\to A/(x)=A\otimes A/(x)$也是单射。

但另一方面考虑自然同态构成的交换图（很容易验证交换性）：

$\xymatrix{(x)\otimes A\ar[r]\ar[d]\ar@{-->}[rd]&(x)\otimes A/(x)\ar[d]\\A\ar[r]&A/(x)}$

注意到$(x)\otimes A\to A/(x)$的像只有$0$。而由右侧箭头单，$(x)\otimes A\longrightarrow (x)\otimes A/(x)$的像只能为0.

另一方面$(x)\otimes A\to (x)\otimes A/(x)$是满射（张量积右正合），于是$(x)\otimes A/(x)=0$，但另一方面，由2.E2$(x)\otimes A/(x)\cong (x)/\big[(x)\cdot(x)\big]=(x)/(x^2)$

于是只能有$(x)=(x^2)$，从而主理想幂等。

$2\implies 3$

对于$x\in A,\exists a\ s.t. x=ax^2$，于是$ax$幂等

并且$(x)=(ax)$，同时注意到幂等元生成的理想满足$(e,f)=(e+f-ef)$

于是结合前述知每个有限生成理想都是某个幂等元的主理想，不妨$(e)$，熟知$A=(e)\oplus (1-e)$，结论自明。

$3\implies 1$

考虑Tor长正合列，$Tor_1(A,N)=0$。

那么$A=C_1\oplus C_2, Tor_1(C_1,N)\oplus Tor_1(C_2,N)=Tor_1(A,N)=0\implies Tor(C_i,N)=0\\\implies Finite\ Generated\ \mathfrak{a},Tor_1(A/\mathfrak a,N)=0\implies N\ flat.$



**28. **

**28.1 Boolean环是绝对平坦的；**

**28.2 1.E7中的环是绝对平坦的；**

**28.3 绝对平坦环的同态像是绝对平坦的；**

**28.4 局部环是绝对平坦的$\iff$它是域；**

**28.5 绝对平坦环$A$中每个非单位都是零因子。**

证：

28.1 Boolean环的主理想幂等。

28.2 1.E7中的环的主理想幂等：$x=x^2\cdot x^{n-2}$

28.3 设像为$B$。对于$b,\exists a,\phi(a)=b$，设$a=ta^2$，则$b=\phi(a)=\phi(t)\phi(a)^2=\phi(t)b^2$，从而证明了主理想是幂等的。

28.4 域当然是绝对平坦的。如果局部环是绝对平坦的，

而局部环若可非平凡地拆成直和$C_1\oplus C_2$，就有了两个极大理想，与局部性矛盾。于是这意味着所有的主理想只能是$(0),(1)$，即说明它是域。

28.5 设$x$非单位，那么$(x)\neq(1)$，即$A=(x)\oplus D$，那么$(x,0)\cdot(0,d)=0$，即说明其为零因子。

### 2.12 节末笔记

## 3. 环和模的分式化

### 3.1 分式环、分式模

对于一个环$A$，一个包含$1$的乘性子集$S$，在$A\times S$上定义等价关系$(a,s)\equiv (b,t)\iff (at-bs)u=0\ for\ some\ u\in S$

于是$A\times S/\sim$上可以定义运算$(a/s)+(b/t)=(at+bs)/(st);(a/s)(b/t)=(ab)/(st)$

这里$(a/s)$表示$(a,s)$所处的等价类，可以验证上述定义良好，并且构成环结构；称得到的环为$S^{-1}A$，同时有同态$f:A\to S^{-1}A:x\mapsto x/1$。注意：除非是整环，否则这个映射可能不是单射。



分式环有如下泛性质：

**3.1（分式环的泛性质）对于每个将$S$中元素映为单位的环同态$g:A\to B$，存在唯一的环同态$h:S^{-1}A\to B$使得$g=h\circ f$**

$\xymatrix{A\ar[r]^f\ar[rd]_{\forall g}&S^{-1}A\ar@{-->}[d]|{\exists ! h}\\&B}$

证：若存在$h$，那么$h(1/s)=h((s/1)^{-1})=g(s)^{-1}$，于是$h(a/s)=g(a)\cdot g(s)^{-1}$被唯一确定了。

存在性：

令$h(a/s)=g(a)\cdot g(s)^{-1}$，若$a/s-a'/s'=0$，即$(as'-a's)t=0$，于是$[g(a)g(s')-g(a')g(s)]g(t)=0$，而$g(t)g(s)g(s')=g(tss')$是单位，于是$g(a)g(s)^{-1}=g(a')g(s')^{-1}$，从而说明了良定义性。



**3.2 （分式环由“嵌入”映射唯一确定）**

**环同态$f:A\to S^{-1}A$满足性质：**

**1. $s\in S\implies f(s)$是单位；2. $f(a)=0\implies as=0$对某个$s$成立；3. $S^{-1}A$中的元素都有形式$f(a)f(s)^{-1}$**

**反过来，如果一个映射$g:A\to B$具有上述三条性质，那么存在唯一同构$h:S^{-1}A\to B$，$g=h\circ f$.**

证：显然$g$满足3.1的条件，因此只需说明$h(a/s)=g(a)\cdot g(s)^{-1}$是同构。

由3，$h$是满的；对于$h$的核，如果$h(a/s)=0$，那么$g(a)=0$，$at=0$对某个$t\in S$成立，于是在$S^{-1}A$中$a/s=0$，从而说明了的确是同构。



例子：（Important！）

1. 对于素理想$\mathfrak p$，$S=A-\mathfrak p$是乘性子集；此时记$S^{-1}A$为$A_\mathfrak p$。

对于$A_\mathfrak p$中$a/s,a\in\mathfrak p$构成的理想是极大理想（若$b\notin \mathfrak p$，$b/s$是单位）

因此由1.6，$A_\mathfrak p$是局部环。这个过程称做在$\mathfrak p$的局部化。



注意：$A_\mathfrak p$中的素理想拉回到$A$上是全体含于$\mathfrak p$的素理想；回忆$A/q$的素理想拉回到$A$上是全体包含$\mathfrak q$的素理想。于是$A_\mathfrak p/\mathfrak qA_\mathfrak p$实际上提取出了$\mathfrak p,q$之间的素理想。特殊地，描述$\mathfrak p$可以通过$A_\mathfrak p/\mathfrak pA_\mathfrak p$完成。



2. $S^{-1}A=0\iff0\in S$

3. 对于$f\in A, S=\{f^n\}_{n\geq 0}$，此时记$S^{-1}A=A_f$

4. $S=1+\mathfrak a$是乘法封闭的。

5. 

5.1 $A=\Z,\mathfrak p=(p)$，那么$A_\mathfrak p$是全体（最简形式下）分母和$p$互素的有理数构成的集合；$f\in\Z,f\neq0$，那么$A_f$是全体（最简形式下）分母是$f$的幂次的有理数构成的集合）

5.2 

$A=k[t_1,\cdots,t_n]$, $A_\mathfrak p$是全体分母不在$\mathfrak p$中的有理分式。设簇$V$由$\mathfrak p$生成，那么$A_\mathfrak p$是全体在$V$上几乎处处有定义的函数构成的环，这个环是$A$在$V$上的局部化。

5.3

设$C(X)$是$X$上紧致Hausdorff空间，全体在点$P$取$0$的$C(X)$中元素构成了$C(X)$的素理想（实际上是极大的）$\mathfrak m_x$，关于这个素理想做局部化得到了函数芽环，它是一个局部环。

注意到：

$f/1=g/1\iff\exists h\in C(X)-\mathfrak m_x,h(f-g)=0\iff\\\exists\ open\ neighbourhood\ U\ni x,(f-g)|_U=0(\Longleftarrow \ given\ by\ Urysohn\ Lemma)$

（当然严格说明$A_{\mathfrak m_x}\cong\mathscr O(X,x)$需要严格论证， ref: https://math.stackexchange.com/questions/1592558/germs-and-local-ring）

这实际上是局部化名称的由来。的确，局部化操作将我们的注意力拉到了$\mathfrak p$附近。



上述讨论可以推广到模上。同样给定乘性子集$S\subseteq A$，在$M\times S$上定义等价关系：$(m,s)\sim(m',s')\iff\exists t\in S,t(sm'-s'm)=0$。这样得到了$S^{-1}M$不仅具有Abel群结构，还是一个$S^{-1}A$模：$(a/s)(m/t)=(am)/(st)$



### 3.2 分式化的性质

我们接下来将会看到，分式化与许多操作都是交换的，也保持了许多性质。

**3.3pre （保持复合）每个模同态$u:M\to N$诱导了分式环的模同态$S^{-1}u:S^{-1}M\to S^{-1}N：m/s\mapsto u(m)/s$，那么$S^{-1}(v\circ u)=S^{-1}v\circ S^{-1}u$**

**3.3 （正合性）$\xymatrix{M'\ar[r]^f& M\ar[r]^g&M''}$在$M$处正合，那么$\xymatrix{S^{-1}M'\ar[r]^{S^{-1}f}&S^{-1}M\ar[r]^{S^{-1}g}&S^{-1}M''}$在$S^{-1}M$处正合。**

证：$S^{-1}g\circ S^{-1}f=S^{-1}(g\circ f)=0\implies Im(S^{-1}f)\subseteq Ker(S^{-1}g)$

若$m/s\in Ker(S^{-1}g)$，则$g(m)/s=0\implies \exists t\in M''s.t. tg(m)=0$。于是$tm\in Ker(g)=Im(f)$。设$f(m')=tm$，那么$m/s=f(m')/st=S^{-1}f(m'/st)\in Im(S^{-1}f)$



于是$M'$是$M$的子模意味着$S^{-1}M'$也可以视作$S^{-1}M$的子模。



**3.4（保持和、交、商）**

**$N,P$均为$M$的子模，那么：**

**3.4.1 $S^{-1}(N+P)=S^{-1}N+S^{-1}P$**

**3.4.2 $S^{-1}(N\cap P)=S^{-1}N\cap S^{-1}P$**

**3.4.3 $S^{-1}(M/M)\cong S^{-1}M/S^{-1}N$**

证：

3.4.1显然。

3.4.2：$n/s=p/s'\implies \exists t\in S,t(ns'-ps)=0\implies tns'=tps\in N\cap P$

于是$n/s=(tns')/(ss't)\in S^{-1}(N\cap P)$

（反向包含显然）

3.4.3 对正合列$\xymatrix{0\ar[r]&N\ar[r]&M\ar[r]&M/N\ar[r]&0}$作用$S^{-1}$即可。



**3.5 （保持纯量扩张）**

**对于$A-$模$M$，$S^{-1}A-$模$S^{-1}M$和纯量扩张$S^{-1}A\otimes_A M$同构。特别地存在唯一的$S^{-1}A-$同构映射$f:S^{-1}A\otimes_A M\to S^{-1}M:a/s\otimes_A m\mapsto am/s$**

证：

存在双线性映射$S^{-1}A\times M\to S^{-1}M:a/s\times m\mapsto (am)/s$

于是由泛性质，存在唯一的同态$f:S^{-1}A\otimes_A M\to S^{-1}M$满足$f(a/s\otimes_Am)=am/s$

首先这显然是满射，只需证明单射。

对于$S^{-1}A\otimes_A M$中的元素$\sum (a_i/s_i)\otimes _A m_i$。记$s=\prod_i s_i, t_i=\prod_{j\neq i}s_j$，则：

$\sum (a_i/s_i)\otimes_A m_i=\sum (a_it_i)/s\otimes_A m_i=1/s\otimes_A \sum a_it_im_i$。故只需讨论$1/s\otimes_A m$形式的元素：

如若$f(1/s\otimes_A m)=0$，则$m/s=0$，即$\exists t,tm=0$。于是$1/s\otimes_A m=t/ts\otimes_A m=1/st\otimes_A tm=0$



**3.6 （局部化是平坦化）$S^{-1}A$是平坦$A-$模。**

结合3.3，3.5，2.19：任给$A-$模正合列$\xymatrix{0\ar[r]&M\ar[r]&N\ar[r]&P\ar[r]&0}$

$\xymatrix{0\ar[r]&S^{-1}A\otimes_A M\ar[r]&S^{-1}A\otimes_A N\ar[r]&S^{-1}A\otimes_AP\ar[r]&0\\&&\cong\\0\ar[r]&S^{-1}M\ar[r]&S^{-1}N\ar[r]&S^{-1}P\ar[r]&0}$

（后一正合列中模作为$S^{-1}A-$模，且映射正是如同3.3中那样）

于是后一列正合，从而前一列正合。



**3.7 （保持张量积）若$M,N$是$A-$模，存在唯一的$S^{-1}A-$模同构$f:S^{-1}M\otimes_{S^{-1}A}S^{-1}N\to S^{-1}(M\otimes_A N)$满足$f((m/s)\otimes_{S^{-1}A} (n/t))=(m\otimes_{A} n)/st$。**

**对于素理想$\mathfrak p$，作为$A_\mathfrak p$模有：$M_\mathfrak p\otimes_{A_\mathfrak p}N_\mathfrak p\cong (M\otimes_A N)_\mathfrak p$**

证：

考虑3.5，对于$A-$模$M\otimes_A N$，存在唯一同构$f:S^{-1}A\otimes_A (M\otimes_A N)\to S^{-1}(M\otimes_A N)$

而前者自然地与$S^{-1}M\otimes_{S^{-1}A}S^{-1}N$同构，得证。



### 3.3 局部性质

称一个$A-$模$M$（或环$A$）的性质$P$是局部的，如果$M(or\ A)$具有性质$P\iff M_\mathfrak p(or\ A_\mathfrak p)$具有性质$P,\ \forall\mathfrak p\ prime$。



接下来是局部性质的例子：

**3.8 （零模是局部性质）**

**对于一个$A-$模$M$，以下三者等价：**

**1. $M=0$; 2. $M_\mathfrak p=0,\ \forall\mathfrak p\ prime$; 3. $M_\mathfrak m=0,\ \forall\mathfrak m\ maximal$.**

证：

$1\implies2\implies3$平凡。如果$3$成立但$M\neq 0$，设$0\neq x\in M$，记$\mathfrak a=Ann(x)\neq(1)$，那么$\mathfrak a\subseteq \mathfrak m$。考虑$x/1\in M_\mathfrak m$，当然不能存在$t\in A-\mathfrak m,\ tx=0$（因为$t\in Ann(x)$），于是$x/1\neq0$，这与$M_\mathfrak m=0$矛盾！



**3.9 （左正合/右正合是局部性质）**

**$\phi:M\to N$是$A-$模同态，以下三者等价：**

**1. $\phi$单；2. $\phi_\mathfrak p$单，$\forall\mathfrak p\ prime$；3. $\phi_\mathfrak m$单，$\forall\mathfrak m\ maximal$.**

**单换成满依然成立**

证：

$1\implies 2$. 局部化是保持正合的

$2\implies 3.$显然

$3\implies 1.$

设$M'=Ker(\phi)$，有正合列$\xymatrix{0\ar[r]&M'\ar[r]&M\ar[r]&N}$

那么$\xymatrix{0\ar[r]&M'_\mathfrak m\ar[r]&M_\mathfrak m\ar[r]&N_\mathfrak m}$正合，于是$M'_\mathfrak m=0 \ \forall\mathfrak m\ maximal$。于是由3.8，$M'=0$

满射情况同理。



**3.10 （平坦性是局部性质）**

**对于$A-$模$M$，以下三者等价：**

**1. $M$是平坦$A-$模；2. $M_\mathfrak p$是平坦$A_\mathfrak p-$模，$\forall\mathfrak p\ prime$；3. $M_\mathfrak m$是平坦$A_\mathfrak m-$模，$\forall\mathfrak m\ maximal$。**

证：

$1\implies2.$

由3.5，2.20.

$2\implies3.$

显然。

$3\implies1.$

对于任何模同态$N\to P$，

$N\to P\ inj.\implies N_\mathfrak m\to P_\mathfrak m\ inj.\\\implies N_\mathfrak m\otimes_{A_\mathfrak m}M_\mathfrak m\to P_{\mathfrak m} \otimes_{A_\mathfrak m}M_\mathfrak m\ inj.\\\implies (N\otimes_AM)_\mathfrak m\to (P\otimes_A M)_\mathfrak m\ inj.\\\implies N\otimes_A M\to P\otimes_A M\ inj.$，于是说明了平坦性。

### 3.4 分式环中理想的扩张和局限

由于环同态$f:A\to S^{-1}A$，我们可以考虑扩张理想和局限理想，分别记为$C(in\ A);E(in\ S^{-1}A)$

对于$A$中理想$\mathfrak a$，$\mathfrak a^e=S^{-1}\mathfrak a$（均有形式$\sum a_i/s_i,a_i\in\mathfrak a$，再通分即可）

**3.11 （扩张理想和局限理想的结构）**

**3.11.1 $S^{-1}A$中的每个理想都是扩张理想**

**3.11.2 $\mathfrak a$是$A$的理想，$\mathfrak a^{ec}=\cup _{s\in S}(\mathfrak a:s)$。于是$\mathfrak a^e=(1)\iff \mathfrak a\cap S\neq \varnothing$**

**3.11.3 $\mathfrak a\in C\iff S$的元素在$A/\mathfrak a$中都不是零因子。**

**3.11.4 $S^{-1}A$中的素理想和$A$中与$S$不交的素理想存在一一对应：$S^{-1}\mathfrak p\leftrightarrow \mathfrak p$**

**3.11.4 Cor. (Example 5 Mentioned In 3.1) 局部环$A_\mathfrak p$的素理想与含于$\mathfrak p$的素理想一一对应。**

**3.11.5 $S^{-1}$操作与和有限和、积、交、根理想交换**

**3.11 Cor. $S^{-1}\mathfrak R$是$S^{-1}A$的幂零根。**

证：

3.11.1 设$\mathfrak b$是$S^{-1}A$中的理想，$x/s\in\mathfrak b\implies x/1\in \mathfrak b$。于是$x\in\mathfrak b^c$，进而$x/s\in\mathfrak b^{ce}$。另一方面$\mathfrak b\supseteq \mathfrak b^{ce}$，于是只能有$\mathfrak b=b^{ce}$从而证明了结论。

3.11.2

 $x\in\mathfrak a^{ec}\iff x\in(S^{-1}\mathfrak a)^c\iff x/1=a/s(a\in\mathfrak a,s\in S)\\\iff \exists t\in S,(xs-a)t=0\iff\exists s,t\in S, xst\in \mathfrak a\\\iff x\in (\mathfrak a:s)\ \exists s\in S\iff x\in\cup(\mathfrak a:s)$

3.11.3 

$\mathfrak a\in C\iff \mathfrak a^{ec}\subseteq \mathfrak a\iff (\exists s\in S,sx\in\mathfrak a\implies x\in\mathfrak a)\iff A/\mathfrak a$中$S$的元素都不是零因子。

3.11.4

$S^{-1}\mathfrak a$素当然意味着$\mathfrak a$素。

反过来：如果给定素理想$\mathfrak p$，$A/\mathfrak p$是整环。由于存在$S^{-1}A$模同构（3.4.3）$S^{-1}(A/\mathfrak p)\cong S^{-1}A/S^{-1}\mathfrak p$

前者要么是0，要么含于$A/\mathfrak p$的分式域中，于是自然是整环。从而$S^{-1}\mathfrak p$要么等于$S^{-1}A$，要么素。而前者这一情况$\iff \exists p,s,p/s=1/1\iff\exists s,t\in S,pt=st\subseteq \mathfrak p\left.\begin{cases}\implies s\ or\ t\in\mathfrak p\implies\\\Longleftarrow s\cdot s=s\cdot s\Longleftarrow\end{cases} \right\}S\cap\mathfrak p\neq\varnothing$

于是得证。

3.11.5 

和、积由1.18保证，交由3.4.2保证。

根理想：由1.18，$S^{-1}(r(\mathfrak a))\subseteq r(S^{-1}\mathfrak a)$

反过来，若$x/t\in r(S^{-1}\mathfrak a)$，$x^n/t^n=a/s(a\in\mathfrak a)$

那么$(x^ns-t^na)u=0\implies \big[x(x^{n-1}s)-t(at^{n-1})\big]u=0\implies x/t=(t^{n-1}a)/(x^{n-1}s)$

而$t^{n-1}a\in \mathfrak a\subseteq r(\mathfrak a)$，于是当然$x/t\in S^{-1}(r(\mathfrak a))$

3.11 Cor.

Nilradical of $S^{-1}A=\cap_{\mathfrak{p} \cap S=\varnothing}S^{-1}\mathfrak p\xlongequal[]{If\ \mathfrak p\cap S\neq\varnothing.S^{-1}\mathfrak p=S^{-1}A}\cap _{\mathfrak p}S^{-1}\mathfrak p=S^{-1}(\cap \mathfrak p)=S^{-1}\mathfrak R$



Rmk. 利用这里的结果，可以更精确地说明为什么幂零根是素理想的交。我们希望说明如果$f$不幂零，那么一定存在一个素理想不包含它。由于$S=(f^n)$不包含0，那么$S^{-1}A=A_f$非0，从而存在极大理想。

这个极大理想的局限是素理想，且不包含$f$（否则$f/f=1$引发矛盾）

（事实上可以发现许多有关素理想的问题在局部化中都得到了很好的解释）



Rmk. 3.1节中举例提到的$A_\mathfrak p/qA_\mathfrak p$中局部化和商操作是可交换的（由3.4）

正如3.1节中举例提到的，我们格外关注形如$A_\mathfrak p/\mathfrak p A_\mathfrak p$的结构。这称为$\mathfrak p$处的剩余域(Residue Field)，它既可看作整环$A/\mathfrak p$的分式域，也可看作局部环$A_\mathfrak p$的剩余域。

考虑$A=C(X),\mathfrak p=\{functions\ that\ vanish\ at\ p\}$作为例子，实际上它几乎就是余切空间$T_p^*$。



**3.14（有限生成前提：局部化保持零化子） 设$M$是有限生成$A-$模，那么$S^{-1}(Ann(M))=Ann(S^{-1}M)$**

证：

如果命题对两个$A-$模$M,N$成立，那么对于$M+N$：

$S^{-1}(Ann(M+N))=S^{-1}(Ann(M)\cap Ann(N))\\=S^{-1}(Ann(M))\cap S^{-1}(Ann(N))=Ann(S^{-1}(M))\cap Ann(S^{-1}(N))\\=Ann(S^{-1}M+S^{-1}N)=Ann(S^{-1}(M+N))$

于是利用对生成元的归纳，只需证明循环模的情况。

此时$M\cong A/\mathfrak a,\mathfrak a=Ann(M)$。那么$S^{-1}M\cong S^{-1}A/S^{-1}\mathfrak a$

于是$Ann(S^{-1}M)=S^{-1}\mathfrak a=S^{-1}Ann(M)$



作为推论我们可以利用商理想的零化子形式得到：

**3.15 （有限生成前提：局部化保持商理想）$N,P$是$M$的子模，且$P$有限生成，那么$S^{-1}(N:P)=(S^{-1}N:S^{-1}P)$**

证：$(N:P)=Ann((N+P)/N)$，只需说明$(N+P)/N$有限生成。而$(N+P)/N\cong P/(N\cap P)$是有限生成模的商模，于是自然有限生成。



**3.16 （素理想是否是素理想的拉回？）给定环同态$f:A\to B$，$\mathfrak p$是$A$的素理想，则它是$B$的素理想的拉回$\iff\mathfrak p^{ec}=\mathfrak p$**

证：如果$\mathfrak p=\mathfrak q^c$，当然$\mathfrak p^{ec}=\mathfrak p$

反过来，如果$\mathfrak p^{ec}=\mathfrak p$，设$S=f(A-\mathfrak p)$。如果$\mathfrak p^e$与$S$相交，即$\exists y\notin\mathfrak p,f(y)\in \mathfrak p^e$，那么$y\in \mathfrak p^{ec}=\mathfrak p$，矛盾。

从而$\mathfrak p^e$与$S$ 不交。

于是$\mathfrak p^e$在$S^{-1}B$中的扩张是一个真理想，那么被某个极大理想$\mathfrak m$包含，设它局限回$B$得到的素理想为$\mathfrak q$，那么$\mathfrak q\supseteq \mathfrak p^e$，且$\mathfrak q$与$S$不交。于是$\mathfrak p^{ec}\subseteq \mathfrak q^c\subseteq \mathfrak p$，但是$\mathfrak p=\mathfrak p^{ec}$，于是只能关系取等，从而得到证明。

### 3.5(E)

**1. 设$S$是$A$的乘性子集，$M$是有限生成$A-$模，则$S^{-1}M=0\iff \exists s\in S,sM=0$.**

证：

$S^{-1}M=0\iff Ann(S^{-1}M)=S^{-1}A\iff S^{-1}(Ann(M))=S^{-1}A\\\iff 1/1\in S^{-1}(Ann(M))\iff\exists s\in Ann(M)\iff \exists s\in S,sM=0$



**2. 设$\mathfrak a$是环$A$的一个理想，记乘性子集$S=1+\mathfrak a$，证明$S^{-1}\mathfrak a\subseteq J(S^{-1}A)$**

证：由1.9，只需证明$\forall a_1/(1+a_2)\in S^{-1}\mathfrak a,1-\mathfrak [a_1/(1+a_2)]\cdot[a/(1+a_3)]$是单位（$a_1,a_2,a_3\in \mathfrak a$）

而这是显然的，因为$1-[a_1/(1+a_2)]\cdot [a/(1+a_3)]=(1+a_2+a_3+a_2a_3-a_1a)/(1+a_2+a_3+a_2a_3)$

而$(1+a_2+a_3+a_2a_3)/(1+a_2+a_3+a_2a_3-a_1a)\in S^{-1}A$，它们的积当然是$1/1$，于是得到证明。

（2cor.）



**3. （多次环的局部化可以交换）设$S,T$均为乘性子集，$U$是$T$在$S^{-1}A$	中的像，证明$(ST)^{-1}A\cong U^{-1}(S^{-1}A)$，从而说明局部化的次序对结果没有影响，均为将这些乘性子集相乘后做局部化得到的分式环。。**

证：

考虑同态$U^{-1}(S^{-1}A)\to (ST)^{-1}A:(a/s)/(t/1)\mapsto a/(st)$

这个同态是良定义且满的，对于单性，如果$a/st=0,\exists s't'\in ST\ s.t. s't'a=0\implies (a/s)(1/1)\overbrace{(s't')/1}^{\in U}=0\\\implies (a/s)/(t/1)=(0/1)/(1/1)=0$



**4. （局部化与纯量扩充交换）$f:A\to B$是环同态，$S$是乘性子集，$T=f(S)$，则$S^{-1}B$和$T^{-1}B$是同构的$S^{-1}A$模。**

证：$b/s\mapsto b/f(s)$，良定义，模同态，满射显然。对于单射：若$b/f(s)=0$，即$\exists s',bf(s')=0$。那么$s'b=0\implies b/s=0/1$



**5. 如果$A$是环，对每个素理想$\mathfrak p$，局部环$A_\mathfrak p$都没有非零的幂零元，证明$A$没有非零的幂零元。**

**如果每个$A_\mathfrak p$是整环，$A$一定是整环吗？**

证：若有一非零幂零元$x$，由于局部环$A_\mathfrak p$没有非零的幂零元，那么在局部环中$x/1=0$，即$\exists y_p\in A-\mathfrak p, xy_p=0$。由于$Ann(x)$一定被包含$x$的极大理想包含，取$\mathfrak p$为这个极大理想就得到了矛盾。

对于第二个问题答案是不一定的，考虑 $\Z/2\Z\times \Z/2\Z$即可。



#### 饱和乘性子集

**6. 对于非零环$A$，设$\Sigma$是全体不包含0的乘性子集构成的集族，证明它有极大元素，且$S\in \Sigma$极大$\iff A-S$是极小素理想。**

证：

由Zorn引理，只需说明对于每个全序链$S_1\subseteq\cdots\subseteq $，存在上界。这当然存在，取为$\cup S_i$即可。

对于第二个结论：

若$S$极大，则$a\notin S\iff \exists s\in S,n\in \N,sa^n=0$（考虑乘性子集$\{sa^n|\forall s,n\}$包含了$S$和$a$，由极大性得证）于是验证知$A-S$是理想：$s_1s_2(a+b)^{n_1+n_2}=0,(ab)^{n_1}s_1=0$。从而一定是素的，进而一定是极小的。

反过来，若$\mathfrak p$极小素理想，$A-\mathfrak p\in \Sigma$是显然的。如果它不极大，那么可以取$S'\supset S$极大，那么$A-S'$是素理想，且严格包含于$\mathfrak p=A-S$中，矛盾。



**7. 称乘性子集$S$饱和，如果$xy\in S\iff x\in S\and y\in S$**

**证明：**

**7.1 $S$饱和$\iff A- S$是素理想的并。**

**7.2 对于任何乘性子集$S$，存在唯一的最小的饱和乘性子集$\bar{S}$包含$S$，$\bar{S}$是与$S$不交的素理想的并在$A$中的补。**

**7.3 若$S=1+\mathfrak a$，求$\overline{S}$。**

证：

7.1 

我们说明如果$S$饱和，$A-S=\cup_{\mathfrak p\cap S=\varnothing}\mathfrak p$。

左侧当然包含右侧，对于反过来的情况：若$x\in A-S$，考虑$(x)$，由于饱和性$(x)\cap S=\varnothing$，于是考虑商环$A/(x)$的子集$S/(x)$当然也是乘性子集。于是由3.E6，$S/(x)\subseteq A/(x)-\overline{\mathfrak p}$，其中最后一项为极小素理想，于是自然$\overline{\mathfrak p}=\mathfrak p/(x)$（对应定理）那么$\mathfrak p\cap S=\varnothing$，且$x\in(x)\subseteq \mathfrak p$，从而$x\in \cup_{\mathfrak p\cap S=\varnothing}\mathfrak p$

7.2

首先$A-\cup_{\mathfrak p\cap S=\varnothing}\mathfrak p:=\overline{S}$当然是饱和乘性子集，且包含$S$。如果有另一个包含$S$的饱和乘性子集$\overline{S}'$，那么应用7.1的结果知$\overline{S}\subseteq \overline{S}'$，于是结论自明。

7.3

$\mathfrak p\cap (1+\mathfrak a)\neq\varnothing\iff \mathfrak{p+a}=(1)$，于是$\mathfrak p\cap S=\varnothing\iff \mathfrak{p+a}\neq(1)$。由于要考虑的是$\cup_{\mathfrak p\cap S=\varnothing}\mathfrak p$，只需考虑$\mathfrak p$是极大理想的情况。由于$\mathfrak p\subseteq \mathfrak {p+a}\neq (1)$，那么$\mathfrak p=\mathfrak {p+a}\iff \mathfrak p\supseteq \mathfrak a$，于是综上所述，有$\overline{S}=\cup_{maximal\ \mathfrak m\supseteq A}\mathfrak m=\cup_{\mathfrak p\supseteq A}\mathfrak p$



**8. 设$S,T$是乘性子集且$S\subseteq T$，那么有自然的同态$\phi:S^{-1}A\to T^{-1}A:a/s\mapsto a/s$。证明以下等价：**

**1. $\phi$是双射；**

**2. 对于$t\in T$，$t/1$是$S^{-1}A$的单位。**

**3. 对每个$t\in T$，存在$x\in A,xt\in S$。**

**4. $T\subseteq \overline{S}$，其中$\overline{S}$指$S$的饱和化。**

**5. 每个与$T$相交的素理想也和$S$相交。**

证：

$1\implies 2.$

考虑$1/t\in T^{-1}A$的原像$a/s$，那么$t/1 \cdot a/s=\phi^{-1}(t/1\cdot1/t)=\phi^{-1}(1/1)=1/1$

$2\implies 1.$

满射：如果在$S^{-1}A$中$t/1\cdot a'/s'=1/1$，那么$\phi(aa'/s')=a/t$

单射：如果$\phi(a/s)=0/1$，即在$T^{-1}A$中$a/s=0/1$，那么$\exists t\in T,at=0$。设$t/1$在$S^{-1}A$中的逆为$a'/s'$，那么自然在$S^{-1}A$中$0/1=at\cdot a'/s'=a/1$，于是$a/s=0/1$。

（Rmk. 也可以考虑泛性质）

$2\implies3.$

设$t/1\in S^{-1}A$的逆为$a/s$，那么$at/s=1$，即$\exists u\in S, u(at-s)=0$，即$t(au)=su\in S$

$3\implies 4.$

若$T$中某个元素$t$属于与$S$不相交的素理想$\mathfrak p$，那么由3，$xt\in S$，但同时更有$xt\in \mathfrak p$，矛盾！

$4\implies 5.$

显然

$5\implies 2.$

如果$t$在$S^{-1}A$中没有逆，即$\forall a,s,s'$，$(ta-s)s'\neq 0$。那么自然$(t)=\{at|a\in A\}$满足$(t)\cap S=\varnothing$

（接下来仿照3.E7）

于是同理有$S/(x)\subseteq A/(x)$是乘性子集。那么由3.E6，$S/(x)\subseteq A/(x)-\overline{\mathfrak p}=(A-\mathfrak p)/(x)$，于是$\mathfrak p\cap S=\varnothing\and x\in(x)\subseteq \mathfrak p$，矛盾。



Rmk. $\overline{S}$正是在局部化中变得可逆的元素，那么当然有$\overline{S}^{-1}A=S^{-1}A$，并且两个局部化的分式环相同当且仅当它们（所使用的乘性子集）的饱和乘性子集相同，于是饱和乘性子集实际上展示了局部化的一切信息。



**9. 全体非零因子构成的集合$S_0$是一个饱和乘性子集，于是零因子集合$D$是一些素理想的并（1.E14的另一证明）并且：**

**9.0 每个极小素理想都被包含在$D$ 内。**

**$S_0^{-1}A$称为全分式环，证明：**

**9.1 $S_0$是最大的满足映射$A\to S^{-1}A$是单射的乘性子集$S$。**

**9.2 $S_0^{-1}A$的元素要么是单位，要么是零因子。**

**9.3 如果一个环其非单位元素均为零因子，那么它的全分式环和它相同，即$\phi$是双射。**

证：

9.0

不包含0的极大的乘性子集等价于它形如$S=A-\mathfrak p\ (minimal.)$，进而它是饱和的乘性子集。

如果$S_0\not\subseteq S$，那么$S\subset S_0S$，于是只能有$s_0s=0$，这和$S_0$定义矛盾，于是只能有$S_0\subseteq S$，进而得证。

9.1

$A\to S^{-1}A$单$\iff (a/1=0\implies a=0)$

若$S\not\subseteq S_0$，设$s$是零因子，$as=0,a\neq 0$，那么$a/1=0$，矛盾。从而$S\subseteq S_0$

9.2

$S_0^{-1}A$的元素若不是零因子，即$a/s_0\cdot a'/s'_0=0\implies a'/s'_0=0$，即$aa'=0\implies a'=0$，即$a\in S_0$，于是当然$a/s_0$是单位。

9.3

由条件$S_0$是其全体单位构成的集合，这样的分式化当然是双射。

#### 绝对平坦环的局部化

**10. 给定环$A$：**

**10.1 如果$A$绝对平坦，那么对于任何乘性子集，局部化的结果$S^{-1}A$依然是绝对平坦的**

**10.2 $A$绝对平坦$\iff$对于每个极大理想，$A_\mathfrak m$是域。**

证：

10.1

由于$A$绝对平坦，$(a)=(a^2)$，$\exists b\in A, as=a^2b$。于是$as^2=a^2bs$，进而$a/s=(a/s)^2 (b/1)$，从而说明$(a/s)=(a^2/s^2)$。于是说明了分式环$S^{-1}A$依然是绝对平坦的。

10.2

$\implies.$ $A$绝对平坦$\implies A_\mathfrak m$绝对平坦。由2.E28，它是局部环，于是这要求它是域。

$\Longleftarrow.$  对于单位$x\in A$，$(x)=(1)$当然幂等，下设$x$非单位，设$x\in\mathfrak m$。由于$A_\mathfrak m$是域，其唯一的极大理想$\mathfrak m A_\mathfrak m$应为0. 即$\forall m\in\mathfrak m,m/1=0$。于是$\exists s\in A-\mathfrak m$，$xs=0$

从而$x^2=x(s+x)$，于是说明了主理想$(x)$幂等，于是得证。



**11. 设$A$为环：**

**11.1 证明以下四者等价：**

**1. $A/\mathfrak R$绝对平坦；2. 每个素理想极大；3. $Spec(A)$（配备Zariski拓扑）是$T_1$的；4. $Spec(A)$是$T_2$的。**

**11.2 如果上述情况成立了，证明$Spec(A)$是紧致Hausdorff且全不连通的。**

证：

11.1

$1\iff 2.$

每个素理想极大$\iff$ $A/\mathfrak R$中没有严格含于$\mathfrak{ m/R}$的素理想$\iff (A/\mathfrak R)_{\mathfrak {m/R}}$ 的素理想只有$(\mathfrak{m/R})_{\mathfrak {m/R}}$$\stackrel{1.E10}\iff $（这个局部环幂零根为0：局部化保持幂零根，而$A/\mathfrak R$幂零根为0）这个局部环是域。

$2\iff 3.$

$Spec(A)\ T_1\iff \overline{\{\mathfrak p\}}=\{\mathfrak p\}\iff V(\mathfrak p)=\{\mathfrak p\}\iff \mathfrak p\ maximal.$

$ 4\implies 3.$

$T_2$当然$T_1$。

$2\implies 4.$

$X_\mathfrak p\cap X_\mathfrak q=\varnothing$



紧致由1.E17保证，Hausdorff即$T_2$已证。

全不连通性由$X_\mathfrak p,X_\mathfrak q$分划$X$得证。



**12. $A$是整环，$M$是其上的模。称$M$的元素$x$是挠元，如果$Ann(x)\neq0$。全体挠元构成了子模$T(M)$。如果$T(M)=0$，则称$M$无挠。**

**12.1 $M/T(M)$无挠。**

**12.2 $f:M\to N$是模同态，那么$f(T(M))\subseteq T(N)$**

**12.3 $T(-)$是左正合的，i.e. $\xymatrix{0\ar[r]&M'\ar[r]&M\ar[r]&M''}$正合，则$\xymatrix{0\ar[r]&T(M')\ar[r]&T(M)\ar[r]&T(M'')}$正合。**

**12.4 $T(M)$是映射$M\to K\otimes_A M:x\mapsto 1\otimes x$的核，其中$K$是$A$的分式域。**

证：

12.1 若否：$a(m+T(M))=T(M)\implies am\subseteq T(M)\implies a_1am\subseteq T(M)\implies m\subseteq T(M)\implies m+T(M)=T(M)$

12.2 $af(m)=f(am)=0$

12.3 

$\xymatrix{0\ar[r]&M'\ar[r]^f&M\ar[r]^g&M''}$

限制到挠模上自然$\bar{f}$单射。$\overline{g}\circ \overline{f}=0$，只需证明$\ker \bar{g}\subseteq im \bar{f}$

若$g(m)=0$，$m=f(m')$。由于$0=am=af(m')=f(am')$，而$f$单要求$am'=0$，即$m'\in T(M')$，得证。

12.4

由3.5，存在$K-$模同构$K\otimes_A M\cong_K S^{-1}M$，其中$S=A-\{0\}$

那么$1\otimes x=0\iff x/1=0(in\ S^{-1}M)\iff ax=0(a\neq 0)\iff x\in T(M)$



**13. 设$S$是整环$A$的乘性子集，证明：**

**13.1 $T(S^{-1}M)=S^{-1}T(M)$**

**13.2 无挠是局部性质，即以下三者等价：**

**1. $M$无挠；2. $M_\mathfrak p$无挠；3. $M_\mathfrak m$无挠。**

证：

13.1 $\exists m_1/s_1,s.t. (m_1/s_1)(m/s)=0\iff \exists m_1, s.t. mm_1=0$，于是结论显然。

13.2 

$1\iff 2. T(S^{-1}M)=S^{-1}T(M)$

那么$M$无挠$\implies T(M)=0\implies T(S^{-1}M)=0$

$M_\mathfrak m$无挠$\implies S^{-1}T(M)=0$，但是无零因子保证了$m/s=0\implies m=0$，从而$T(M)=0$。



**14. $M$是$A-$模，$\mathfrak a$是$A$的理想。只要极大理想$\mathfrak m\supseteq \mathfrak a$，就有$M_\mathfrak m=0$，证明：$M=\mathfrak aM$**

证：

 考虑$A/\mathfrak a-$模$M/\mathfrak aM$。它对其中任何极大理想做局部化得到的是0，那么由3.8知$M/\mathfrak aM=0$，得证。



**15. 对于自由模$F=A^n$，证明$F$的任何一组$n$个元素构成的生成元系都是$F$的一组基。**

证：

设这组生成元为$x_1,\cdots,x_n$，以及自然的基底$e_1,\cdots, e_n$。自然有模同态$\phi:F\to F:e_i\mapsto x_i$，这当然是一个满同态，接下来证明同构，即说明其为单同态。

由定理3.9，可以假设$A$是局部环，$N=\ker\phi, k=A/\mathfrak m$。由于自由模$F$是平坦的，那么正合列$0\to N\to F\to F\to0$诱导出了张量正合列$\xymatrix{0\ar[r]&k\otimes N\ar[r]&k\otimes F\ar[r]^{1\otimes\phi}&k\otimes F\ar[r]&0}$ 

由于$k\otimes F=k^n$是线性空间，$1\otimes\phi$满进而是单的，于是只能有$k\otimes N=0$。而$N$作为自由模的子模是有限生成的，那么由2.E3知$N=0$，从而得证。



进一步地，任何一组$F$的生成元至少有$n$个元素。若否，添加元素至$n$个是一组基，于是立刻引出矛盾。



#### 忠实平坦

**16. $B$是平坦$A$代数，那么以下五者等价：**

**1. $\mathfrak a^{ec}=\mathfrak a$对所有$A$中理想成立。**

**2. $Spec(B)\to Spec(A)$是满的。**

**3. 每个$A$中的极大理想都满足$\mathfrak m^e\neq (1)$**

**4. 对于非零$A-$模$M$，$M_B\neq 0$。**

**5. 对于$A-$模$M$，$M\to M_B: x\mapsto 1\otimes x$是单射。**

**在这样的条件下，称$B$是$A$上忠实平坦的。**

证：

$1\implies 2.$ 由3.16结论成立。

$2\implies 3.$ 显然。

$3\implies 4.$ 设有非零元素$x\in M$，记$M'=Ax$。由于$B$是平坦的$A$代数，那么嵌入$M'\hookrightarrow M$诱导出了嵌入$M'_B\hookrightarrow M_B$。而$M'\cong A/\mathfrak a$，由2.E2有$M'_B=B/\mathfrak aB=B/\mathfrak a^e$。由于$\mathfrak a\neq (1)$，由3.知$\mathfrak a^e\neq (1)$，从而$M'_B$非0。于是嵌入就保证了$M_B\neq 0$。

$4\implies 5.$ 如果这个映射不是单射，即$1\otimes x=0, x\neq 0$。而$Ax\hookrightarrow M$诱导出了嵌入$(Ax)_B\hookrightarrow M_B$

那么这要求在$(Ax)_B$中也有$1\otimes x=0$，于是$(Ax)_B=0$，矛盾。

$5\implies 1.$ 取$M=A/\mathfrak a$，即有单射$A/\mathfrak a\to B/\mathfrak a^e$，并且这个映射正是由环同态$f$诱导出。那么考虑$\mathfrak a^e$的原像：当然为$\mathfrak a^{ec}/\mathfrak a$，但另一方面单射保证了它应该是0，于是就有$\mathfrak a^{ec}=\mathfrak a$。



**17. $\xymatrix{A\ar[r]^f&B\ar[r]^g&C}$，如果$g\circ f$平坦，且$g$忠实平坦，那么$f$平坦。**

证：

对于任何一个$A$模单同态$M'\to M$，需证$M'\otimes_A B\to M\otimes_A B$是单同态。

考虑正合列$0\to \ker (f\otimes_A 1_B)\to M'\otimes_A B\to M\otimes_A B$

这天然地具有$B$模结构，于是有正合列$0\to \ker (f\otimes_A 1_B)\otimes_BC\to M'\otimes_A B\otimes_BC\to M\otimes_A B\otimes_BC$

而上述列的最右一侧变为$M'\otimes_A C\to M\otimes_A C$，这是单射。

但是考虑交换图：

$\xymatrix{M'\otimes_AB\ar[r]\ar[d]&M\otimes_AB\ar[d]\\M'\otimes_AC\ar[r]&M\otimes_AC}$

由于$C$在$B$上忠实平坦，由3.E16.5：左、右、下三个映射都是单射，且这个图交换，于是只能有第四条边也是单射。

从而得到了结论。



**18. $f:A\to B$是平坦环同态，$\mathfrak q$是$B$的素理想且$\mathfrak p=\mathfrak q^c$。那么$f^*:Spec(B_\mathfrak q)\to Spec(A_\mathfrak p)$是满射。**

证：

需要说明$B_\mathfrak q$是$A_\mathfrak p$上的忠实平坦代数。

首先说明它是平坦的：$B_\mathfrak q$是



**19. 给定环$A$，$M$是$A-$模。称$M$的支撑为全体满足$M_\mathfrak p\neq 0$的素理想。**

**19.1 $M\neq 0\iff Supp(M)\neq \varnothing$**

**19.2 $V(\mathfrak a)=Supp(A/\mathfrak a)$**

**19.3 给定正合列$0\to M'\to M\to M''\to 0$，则$Supp(M)=Supp(M')\cup Supp(M'')$**

**19.4 $M=\sum M_i$，则$Supp(M)=\cup  Supp(M_i)$**

**19.5 $M$有限生成，则$Supp(M)=V(Ann(M))$**

**19.6 $M,N$有限生成，则$Supp(M\otimes_A N)=Supp(M)\cap Supp(N)$**

**19.7 $M$有限生成，$\mathfrak a$是$A$的理想，那么$Supp(M/\mathfrak aM)=V(\mathfrak a+Ann(M))$**

**19.8 $f:A\to B$是环同态，$M$是有限生成$A-$模，那么$Supp(B\otimes_A M)=f^{*-1}(Supp(M))$**

证：

19.1 $\Longleftarrow$方向显然，$\implies$方向成立因为$M_\mathfrak p\neq 0\iff\exists m,\forall s\in A-\mathfrak p,ms\neq 0\iff \exists m,(A-\mathfrak p)\cap Ann(m)=\varnothing\iff\exists m, \mathfrak p\supseteq Ann(m)$

于是取$\mathfrak p$是包含$Ann(m)$的极大理想即证。

19.2 $\mathfrak p\in Supp(A/\mathfrak a)\iff (A/\mathfrak a)_{\mathfrak p}\neq 0\\\iff\exists a+\mathfrak a,\mathfrak p\supseteq Ann(a+\mathfrak a)\iff\mathfrak p\supseteq\mathfrak a\iff \mathfrak p\in V(\mathfrak a)$

19.3 对于$\mathfrak p$，有正合列$0\to M'_\mathfrak p\to M_\mathfrak p\to M''_\mathfrak p\to 0$

那么$M_\mathfrak p=0\iff M'_\mathfrak p=0\and M''_\mathfrak p=0$，于是结论自明。

19.4 由于$M_\mathfrak p=\sum (M_i)_\mathfrak p$，结论自明。

19.5 这是3.E19.7的特例。

19.6 由于$(M\otimes_A N)_\mathfrak p =M_\mathfrak p\otimes_{A_\mathfrak p}N_\mathfrak p$，且由2.E3（有限生成性当然在局部化中被保持）知它非零当且仅当两个因子至少存在一个非零，于是结论自明。

19.7 $(M/\mathfrak aM)_\mathfrak p\neq0\iff\exists x+\mathfrak a M,\forall k\in A-\mathfrak p, kx\notin \mathfrak aM$

如果存在这样的$x$，那么立刻就有$\mathfrak p\supseteq \mathfrak a+Ann(M)$

反过来如果$\mathfrak p\supseteq \mathfrak a+Ann(M)$

那么取$x\in M-\mathfrak a M$就有$kx\in \mathfrak a M$，从而说明了结论。

19.8 设$\mathfrak q\in Spec(B),\mathfrak p=\mathfrak q^c$。只需$\mathfrak q\in Supp(M_B)\iff\mathfrak p\in Supp(M)$

然而$(B\otimes_A M)_\mathfrak q=$



**20. $f:A\to B$环同态，以及$f^*:Spec(B)\to Spec(A)$，那么：**

**20.1 每个$A$中素理想都是局限理想$\iff f^*$满。**

**20.2 每个$B$中素理想都是扩张理想$\implies f^*$单。**

证：

20.1 $(\Longleftarrow)$显然。$(\implies)$ $\forall \mathfrak p\in Spec(A), \mathfrak p=\mathfrak p^{ec}\implies f^*$满。

20.2 $(\implies)$ 若否，则$\mathfrak q_1^c=\mathfrak q_2^c=\mathfrak p$

即$\mathfrak p_1^{ec}=\mathfrak p_2^{ec}=\mathfrak p$

于是$\mathfrak q_1=\mathfrak p_1^e=\mathfrak p_1^{ece}=\mathfrak p_2^{ece}=\mathfrak p_2^e=\mathfrak q_2$



#### 纤维积

**21.1 给定环$A$，$S$乘性子集，以及自然同态$\phi:A\to S^{-1}A$。则$\phi^*:Spec(S^{-1}A)\to Spec(A)$作为$Spec(S^{-1}A)$到$S^{-1}X\subseteq Spec(A)$的同胚。（这里$S^{-1}X$是一个记号，$Y=Spec(S^{-1}A),X=Spec(A)$）**

**特别地，取$f\in A$，$Spec(A_f)$的像是主开集$X_f$。**

**21.2 给定环同态$f:A\to B$，$X=Spec(A),Y=Spec(B), f^*:Y\to X$。将$Spec(S^{-1}A)$对应到$Spec(A)$的子集$S^{-1}X$（21.1中的同胚像），$Spec(S^{-1}B)(=Spec(f(S)^{-1}B))$对应到$Spec(B)$的子集$S^{-1}Y(=f(S)^{-1}Y)$，证明：$S^{-1}f^*:Spec(S^{-1}B)\to Spec(S^{-1}A)$是$f^*$限制到$S^{-1}Y$，并且$S^{-1}Y=f^{*-1}(S^{-1}X)$。**

**21.3 $\mathfrak a$是$A$的理想，$\mathfrak b=\mathfrak a^e$，$\overline{f}:A/\mathfrak a\to B/\mathfrak b$。将$Spec(A/\mathfrak a)$对应到$V(\mathfrak a)$，$Spec(B/\mathfrak b)$对应到$V(\mathfrak b)$。证明：$\overline{f}^*$是$f^*$限制到$V(\mathfrak b)$。**

**21.4 设$\mathfrak p$是$A$的素理想，取$S=A-\mathfrak p$。在21.2中局部化，再在21.3中商去$S^{-1}\mathfrak p$，说明$f^{*-1}(\mathfrak p)$和$Spec(B_\mathfrak p/\mathfrak p B_\mathfrak p)=Spec(k(\mathfrak p)\otimes_A B)$同胚。其中$k(\mathfrak p)$是局部环$A_\mathfrak p$的剩余域。**

**称$Spec(k(\mathfrak p)\otimes_A B)$是$f^*$在点$\mathfrak p$处的纤维。**

证：

21.1

由3.11，可取$S^{-1}X=\{\mathfrak p\in X|\mathfrak p\cap S=\varnothing\}$。只需说明同胚。由1.E21.4有$Spec(S^{-1}A)$到$V(\ker \phi)$的同胚。然而$V(\ker \phi)=V(\{a|\exists s, as=0\})=S^{-1}X$

21.2 

的确：$S^{-1}Y$映到了$S^{-1}X$内，并且也只有$S^{-1}Y$元素能够被映到$S^{-1}X$内。

21.3

同样地，$V(\mathfrak b)$的确被映到了$V(\mathfrak a)$。

21.4

结合21.3，21.4即证。



**22. 给定环$A$和素理想$\mathfrak p$，那么$Spec(A_\mathfrak p)$到$Spec(A)$中的同胚像是全体包含$\mathfrak p$的开集的交。**

证：

由3.E21.1，同胚像为$\{\mathfrak q\in Spec(A)|\mathfrak q\cap (A-\mathfrak p)=\varnothing\}\\=\{\mathfrak q\in Spec(A)|\mathfrak q\subseteq \mathfrak p\}=\cap_{a\not\in \mathfrak p} X_{a}$



#### 仿射概形

**23. 给定环$A$，$X=Spec(A)$，主开集$U=X_f$。**

**23.1 $U=X_f$，$A(U)=A_f$是良定义的（即：与$X_f$的选取无关）**

**23.2 $U'=X_g$，且$U'\subseteq U$。证明：存在$n>0,u\in A: g^n=uf$。然后诱导出$\rho:A(U)\to A(U'): a/f^m\mapsto au^m/g^{mn}$。并且证明$\rho$仅和$U,U'$有关。**

称$\rho$为限制映射。

**23.3 $U=U'$时$\rho=id$**

**23.4 $U\supseteq U'\supseteq U''$，则：**

$\xymatrix{A(U)\ar[rr]\ar[rd]&&A(U'')\\&A(U')\ar[ru]}$交换。

**23.5 $x(=\mathfrak p)$是$X$中一点，则$\varinjlim_{U\ni x}A(U)\cong A_\mathfrak p$**



上述结论建立了素谱上的环预层，并且满足其在每一点的茎是环在该点处局部化。

证：

23.1 考虑饱和乘性子集结论3.E8Rmk.，结论自明。

若$X_f=X_g$，$f\in \mathfrak p\iff g\in\mathfrak p$，$r((f))=r((g)): g^x=uf;f^y=vg$。

$A_f\cong A_g: a/f^n\mapsto a/g^n$。

满性显然，单性只需注意$a/g^n=0\implies ag^m=0\implies ag^mv^m=0\implies af^{ym}=0$

23.2 $X_g\subseteq X_f\implies (g\notin\mathfrak p\implies f\notin\mathfrak p)\\\implies(f\in\mathfrak p\implies g\in \mathfrak p)$

将所有这样的$\mathfrak p$相交，有$g\subseteq r((f))$，即证。23.1保证我们可以随意地选定一组满足要求的$f,g$，此时$au^m/g^{mn}=au'^{m'}/g^{m'n}$

23.3 显然。

23.4 直接验证即可。

23.5 

为了和一般的预层相对应，对于任意开集$V$，由于$A(X_f)$形式的环是Co-final的，因此仍然只需考虑邻域为主开集的情况。

有环同态$\oplus A(U)\to A_\mathfrak p:(a_1/f_1^{m_1},\cdots,a_n/f_n^{m_n})\mapsto (a_1\cdots a_n)/(\prod f_i^{m_i})$

于是自然诱导出一个同态$\varinjlim A(U)\to A_\mathfrak p$

满显然。单只需注意到任何$\varinjlim A(U)$的元素都是某个$A_f$的像，设为$a/f^n$的像，接下来只需显然地验证。



**24. 证明3.E23中的预层满足：$X$被$(U_i)_{i\in I}$开覆盖。如果对于每个$i$，存在$s_i\in A(U_i)$满足对于任意$i,j$，$s_i,s_j$限制进$A(U_i\cap U_j)$的像相同；那么存在唯一的$s\in A(X)=A$满足它限制进$A(U_i)$的像是$s_i$。**

（这说明3.E23中的预层是层）

证：

紧性保证可以假定有限开覆盖，不妨取为有限个数的主开集。

唯一性：若$a,a'\to_i s_i $，即$f_i^{n_i}\cdot(a-a')=0$。由于开覆盖，$\sum t_if_i^n=1$。于是$0=\sum t_if_i^{n_i} \cdot(a-a')=a-a'$

存在性：只需考虑$A(U_1),A(U_2)\longrightarrow A(U_1\cup U_2)$。$u_1/f_1^m,u_2/f_2^n$限制进$A(U_1\cap U_2)$的像分别是$(u_1f_2^m)/(f_1f_2)^m,(u_2f_1^n)/(f_1f_2)^n$

即：$u_1f_2^m(f_1f_2)^{n+t}=u_2f_1^n(f_1f_2)^{m+t}$，取它为$ A$的元素即可。



Rmk.(Affine Scheme.)

实际上对于每个开集$U\subseteq Spec(A)$，我们为其指定的环是开集上的正则函数环。这里需要更进一步地解释：正则函数将素谱$X=Spec(A)$中的一个元素$x$映入剩余域$\kappa(\alpha)$中。对于主开集$X_f$，其上 的正则函数一定形如$a(x)/f^n(x)$，对于更大的开集，使用3.E.24（即Gluing Condition）定义即可。

古典的例子即考虑$A=\C[x]$的情况。



**25. $f:A\to B;g:A\to C$是环同态，于是有$h:A\to B\otimes_A C$。设$X,Y,Z,T$分别是$A,B,C,B\otimes_AC$的素谱，那么$h^*(T)=f^*(Y)\cap g^*(Z)$**

证：

由3.E21，$\mathfrak p\in h^*(T)\iff (B\otimes_A C)\otimes_A k(\mathfrak p)\neq 0\iff (B\otimes_A k)\otimes_k(C\otimes_Ak)\neq 0\\\iff B\otimes_Ak\neq 0\and C\otimes_A k\neq 0\iff \mathfrak p\in f^*(Y)\cap g^*(Z)$



**26. 设$(B_\alpha,g_{\alpha\beta})$是一组正向系统，$B$是正向极限；以及有$f_\alpha: A\to B_\alpha$，并且满足$f_\beta=f_\alpha\circ g_{\alpha\beta}$。那么这诱导出了映射$f:A\to B$。证明：$f^*(Spec(B))=\cap_{\alpha}f_\alpha^*(Spec(B_\alpha))$**

证：

对于$\mathfrak p\in Spec(A)$，$f^{*-1}(\mathfrak p)$同胚于以下的素谱：$B\otimes_Ak(\mathfrak p)\cong \varinjlim (B_\alpha\otimes_A k(\mathfrak p))$。

那么由2.E21:$f^{*-1}(\mathfrak p)=\varnothing\iff \exists\alpha ,B_\alpha\otimes_A k(\mathfrak p)=0$，于是得到结论。



#### 可构造拓扑

**27.1 考虑2.E23中构造出的任意指标集上$A-$代数$B_\alpha$的张量积$B$，有$f:A\to B$。那么$f^*(Spec(B))=\cap_\alpha f^*_\alpha (Spec(B_\alpha))$**

**27.2 给定$f_\alpha :A\to B_\alpha$，其中$\alpha$是有限指标集中元素。令$B=\prod_\alpha B_\alpha$。定义$f:A\to B: x\mapsto (f_\alpha(x))$。那么$f^*(Spec(B))=\cup_\alpha f_\alpha^*(Spec(B_\alpha))$**

**27.3 $Spec(A)$中全体形如$f^*(Spec(B))$的子集满足闭集公理，于是诱导出一个拓扑，称为可构造拓扑。这个拓扑比Zariski拓扑更精细。**

**27.4 在可构造拓扑下，$Spec(A)$是紧的。**

**27.5 对于$X_g$，在可构造拓扑中它既开又闭。**

**27.6 设$C'$是最粗的满足$X_g$既开又闭的拓扑，那么拓扑空间$(X,C')$是Hausdorff的。**

**27.7 记可构造拓扑为$(X,C)$，那么$(X,C)\to (X,C'):x\mapsto x$是同胚。从而$E\subseteq X$具有形式$f^*(Spec(B))\iff$在$C'$中$E$闭。（这说明$C=C'$）**

**27.8 $(X,C)$是紧、Hausdorff、全不连通的。**

证：

27.1 由3.E.26 ，$f^*(Spec(B))=\cap_{\Lambda\subseteq \Alpha}f^*_\Lambda (Spec(B_\Lambda))$

再结合3.E.25：$f^*_\Lambda(Spec (B_\Lambda))=\cap f^*_\alpha(Spec(B_\alpha))$，于是得到了结论。

27.2 $\mathfrak p\in Spec(A)$，$f^{*-1}(\mathfrak p)$同胚于以下的素谱：$B\otimes_A k(\mathfrak p)\cong \oplus(B_\alpha\otimes_A k(\mathfrak p ))$

那么$f^{*-1}(\mathfrak p)=\varnothing\iff \forall \alpha, B_\alpha\otimes_A k(\mathfrak p)=0$，即证。

27.3 闭集公理中只需验证$Spec(A)$闭，但是取$B=A,f=id$即说明。

精细只需说明在可构造拓扑中$X_g$仍然是开的。

然而这是显然的：取$B=A/r((g))$即可。

27.4 考虑一族满足有限交性质的闭集：$\{Im f^*_i\}$。其中$f_i:A\to B_i$. 那么每个有限子集$J$, $B_J$非零。于是它的正向极限非零，进而$\cap Im f_i^*\neq\varnothing$，从而结论得证。

27.5 开已经被验证了。闭：取$B=A_g$即可。

27.6 取$f\in\mathfrak p_x-\mathfrak p_y$, 则$y\in X_f, x\in V(f)$，它们都是开的。

27.7 双射显然。$(X,C)\to (X,C')$ 当然是连续的：$(X,C')$的开集一定是$X_f,X-X_f$的并，它们的原像也是开的，从而得证。

而熟知紧拓扑空间$Y$到Hausdorff空间$Z$的连续双射$\psi$是同胚，得证。

（It suffices to prove it takes open sets to open sets. Let $U ⊆ Y$ be open; then its complement $K = Y-U$ is closed. As a closed subset of a compact space, K is compact. Since $ψ$ is continuous, $ψ(K)$ is compact. As a compact subset of a Hausdorff space, $ψ(K)$ is closed. Thus $Z-ψ(K) = ψ(Y-K) = ψ(U)$） 

27.8 由于$(X,C)$和$(X,C')$同胚，且后者Hausdorff，于是说明了Hausdorff性。

只需说明全不连通。同理27.6的取法，对于任意集合$S$, $x\neq y,x,y\in S$有$S=(X_f\cap S)\coprod (V(f)\cap S)$是分划，从而不连通。



**29. $f:A\to B$，则$f^*: Spec(B)\to Spec(A)$是连续闭映射，其中$Spec$上配备的是可构造拓扑。**

证：连续闭映射等价于每个闭集的像是闭集。

若可构造拓扑下闭集$F\subseteq Spec(B)$，设$F=Im\ g^*$，其中$g:B\to C$。则$f^*(F)= Im (fg)^*$，从而也是闭的。



**30. Zariski拓扑和可构造拓扑相同$\iff A/\mathfrak R$绝对平坦。**

证：$\implies$由3.E11，Zariski拓扑和可构造拓扑相同$\implies$ $Spec(A)_{Zar}$ Hausdorff$\implies A/\mathfrak R$绝对平坦。

$\Longleftarrow $ $A/\mathfrak R$绝对平坦$\implies Spec(A)_{Zar}$ Hausdorff. 而$Spec(A)_{construct}\to Spec(A)_{Zar}$是连续双射，且前者紧，后者Hausdorff，于是这个映射是同胚。从而$Spec(A)_{construct}=Spec(A)_{Zar}$.



