# Introduction to Commutative Algebra - Part2.

Note. 4.E13

## 4. 准素分解

### 4.0 引言

对一个理想做准素分解得到$\mathfrak a=\cap_{i=1}^n \mathfrak q_i$。今后的结论将指出如果这样的分解是极小的，它对应到代数簇上正是对簇进行不可约分支分解。

### 4.1 准素理想

**定义（准素理想）称一个理想$\mathfrak q$是准素理想，如果$\mathfrak q\neq A$且$xy\in\mathfrak q\implies x\in\mathfrak q\or y^n\in\mathfrak q$对某些$n>0$成立。**
从而：$\mathfrak q$准素$\iff A/\mathfrak q\neq 0$且每个零因子都是幂零元。

**性质（准素理想的性质）**
**素理想准素；准素理想的局限准素（$A/\mathfrak q^c$同构与$B/\mathfrak q$的子环）**

**4.1（$\mathfrak p-$准素）$\mathfrak q$是准素理想，那么$r(\mathfrak q)$是最小的包含$\mathfrak q$的素理想，记为$\mathfrak p$，则称$\mathfrak q$是$\mathfrak p-$准素的。**
证：
由1.8，只需说明$r(\mathfrak q)$是素的。若$xy\in r(\mathfrak q)$，则$(xy)^n\in\mathfrak q$。从而$x^n\in\mathfrak q\or y^{mn}\in\mathfrak q$即$x\in r(\mathfrak q)\or y\in r(\mathfrak q)$。

Remarks and Examples.

1. $\Z$中的情况是熟知的：$(0),(p^n)$是全体的准素理想，同时它也是全体根理想为素的理想。但是最后这个论断对于一般的环中并不一定成立。
2. 准素理想不一定具有形式$\mathfrak p^n$：$A=k[x,y],\mathfrak q=(x,y^2)$。$A/\mathfrak q\cong k[y]/(y^2)$，其中的零因子是$y$的倍数，从而幂零。于是说明$\mathfrak q$的确准素。然而$\mathfrak q$是$(x,y)-$准素的，若其具有形式$\mathfrak p^n$，一定有$\mathfrak p=(x,y)$。但是$(x,y)^2\subset \mathfrak q\subset (x,y)$，从而不可能具有形式$\mathfrak p^n$。
3. 根理想为素的理想不一定准素，更进一步地：$\mathfrak p^n$不一定准素：取$A=k[x,y,z]/(xy-z^2)$，$\mathfrak p=(x,z)$。由于$A/\mathfrak p\cong k[y]$是整环，因而它的确素。而对于$\mathfrak p^2$：$\bar{x}\bar{y}=\bar{z}^2\in\mathfrak p^2$，但是$\bar{x}\notin\mathfrak p^2,\bar{y}\notin\mathfrak r(\mathfrak p^2)=\mathfrak p$，从而它并不准素。

尽管有Remark3.的反例存在，将根理想为素这一条件更换为根理想极大则能够得到结论成立。
**4.2 $r(\mathfrak a)$极大，则$\mathfrak a$准素。特殊地，给定极大理想$\mathfrak m$，$\mathfrak m^n$准素。**
证：
$r(\mathfrak a)$在$A/\mathfrak a$中的像仍然极大，并且是幂零根。那么$A/\mathfrak a$局部，从而$A/\mathfrak a$中元素要么是单位，要么是幂零元。（若有一个非单位非幂零元的元素，它应该被某个极大理想包含，于是矛盾）

### 4.2 准素分解

**4.3（$p-$交$p-$还是$p-$）对于$\mathfrak p-$准素理想$\mathfrak q_i$，$\mathfrak q=\cap_{i=1}^n \mathfrak q_i$仍然是$\mathfrak p-$准素的。**
证：
$r(\mathfrak q)=\cap r(\mathfrak q_i)=\mathfrak p$。令$xy\in\mathfrak q,y\notin\mathfrak q$，即存在某个$i,xy\in\mathfrak q_i,y\notin\mathfrak q_i$，从而说明$x\in\mathfrak p$，进而准素。

**4.4（准素理想的商理想）设$\mathfrak q$是$\mathfrak p-$准素的，$x\in A$。**
**4.4.1 $x\in\mathfrak q$，则$(\mathfrak q:x)=(1)$**
**4.4.2 $x\notin\mathfrak q$，则$(\mathfrak q:x)$是$\mathfrak p-$准素的。**
**4.4.3 $x\notin\mathfrak p$，则$(\mathfrak q:x)=\mathfrak q$**
证：
4.4.1 显然
4.4.2 $y\in(\mathfrak q:x)\iff xy\in\mathfrak q\implies y\in r(\mathfrak q)\implies y\in\mathfrak p$，于是$\mathfrak q\subseteq (\mathfrak q:x)\subseteq \mathfrak p$。两侧取根理想，$r(\mathfrak q:x)=\mathfrak p$。
若$yz\in(\mathfrak q:x)$，并且$y\notin\mathfrak p$，则$xyz\in\mathfrak q$，从而$xz\in\mathfrak q$，于是$z\in(\mathfrak q:x)$，从而说明了准素。
4.4.3 有定义显然。

准素分解是将一个理想分解成有限个准素理想的交的过程。（尽管这个分解并不总是一定存在，但是它在代数几何中意义是明显的）
更进一步地，如果：1. $r(\mathfrak q_i)$各不相同；2. $\mathfrak q_i\not\supseteq \cap_{j\neq i} \mathfrak q_j$。那么称这个准素分解是极小的。
**每个准素分解都可以被约化为极小准素分解。**
证：
1.条件利用4.3可以取到。
2.若$\mathfrak q_i\supseteq \cap_{j\neq i}\mathfrak q_j$，将$\mathfrak q_i$除掉即可。

接下来研究可准素分解理想的准素分解的唯一性。
**4.5（第一唯一性定理）设$\mathfrak a$可准素分解，对于极小准素分解$\mathfrak a=\cap_{i=1}^n \mathfrak q_i$，取$\mathfrak p_i=r(\mathfrak q_i)$，则$\mathfrak p_i$是全体$\{r(\mathfrak a:x)|x\in A\}\cap Spec(A)$，进而与准素分解的选取无关。**
证：由于$(\mathfrak a:x)=\cap (\mathfrak q_i:x)$，那么$r(\mathfrak a:x)=\cap r(\mathfrak q_i:x)\xlongequal[]{4.4}\cap_{x\notin \mathfrak q_i} \mathfrak p_i$

若$r(\mathfrak a:x)$素，由包容引理1.11，有$r(\mathfrak a:x)=\mathfrak p_i$

反过来，对于每个$i$，存在$x_i\notin \mathfrak q_i,x_i\in \cap_{j\neq i} \mathfrak q_j$，那么$r(\mathfrak a:x_i)=\mathfrak p_i$。

于是说明了定理的正确性。



Cor. 对于每个$i$，存在$x_i\in A$, $(a:x_i)$是$\mathfrak p_i-$准素的。

Cor. 对于$A-$模$A/\mathfrak a$，$\mathfrak p_i$正是$A/\mathfrak a$中每个元素的零化理想的根理想与$Spec(A)$的交。

Rmk. 准素分解并不一定唯一。



沿用4.5的记号，称素理想$\mathfrak p_i$属于理想$\mathfrak a$。那么：$\mathfrak a$准素当且仅当仅有一个素理想属于它。极小准素分解中对应的那些素理想中的极小元$\{\mathfrak p_i\}$称为孤立素理想（又称极小素理想，4.6解释了为什么这个名称是不会引起歧义的），而其余的素理想则称为嵌入素理想。（注意：极小的准素分解并不能保证对应的素理想之间不存在包含关系）

孤立和嵌入的例子在考虑代数簇时有了直观的几何意义：例如取$A=k[x,y]$, $\mathfrak a=(x^2,xy)$，则$\mathfrak a= (x)\cap (x,y)^2$, 但是$(x)\subseteq (x,y)$，从而$(x)$是孤立的，$(x,y)$是嵌入的。

对应到理想对应的代数簇上，此时$\mathfrak a$当然对应的直线$x=0$，因此$(x)$是孤立的在几何层面上是显然的，而$(x,y)$正是对应着一个嵌入的子簇$(0,0)$。

这解释了为什么在4.0中提到的准素分解正是不可约分支分解。



直觉提示孤立素理想和极小素理想相近，接下来的性质表明它们完全相同。

**4.6（孤立素理想是极小素理想）$\mathfrak a$可分解，那么每个素理想$\mathfrak p\supseteq \mathfrak a$都包含着一个从属的素理想。从而孤立素理想（即从属素理想的极小元）正是全体包含$\mathfrak a$的极小素理想。**

证：

$\mathfrak p\supseteq \cap \mathfrak q$，则$\mathfrak p=r(\mathfrak p)\supseteq \cap r(\mathfrak q_i)=\cap r(\mathfrak p_i)$，由1.11回避引理，$\mathfrak p\supseteq \mathfrak p_i$对某个$i$成立，从而得证。



### 4.3 准素理想与局部化

**4.8 $S$乘性子集，$\mathfrak q$是$\mathfrak p-$准素的。**

**1. 如果$S\cap \mathfrak p\neq \varnothing$，$S^{-1}\mathfrak q=S^{-1}A$**

**2. 如果$S\cap \mathfrak p=\varnothing$，那么$S^{-1}\mathfrak q$是$S^{-1}\mathfrak p-$准素的，并且它的局限是$\mathfrak q$。进而同理3.11中的素理想对应，准素理想之间也是存在对应的。**

证：

4.8.1 $s\in S\cap \mathfrak p\implies s^n\in S\cap \mathfrak q$对某个$n$成立$\implies s^n/1\in S^{-1}\mathfrak q\implies 1/1\in S^{-1}\mathfrak q\implies S^{-1}\mathfrak q=S^{-1}A$

4.8.2 $S\cap \mathfrak p=\varnothing$，于是$s\in S, as\in\mathfrak q\implies a\in\mathfrak q$，从而由3.11$\mathfrak q^{ec}=\cup_{s\in S}(\mathfrak q:s)=\mathfrak q$。

这里的扩张和局限是在环同态$A\to S^{-1}A$下的。

于是$r(S^{-1}\mathfrak q)=S^{-1}r(\mathfrak q)=S^{-1}\mathfrak p$，并且$S^{-1}A/S^{-1}\mathfrak q\cong S^{-1}(A/\mathfrak q)$

若$[a]/s\cdot[a']/s'=0\ ([a']/s\neq 0)$，即$\exists t\in S, [aa']t=0$，那么$[a]\cdot[a't]=0$，由于$[a']/s\neq 0$，当然$[a't]\neq 0$，从而$[a]$是零因子，于是幂零，从而$[a]/s$幂零，这就说明了$S^{-1}\mathfrak q$准素。



由4.8.2.的结果，记$S^{-1}\mathfrak a$的局限为$S(\mathfrak a)$，那么$S(\mathfrak q)=\mathfrak q$，自然想问一般的理想在$S(-)$下的表现如何。

**4.9（$S(-)$的性质）设$\mathfrak a$有准素分解$\bigcap _{i=1}^n\mathfrak q_i$，$\mathfrak p_i=r(\mathfrak q_i)$，且$S$和$\mathfrak p_1,\cdots,\mathfrak p_m$不交，但和$\mathfrak p_{m+1},\cdots,\mathfrak p_n$相交。那么：**

**$\displaystyle{S^{-1}\mathfrak a=\bigcap_{i=1}^mS^{-1}\mathfrak q_i,\quad S(\mathfrak a)=\bigcap_{i=1}^m\mathfrak q_i}$**

并且这两者仍然是准素分解。

证：

第一式显然，$S^{-1}\mathfrak q_i$准素（由4.8.）

而$S(\mathfrak a)=(S^{-1}\mathfrak a)^c=\displaystyle{\bigcap _{i=1}^m (S^{-1}\mathfrak q_i)^c=\bigcap_{i=1}^m\mathfrak q_i}$



称一族从属于理想$\mathfrak a$的素理想族$\Sigma$是孤立的，如果$\mathfrak a\subseteq \mathfrak p'\subseteq \mathfrak p\in\Sigma \implies \mathfrak p'\in \Sigma$.

对于一个孤立素理想族，$S-\cup_{\Sigma}\mathfrak p$是乘性子集，且对于任何从属于$\mathfrak a$的素理想$\mathfrak p'$，$\mathfrak p'\in \Sigma\implies \mathfrak p'\cap S=\varnothing;\\\mathfrak p'\notin \Sigma\implies \mathfrak p'\notin \cup_{\Sigma}\mathfrak p(1.11)\implies \mathfrak p'\cap S=\varnothing.$



于是，结合4.9和这个结论，得到：

**4.10（第二唯一性定理）设$\mathfrak a$可分解，$\mathfrak a=\cap \mathfrak q_i$是极小准素分解，$\Sigma=\{\mathfrak p_{i_1},\cdots,\mathfrak p_{i_m}\}$是孤立素理想族，那么$\mathfrak q_{i_1}\cap \cdots\mathfrak q_{i_m}$与分解无关。**

证：$\mathfrak q_{i_1}\cap \cdots\cap \mathfrak q_{i_m}=S(\mathfrak a)$，其中$S=A-\mathfrak p_{i_1}\cup\cdots\cup \mathfrak p_{i_m}$由第一唯一性定理与分解无关。


做为推论，有：

**4.11（孤立分支唯一）孤立准素分支（即孤立素理想$\mathfrak p_j$对应的准素理想$\mathfrak q_j$）被$\mathfrak a$唯一决定。**

证：取$\Sigma$为一个极小素理想组成的单元集即可。

### 4.4 可分解理想

最后我们讨论一些可分解理想的性质。

**4.7 $\mathfrak a$是可分解理想，给定极小准素分解$\mathfrak a=\cap _{i=1}^n\mathfrak q_i$，以及$r(\mathfrak q_i)=\mathfrak p_i$，那么$\displaystyle{\bigcup_{i=1}^n\mathfrak p_i=\{x\in A|(\mathfrak a:x)\neq\mathfrak a\}}$**

证：

过渡到商环：如果$\mathfrak a$可分解，那么在商环$A/\mathfrak a$中$0$理想可分解。即$0=\cap \bar{\mathfrak q_i}$，其中后者是$\mathfrak q_i$在商环中的像，也是准素的。

（注记：如果$\mathfrak a\subseteq \mathfrak q$，那么$\overline{r(\mathfrak q)}=r(\overline{\mathfrak q})$；更进一步地如果$\mathfrak q$是准素的，那么$\overline{\mathfrak q}$也是准素的）

由上，只需说明零理想的极小准素分解对应的素理想的并是全体零因子，记零因子集合为$D$，那么：

$D=\cup_{x\neq 0}r(0:x)$，而由4.5的证明$r(0:x)=\cap_{x\notin\mathfrak q_j}\mathfrak p_j\subseteq \mathfrak p_j$ 对某些$j$成立。从而$D\subseteq \cup\mathfrak p_i$，但是4.5也说明了$\mathfrak p_i$具有形式$r(0:x)$，于是得证。



### 4.5(E)

**1. $\mathfrak a$如果存在准素分解，那么$Spec(A/\mathfrak a)$仅有有限个不可约分支。**

证：

由1.20，$Spec(A/\mathfrak a)$的不可约分支为全体$V(\overline{\mathfrak p})$，其中$\mathfrak p$为包含$\mathfrak a$的极小素理想。由于准素分解存在，取出极小准素分解，那么包含$\mathfrak a$的极小素理想当然有限个，于是结论自明。

**2. $\mathfrak a=r(\mathfrak a)$，那么$\mathfrak a$不含有嵌入素理想。**

证：

$r(\mathfrak a)$一定可分解。

给定一个极小准素分解$\mathfrak a=\cap \mathfrak q_i$，$\mathfrak a=r(\mathfrak a)=\cap r(\mathfrak q_i)=\cap \mathfrak p_i$，那么后者也是$\mathfrak a$的一个极小准素分解。于是自然不存在嵌入分支。



**3. 如果$A$绝对平坦，那么每个素理想都是极大的。**

证：

对于一个素理想$\mathfrak p$，对于$x\in A-\mathfrak p$，由于主理想幂等，$\exists a\in A$，$x=ax^2$，即$x(ax-1)=0$。

那么在$A/\mathfrak p$中$\overline{x}(\overline{ax}-\overline{1})=\overline{0}$。然而$\overline{ax}-\overline1$是零因子，于是只有$\overline{ax}=\overline1$（整环），从而$\overline{x}$是单位。



**4. 对于环$\Z[t]$，理想$\mathfrak m =(2,t)$是极大的，$\mathfrak q=(4,t)$是$\mathfrak m-$准素的，但不是$\mathfrak m$的幂。（4.2的逆命题反例）**

证：$\Z[t]/\mathfrak m=F_2$，于是说明极大。$\Z[t]/\mathfrak q=\Z/4\Z$，那么每个零因子(2)是幂等的($2^2=0$)，从而说明准素。

由于 $\mathfrak q=\{tP(t)+4c\}$

$f^m\in\mathfrak q\iff f$的常数项是$2$的倍数。于是$r(\mathfrak q)=\{tP(t)+2c\}=\mathfrak m$

而$\mathfrak m\supset \mathfrak q\supset \mathfrak m^2$，从而说明了结论。



**5. 对于域上的多项式环$K[x,y,z]$，$\mathfrak p_1=(x,y);\mathfrak p_2=(x,z);\mathfrak m=(x,y,z)$。证明$\mathfrak p_{1,2}$是素的，$\mathfrak m$是极大的。取$\mathfrak a=\mathfrak p_1\mathfrak p_2$，说明$\mathfrak a=\mathfrak p_1\cap \mathfrak p_2\cap \mathfrak m^2$是极小准素分解，指出孤立分支和嵌入分支。**

证：

不难验证极小准素分解。孤立分支为$(x,y);(x,z)$，嵌入分支为$(x,y,z)$。



**6. $X$是无限元素的紧Hausdorff空间，$C(X)$是其上连续实值函数环。在这个环中零理想是否可以分解？**

证：

如果零理想可以分解，那么$Spec(C(X))$仅存在有限个不可约分支。然而$\mathfrak m_x,\mathfrak m_y$从属于不同的不可约分支，且$x,y$选择无限，矛盾。



**7. 给定环$A$，其上多项式环$A[x]$。对理想$\mathfrak a$，有集合$\mathfrak a[x]$。**

**7.1 对于环同态$A\to A[x]$，$\mathfrak a[x]=\mathfrak a^e$。**

**7.2 $\mathfrak p$素，则$\mathfrak p[x]$素。**

**7.3 $\mathfrak q$是$\mathfrak p-$准素，那么$\mathfrak q[x]$是$\mathfrak p[x]-$准素。**

**7.4 对于极小准素分解$\mathfrak a=\cap \mathfrak q_i$，$\mathfrak a[x]=\cap\mathfrak q_i[x]$也是极小准素分解。**

**7.5 $\mathfrak p$极小，则$\mathfrak p[x]$极小。**

证：

7.1 注意到$\mathfrak a\cdot A[x]=\mathfrak a[x]$，则命题显然。

7.2 即2.E7.

7.3 首先说明准素：$A[x]/\mathfrak q[x]\cong (A/\mathfrak q)[x]$，则对于任何$(A/\mathfrak q)[x]$中的零因子，设为$f$，那么由1.E2.3，存在$t(\neq 0)\in A/\mathfrak q$使得$tf=0$，$f$的每个系数都是零因子。而在$A/\mathfrak q$中零因子都是幂零元，再次运用1.E.2.2，即有$f$幂零。

接下来说明$\mathfrak p[x]-$准素。

$r(\mathfrak q[x])=r(\mathfrak q\cdot(x)+\mathfrak q)=r(r(\mathfrak q)+r(\mathfrak q\cdot (x)))=r(\mathfrak p+r(\mathfrak q)\cap r((x)))\\=r(\mathfrak p[x])=\mathfrak p[x]$

7.4 只需说明极小性。根理想互不相同是显然的；包含性是显然的。

7.5 $\mathfrak p=\mathfrak p$自然是极小准素分解，那么$\mathfrak p[x]=\mathfrak p[x]$也是。于是$\mathfrak p[x]$从属于$\mathfrak p[x]$，自然是极小素理想。



**8. 给定域$k$，其上多项式环$k[x_1,\cdots,x_n]$。证明理想$\mathfrak p_i=(x_1,\cdots,x_i)$是素的，并且它的任意次幂是准素的。**

证：

$A/\mathfrak p_i=k[x_{i+1},\cdots,x_n]$当然是整环。

考虑$xy\in \mathfrak p_i^m$，那么$xy$只含有$x_1,\cdots,x_i$，没有常数项，并且每项次数至少为$m$。于是利用整除理论，如果$x\notin \mathfrak {p_i^m}$，当然只能有$y^n\in\mathfrak {p_i^m}$。



**9.1 对于环$A$，$D(A)$指满足以下条件的素理想构成的集合：$\exists a\in A$，使得$\mathfrak p$是所有包含$(0: a)$的素理想中极小的。证明：$x\in A$是零因子$\iff x\in\mathfrak p$对某个$\mathfrak p\in D(A)$成立。**

**9.2 如果$S$是$A$的乘性子集，将$Spec(S^{-1}A)$视作$Spec(A)$的子集(3.E21)，那么$D(S^{-1}A)=D(A)\cap Spec(S^{-1}A)$**

**9.3 如果零理想可分解，证明$D(A)$是全体从属于它的素理想集合。**

证：

9.1 如果$x$是零因子，那么$x\in \mathfrak a=(0: a)$，于是自然属于某个包含$(0: a)$中极小的素理想。

反过来如果$x$属于某个包含$(0: a)$的极小素理想，不妨设$x\in\mathfrak p$，其中后者是包含$\mathfrak a=(0:a)$的素理想中的极小元。那么由2.E9，$x$在$A/\mathfrak a$中是零因子。即$\exists y$，$xy\in\mathfrak a$，从而$xya=0$即证。

9.2 首先$S^{-1}Ann(x)=Ann(x)^e=S^{-1}((0):(x))=(S^{-1}(0):S^{-1}(x))\\=Ann(S^{-1}(x))=Ann(x/1)$，并且$Ann(x/s)=Ann(x/1)$.

而$S^{-1}A$的每个素理想都是扩张理想（3.11），因此可记为$S^{-1}\mathfrak p$。那么$S^{-1}\mathfrak p\in D(S^{-1}A)\iff \exists x,S^{-1}\mathfrak p$是包含$Ann(x/s)=Ann(x/1)=S^{-1}Ann(x)$的极小素理想。那么$\mathfrak p$也是包含$Ann(x)$的极小素理想，从而说明了$D(S^{-1}A)=D(A)\cap Spec(S^{-1}A)$.

9.3 由4.5,4.7，零理想的从属素理想是全体$r(0:x)$中出现的素理想，于是$\{associative\ to \ 0\}\subseteq D(A)$。

反过来对于$\mathfrak p\in D(A)$，设$x$使得$\mathfrak p$是包含$\mathfrak a=(0:x)$的极小素理想，即$\mathfrak p$是由零因子组成的素理想。

由4.5的证明$r(0:x)=\cap_{x\notin\mathfrak q_j}\mathfrak p_j$，那么$\mathfrak p\supseteq\cap\mathfrak p_j$，由1.11必定有$\mathfrak p\supseteq \mathfrak p_j$对某个$j$成立。但与此同时$\mathfrak p_j$也包含着$(0:x)$，于是由$\mathfrak p$的极小性，只能有$\mathfrak p=\mathfrak p_j$成立，从而证明了结论。



**10. 对于任何环$A$的素理想$\mathfrak p$，记$S_\mathfrak p(0)$是同态$A\to A_\mathfrak p$的核。证明：**

**10.1 $S_\mathfrak p(0)\subseteq \mathfrak p$**

**10.2 $r(S_\mathfrak p(0))=\mathfrak p\iff \mathfrak p$极小。**

**10.3 如果$\mathfrak p\supseteq \mathfrak p'$，那么$S_\mathfrak p(0)\subseteq S_\mathfrak p'(0)$**

**10.4 $\cap_{\mathfrak p\in D(A)}S_\mathfrak p(0)=0$，其中$D(A)$的定义见4.E9.**

证：

10.1 显见这里$S_\mathfrak p(0)$和正文（定理4.9）前的$S(\mathfrak a)$的定义是一致的。

如果$x\notin\mathfrak p$，且$x/1=0$。即$\exists s\in A-\mathfrak p,xs=0\in\mathfrak p$，矛盾。

10.2 

$\Longleftarrow$方向是显然的。

对于$\implies $，假定$\mathfrak p=r(S_\mathfrak p(0))$。则$\forall x\in\mathfrak p\iff\exists n,\exists s\in A-\mathfrak p, x^ns=0$。

若存在素理想$\mathfrak q\subset \mathfrak p$，必定存在$x\in\mathfrak p$，但$x\notin\mathfrak q$。由于存在$s\in A-\mathfrak p,x^ns=0$，且$s\notin\mathfrak q$，那么只能有$x^n\in\mathfrak q$。但是由素理想性质以及$x\notin\mathfrak q$立刻得到矛盾。

10.3

注意：$x\in S_\mathfrak p(0)\iff \exists s\in A-\mathfrak p,xs=0\iff x\in\cup_{s\in A-\mathfrak p} Ann(s)$，于是命题显然。

10.4

若$x\neq 0$，选出$(0:x)$的一个极小素理想$\mathfrak p$，那么在$A_\mathfrak p$中$x/1$如果为0就要求$\exists s\in A-\mathfrak p$，$sx=0$。即$s\in\mathfrak (0:x)\subseteq\mathfrak p\and s\in A-\mathfrak p$，这是不可能做到的。于是$x\notin S_\mathfrak p(0)$，得证。



**11.1 $\mathfrak p$是极小素理想，那么$S_\mathfrak p(0)$是最小的$\mathfrak p-$准素理想。**

**11.2 记$\mathfrak a=\cap_{\mathfrak p\ minimal} S_\mathfrak p(0)$，则$\mathfrak a\in \mathfrak R(A)$**

**11.3 如果在环$A$中零理想可分解，那么$\mathfrak a=0\iff 0$的所有从属素理想都是孤立的。**

证：

11.1 首先有$r(S_\mathfrak p (0))=\mathfrak p$（4.E10.2），其次如果$xy\in S_\mathfrak p(0)$ ，存在$s\in A-\mathfrak p, sxy=0$，再设$y\notin S_{\mathfrak p}(0)$，即$sy\neq 0$，于是$x/1$在局部环$A_\mathfrak p$中是零因子。然而$\mathfrak p$是极小的，于是在$A_\mathfrak p$中不再存在除了极大理想$\mathfrak pA_\mathfrak p$以外的理想。然而零因子非单位，于是一定能够包含在极大理想内，进而$x/1\in \mathfrak pA_\mathfrak p$，即$x\in\mathfrak p=r(S_\mathfrak p (0))$，从而说明了准素。

对于任何一个$\mathfrak p-$准素理想$\mathfrak q$，由于$r(\mathfrak q)=\mathfrak p$，必定有$\mathfrak q\subseteq \mathfrak p$。对于任意给定的$x\in S_\mathfrak p(0)$，那么$\exists s\in A-\mathfrak p, sx=0$. 若$x\notin \mathfrak q$，由于$0\in\mathfrak q$，只能有$s\in r(\mathfrak q)=\mathfrak p$，矛盾。

于是以上内容说明了结论。

11.2 $\mathfrak a$包含在所有极小素理想内，进而包含在所有素理想内，于是结论自明。

11.3 如果$0=\cap S_{\mathfrak p_i}(0)$，它的从属素理想族是极小素理想族的子族，自然孤立。

反过来假定准素分解中$0$的从属素理想都是孤立的：4.E10.4表明$0=\cap _{\mathfrak p\in D(A)} S_\mathfrak p(0)$是准素分解。

如果$S_{\mathfrak p_i}(0)\supseteq \cap_{other} S_\mathfrak p(0)$，那么将其约化掉得到了更小的准素分解，从而$0$从属素理想族是$D(A)$的真子族，矛盾！于是$0=\cap _{\mathfrak p\in D(A)}S_\mathfrak p(0)$是约化准素分解。同时从属素理想均孤立表明$D(A)$正是极小素理想族，于是自然有$0=\cap_{\mathfrak p\in D(A)}S_\mathfrak p(0)=\cap _{\mathfrak p\ minimal}S_\mathfrak p(0)=\mathfrak a$



**12. 设$A$是环，$S$是乘性子集，$S(\mathfrak a)$记号意义同前。称$S(\mathfrak a)$为$\mathfrak a$ w.r.t. $S$的饱和化，证明：**

**12.1 $S(\mathfrak a)\cap S(\mathfrak b)=S(\mathfrak a\cap b)$**

**12.2 $S(r(\mathfrak a))=r(S(\mathfrak a))$**

**12.3 $S(\mathfrak a)=(1)\iff \mathfrak a\cap S\neq\varnothing$**

**12.4 $S_1(S_2(\mathfrak a))=(S_1S_2)(\mathfrak a)$**

**12.5 如果$\mathfrak a$存在准素分解，那么理想族$S(\mathfrak a)$（$S$取遍全体乘性子集）是有限的。**

证：

12.1 由1.18，$S(\mathfrak a)\cap S(\mathfrak b)=(S^{-1}\mathfrak a\cap S^{-1}\mathfrak b)^c=[S^{-1}(\mathfrak a\cap b)]^c=S(\mathfrak a\cap \mathfrak b)$

12.2 由1.18显然。

12.3 $S(\mathfrak a)=(1)\iff A\subseteq S^{-1}\mathfrak a\iff 1/1\in S^{-1}\mathfrak a\iff \mathfrak a\cap S\neq\varnothing$

12.4 只需回忆3.E3.

12.5 由定理4.9，结论显然。（至多$2^m$个）



**13. 在环$A$中记素理想$\mathfrak p$的$n-$次形式幂$\mathfrak p^{(n)}$为$S_\mathfrak p(\mathfrak p^n)$，证明：**

**13.1 $\mathfrak p^{(n)}$是$\mathfrak p-$准素的。**

**13.2 如果$\mathfrak p^n$存在准素分解，那么$\mathfrak p^{(n)}$是它的$\mathfrak p-$准素分支。**

**13.3 如果$\mathfrak p^{(m)}\mathfrak p^{(n)}$存在准素分解，那么$\mathfrak p^{(m+n)}$是它的$\mathfrak p-$准素分支。**

**13.4 $\mathfrak p^{(n)}=\mathfrak p^n\iff \mathfrak p^n$准素。**

证：

13.1 首先$r(\mathfrak p^{(n)})=r(S_{\mathfrak p} (\mathfrak p^n))=(r(S_{\mathfrak p}^{-1}\mathfrak  p ^n  ))^c=(S_{\mathfrak p}^{-1}\mathfrak p)^c$（注意$S_{\mathfrak p}^{-1}\mathfrak p$是唯一的极大理想）

那么$r(\mathfrak p^{(n)})=\mathfrak p$.

由4.2，$S_{\mathfrak p}^{-1}\mathfrak p^n$是$S_{\mathfrak p}^{-1}\mathfrak p-$准素的，从而由4.8知准素性。

13.2 



**14. 设$\mathfrak a$是环$A$的可分解理想，$\mathfrak p$是$(\mathfrak a:x)$中的极大者（其中$x\in A-\mathfrak a$）证明$\mathfrak p$是从属于$A$的素理想。**

证：如果$\mathfrak p$是素的，那么$r(\mathfrak p)=\mathfrak p$，自然得到结论。

设$\mathfrak p=(\mathfrak a:m)$, $xy\in\mathfrak p$, i.e. $xym\in\mathfrak a$。如果$xm,ym\notin\mathfrak a$，那么考虑$(\mathfrak a:xm)$。首先$xm\in A-\mathfrak a$，其次注意到$sm=0\implies sxm=0$，而后$y\notin \mathfrak p$，但是$y\in (\mathfrak a:xm)$，于是$(\mathfrak a :m)\subset(\mathfrak a:xm)$，与极大性矛盾！从而证明了结论。



**15. 设$\mathfrak a$在环$A$中可分解，$\Sigma$是$\mathfrak a$的孤立的素理想族。$q_\Sigma$是这族中素理想对应的准素理想的交。$f\in A$满足对于每个从属于$\mathfrak a$的素理想$\mathfrak p$，均有$f\in\mathfrak p\iff \mathfrak p\notin \Sigma$。$S_f=\{f^n|n\in \N\}$，证明$\mathfrak q_\Sigma=S_f(\mathfrak a)=(\mathfrak a:f^n)$对于充分大的$n$成立。	**																																																																																											证：

由4.9，$S_f(\mathfrak a)=\mathfrak q_{\Sigma}$成立。

由于$(\mathfrak a:f^n)=\cap_{r(q_i)\notin \Sigma} (\mathfrak q_i:f^n)\cap_{r(q_i)\in \Sigma} (\mathfrak q_i:f^n)$

对于充分大的$n$，若$r(\mathfrak q_i)\notin \Sigma$，那么$f\in \mathfrak p_i=r(\mathfrak q_i)$，于是当然可假定对于$n>N$，$f^n\in \mathfrak q_i, \forall r(\mathfrak q_i)\notin \Sigma$，即$(\mathfrak q_i:f^n)=A$.

若$r(\mathfrak q_i)\in \Sigma$，那么$f^n\notin \mathfrak q_i$，于是只能有$(\mathfrak q_i:f^n)=\mathfrak q_i$，故$(\mathfrak a:f^n)=\mathfrak q_{\Sigma}$对$n>N$均成立。



**16. $A$的每个理想都存在准素分解，那么对于任何一个分式环$S^{-1}A$也满足每个理想存在准素分解。**

证：由于$S^{-1}A$中的每个理想都是$A$中理想的扩张，那么由4.9结论显然。



#### 环中任一理想存在准素分解的条件

**17. 对于满足以下条件的环$A$：**

**L1. 对每个非$A$的理想$\mathfrak a$和每个素理想$\mathfrak p$，存在$x\notin \mathfrak p$满足$S_{\mathfrak p}(\mathfrak a)=(\mathfrak a:x)$，其中$S_\mathfrak p=A-\mathfrak p$。**

**那么$A$中每个理想都是若干（可能无穷）准素理想的交。**

证：

假定$\mathfrak a$是非$A$理想，$\mathfrak p_1$是包含$\mathfrak a$的极小素理想。由4.E11，$\mathfrak q_1=S_{\mathfrak p_1}(\mathfrak a)$是$\mathfrak p_1-$准素理想，且由条件$\mathfrak q_1=(\mathfrak a:x)$对某个$x\notin\mathfrak p_1$成立。

显然$\mathfrak a\subseteq (\mathfrak a:x)\cap (\mathfrak a+(x))$。反过来，若$y=a+tx$满足$yx\in\mathfrak a$，于是$tx^2\in \mathfrak a\subseteq \mathfrak q_1$。然而$x\notin \mathfrak p_1=r(\mathfrak q_1)$，即$x^n\notin \mathfrak q_1$，但是$tx^2\in \mathfrak q_1$，于是只能有$t\in\mathfrak q_1=(\mathfrak a:x)$。因此$tx\in\mathfrak a$，从而$y\in\mathfrak a$，故反包含得证。

故：$\mathfrak a=\mathfrak q_1\cap (\mathfrak a+(x))$



现在令$\mathfrak a_1$是集合$\{\mathfrak b|\mathfrak b\supseteq \mathfrak a\and \mathfrak q_1\cap \mathfrak b=\mathfrak a\}$中极大元（存在性可以直接应用Zorn引理）。选取$\mathfrak a_1$使得$x\in\mathfrak a_1$，$\mathfrak a_1\not\subseteq \mathfrak p_1$。

反复重复上述构造，构造到第$n$次时我们有$\mathfrak a=\mathfrak q_1\cap \cdots\cap\mathfrak q_n\cap \mathfrak a_n$，$\mathfrak q_1,\cdots,\mathfrak q_n$准素，并且$\mathfrak a_n$是满足$\mathfrak a_{n-1}=\mathfrak b\cap \mathfrak q_n$，$\mathfrak a=\mathfrak q_1\cap \cdots\cap \mathfrak q_n\cap \mathfrak b$，$\mathfrak b\not\subseteq \mathfrak p_n$中极大的$\mathfrak b$。

如果$\mathfrak a_n=(1)$对某步成立，构造终止。

否则注意到$\mathfrak a_{n-1}\subset \mathfrak a_n$由超穷归纳法结论成立。



Remark. 超穷归纳法

对于一个关于序数的命题$P(n)$（其中序数是指典范选取出的良序集）

如果$P(0)$成立；对于任何$a\leq e$（其中$e$是一个恒定的序数）如果假定$\forall b<a$ $P(b)$成立能够推出$P(a)$成立：

那么$P(n)$对所有$n\leq e $成立。

更一般地，如果条件中去掉$a\leq e$中的$\leq e$，那么能够说明$P(n)$对任何序数成立。





**18. 给定以下关于环$A$的性质：**

**L2. 任给一理想$\mathfrak a$和乘性子集的降链$S_1\supseteq S_2\supseteq\cdots$，那么对应的理想降链$S_1(\mathfrak a)\supseteq S_2(\mathfrak a)\supseteq \cdots$稳定。**

**那么$A$的每个理想都有准素分解$\iff$$A$满足$L1,L2$两个条件**

证：

$\implies$ 

L1：由4.9，$S_\mathfrak p(\mathfrak a)=\cap_{\mathfrak p_i \subseteq \mathfrak p}\mathfrak q_i$，容易验证这些$\mathfrak p_i$构成了一个孤立族$\Sigma$。由4.E15，取$f\in \cap_{\mathfrak p\notin\Sigma,\mathfrak p\ associated \ to\ \mathfrak a} \mathfrak p-\mathfrak p$，这当然是可以取到的。可以验证它满足4.E15中$f$的条件，那么$S_{\mathfrak p}(\mathfrak a)=q_{\Sigma}=(\mathfrak a:f^n)$。

L2：给定$\mathfrak a$的准素分解$\mathfrak q_1\cap \cdots\cap \mathfrak q_n$，由4.9$S_k(\mathfrak a)=\cap_{S\cap \mathfrak p_i=\varnothing} \mathfrak q _i$，于是收缩$S_k$，最终得到的$S_k(\mathfrak a)$也会稳定。

$\Longleftarrow$

保持4.E17的记号：

如果$S_n=S_{\mathfrak p_1}\cap \cdots\cap S_{\mathfrak p_n}$，归纳地说明$S_n$与$\mathfrak a_n$有交：

$n=1$时情况显然，因为$a_1\not\subseteq \mathfrak p_1$，则$S_1=S_{\mathfrak p_1}$与$\mathfrak a_1$有交。

假定$n-1$情况已证，$\mathfrak a_n\cap \mathfrak q_n=\mathfrak a_{n-1}$与$S_{n-1}$有交；由于$\mathfrak a_n\not\subseteq \mathfrak p_n$，那么$S_{\mathfrak p_n}$与$\mathfrak a_n$有交。

于是$\mathfrak a_n$同时与$S_{n-1}$和$S_{\mathfrak p_n}$有交，同时$\mathfrak a_{n-1}\cap S_{n-1}\subseteq \mathfrak q_n\subseteq\mathfrak p_n\subseteq S_{\mathfrak p_n}$，且当然$\mathfrak a_{n-1}\cap S_{n-1}\subseteq \mathfrak a_n$

那么$S_n\cap \mathfrak a_n=(S_{n-1}\cap \mathfrak a_{n})\cap (S_{\mathfrak p_n}\cap \mathfrak a_n)\supseteq (S_{n-1}\cap \mathfrak a_{n-1})\cap (S_{\mathfrak p_n}\cap \mathfrak a_n)=S_{n-1}\cap \mathfrak a_{n-1}\neq\varnothing$



于是$S_n(\mathfrak a_n)=(1)$，进一步地$S_n(\mathfrak a)=S_n(\mathfrak q_1)\cap \cdots\cap S_n(\mathfrak q_n)\cap S_n(\mathfrak a_n )=\mathfrak q_1\cap\cdots\cap \mathfrak q_n$（最后一个等号是因为4.9）

由$L2$，$S_n(\mathfrak a)$一定稳定。于是$\mathfrak q_1\cap\cdots\cap \mathfrak q_n$一定稳定，那么实际上超过$n$的构造过程均得到了$\mathfrak a=\mathfrak q_1\cap \cdots\cap \mathfrak q_n\cap \mathfrak a_N$，并且$\mathfrak a_N$严格升于是只有$\mathfrak a_n=(1)$，从而完成了证明。



**19. 回想4.E11的证明过程：每个$\mathfrak p-$准素理想都包含$S_\mathfrak p(0)$。**

**如果环$A$满足对于每个素理想$\mathfrak p$，全体准素理想的交为$S_\mathfrak p(0)$。那么对于一族互异的素理想$\mathfrak p_1,\cdots,\mathfrak p_n$，且它们均不是极小素理想，那么存在一个理想$\mathfrak a$使得其从属的素理想正是$\mathfrak a$。**

证：

对$n$归纳，$n=1$的情况显然。

假定$n-1$的情况成立。对于$n$，设理想族$\{\mathfrak p_1,\cdots,\mathfrak p_n\}$中$\mathfrak p_n$是极大的。对$\{\mathfrak p_1,\cdots,\mathfrak p_{n-1}\}$使用归纳假设，存在一个理想$\mathfrak b$具有极小准素分解$\mathfrak b=\mathfrak q_1\cap \cdots\cap \mathfrak q_{n-1}$，满足$r(\mathfrak q_i)=\mathfrak p_i$。



如果$\mathfrak b\subseteq S_{\mathfrak p_n}(0)$，设$\mathfrak p$是包含在$\mathfrak p_n$内的极小素理想，于是$\mathfrak b\subseteq S_{\mathfrak p_n}(0)\subseteq S _{\mathfrak p}(0)$。

两侧取根，则$\mathfrak p_1\cap\cdots\cap \mathfrak p_n=r(\mathfrak q_1\cap\cdots\cap \mathfrak q_n)=r)\mathfrak b\subseteq r(S_{\mathfrak p}(0))\xlongequal[]{4.E10.2}\mathfrak p$

由包容引理$\mathfrak p_i\subseteq \mathfrak p$对某个$i$成立，由极小性只能有$\mathfrak p=\mathfrak p_i$。这和不存在$\mathfrak p_i$极小矛盾。



因此$\mathfrak b\not\subseteq S_{\mathfrak p_n}(0)$，于是存在一个$\mathfrak p_n-$准素理想$\mathfrak q_n$满足$\mathfrak b\not\subseteq \mathfrak q_n$。那么考虑$\mathfrak a=\mathfrak q_1\cap\cdots\cap\mathfrak q_n$。只需验证这个准素分解是否极小：$r(\mathfrak q_i)$当然互异，并且$\mathfrak q_n\not\supseteq \mathfrak q_1\cap\cdots\cap \mathfrak q_n$，并且$\mathfrak q_i\not\supseteq \mathfrak q_1\cap\cdots\cap\mathfrak q_{i-1}\cap\mathfrak q_{i+1}\cap\cdots\cap\mathfrak q_{n-1}\not\supseteq \mathfrak q_{i-1}\cap\mathfrak q_{i+1}\cap\cdots\cap\mathfrak q_{n}$($i<n$)

于是这样的$\mathfrak a$满足要求。



#### 模的准素分解

**20. 对于给定的$A-$模$M$，子模$N$。$N$在$M$中的根定义为$r_{M}(N)=\{x\in A|x^qM\subseteq N\ for\ some\ q>0\}$**

**证明：$r_M(N)=r(N:M)=r(Ann(M/N))$，从而说明这是一个理想，并说明它满足1.13中类似性质。**

证：

前三个等式成立由定义直接验证即可，性质验证同1.13. 详见下图：

![image-20230515101237832](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515101237832.png)



**21. 每个$x\in A$都诱导出了一个环的自同态$\phi_x:m\mapsto xm$。称$x$是零因子如果$\phi_x$不是单射；称$x$是幂零元如果$\phi_x$这个同态是幂零的。称$M$的子模$Q$是准素的如果$M/Q$中每个零因子都是幂零的。**

**证明如果$Q$是准素的子模，那么$(Q:M)$是准素的，于是$r_M(Q)$是一个素理想$\mathfrak p$。称$Q$在$M$中是$\mathfrak p-$准素的。**

**进一步地，验证它具有4.3,4.4中类似结论。**

$xyM\subseteq Q$，则在$M/Q$中$\phi_{xy}$是零映射。如果$yM\not\subseteq Q$，那么$\phi_y$不是零映射。于是只能有$\phi_x$有非零的核，从而是零因子，于是幂零，即$x^nM\subseteq Q\ i.e.\ x^n\in (Q:M)$。因此$(Q:M)$是准素理想，接下来的推论是自然的。



4.3,4.4 验证：

![image-20230515101350624](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515101350624.png)



**22.（准素分解）如果子模$N$能够表示成若干准素子模的交$N=Q_1\cap\cdots\cap Q_n$，称之为准素分解。如果它满足$r_M(Q_i)$互异且$Q_i\not\supseteq \cap _{j\neq i}Q_j$ 则称之为极小准素分解；证明第一唯一性定理（4.5）并且说明从属素理想是$M/N$中从属于0的素理想。**

![image-20230515103303124](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515103303124.png)



**23. 4.6~4.11的结论在模的情况下仍然成立。**

![image-20230515103415084](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515103415084.png)

![image-20230515103453562](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515103453562.png)

![image-20230515103506609](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/image-20230515103506609.png)



## 5. 整性相关和赋值

### 5.0 引言

在代数几何中经常将曲线视作若干直线的覆盖，这和环中元素关于某个子环的整性非常相似，相关的应用将在习题中详细介绍。



### 5.1 整性相关

给定环$B$，子环$A,1\in A$。称$x\in B$是$A$中整的如果它是某个首一$A$上多项式的根。

**5.1（整元的刻画）TFAE：**

**1. $x\in B$在$A$中整**

**2. $A[x]$是有限生成$A-$模**

**3. $A[x]$被某个$B$的子环$C$包含，并且$C$是有限生成$A-$模。**

**4. 存在一个忠实$A[x]-$模$M$，使得$M$作为$A-$模是有限生成的。**

Remark. $A[x]=\{f(x)|f\in A[T],T\ indeterminate\}$

证：

$1\implies 2.$ 显然，设$f(x)=0,\deg f=n$，那么$A[x]$做为$A-$模被$1,x,\cdots,x^{n-1}$生成。

$2\implies 3.$ 显然，取$C=A[x]$

$3\implies 4.$ 取$M=C$ 

$4\implies 1. $ 在2.4中取$\phi$为$m\mapsto xm$，由于$M$是$A[x]$模，自然有$xM\subseteq M$。于是有$(x^n+a_1x^{n-1}+\cdots+a_n  )m=0\forall m$，而忠实保证了$x^n+\cdots+a_n=0$ 



**5.2 若$x_i\in B(1\leq i\leq n)$，且均在$A$中整，那么$A[x_1,\cdots,x_n]$是有限生成$A-$模。**

证：只需回忆2.16，有限生成的结合还是有限生成。



**5.3 $B$中全体$A$中整的元素是一个包含$A$的子环。**

证：$x+y,x-y,xy\in A[x,y]$由5.2是有限生成$A-$模，由5.1条件3知它们都在$A$上整。



**Remark.（代数的整性）对于环同态$f:A\to B$，$B$是$A$代数。称$f$整，$B$是整的$A-$代数，如果$B$中元素在子环$f(A)$中整。**

**Remark. （整性闭包，整闭环）设$B$中全体$A$中整的元素构成的环是$C$，即$A\subseteq C\subseteq B$。称$C$为$A$在$B$中的整性闭包；若$C=A$，称$A$在$B$中整闭；若$C=B$，称环$B$在$A$上整。**



**5.4 （整性相关的传递性）$A\subseteq B\subseteq C$，如果$B$的元素在$A$中整，$C$的元素在$B$中整，那么$C$的元素在$A$中整。**

证：设$c\in C$满足$c^n+b_1c^{n-1}+\cdots+b_n=0$，且$B'=A[b_1,\cdots,b_n]$是有限生成$A-$模；又由于$c$在$B'$中整，于是$B'[c]$有限生成。由2.16，$B'[c]$是有限生成的$A-$模，于是$c$在$A$中整。



**5.5  $A\subseteq B$，$C$是$A$在$B$中的整性闭包，则$C$在$B$中整闭。**

证：$x$在$C$中整，于是由5.4，$x$在$A$中整，于是$x\in C$。



**5.6 （整性在商和分式化下保持）**

**$A\subseteq B$，环$B$在环$A$上整**

**1. $\mathfrak b$是$B$的理想；$\mathfrak a=\mathfrak b^c=A\cap\mathfrak b$，那么$B/\mathfrak b$在$A/\mathfrak a$上整。**

**2. $S$是$A$的乘性子集，那么$S^{-1}B$在$S^{-1}A$上整。**

证：

直接验证即可。



### 5.2 Cohen-Seidenberg 定理

接下来将要研究素理想的升降链在整扩张中的表现，主要结果被称为Cohen-Seidenberg的上升定理和下降定理。

#### 5.2.1 上升定理

**5.7 $A\subseteq B$是整环，$B$在$A$上整。那么$B$是域$\iff A$是域。**

证：

$\implies. $ 对$y\in B,y\neq 0,y^{n}+a_1y^{n-1}+\cdots+a_n=0$ 是极小首一多项式。

由于整环，$y\neq 0$则极小多项式中$a_n\neq 0$

于是$y(y^{n-1}+a_{1}y^{n-2}+\cdots+a_{n-1})=-a_n$，即$y(-a_{n}^{-1}y^{n-1}-a_{n}^{-1}a_1y^{n-2}-\cdots-a_n^{-1}a_{n-1})=1$

$\Longleftarrow. $ 对$x\in A$, 设$x^{-1}\in B$使得$xx^{-1}=1$。于是$x^{-1}$在$A$上整：$x^{-n}+a_1x^{-n+1}+\cdots+a_n=0$，两侧乘上$x^{n-1}$有$x^{-1}=-(a_1+\cdots+a_nx^{n-1})$,浴室$x^{-1}\in A$。



**5.8 $A\subseteq B$，环$B$在环$A$上整；$\mathfrak q$是$B$的素理想，$\mathfrak p=\mathfrak q^c=\mathfrak p\cap A$是拉回。则$\mathfrak q$极大$\iff\mathfrak p$极大。**

证：5.6和5.7的直接推论。



**5.9 $A\subseteq B$，环$B$在环$A$上整；$\mathfrak q,q'$是$B$的素理想，$\mathfrak q\subseteq \mathfrak q'$且$\mathfrak q^{c}=\mathfrak q'^{c}=\mathfrak p$，则$\mathfrak q=\mathfrak q'$**

证：记$S=A-\mathfrak p$，由5.6$S^{-1}B$在$S^{-1}A$上整，设$\mathfrak m$是$\mathfrak p$在$S^{-1}A$中的扩张；$\mathfrak{n,n'}$是$\mathfrak {q,q'}$在$S^{-1}B$中的扩张。

注意到$\mathfrak m$在$S^{-1}A$中是极大的；并且考虑嵌入$S^{-1}A\hookrightarrow S^{-1}B$：$\mathfrak {n,n'};$在这个嵌入下的局限均为$\mathfrak m$。由5.6，$\mathfrak {n,n'}$都是极大的，但另一方面$\mathfrak n\subseteq \mathfrak n'$于是只能有$\mathfrak n=\mathfrak n'$. 拉回至$B$中即有$\mathfrak q=\mathfrak q'$.

$\xymatrix{A\ar[r]\ar[d]&B\ar[d]\\A_{\mathfrak p}\ar[r]&(A-\mathfrak p)^{-1}B}$

**5.10 $A\subseteq B$，环$B$在环$A$上整；$\mathfrak p$是$A$的素理想。存在$B$的素理想$\mathfrak q$使得$\mathfrak q\cap A=\mathfrak p$**

同样在交换图$\xymatrix{A\ar[r]\ar[d]&B\ar[d]\\A_{\mathfrak p}\ar[r]&(A-\mathfrak p)^{-1}B}$中考虑$(A-\mathfrak p)^{-1}B$的极大理想。

由5.8，它拉回至$A_\mathfrak p$是极大的。于是拉回至$A$为$\mathfrak p$。因此取$\mathfrak q$为$(A-\mathfrak p)^{-1}B$中的极大理想拉回至$B$内的理想即可。



**5.11（上升定理）$A\subseteq B$，环$B$在环$A$上整。环$A$中$\mathfrak p_1\subseteq \cdots\mathfrak p_n$是素理想上升链，环$B$中也有一个素理想上升链$\mathfrak q_1\subseteq\cdots\mathfrak q_m(m<n)$，并且$\mathfrak q_i\cap A=\mathfrak p_i$。**

**那么$B$中的素理想链可以扩充为$\mathfrak q_1\subseteq\cdots\subseteq \mathfrak q_n$，使得$\mathfrak q_i\cap A=\mathfrak p_i$。**

证：由归纳只需证明$m=1,n=2$的情况。

取$A'=A/\mathfrak p_1;B'=B/\mathfrak q_1$，那么依然有$A'\subseteq B'$。由5.6$B'$在$A'$上整，由5.10存在$\mathfrak q_2'$是$B'$的素理想，并且$\mathfrak q_2'\cap A'=\mathfrak p_2'$，那么$\mathfrak q_2\cap A=\mathfrak p_2$。从而完成证明。



#### 5.2.2 整闭环, 下降定理

首先指出不仅仅是整性(5.6)，整性闭包也在分式化下保持。

**5.12 $A\subseteq B$，$C$是$A$在$B$中的整性闭包。$S$是$A$的乘性子集，则$S^{-1}C$是$S^{-1}A$在$S^{-1}B$中的整性闭包。**

证：首先$S^{-1}C$在$S^{-1}A$上整是显然的。如果$b/s\in S^{-1}B$在$S^{-1}A$上整，即：

$(b/s)^n+(a_1/s_1)(b/s)^{n-1}+\cdots+(a_n/s_n)=0$

两侧同时乘以$(ss_1\cdots s_n)^n$，于是$bs_1\cdots s_n$在环$A$上整，从而属于$C$，于是$b/s=(bs_1\cdots s_n)/(ss_1\cdots s _n)\in S^{-1}C$



**Def. （整闭环）称一个整环是整闭的，如果它在其分式域中是整闭的。**

**Prop. UFD都是是整闭环，于是特别地$\mathbb{Z}$和$k[x_1,\cdots,x_n]$是整的。**

证：若$r/s$整，$r,s$没有共同因子。则$r^n+a_1r^{n-1}s+\cdots+a_ns^n=0$，于是$s|r^n$，故$s$是单位，于是$r/s$在环中。



**5.13（整闭性是局部性质）给定整环$A$，以下三者等价：**

**1. $A$整闭；2. $A_\mathfrak p$对每个素理想$\mathfrak p$整闭；3. $A_\mathfrak m$对每个极大理想$\mathfrak m$整闭。**

证：

设$K$是$A$的分式域，$C$是$A$在$K$中的整性闭包，则$A$整闭当且仅当嵌入映射$f:A\to C$是满的。

同样由5.12，$A_{\mathfrak p(\mathfrak m)}$是整闭的$\iff f_{\mathfrak p(\mathfrak m)}$是满射。由于局部化操作是正合的二者等价性立刻得证。



**Def. （理想上的整元）$A\subseteq B$称为$A$中的理想$\mathfrak a$上的整元素，如果它是某个首一$\mathfrak a$系数的多项式的根。同样也可以定义理想上的整性闭包。**

**5.14（理想上整性闭包的刻画）$C$是$A$在$B$中的整性闭包，$\mathfrak a^e$记为$\mathfrak a$在$C$中的扩张。那么$\mathfrak a$在$B$中的整性闭包是$\mathfrak a^e$的根理想。**

证：

设$x$在$\mathfrak a$上整，即$x^n+a_1x^{n-1}+\cdots+a_n=0$，$a_i\in\mathfrak a$。于是$x$也在$A$上整，即$x\in C$，故$x^n\in\mathfrak a^e$，进而$x\in r(\mathfrak a^e)$

反过来，如果$x\in r(\mathfrak a^e)$，$x^n=\sum a_ix_i$， 其中$a_i\in\mathfrak a,x_i\in C$。于是$M=A[x_1,\cdots,x_n]$有限生成，进而在2.4中取$\phi$为乘以$x^n$有$x^nM\subseteq \mathfrak aM$，于是$x^n$在$\mathfrak a$上整。



**5.15 $A\subseteq B$是整环，$A$整闭且$x\in B$在$A$的某个理想$\mathfrak a$上整。那么$x$是$A$的分式域$K$上的代数元，并设极小多项式为$t^{n}+a_1t^{n-1}+\cdots+a_n$，则系数$a_1,\cdots,a_n\in r(\mathfrak a)$**

证：

$x$是$K$上代数元是显然的。

