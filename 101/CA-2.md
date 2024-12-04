# Introduction to Commutative Algebra - Part2.

Note. 4.E13，5.E22（答案有误），5.E24

作为模有限生成：有限。

作为代数有限生成：有限型。

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

**Remark. 有限型+整=有限：设$f:A\to B$，则$B$是有限生成$A-$代数且$B$在$A$上整$\iff B$是有限生成$A-$模。**

证：$\implies$. 若$B$是有限生成$A-$代数，则$B=f(A)[x_1,\cdots,x_n]$。由于$x_i$在$f(A)$上整，由5.2立刻有$f(A)[x_1,\cdots,x_n]$是有限生成$f(A)-$模，于是是有限生成$A-$模。

$\Longleftarrow$ . 若$B$是有限生成$A-$模，那它自然是有限生成代数。那么$B=f(A)<x_1,\cdots,x_n>_{mod}\subseteq f(A)[x_1,\cdots,x_n]\subseteq B$，于是任何$b\in B$都有$f(A)[b]\subseteq B$为有限生成$A-$模，于是证明了整性。



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

$\Longleftarrow. $ 对$x\in A$, 设$x^{-1}\in B$使得$xx^{-1}=1$。于是$x^{-1}$在$A$上整：$x^{-n}+a_1x^{-n+1}+\cdots+a_n=0$，两侧乘上$x^{n-1}$有$x^{-1}=-(a_1+\cdots+a_nx^{n-1})$, 于是$x^{-1}\in A$。



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

考虑极小多项式的分裂域$L$。那么极小多项式在$L$中的根$x_1,\cdots,x_n$均在理想$\mathfrak a$上整，于是均在$A$˙中，于是由5.14均在$r(\mathfrak a)$中，于是系数由Vieta定理都在$r(\mathfrak a)$中、



**5.16（下降定理）$A\subseteq B$是整环，$A$整闭，$B$在$A$上整。环$A$中$\mathfrak p_1\supseteq \cdots\mathfrak p_n$是素理想下降链，环$B$中也有一个素理想下降链$\mathfrak q_1\supseteq\cdots\mathfrak q_m(m<n)$，并且$\mathfrak q_i\cap A=\mathfrak p_i$。**

 **那么$B$中的素理想链可以扩充为$\mathfrak q_1\supseteq\cdots\supseteq \mathfrak q_n$，使得$\mathfrak q_i\cap A=\mathfrak p_i$。**

证：

同样我们可以只考虑$m=1,n=2$的情况。

只需说明$\mathfrak p_2$是某个$B_{\mathfrak q_1}$到$A$的拉回：其中映射定义为$A\hookrightarrow B\hookrightarrow B_{\mathfrak q_1}$，即需要满足$\mathfrak p_2B_{\mathfrak q_1}\cap A=\mathfrak p_2$。

每个$\mathfrak p_2 B_{\mathfrak q_1}$的元素$x$具有形式$y/s$，$y\in\mathfrak p_2B,s\in B-\mathfrak q_1$。由5.14，$y$是$\mathfrak p_2$上的整元，于是其在$A$的分式域$K$上有极小多项式$y^r+u_1y^{r-1}+\cdots+u_r=0$，其中$u_i\in\mathfrak p_2$。

现在设$x\in \mathfrak p_2B_{\mathfrak q_1}\cap A$，$s=yx^{-1}$，其中$x^{-1}\in K$，于是$s$在$K$中的极小多项式是前述多项式除以$x^r$，设为$s^{r}+v_1s^{r-1}+\cdots+v_r=0$，$v_i=u_i/x^i$。

即$x^iv_i=u_i\in\mathfrak p_2$。

另一方面$s$在$A$上整，于是由5.15（取$\mathfrak a=A$）知$v_i\in A$。如果$x\not\in\mathfrak p_2$，那么由$x^iv_i\in\mathfrak p_2$知$v_i\in\mathfrak p_2$，于是$s^r\in \mathfrak p_2B\subseteq \mathfrak p_1B\subseteq \mathfrak q_1$。从而$s\in\mathfrak q_1$，矛盾。

于是$x\in\mathfrak p_2$，即$\mathfrak p_2B_{\mathfrak q_1}\cap A=\mathfrak p_2$.



**5.17 设$A$是整闭环，$K$是分式域，$L$是$K$的有限可分扩张，$B$是$A$在$L$中的整性闭包。那么存在$L$的一组($K-$)基$v_1,\cdots,v_n$使得$B\subseteq \sum Av_i$。**

证：对于$L$中元素$v$，$v$是$K$上代数元且满足$a_0v^r+a_1v^{r-1}+\cdots+a_n=0,a_i\in A$

两侧乘以$a_0^{r-1}$，于是$a_0v=u$自然在$A$上整，于是$u\in B$。因此对于任何一组基乘上对应的$A$中元素得到$u_1,\cdots,u_n\in B$，同时也是一组基。



由于$L/K$是可分扩张，于是$(x,y)\mapsto T(xy)$是非退化的双线性型，于是有一组对偶基$v_1,\cdots,v_n$, 满足$T(u_iv_j)=\delta_{ij}$

对于$x\in B$，$x=\sum x_jv_j$。而$u_i\in B$说明$xu_i\in B$，于是由5.15$T(xu_i)\in A$。

然而$T(xu_i)=\sum_j T(x_ju_iv_j)=\sum x_j\delta_{ij}=x_i$，即$x_i\in A$。故$B\subseteq \sum Av_i$。



### 5.3 赋值环

**Def.（赋值环）$B$是整环，$K$是它的分式域。称$B$是$K$的赋值环如果对于每个非零的$x\in K$，$x,x^{-1}$至少有一个在$B$中。	**

**5.18 对于赋值环$B$，以下性质成立：**

**1. $B$是局部环。**

**2. 如果$B\subseteq B'\subseteq K$，则$B'$也是$K$的赋值环。**

**3. $B$是整闭的。**

证：

5.18.1

取$\mathfrak m$为全体$B$中的非零元构成的集合，于是$x\in\mathfrak m\iff x=0\ or\ x^{-1}\notin B$。

对于$ax,x\neq 0$，若$(ax)^{-1}\in B$，那么$x^{-1}=a(ax)^{-1}\in B$，矛盾。

对于$x,y\in\mathfrak m$，无妨$x,y\neq 0$。

那么$xy^{-1}\in B; x^{-1}y\in B$至少有一个成立。若前者成立，$x+y=(1+xy^{-1})y\in B\mathfrak m\subseteq \mathfrak m$，另外一种情况同理说明成立。

5.18.2

显然。

5.18.3

若$x\in K$在环$B$上整，$x^n+b_1x^{n-1}+\cdots+b_n=0$。如果$x\in B$则已证，否则$x^{-1}\in B$，$x=-b_1-b_2x^{-1}-\cdots-b_nx^{1-n}$。



#### 指定域中赋值环的构造

设$K$是域，$\Omega$是代数闭域。设$\Sigma$是$(A,f)$构成的组，其中$A$是$K$的子环，$f$是$A$到$\Omega$的同态。定义偏序$(A,f)\leq (A',f')\iff A\subseteq A'\ and\ f'|_A=f$，于是应用Zorn引理立刻有$\Sigma$有极大元。

设$(B,g)$是极大元，接下来的目标是证明$B$是$K$的赋值环。

**Step 1.**

**5.19 $B$是局部环且$\mathfrak m=\ker g$是其极大理想。**

证：由于$g(B)$是域$\Omega$的子环，自然是整环。从而$\mathfrak m=\ker g$是素理想。将同态$g:B\to \Omega$扩展为同态$\widetilde{g}:B_\mathfrak m\to \Omega:\widetilde{g}(b/s)=g(b)/g(s)$：注意$g(s)$永远不是0.

由极大性有$B=B_\mathfrak m$，于是得证。

**Step2.**

**5.20 设$x$是$K$的非零元，$B[x]$是$K$的子环，由$x$在$B$上生成。记$\mathfrak m[x]$为$\mathfrak m$在同态$B\to B[x]$下的扩张，那么$\mathfrak m[x]\neq B[x]$和$\mathfrak m[x^{-1}]\neq B[x^{-1}]$至少有一成立。**

证：若否，$\mathfrak m[x]=B[x],\mathfrak m[x^{-1}]=B[x^{-1}]$

由条件，$x$满足：

$u_0+u_1x+\cdots+u_mx^m=1\quad(u_i\in\mathfrak m)\\v_0+v_1x^{-1}+\cdots+v_nx^{-n}=1\quad(v_i\in\mathfrak m)$

假定在上述两式中$m,n$次数尽量小，并且$m\geq n$。那么$v_1x^{n-1}+\cdots+v_n=(1-v_0)x^n$

由于$v_0\in\mathfrak m$，由5.19，$1-v_0$是单位。于是$x^n=w_1x^{n-1}+\cdots+w_n\quad w_i\in\mathfrak m$

于是$x^m=w_1 x^{m-1}+\cdots+w_nx^{m-n}$，那么将$x^m$代入$u_0+u_1x+\cdots+u_mx^m=1\quad(u_i\in\mathfrak m)$，得到次数更低者，矛盾。

**Step 3.**

**5.21 对这个极大元素$(B,g)$，$B$是域$K$的赋值环。**

证：

对于任意$x\in K,x\neq 0$，由5.20可以假设$\mathfrak m[x]\neq B[x]$，于是它必然被$B[x]$的某个极大理想$\mathfrak m'$包含。拉回至$B$有$\mathfrak m'\cap B=\mathfrak m$，于是嵌入$B\hookrightarrow B[x]$诱导了域嵌入$B/\mathfrak m\hookrightarrow B[x]/\mathfrak m'$。记这两个域分别为$k,k'$，于是$k'=k[\bar{x}]$，其中$\bar{x}$指$x$在$k'$中的像。于是扩域$[k',k]$是有限代数扩张。

同态$g$诱导出了嵌入$\bar{g}:k\to \Omega$，由于$\Omega$是代数闭域，$\bar{g}$可以扩展为$\bar{g}':k'\to \Omega$。再复合上自然同态$B’\to k'$，我们得到了$(B,B'\to k'\to \Omega)$。于是由极大性有$B=B'$，$x\in B$。

**Corollary. 5.22**

**设$A$是域$K$的子环，$A$在$K$中的整性闭包$\bar{A}$是全体包含$A$赋值环的交。**

证：

由于赋值环是整闭的，于是整性闭包当然被赋值环的交包含。

反过来如果$x\notin \bar{A}$，那么$x\notin A'=A[x^{-1}]$，即在$A'$中$x^{-1}$不是单位，于是被极大理想$\mathfrak m'$包含。设$\Omega$是$k'=A'/\mathfrak m'$的代数闭包，那么将同态$A'\to k'$限制在$A$上得到了同态$A\to \Omega$。由5.21，存在某个包含$A$的赋值环$(B,g)$，其中后者是映射$A\to \Omega$的延拓。由于$x^{-1}$在这个映射下变为0，那么$x\notin B$。从而不属于赋值环的交。



#### Zariski引理

**5.23 设$A\subseteq B$是整环，$B$在$A$上有限生成。设$v$是$B$中的非零元素，那么存在$u\neq 0,u\in A$，满足以下性质：**

**每个$A$到一个代数闭域$\Omega$上满足$f(u)\neq 0$的同态$f$都可以被延拓为$B$到$\Omega$的同态$g$，且$g(v)\neq 0$**

证：

由归纳，只需考虑$B$由一个元素$x$在$A$上生成的情况。

A. $x$在$A$的分式域上是超越元，设$v=a_0x^n+a_1x^{n-1}+\cdots+a_n$，取$u=a_0\neq 0$

对于$f:A\to \Omega,f(u)\neq 0$，存在$\xi\in \Omega$，使得$f(a_0)\xi^n+\cdots+f(a_n)\neq 0$（否则注意到使得方程为0的根只有有限个，而代数闭域不是有限域），那么定义$g:B\to \Omega$：$g(a)=f(a),a\in A\quad g(x)=\xi$，满足要求。

B. $x$在$A$的分式域上是代数元。同时$v^{-1}$也是$A$的分式域上的代数元（因为$v$可表示为$x$在$A$上的多项式值），故有如下方程式：

$a_0x^m+\cdots+a_m=0\quad a_0'v^{-n}+\cdots+a'_n=0$，取$u=a_0a_0'$，对于任何$f:A\to \Omega, f(u)\neq 0$：

首先延拓至$f_1:A[u^{-1}]\to \Omega,f_1(u^{-1})=f(u)^{-1}$，于是由5.21存在一个包含$A[u^{-1}]$的赋值环$C$，以及一个延拓的同态$h:C\to \Omega$。

由于$x$在$A[u^{-1}]$上整，于是$x\in C$（5.22），于是$B\subseteq C$。特殊地$v\in B\subseteq C$

另一方面$v^{-1}$在$A[u^{-1}]$上整（观察上文中第二个方程式），于是又一次的有$v^{-1}\in C$，即$v$在$C$中是单位，于是$h(v)\neq 0$。现在将$h$从$C限制到$$B$即可。



**5.24（Zariski Lemma） 设$k$是域，$B$是有限生成$k$代数。如果$B$是域那么它是$k$的有限代数扩张。**

证：在5.23中取$A=k$，$v=1$，$\Omega=\bar{k}$，可以验证此时同态$f,g$都是嵌入。于是$k\subseteq B\subseteq \bar{k}$，又由有限生成自然说明结论。

注意：5.24(Zariski Lemma)能够推出Weak Hilbert Nullstellenstaz.

**5.25（Hilbert Nullstellenstaz Weak Form）$\mathfrak m$是$k[x_1,\cdots,x_n]$的极大理想，$k$代数闭，则$k[x_1,\cdots,x_n]/\mathfrak m \cong k$**

证：记$B=k[x_1,\cdots,x_n]$，其中$k$代数闭，$\mathfrak m$为$B$的极大理想。

域$B/\mathfrak m$是$k$的扩张：注意复合映射$k\to B\to B/\mathfrak m$不是零映射，于是只能是嵌入。那么自然是有限生成$k$代数。

于是$B/\mathfrak m$是$k$的有限代数扩张，但$k=\bar{k}$，只有$B/\mathfrak m=k$。

**5.25 Cor. 更进一步地极大理想一定形如$<x_1-k_1,\cdots,x_n-k_n>$。**

证：首先注意到上述形式是极大理想，因为它是映射$k[x_1,\cdots,x_n]\to k:f\mapsto f(k_1,\cdots,k_n)$的核：对$n$归纳。然后对$x_1-k_1$做带余除法即可。

反过来对于任何一个极大理想$\mathfrak m$，有$k[x_1,\cdots,x_n]/\mathfrak m\cong k$，设$x_1,\cdots,x_n$的像分别为$k_1,\cdots,k_n$，于是$\mathfrak m=\ker\supseteq <x_1-k_1,\cdots,x_n-k_n>$，而后者已然是极大理想，于是只有$\mathfrak m=<x_1-k_1,\cdots,x_n-k_n>$

### 5.4(E)

**1. 设$f:A\to B$是整的环同态，i.e. $B$在$f(A)$上整。证明$f^*:Spec(B)\to Spec(A)$是闭映射。**

证：

$f$可以分解为$A\to f(A)\to B$，其中前一个箭头诱导的的是到$V(\ker)$同胚，必然是闭映射。

于是只需研究第二个箭头，因此不妨$A\subseteq B$，且$B$在$A$上整。此时每个$A$中的素理想$\mathfrak p$都具有形式$A\cap \mathfrak q$，同时每个$B$中素理想$\mathfrak q$都诱导出$A$中素理想$A\cap \mathfrak q$，于是自然有$V(\mathfrak q)$在$f^*$下的像为$V(\mathfrak q^c)$

即$V(\mathfrak q)$的像也形如$V(\mathfrak r)$，自然说明了闭映射。



**2. $A$是$B$的子环，$B$在$A$上整，$f:A\to \Omega$是$A$到某个代数闭域$\Omega$的环同态，证明$f$可以被延拓为$B\to\Omega$的环同态。**

证：

$f$可以分解为$A\to A/\mathfrak p\to\Omega$，其中$\mathfrak p=\ker f=(0)^c$自然是素理想。

那么存在$B$中素理想$\mathfrak q$使得$\mathfrak q\cap A=\mathfrak p$，由5.6.1，$B/\mathfrak q$在$A/\mathfrak p$上整。

因此只需说明$A\subseteq B$且$A,B$均为整环时，单环同态$f:A\to \Omega$可以被延拓为环同态$B\to\Omega$。

如同在5.3中做的那样，考虑这样的元素对$(C,\sigma)$，其中$A\subseteq C\subseteq B$，$\sigma: C\to \Omega$并且$\sigma|_A=f$。利用Zorn引理知极大元素存在，设为$(C,\sigma)$。

若$C\neq B$，设$b\in B-C$. $b$在$A$上整，自然在$C$上整。设$p(x)\in C[x]$满足$p(b)=0$

注意$\sigma p(x)=\sum \sigma(c_i)x^i$在$\Omega$中必定有一根，取为$z$。那么$C[b]\to \Omega: b\mapsto z$满足条件。于是与极大性矛盾，进而只有$B=C$。



**3. $f:B\to B'$是$A-$代数同态，$C$是$A-$代数。如果$f$是整同态，那么$f\otimes_A1:B\otimes_AC\to B'\otimes_AC$是整同态。**

证：

由于整元素构成环，只需验证生成元$b'\otimes_Ac$是整的。

设$b'$满足$b'^n+f(b_{n-1})b'^{n-1}+\cdots +f(b_0)=0$，于是$(b'\otimes c)^n+(f(b_{n-1})\otimes c)(b'\otimes c)^{n-1}+\cdots+(f(b_0)\otimes c^n)\cdot(b'\otimes c)^0=0$

从而得证。



**4. 设$A$是$B$的子环，并且$B$在$A$上整。设$\mathfrak n$是$B$的极大理想，$\mathfrak m=\mathfrak n\cap A$也是$A$的极大理想。（Recall 5.10），那么$B_{\mathfrak n}$一定在$A_{\mathfrak m}$上整吗？**

不一定。取$B=k[x]$的子环$A=k[x^2-1]$（其中$k$为域），$\mathfrak n=(x-1),\mathfrak m=(x^2-1)\cap A$。

如果$B_{\mathfrak n}$在$A_\mathfrak m$上整，考虑元素$1/(x+1)$。

那么有如下成立：$1/(x+1)^n+\sum_{m=0}^{n-1}+g_m(x^2-1)/[k_m(x^2-1)]\cdot [1/(x+1)^m]=0$

其中$k_m(0)\neq 0$，那么两侧同乘$(x+1)^{n-1}$后令$x=-1$即得到矛盾。



**5. 环$A\subseteq B$, $B$在$A$上整。**

**5.1 如果$x\in A$在$B$中是单位，那么$x$在$A$中是单位。**

**5.2 $J(A)=J(B)^c$**

证：

5.1 这和定理5.7中的$\Longleftarrow$方向证明完全相同。

5.2 即证$J(A)=J(B)\cap A$

考虑5.8，以及$J(R)=\cap_{\mathfrak m\ maximal}\mathfrak m$，命题显然。



**6. 设$B_1,\cdots,B_n$是整的$A-$代数，那么$\prod_{i=1}^n B_i$是整的$A-$代数。**

证：由归纳只需证明$n=2$的情况。

对于$(b_1,b_2)\in B_1\times B_2$。设$f,g\in A[x]$是两个首一多项式，且它们分别将$b_1,b_2$零化。那么考虑$(fg)(b_1,b_2)=(f(b_1)g(b_1),f(b_2)g(b_2))=0$，$fg$仍然是$A[x]$中的首一多项式，于是这就说明了$(b_1,b_2)$是在$A$上整的，进而$B_1\times B_2$是整的$A-$代数。



**7. 设$A$是$B$的子环，$B-A$在乘法下封闭。证明$A$在$B$中是整闭的。**

证：

若否，设$b\in B-A$且$b$在$A$上整。

即$b^n+a_1b^{n-1}+\cdots a_{n-1}b+a_n=0$，于是$-a_n=b(b^{n-1}+\cdots+a_{n-1})$。于是只有$b^{n-1}+\cdots+a_{n-1}\in A$。

同样地有$b(b^{n-2}+\cdots +a_{n-2})\in A$，反复进行此操作得到$b+a_1\in A$，矛盾。

故$A$整闭。



#### 整性闭包在多项式环上保持

**8.**

**8.1 设$A$是整环$B$的子环，$C$是$A$在$B$中的整性闭包。首一多项式$f,g\in B[x]$满足$fg\in C[x]$。则$f,g\in C[x]$**

**8.2 将整环的条件去掉后证明此命题。**

证：

8.1 考虑包含$B$（或准确地说$Frac(B)$）且$f,g$在其上分裂的域。设此时$f=\prod (x-f_i),g=\prod (x-g_i)$，于是$f_i,g_i$均为$fg$的根，于是在$C$上整。从而$f,g$的系数均在$C$上整，进而均属于$C$，即$f,g\in C[x]$

8.2 

此时仍然只需证明使多项式分裂的环的存在性：

对于$f(x)$，考虑扩环$B[x]/(f(x))$，那么在其中$T-x|f(T)$，考虑$f(T)/(T-x)$继续扩环即可。



**9. 设$A$是$B$的子环，$C$是$A$在$B$中的整性闭包。证明$C[x]$是$A[x]$在$B[x]$中的整性闭包。**

证：

若$f\in B[x]$在$A[x]$上整。即$f^m+g_1f^{m-1}+\cdots +g_m=0$对某些$g_i\in A[x]$成立。

对$r>m$，取$f_1=f-x^r$，即有$f_1^m+h_1f_1^{m-1}+\cdots +h_m=0$，其中$h_m=(x^r)^m+g_1(x^r)^{m-1}+\cdots\in A[x]$.

那么对$-f_1, f_1^{m-1}+h_1f_1^{m-2}+\cdots +h_{m-1}$应用8，当然有它们的乘积($h_m$)属于$A[x]$，进而属于$C[x]$，于是$f_1$属于$C[x]$。而$x^r$当然属于$C[x]$，于是$f\in C[x]$。

反过来由于$x$在$A[x]$上整，$C$在$A[x]$上整，于是$C[x]$在$A[x]$上整。



#### 环同态的上升性质和下降性质

**10. 称环同态$f:A\to B$具有上升（下降）性质如果对于扩环$f(A)\subseteq B$上升（下降）定理成立。**

**取拉回映射$f^*:Spec(B)\to Spec(A)$**

**10.1 对于以下三个条件**

**1a. $f^*$是闭映射；1b. $f$具有上升性质；1c. 对于任何$B$中素理想$\mathfrak q$，$\mathfrak p=\mathfrak q^c$，那么映射$Spec(B/\mathfrak q)\to Spec(A/\mathfrak p)$是满的。**

**证明：$a\implies b\iff c$，**

**10.2 对于以下三个条件**

**2a. $f^*$是开映射；2b. $f$具有下降性质；2c. 对于任何$B$中素理想$\mathfrak q$，$\mathfrak p=\mathfrak q^c$，那么$f^*:Spec(B_{\mathfrak q})\to Spec(A_{\mathfrak p})$是满的。**

证：

10.1  

$1b\iff 1c$是显然的。因为这相当于要求对每个包含$\mathfrak p_1$的素理想$\mathfrak p_2$，都能够找到一个包含$\mathfrak q_1$的素理想，并且满足其在拉回映射的像下为$\mathfrak p_2$，而这正是$Spec(B/\mathfrak q)\to Spec(A/\mathfrak p)$

$1a\implies 1c$. 考虑$V(\mathfrak q)$的像，由于$f^*$闭映射，其像集一定具有$V(\mathfrak a)$的形式。首先显然有$V(\mathfrak a)\subseteq V(\mathfrak p)$，但另一方面由于$\mathfrak p$是$\mathfrak q$的像，$\mathfrak p\subseteq V(\mathfrak a)$。于是只能有$V(\mathfrak p)\subseteq V(\mathfrak a)$，即$Im V(\mathfrak q)=V(\mathfrak a)=V(\mathfrak p)$，从而证明了1c成立。

10.2

$2b\iff 2c$成立原因同前。

$2a\implies 2c$.

注意：这里完全不和1中情况对偶。

首先由于Zariski的拓扑中开集具有下降性质，即$\mathfrak p\in U, \mathfrak p'\subseteq \mathfrak p\implies\mathfrak p'\in U$. （考虑补集即可）

由于$B_{\mathfrak q}$是全体$B_{t}$环的正向极限，$t\in B-\mathfrak q$。于是由3.E26$f^*(Spec(B_{\mathfrak q}))=\cap f^*(Spec(B_t))=\cap f^*(Y_t)$。其中$Y_t$是包含$\mathfrak q$的开集，于是$f^*(Y_t)$是包含$\mathfrak p$的开集。对于每个$\mathfrak p'\subseteq \mathfrak p$，都有$\mathfrak p'\subseteq f^*(Y_t)$，从而$f^*(Spec(B_{\mathfrak q}))=Spec(A_{\mathfrak p})$



**11. 设$f:A\to B$是平坦环同态，那么$f$有下降性质。**

（Recall. 平坦环同态即$B$作为$A-$模是平坦的）

证：由3.E18和5.E10显然。



**12. 设$G$是环$A$的自同构群的有限子群。记$A^G$为$A$中全体$G-$不变元素构成的子环（可以迅速地验证它的确是子环），那么$A$在$A^G$上整。**

**设$S$是$A$的乘性子集，且满足$\sigma(S)\subseteq S,\forall\sigma\in G$，并记$S^G=S\cap A^G$。证明$G$在$A$上的作用可以延拓到$S^{-1}A$上，并且$(S^G)^{-1}A^G\cong(S^{-1}A)^G$**

证：

12.1 $A$在$A^G$上整：对于任何$x\in A$，注意到$x$是多项式$f(t)=\prod_{\sigma\in G}(t-\sigma(x))$的解，并且由于系数为初等对称多项式，自然是$G$不变的。

12.2 对于$\sigma\in G$，取$\sigma(a/s)=\sigma(a)/\sigma(s)$即可。

良定义性：若$a/s=b/t, s'(at-bs)=0$，则$\sigma(s')[\sigma(a)\sigma(t)-\sigma(b)\sigma(s)]=0$，从而$\sigma(a)/\sigma(s)=\sigma(b)/\sigma(t)$

$\sigma$诱导了$S^{-1}A$的环同态也是显然的。

12.3 $(S^G)^{-1}A^G\cong (S^{-1}A)^G$

取映射$\rho:(S^G)^{-1}A^G\to (S^{-1}A)^G: a/s\mapsto a/s$

这个定义是良好的因为$\sigma(a/s)=\sigma(a)/\sigma(s)=a/s$，于是$a/s\in (S^{-1}A)^G$。

映射$\rho$是单同态：因为如果$\rho(a/s)=0$，那么在$S^{-1}A$中$a/s=0$，即$\exists s'\in S, as'=0$。注意此时$a\in A^G$，那么$\forall \sigma \in G,0=\sigma(as')=a\sigma(s')$

于是$a\cdot \sum_{\sigma\in G} \sigma(s')=0 $，并且$\sum_{\sigma\in G}\sigma(s')\in A^G$，另一方面$\sigma(S)\subseteq S$，于是$\sum_{\sigma\in G}\sigma(s')\in S$，从而$\sum_{\sigma\in G}\sigma(s')\in S^G$。故在$(S^G)^{-1}A^G$中$a/s=0$

映射$\rho$是满同态：对于任何$a/s\in (S^{-1}A)^G$. 由于$\sigma(a)/\sigma(s)=\sigma(a/s)=a/s$，我们断言在$S^{-1}A$中$(\sum_{\sigma\in G}\sigma(a))/(\sum_{\sigma\in G}\sigma(s))=a/s$

断言成立，因为假设对每个$\sigma\in G, s_{\sigma}(\sigma(a)s-\sigma(s)a)=0$，那么$\left[\sum_{\sigma\in G}\sigma(a)s-\sum_{\sigma\in G}\sigma(s)a\right]\cdot\prod_{\sigma\in G} s_{\sigma}=0$

于是$\rho(\sum_{\sigma\in G}\sigma(a)/\sum_{\sigma\in G}\sigma(s))=a/s$。

因此$\rho$是同构。



**13. 记号沿用5.E12，设$\mathfrak p$是$A^G$中的素理想，$P$是$A$中素理想构成的集合满足其元素的局限是$\mathfrak p$，证明$G$在集合$P$上的作用是传递的，于是作为推论得到$P$有限。**

证：

对于$\mathfrak p_1,\mathfrak p_2\in P$，设$x\in \mathfrak p_1$。于是$\prod_{\sigma\in G} \sigma(x)\in\mathfrak p_1\cap A^G=\mathfrak p\subseteq \mathfrak p_2$，从而存在一个$\sigma$使得$\sigma(x)\in \mathfrak p_2$。由于对每个$x$均为如此，于是$\mathfrak p_1\subseteq \cup_{\sigma\in G}\sigma(\mathfrak p_2$).

注意$\sigma$是自同构于是$\sigma(\mathfrak p_2)$是$A$的素理想。由包容引理(1.11)，知$\mathfrak p_1\subseteq \sigma(\mathfrak p_2)$对某个$\sigma\in G$成立。那么由5.9，注意$A$在$A^G$上整，即有$\mathfrak p_1=\sigma(\mathfrak p_2)$。从而证明了结论。



**14. 设$A$是整闭环，$K$是其分式域，$L$是其有限正规可分扩张。记$G=Gal(L/K)$，$B$是$A$在$L$中的整性闭包。证明$\sigma(B)=B,\forall\sigma\in G$并且$A=B^G$。**

证：

14.1 $\sigma(B)=B $

对于$b\in B$，设它满足$b^n+a_1b^{n-1}+\cdots+a_n=0$，于是$\sigma(b)^n+\sigma(a_1)\sigma(b)^{n-1}+\cdots+\sigma(a_n)=0$，即$\sigma(b)^n+a_1\sigma(b)^{n-1}+\cdots+a_n=0$，从而$\sigma(b)$也在$A$上整，故$\sigma(b)\in B$。

同样上述叙述对$\sigma^{-1}$依然成立，那么对于$\sigma(b)\in B$有$b=\sigma(\sigma^{-1}(b))\in B$，于是$\sigma(B)=B$。

14.2 $A=B^G$

$B^G=B\cap L^G=B\cap K=A$。倒数第二个等号是Galois扩张性质，最后一个等号是因为$A$在$K$中整闭，如果存在$k\in K-A$，并属于$B$，这就说明$k$在$A$上整，于是只有$k\in A$，矛盾。从而只有$B\cap K=A$。



**15. $A$是整闭环，$K$是其分式域，$L$是$K$的有限扩张，$B$是$A$在$L$中的整性闭包。对于$A$中素理想$\mathfrak p$，全体满足局限为$\mathfrak p$的$B$中素理想$\mathfrak q$个数有限。**

证：

域论相关：https://wuli.wiki/changed/PInsEx.html

每个有限扩张都可以分解为一次可分扩张再作一次纯不可分扩张。当然此时两个扩张都是有限的，于是只需证明$L$是$K$的可分扩张和$L$是$K$的纯不可分扩张的情况即可。

a. $L/K$是有限可分扩张，于是是单扩张，那么添加其分裂域就有$L$能够被嵌入到某个$\Omega$中，且$\Omega/K$是有限正规可分扩张。于是由5.E14$A=B^G$，那么在5.E13中收缩到$A=B^G$中某个素理想$\mathfrak p$的$B$中素理想个数有限。

b. $L/K$是纯不可分扩张。注意零特征域的有限扩张一定是可分的，于是只需考虑有限域。设$\text{char} K=p$，如果$\mathfrak q$是$B$的素理想满足$\mathfrak q\cap A=\mathfrak p$，

对于一个素理想$\mathfrak q$满足$\mathfrak q\cap A=\mathfrak p$，若$x\in \mathfrak q$，则有$x^{p^m}\in\mathfrak p$；反过来若$x^{p^m}\in\mathfrak p\subseteq\mathfrak q$，于是$x\in\mathfrak q$。

另一方面$\{x|\exists m\geq0,x^{p^m}\in\mathfrak p\}$的确是一个理想（验证即可）从而说明满足$\mathfrak q\cap A=\mathfrak p$存在且唯一。于是这就证明了结论。



#### Noether正规化定理，零点定理

https://www.cnblogs.com/XiongRuiMath/p/10289644.html

**16. (Noether正规化定理) 设$k$是域，$A\neq 0$是有限生成$k-$代数，则存在$x_1,\cdots,x_d\in A$，满足它们在$k$上代数无关，并且$A$在$k[x_1,\cdots,x_d]$上整。**

**即任何一个有限生成$k-$代数可以分解为$k\subseteq_{纯超越}k[x_1,\cdots,x_d]\subseteq_{整}A$.**

证：

设$A$由$y_1,\cdots,y_m$作为$k$代数生成。

对$m$归纳，

若$m=0$命题显然。若否，由归纳法只需说明存在子环$S\subseteq A$，满足$S$作为$k-$代数由$m-1$个元素生成，并且$A$在$S$上有限（作为模有限生成）。

这是因为如果$S$满足要求，设对应的$k[x_1,\cdots,x_d]=R$，$R$当然在$k$上纯超越。又$R\subseteq_{整}S\subseteq_{有限}A$，于是$A$在$S$上整。由整性传递性$A$在$R$上整，从而得证。



由于$y_1,\cdots,y_m$如果代数无关，命题已经自然成立（取$x_i=y_i$）。故可以假设存在$f\in k[T_1,\cdots,T_m]$，使得$f(y_1,\cdots,y_m)=0$

首先待定$r$，记$z_i=y_i-y_1^{r^{i-1}},2\leq i\leq m$，于是$f(y_1,z_2+y_1^r,z_3+y_1^{r^2},\cdots,z_m+y_1^{r^{m-1}})=0$

于是左侧由如下形式的项构成：$ay_1^{\alpha_1}\prod_{i=2}^m (z_i+y_1^{r^{i-1}})^{\alpha_i}$，其中系数$a\in k$。那么在这之中$y_1$的最高次项形如$ay_1^{\alpha_1+r\alpha_2+\cdots+r^{m-1}\alpha_m}$

可以取$r$使得对于对于每一项的$\alpha_i$，都有$\alpha_i<r$，那么每个$y_1$的最高次项次数各不相同。于是通过将全局最高次的$y_1$项前系数归一，有$y_1$在$k[z_2,\cdots,z_m]$上整；同样$y_2,\cdots,y_m$由$z_i$的定义自然在$k[z_2,\cdots,z_m]$上整。从而$S=k[z_2,\cdots,z_m]$即为满足要求的子环$S$。



**17a.(Schein零点定理) 给定环$A$，理想$\mathfrak a\subseteq A$，则$r(\mathfrak a)=\cap_{\mathfrak p\supseteq \mathfrak a}\mathfrak p$**

证：（这里写一个迅速的局部化证法：3.11Rmk. $f\notin r(0)\iff 0\notin \{1,f,\cdots,f^n\}\iff A_f\neq 0$，$A_f$的极大理想在$A$中的原像为不含$f$的素理想）

**17b.(Zariski零点定理 - Zariski引理) 设$k$是域，$A$是有限生成$k$代数。如果$A$是域那么它是$k$的有限代数扩张。**

证：由Noether正规化，$k\subseteq A$可以分解为$k\subseteq P\subseteq A$，其中$A$在$P$上整，并且由代数无关性有$P$同构于$k$上多项式环。由5.7，$A$是域，则$P$是域，从而多项式环必然退化成$P$本身。那么$A$在$k$上整，又是有限生成代数，于是是有限代数扩张。

**17c.(Weak Nullstellenstaz) 对于代数闭域$k$，$k[X_1,\cdots,X_n]/\mathfrak m\cong k$，其中$\mathfrak m$是$k[X_1,\cdots,X_n]$的极大理想。更进一步，$\mathfrak m$必定有形式$<X_1-k_1,\cdots,X_n-k_n>$**

证：同5.25.

**17d. (Hilbert Nullstellenstaz) 对于域$k$，有限生成$k-$代数$A$，$\mathfrak a$是$A$的理想，则$r(\mathfrak a)=\cap_{\mathfrak m\supseteq \mathfrak a}\mathfrak m$**

证：同样无妨$\mathfrak a=0$，$f\notin r(0)\iff A_f\neq 0$. 于是$A_f$存在极大理想，设为$\mathfrak m$。其在$A$中的原像是素理想，设为$\mathfrak n$。

于是有域$k$出发的环同态（自然是单的）$k\to A/\mathfrak n$；并有$A/\mathfrak n< A_f/\mathfrak m$。于是$k\to A_f/\mathfrak m$是单同态。设$A$由$x_1,\cdots,x_n$作为$k-$代数有限生成，那么$A_f/\mathfrak m$由$\overline{x_1/1},\cdots,\overline{x_n/1},\overline{1/f}$作为$k-$代数有限生成。于是由Zariski引理，$A_f/\mathfrak m$是$k$的有限代数扩张。

于是$A_f/\mathfrak m$在$k$上整，当然在$A/\mathfrak n$上整，于是由5.7$A/\mathfrak n$是域。故$\mathfrak n$是极大理想，从而$f\notin\mathfrak n$，命题得证。

**17e. (Strong Nullstellenstaz) 对于代数闭域$k$**，理想$\mathfrak a\subseteq k[X_1,\cdots,X_n]$，则$I(Z(\mathfrak a))=r(\mathfrak a)$

证：

对于$(x_1,\cdots,x_n)\in\mathbb{A}^n$，$(x_1,\cdots,x_n)\in Z(\mathfrak a)\iff \mathfrak a\subseteq <X_1-x_1,\cdots,X_n-x_n>$ (See 5.25 Cor.)

另一方面

$f(x_1,\cdots,x_n)=0\iff f\in <X_1-x_1,\cdots,X_n-x_n>$ (See 5.25 Cor.)

于是

$I(Z(\mathfrak a))=\bigcap_{(x_1,\cdots,x_n)\in Z(\mathfrak a)}<X_1-x_1,\cdots,X_n-x_n>\\=\bigcap_{<X_1-x_1,\cdots,X_n-x_n>\supseteq \mathfrak a}<X_1-x_1,\cdots,X_n-x_n>\\=\bigcap_{maximal\ \mathfrak m\supseteq \mathfrak a}\mathfrak m\text{\color{red}(Weak\ Nullstellenstaz)}\\=r(\mathfrak a)\text{\color{red}(Hilbert\ Nullstellenstaz)}$

最后一式注意$k[X_1,\cdots,X_n]$当然是有限生成$k-$代数。





**20. 设$A$是整环$B$的子环，并且$B$在$A$上作为$A-$代数有限生成。证明存在$s\neq 0,s\in A$，$y_1,\cdots,y_n\in B$在$A$上代数无关，并且满足$B_s$在$B'_s$上整，其中$B'=A[y_1,\cdots,y_n]$。**

证：

取$S=A-\{0\}$，$K=S^{-1}A$，$S^{-1}B$是有限生成$K-$代数。由Noether正规化定理，存在$y_1/s_1,\cdots,y_n/s_n\in S^{-1}B$，在$K$上代数无关，并且$S^{-1}B$在$C=K[y_1/s_1,\cdots,y_n/s_n]$上整。

设$z_1,\cdots,z_m$作为$A-$代数生成$B$，那么$z_1/1,\cdots,z_m/1$在$K[x_1,\cdots,x_n]$上整。。

将$z_i/1$对应的零化多项式写出，即$p_{i}(z)=\sum c_{i,j}(z_i/1)^j$

取充分大的$s\in S$使得$sc_{i,j}\in B'$（乘以最小公倍数）那么$p_i(z)\in B'_s[T]$对每个$i$成立，于是$z_i/1$在$B'_s$上整。另一方面$B_s=B_s'[z_1/1,\cdots,z_m/1]$，于是由5.3得证。





**21. 设$A$是整环$B$的子环，并且$B$在$A$上作为$A-$代数有限生成。证明存在$s\neq 0,s\in A$，满足如果$\Omega$是代数闭域，$f:A\to \Omega$是一个同态满足$f(s)\neq 0$，那么$f$可以被延拓为$B\to \Omega$。**

证：

沿用5.E20的记号：首先$f$可以延拓至$B'$，例如将$y_i$映至0。由$s\neq 0$可以延拓至$B'_s$.

由5.E2，可以延拓至$B_s$，于是自然延拓至了$B$。



**22. 设$A$是整环$B$的子环，并且$B$在$A$上作为$A-$代数有限生成。如果$J(A)=0$，那么$J(B)=0$**

证：

取$B$的一个非零元素$v$，需要证明存在一个不包含$v$的极大理想。对$B_v$和子环$A$应用5.E21（整环的局部化仍然是整环），得到了满足要求的$s\neq 0,s\in A$。

设$\mathfrak m$是$A$的极大理想，$s\notin\mathfrak m$，令$k=A/\mathfrak m$。那么典范同态复合上嵌入$A\to k\to \bar{k}$可以被延拓为$g:B_v\to \bar{k}$。当然有$g(v)\neq 0$，否则$g(1/v)$不存在。

另一方面$\text{Im}\ g\cong B_v/\ker g\cong B/(\ker g\cap B)$

？



#### Jacobson环

**23. 设$A$是环，证明下列等价，称满足这个条件的环为Jacobson环：**

**a. 每个素理想都是若干极大理想的交。**

**b. 每个$A$的同态像的Jacobson根和幂零根都相同**

**c. 每个$A$的非极大的素理想都等于严格包含它的素理想的交。**

证：

$b\implies a.$ 对于某个素理想$\mathfrak p$，考虑$A/\mathfrak p$，即证。

$a\implies c.$ 显然

$c\implies b.$ 首先环的同态像总是同构于某个$A$的商环，过渡到商环，于是可以假设$A$是整环但Jacobson根非零。设$0\neq f\in J(A)$，于是$A_f\neq 0$。故$A_f$中存在极大理想，设其拉回是$\mathfrak p$。那么$f\notin \mathfrak p$（否则含1），于是$\mathfrak p$不是极大的。

另一方面，由于$\mathfrak p$是$A_f$中极大理想的拉回，那么严格包含$\mathfrak p$的素理想一定和$\{f,\cdots,f^n,\cdots\}$有交，于是一定包含$f$，从而与c条件矛盾。



**24. 设$A$是Jacobson环，$B$是$A-$代数，证明如果以下二者至少成立其一：$B$在$A$上整；$B$作为$A-$代数有限生成，那么$B$是Jacobson环。**

**特别地，每个有限生成环，和域的有限生成代数是Jacobson环。**

证：



**25. 设$A$是环，证明以下两者等价：**

**1. $A$是Jacobson环；2. 每个有限生成$A-$代数$B$如果是域，那么作为$A$模有限生成。**

证：

$1\implies 2.$ 

设代数$f:A\to B$，$A$的同态像为$A'\subseteq B$（故$A'$是整环），并且$A'$仍然是Jacobson环。因此可设$A\subseteq B$，且$A$整。

由5.E21，存在$s\in A$满足要求，且$s\neq 0$。现在考虑$A$的Jacobson根：$J(A)=\mathfrak R(A)=(0)$，于是$s\notin J(A)$，故存在极大理想$\mathfrak m\not\ni s$. 于是考虑同态$A\to A/\mathfrak m(=k)\hookrightarrow \bar{k}$，那么它可延拓为$g:B\to \bar{k}$。由于$B$是域，于是$g$是单同态，故$B$在$k$上整。即$B$在$A$上整，回忆5.3后Remark（有限型+整=有限）有$B$是有限生成$A$模。

$2\implies1.$

利用23.3判别：

考虑$A$的非极大的素理想$\mathfrak p$，$B=A/\mathfrak p$。设$f$是$B$的非零元素。那么$B_f$是有限生成$A$代数。如果$B_f$是域，那么它是有限生成$A$模，从而在$B$上整。由5.7$B$是域，和$\mathfrak p$非极大矛盾，故$B_f$不是域，从而含有一个非零素理想，将其拉回至$B$，设为$\mathfrak p'$，那么$f\notin\mathfrak p'$.

从而$B$中的全体非零素理想的交是$0$。

因而$\mathfrak p$是全体严格包含其的素理想的交。



**26. 对于拓扑空间$X$，称它的子集是局部闭的如果它是一个开集和闭集的交，或者等价地：它在它的闭包内是开的。**

**证明对于$X_0\subseteq X$，以下三者等价**

**1. 每个非空局部闭集与$X_0$有交；2. 对每个闭集$E$,$\overline{E\cap X_0}=E$；3. $X$中开集到$X_0$中开集（子空间拓扑）的映射：$U\mapsto U\cap X_0$是双射。**

**称满足要求的集合$X_0$是相当稠密集。**

证：

$1\implies 2.$  

首先显然有$\overline{E\cap X_0}\subseteq E$，另一方面对于任何$x\in E$，开邻域$x\in U$。那么$U\cap E$是非空局部闭集，进而和$X_0$有交，进而$U$和$X_0$有交，于是说明$x\in \overline{E\cap X_0}$，故$\overline{E\cap X_0}=E$

$2\implies 3.$

子空间拓扑的定义保证了这个映射是满的。接下来说明它是单的：如果$U\cap X_0=V\cap X_0$，进而$X-U=\overline{(X-U)\cap X_0}=\overline{(X-V)\cap X_0}=X-V$，故$U=V$。

$3\implies 1.$

考虑非空局部闭集$U\cap V(U\ open, V\ closed)$。

由于$U\neq \varnothing$，由双射条件知$U\cap X_0\neq \varnothing$。而$U\cap V\neq \varnothing$，如果$V\cap (U\cap X_0)=\varnothing$，于是$U\cap X_0\subseteq X-V$。那么$[(X-V)\cap U]\cap X_0=U\cap X_0$，从而只有$(X-V)\cap U=U$，即$X-V\supseteq U$。这和$U\cap V\neq\varnothing$矛盾。

**接下来的命题将会指出Jacobson环的素谱具有的拓扑性质：**

**对于一个环$A$，以下三者等价：**

**1. $A$是Jacobson环；2. $A$的极大理想点构成的集合是相当稠密集；3. $Spec(A)$的每个单点局部闭集都是闭的。（这是23的几何解释）**

证：

$1\iff 2.$ 

记极大理想点集为$Max(A)$.  对于任何理想$\mathfrak a$，考虑$V(\mathfrak a)\cap Max(A)$，它的闭包也是$V(\mathfrak a)$。设包含$\mathfrak a$的极大理想的交都是$\mathfrak b$，如果$r(\mathfrak a)\sub \mathfrak b $

那么$V(\mathfrak b)\supseteq V(\mathfrak a)\cap Max(A)$，但$V(\mathfrak b)\sub V(\mathfrak a)$，这与闭包的定义矛盾，于是只能$\mathfrak b=r(\mathfrak a)$，即等价于$A$的每个同态像中Jacobson根和幂零根相同。由5.E23.2即证。

$1\implies 3.$ 

设$\{\mathfrak p\}=V(\mathfrak a)-V(\mathfrak b)$，那么记$Q=\{\mathfrak q|\mathfrak p\sub\mathfrak q\}$，$Q\subseteq V(\mathfrak a)$，于是$Q\subseteq V(\mathfrak b)$，故$\mathfrak b\subseteq \cap_{\mathfrak p\sub\mathfrak q}\mathfrak q\xlongequal[]{Jacobson\ Ring}\mathfrak p$，那么$\{\mathfrak p\}\in V(\mathfrak b)$，矛盾！

$3\implies 1.$

若对于某个非极大理想$\mathfrak p$，$\mathfrak p\sub\cap _{\mathfrak p\sub\mathfrak q}\mathfrak q$，则$\{\mathfrak p\}=V(\cap_{\mathfrak p\subset \mathfrak q}\mathfrak q)-V(\mathfrak p)$，于是$\mathfrak p$极大，矛盾。



#### 赋值

**27. 设$A,B$是两个局部环，$B$被称为优于$A$如果$A\subseteq B$，并且$A$中的极大理想$\mathfrak m$被$B$中极大理想$\mathfrak n$包含（或更准确地$\mathfrak m=\mathfrak n\cap A$）。设$K$是域，$\Sigma$是$K$的全体子局部环。给$\Sigma$赋以优序，证明$\Sigma$有极大元，并且$A\in \Sigma$极大$\iff A$是$K$的赋值环。**

证：

极大元存在：

考虑升链$(A_1,\mathfrak m_1)\sub \cdots \sub (A_n,\mathfrak m_n)\sub\cdots$.

考虑$k_i=A_i/\mathfrak m_i$, 因而存在$k_i\to k_{i+1}$的同态。由于$k$是域，只能有这些同态是嵌入。

因而存在正向系统之间的正合列$0\to\mathbf{m}\to \mathbf{A}\to \mathbf{k}\to 0$. 从而正向极限之间存在正合列$0\to \cup \mathfrak m_i\to\cup A_i\to \cup k_i\to 0$. 

因而$\cup \mathfrak m_i$是$\cup A_i$的极大理想，接下来证明它是局部环。

由1.6.2，$1+\cup \mathfrak m_i$中元素设为$1+m$，必然有$m\in \mathfrak m_i$，于是$1+m$在$A_i$中是单位，进而在$\cup A_i$中是单位，从而说明了局部环。

赋值环：

$A\in \Sigma$极大$\implies $赋值环

记$\Omega=\bar{K}$，考虑同态$f:A\to A/\mathfrak m\hookrightarrow \Omega$（注意到$A/\mathfrak m$可以嵌入到$K$，于是嵌入到$\Omega$）

回忆5.3节赋值环的构造，如果存在$(A',f')>(A,f)$，无妨将$(A',f')$取为一个极大元，于是由5.19它是局部环，并且$f'|_A=f$。那么极大理想$\mathfrak n=\ker f'$当然满足$\mathfrak n\cap A=\mathfrak m$，与$A\in \Sigma$极大矛盾。

于是$(A,f)$在5.3节序关系中极大，于是由5.21是赋值环。

赋值环$\implies A\in \Sigma$极大

现在假定$A$是赋值环，如果局部环$B$优于$A$，那么$A\sub B\sub K$。由5.18.2，$A,B$都是局部环。

考虑$(A,\mathfrak m)$, $(B,\mathfrak n)$，由5.18.1的证明，$\mathfrak m$是$x\in A,x^{-1}\notin A$的$x$构成的集合。于是对其扩环必定会导致$x\in A$，$x^{-1}\in B$的情形的出现。因此$\mathfrak n$反而要小于$\mathfrak m$。从而只能$A=B$



**28. 设$A$是整环，$K$是分式域，证明以下两者等价：**

**1. $A$是$K$的赋值环；2. $\mathfrak a,b$是$A$的理想，则$\mathfrak {a\subseteq b,b\subseteq a}$必定出现其一。** 

**自然地作为推论$A/\mathfrak p$和$A_{mathfrak p}$都是它们各自分式域中的赋值环。**

证：

$1\implies 2.$

若否，设$x\in\mathfrak a-\mathfrak b,y\in\mathfrak b-\mathfrak a$，自然$x,y\neq 0$。由于$x/y\in K$，无妨$x/y\in A$。那么$\mathfrak b\ni y\cdot x/y=x\in\mathfrak {a-b}$，矛盾。

$2\implies 1.$

对于$a/b\in K^{\times}$，只要$(a)\subseteq (b)$就有$b/a\in A$，反之$a/b\in A$，得证。



**29. 设$A$是$K$的赋值环，那么每个包含$A$的$K$的子环都是$A$的某个局部化。**

证：

设子环为$B$，5.18保证$B$是赋值环，进而是局部环。设$B$的极大理想是$\mathfrak n$，$A$的极大理想是$\mathfrak m$。由5.E27.2的讨论知$\mathfrak n\subseteq \mathfrak m$. 那么$\mathfrak n=\mathfrak n\cap A$是$A$的素理想。我们证明$B=A_{\mathfrak n}$

这是显然的，只需将局部环嵌入到分式域中立即得证。

（注意有如下关系：

![TpvBoard_2023_06_16_14_33_22](/Users/wanglijun/Desktop/笔记/Introduction to Commutative Algebra - Part2.assets/TpvBoard_2023_06_16_14_33_22.png)

）



**30.（赋值环$\rightarrow$赋值） 设$A$是$K$的赋值环，$A$的单位群$U$是$K^*$的子群。**

**令$\Gamma=K^*/U$，设$\xi,\eta\in \Gamma$，被$x,y\in K$代表。定义$\xi\geq \eta$如果$xy^{-1}\in A$（很容易验证这是良定义的）证明这是全序，并且和群乘法相容：$\xi\geq\eta\implies \xi\omega\geq \eta\omega$。于是我们得到了一个全序Abel群，称为环$A$的值群。**

**$v:K^*\to \Gamma$记为自然同态，证明$\forall x,y\in K^*$，$v(x+y)\geq \min\{v(x),v(y)\}$**

证：

全序显然，相容性显然。

下面证明不等式。无妨$v(x)\geq v(y)$，则$(x+y)y^{-1}=xy^{-1}+1\in A$.



**31. （赋值$\rightarrow$赋值环）设$\Gamma$是一个全序Abel群，群运算以加法记。设$K$是一个域，那么它的赋值被定义为一个映射$v:K^*\to \Gamma$，满足：1. $v(xy)=v(x)+v(y)$；2.$v(x+y)\geq\min\{v(x),v(y)\}$.**

**证明全体满足$v(x)\geq 0$的元素构成一个赋值环，并且$v(K^*)$正好构成了对应的值群。**

证：

首先这样的元素对加法和乘法封闭，$v(1)=0$。$2v(-1)=v(1)=0$，故元素对加法逆封闭，于是说明了它构成环。

它是赋值环是因为$0=v(1)=v(x)+v(x^{-1})$，于是至少存在一个大于0，故$x,x^{-1}$至少存在一属于这个环，从而是赋值环。记这个环为$A$。



另一方面$v(x)=0\iff v(x)\geq 0,v(x^{-1})\geq 0\iff x\in A^*=U$，并且$v$当然是群同态，于是当然有$v(K^*)\cong K^*/U$，并且序关系相容。于是这说明了5.E30和5.E31内容的等价性。



**32. 设$\Gamma$是全序Abel群。称子群$\Delta$是孤立的如果$0\leq \beta\leq \alpha,\alpha\in \Delta\implies\beta\in\Delta$**

**设赋值环$A$(w.r.t. 域$K$)，值群$\Gamma$。如果$\mathfrak p$是$A$的素理想，证明$v(A-\mathfrak p)$是某个孤立子群$\Delta$和非负（即$\geq 0$）元素的交。**

**这样诱导出了$Spec(A)$到全体孤立子群的映射，证明这个映射是双射**。

**研究$A/\mathfrak p,A_{\mathfrak p}$的值群。**

证：

32.1 如果一个子群的非负部分被确定了，那么这个子群就被唯一确定了。于是只需考虑$v(A-\mathfrak p)$是否满足孤立条件。

设$\alpha$的代表元为$x\in A-\mathfrak p$，$\beta$代表元为$y$，那么$y\in A$，$xy^{-1}\in A$。若$y\in\mathfrak p$，$x=xy^{-1}y\in\mathfrak p$，矛盾。于是$y\in A-\mathfrak p$，从而验证了孤立条件。

32.2 

单射：如果$\Delta(\mathfrak p)=\Delta(\mathfrak q)$

于是$\forall x\in A-\mathfrak p$，$\exists y\in A-\mathfrak q$满足$v(x)=v(y)$, i.e. $v(xy^{-1})=0$，即$x,y$相差一个单位。然而$A-\mathfrak p$，$A-\mathfrak q$分别乘以单位群后都不动，于是这说明$A-\mathfrak p\subseteq A-\mathfrak q$。类似地存在反包含关系，于是$A-\mathfrak p=A-\mathfrak q$，从而得证。

满射：给定$\Delta$，考虑$\mathfrak p=A-v^{-1}(\Delta)$，需要证明这是素理想。首先当然$0\in \mathfrak p$。若$x,y\in\mathfrak p$, $x+y\not\in\mathfrak p$，那么由$v(x+y)\geq \min\{v(x),v(y)\}$及孤立条件知至少有一（设为$x$）满足$v(x)\in \Delta$，即$x\notin \mathfrak p$，矛盾。

若$x\in\mathfrak p,a\in A$，但是$ax\notin\mathfrak p$，于是$v(ax)=v(x)+v(a)$，即$v(ax)\geq v(x)\geq 0$，故$v(x)\in\Delta$，即$x\notin\mathfrak p$，矛盾。

若$x,y\notin\mathfrak p,xy\in\mathfrak p$，$v(xy)=v(x)+v(y)$。而$v(x),v(y)\in \Delta$，于是只能有$v(xy)\in\Delta$，矛盾。从而$\mathfrak p$的确是素理想，得证。

32.3

设$\mathfrak p$对应的孤立子群为$\Delta$。

结论$A/\mathfrak p: \Delta;A_{\mathfrak p} :\Gamma/\Delta$



**33.（值群构造赋值） 设$\Gamma$是全序Abel群。接下来从$\Gamma$构造出域$K$和赋值$v$。设$k$是任意域，$A=k[\Gamma]$是群代数，那么$A$是$k-$线性空间。基为$x_{\alpha},\alpha\in \Gamma $，说明$A$是整环。**

**如果$u=\lambda_1x_{\alpha_1}+\cdots+\lambda_nx_{\alpha_n}$是$A$的非零元素，并且$\lambda_i\neq 0,\forall i$，$\alpha_1<\cdots<\alpha_n$，定义$v_0(u)=\alpha_1$。证明$v_0:A-\{0\}\to \Gamma$满足赋值的两个条件。**

**记$K$为$A$的分式域，证明$v_0$可以被唯一的延拓成$K$的赋值$v$，并且值群恰好为$\Gamma$。**

证：

33.1 考虑指标序最小两项的乘积，对应项的系数就应该是系数乘积，自然非零。

33.2 直接验证即可。

33.3 $v(1/f)=-v_0(f)$，经验证的确是赋值。



**34. 设$A$是赋值环，$K$是分式域。$f:A\to B$诱导出$f^*:Spec(B)\to Spec(A)$是闭映射。那么如果$g:B\to K$是代数同态（即$g\circ f$是嵌入），那么$g(B)=A$。**

证：

设$C=g(B)$，当然$A\subseteq C$。取$C$的极大理想为$\mathfrak n$，由于闭映射，那么$\mathfrak m=\mathfrak n\cap A$也是极大理想。因此$A=A_{\mathfrak m}$，而$C_{\mathfrak n}$优于$A_\mathfrak m$，于是$C_\mathfrak n=A$，因此$C\subseteq A$，从而$A=C$，得证。



**35. 利用5.E1和5.E3说明$f:A\to B$是整的，$C$是任意$A-$代数，那么映射$(f\otimes 1)^*:Spec(B\otimes_A C)\to Spec(C)$**.

**反过来，如果$f:A\to B$满足上述条件，且$B$是整环，那么$f$是整的。**

证：

正方向是显然的。反过来：

记$A'=f(A)\subseteq B$，$K$是$B$的分式域。欲证整性，由5.22，只需说明$B$在每个包含$A'$的$K$的赋值环中。设$C$是这样的一个赋值环，那么$A'\subseteq B,C\subseteq K$。那么$B\times C\to K$是$A$双线性的。于是诱导出了双线性映射$g:B\otimes_A C\to K$。

现在记$F=(f\otimes 1):C\to B\otimes C$，$F^*$是闭映射。$g\circ F:c\mapsto 1_B\otimes c\to c$，即给出了单射$C\hookrightarrow K$。5.E34保证了$g(B\otimes_AC)=C$，那么$g(b\otimes 1_c)\in C$，故$B\subseteq C$。于是完成了证明。

**证明这个结果仍然成立如果$B$只有有限个素理想。**

证：

设$\mathfrak p_i$是极小素理想，那么考虑$A\to B\to B/\mathfrak p_i$。由于$Spec(B\otimes_AC)\to Spec(C)$是闭映射，而1.E21.4保证$Spec((B/\mathfrak p_i)\otimes C)\to Spec(B\otimes C)$是闭的，因而$Spec((B/\mathfrak p_i)\otimes C)\to Spec(C)$是闭映射。由前述命题（$B/\mathfrak p_i$是整环）得$A\to B/\mathfrak p_i$是整的。

那么在$\prod (B/\mathfrak p_i)$中$(0,\cdots,B/\mathfrak p_i,\cdots,0)$在$A$上整，由整元一定构成子环知$\prod(B/\mathfrak p_i)$在$A$上整。

由于$B\to \prod (B/\mathfrak p_i)$可分解为$B {\twoheadrightarrow} B/\mathfrak R\hookrightarrow \prod (B/\mathfrak p_i)$，那么自然$B/\mathfrak R$在$A$上整。

设$\overline{x}$满足某个首一$A$系数多项式$p(x)=\overline{0},i.e.\in \mathfrak R$，那么$p(x)^l=0$，得证。