# Algebraic Number Theory

## 0. Plan

1. Algebraic integers
2. Dedekind domain
3. Finiteness Thms
4. Valuation Theory

## 1. Introduction

Examples. 

Solve eq. $x^2+y^2=z^2$. One can easily deduced that $\begin{cases} x=2ab\\y=a^2-b^2\\z=a^2+b^2\end{cases}$ (with some additional conditions)

Solve $y^2=x^3-2$, $x^3=(y+\sqrt{-2})(y-\sqrt{-2})$.

Consider $\Z[\sqrt{-2}]$. This ring is a UFD; its units are $\pm1$; $\sqrt{-2}$ is irreducible; $gcd(y+\sqrt{-2},y-\sqrt{-2})=1$. 

($z|y\pm\sqrt{-2}\implies z|2\sqrt{2}\implies \sqrt{-2}|z\implies \sqrt{-2}|y\implies 2|y\\\implies y^2=x^3-2\equiv 2\mod 8$.Contradiction)

Thus $x^3=(y+\sqrt{-2})(y-\sqrt{-2})\implies y+\sqrt{-2}=\\(a+b\sqrt{-2})^3=a(a^2-6b^2)+b(3a^2-2b^2)\sqrt{-2}\implies b(3a^2-2b^2)=1\\\implies (a,b)=(\pm1,1);(3,\pm5)$

This leads to the first "fake" proof of Fermat's Last Thm. (Error occurs that mathematicians assume that $\Z[\sqrt{-p}]$ is always an UFD which is obviously not true.)



Thus the main aspects we concern is:

1. $\Z[\zeta_p]$ UFD?
2. What is $\Z[\zeta_p]^\times$
3. Iwasawa Theory.

General Statement:

Intregral ring of $\Q[\sqrt{-d}]$ in $\Z$ is $\mathcal O_k$.

Thm1. (Factorization of Ideals)

Given an ideal $I\subseteq \mathcal O_k$,one can decomposite $I=\prod p_i^\alpha$ in a uniquely (Primary decomposition)

Thm2. (Finiteness of class number)

$Cl_k=\{fractional\ ideals\}/\{principle \ ideals\}$, which is a F.G. Abelian Group.

This evaluate how far a dedekind domain is from the principal ideal domain.

Thm3. (Dirichlet's Unit Theorem.)

$\mathcal O_k^{\times}=W_k\times V_k$, where $W_k$ is finite abelian group, generated by $\zeta_k$, $V_k$ is free abelian group $\Z^{r_1+r_2-1}$, where $r_1,r_2$ are numbers of real embedding and non-real embedding, resp.



Galois Theory.

$L/K$ a finite extension. $Gal(L/K)=\{\phi:L\to L,iso|\phi|_K=id.\}$

$Gal(L/K)=\Z/2\Z$.

Thm4. Middle field of $L/K$ $M$,it leads to subgroup of $Gal(L/K)$ $Gal(L/M)$. Conversly  a subgroup $H$ leads to $L^H$.

Thus we need to study $Gal(L/\Q)$.



Issue. $Rep(Gal_\Q)$ is far too complicated, we study $Gal_{\Q_p}$ instead.

(Here $Gal_\Q=Gal(\bar{\Q}/\Q),Gal_{\Q_p}=Gal(\Q_p/\Q)$

Class Field Theory.

We find that $Gal(L/\Q_p)\cong \Q_p^{\times}/Nm(L^{\times})$

Here $Nm:L\to K, x\in L,\phi_x:y\mapsto xy, take \ Nm(x)=\det$.

This is a local case.

For global cases $I_\Q=\prod_v\Q_v^{\times}$, here $v$ are all valuations (absolute, $p-$adic)

$=\{(x_v)|x_v\in \Q_v^{\times}, x_v=\mathcal O_v^{\times} for\ all\ but\ finite\ many\ v\}$

Thm. $Gal(L/\Q)^{ab}\cong I_\Q/Nm(I_L)$



Langlands Conjecture.



## 2. Algebraic integers

Given a ring extension $A\subseteq B$. Say $x\in B$ integral over $A$ if exists monic polynomial with coefficient in $A$ such that it is the root of this polynomial.

Say $B$ integral over $A$ if $\forall x\in B$ is integral over $A$.

Prop. $A\subseteq B$, TFAE:

$1.x$ integral; $2. A[x]$ f.g.$A-$module; 3. $x$ contained in a f.g. $A-$module.

Cor. Integral closure of $A$ in $B$ form a subring of $A$ containing $A$. ($x+y,xy\in A[x,y]$, while the latter module is f.g. $A-$module)



If the integral closure of a ring is itself, then we say the ring to be integrally closed.(整闭)

If a ring $A$ is an integral domain, then it is integrally closed if it is integrally closed in its fraction field.

Def. $K/\Q$ finite extension, then $\mathcal O_k$ is the integral closure of $\Z$ in $K$.



### **Trace and Norm.**

Given a finite extension of fields $L/K$, $\forall x\in L.\phi_x:L\to L,y\mapsto xy$

Define the trace of $x$ is $tr(\phi_x)$, norm is $\det \phi_x$, where $\phi_x$ viewed as a $K-$linear transformation. Obv that trace and norm belongs to $K$.

Productivity: $N(ab)=N(a)N(b)$

E.g. In $\Q[2+\sqrt{3}]/\Q$, $Nm(2+\sqrt{-3})=7$. (Which has a direct relation with the complex cases.) 



**Prop. $L/K$ finite extensions of fields of char 0. $n=[L:K]$, $\tau : K\to \Omega$ is a fixed embedding into its algebraic closure.**

**Then $\exists\ n$ distinct embedding $\sigma_1,\cdots,\sigma_n: L\to \Omega$, s.t. $\sigma_i|_K=\tau$; and all of the embeddings $\sigma_1,\cdots,\sigma_n$ are linear independent.**



$Tr_{L/K} (x)=\displaystyle \sum_{i=1}^{n}\sigma_i(x)$

$Nm_{L/K}(x)=\displaystyle\prod_{i=1}^{n}\sigma_i(x)$

Pf: Fact $Tr_{L/K}(x)=[L:K(x)]Tr_{K(x)/K} (x)$; $Nm_{L/K}(x)=Nm_{K(x)/K}(x)^{[L:K(x)]}$

Say $f(T)=T^n+\cdots \in K[T]$ is the minimal polynomial of $x$. Then $Tr_{K(x)/K}(x)=-a_1=\sum \{roots\ of\ f\}=\sum \sigma_i(x)$, similarly we get similar results for the norms.



**Prop. Consider $L\times L\to K:(x,y)\mapsto Tr_{L/K}(xy)$ which leads to a quad. form, it is non-degenerate.**

**Cor. $\alpha_1,\cdots,\alpha_n$ are $n=[L:K]$ elements of $L$. Then $(\alpha_1,\cdots,\alpha_n)$ is a $K-$basis of $L\iff \det \big(Tr_{L/K}(\alpha_i\alpha_j)\big)\neq 0$ **

Hint. Consider: $\begin{CD}K^n@>>> L@>>> K^n\\\\(x_i)@>>>\sum x_i\alpha_i\\\\@.x@>>>\big(Tr(x\alpha_i)\big)\end{CD}$

### **Discriminents**

**Discriminents. Consider $K/\Q$, $n=[K:\Q]$, $\alpha_1,\cdots,\alpha_n\in K$, define the discriminant $\det\big(Tr(\alpha_i\alpha_j\big)$.**

**Lem.(1) $\sigma_1,\cdots,\sigma_n$ are embeddings of $K$ into $\bar{Q}$, then $Disc(\alpha_1,\cdots,\alpha_n)=\det\big(\sigma_i(\alpha_j)\big)^2$**

**(2) $(beta_1,\cdots,\beta_n)=(\alpha_1,\cdots,\alpha_n)C$, where $C\in M_{n\times n}(K)$, then $Disc(\beta_1,\cdots,\beta_n)=Disc(\alpha_1,\cdots,\alpha_n)(\det C)^2$**



E.g. $f(T)\in \Q[T]$ the minimal polynomial of $\alpha\in K$, then $Disc(1,\alpha,\cdots,\alpha^{n-1})=\begin{cases}0&\deg f<n\\(-1)^{n(n-1)/2} N_{K/\Q}(f(\alpha))&\deg f=n\end{cases}$



**Prop. $\mathcal O_K $ is a free abelian group of rank $n$.**

Pf. $(\alpha_1,\cdots,\alpha_n)$ the basis of $K/\Q$

Given $M=\oplus \Z\alpha_i\subseteq \mathcal O_K$

Consider the dual basis $\alpha_i^*$ such that $Tr_{K/\Q}(\alpha_i^*\alpha_j)=\delta_{ij}$, thus we get the dual span $M^*=\oplus_i\Z\alpha_i^*=\{x\in K|Tr_{K/\Q}(xy)\in \Z|\forall y\in M\}$, thus $\mathcal O_K\subseteq M^*$

Moreover $|M^*/M|=|Disc(\alpha_1,\cdots,\alpha_n)|$ finite, thus $\mathcal O_K$ must be a rank $n$ free abelian group.

**Definition. A basis $\alpha_1,\cdots,\alpha_n$ of $K/\Q$ is called an integral basis if it is a basis of $O_K/\Z$**

(From the prop. previously shown, it is a reasonable definition)

**Definition. $\Delta_K=Disc(integral\ basis)\in\Z$ is invariant under changes of the integral basis. It is called the discriminent of $K$**

Invariant property comes from the following fact:

Since $(\beta_1,\cdots,\beta_n)=(\alpha_1,\cdots,\alpha_n)C;(\alpha_1,\cdots,\alpha_n)=(\beta_1,\cdots,\beta_n)D$

Thus $Disc(\beta)=Disc(\alpha)(\det C)^2;Disc(\alpha)=Disc(\beta)(\det D)^2$, since integrality, $Disc(\alpha)=Disc(\beta) $



**Prop. $\alpha\in \mathcal O_K$ s.t. $K=\Q(\alpha)$, $f(T)\in \Z[T]$ being its minimum polynomial. Assume $p^2|Disc(1,\alpha,\cdots,\alpha^{n-1})$。**

**If $\exists i s.t. \ f(T+i)$ is a $p-$Eisenstein polynomial, then $\mathcal O_K=\Z[\alpha]$**

Lem. $\beta_1,\cdots,\beta_n\in \mathcal O_K$ s.t. $\beta_i$ a basis of $K/\Q$, then $\beta_i$ integral basis $\iff$ $\forall p^2|Disc(\beta_i)$, $\not\exists x_1\in\{0,\cdots,p-1\}$ s.t. $\exists$ notall 0 coefficients $x_i$ s.t. $\sum x_i\beta_i\in p\mathcal O_K$.

Pf: Take $\alpha_i$ a integral basis, assume $\beta_i$ is not a integral basis, $(\beta_i)=(\alpha_i)C$, then $|\det C|\neq 1$. Take $p\mid |\det C|$, consider $\bar{C}=C\mod p$, $\exists \bar{x_i}\in \mathbb{F}_p, \bar{C}\bar{x}=0$

Then we get $\sum x_i\beta_i\in p\mathcal O_k$.

Conversely if $\sum x_i\beta_i\in p\mathcal O_K$, then $p|\det C$, thus $\det C\neq 1$.



Now back to the prop.

For $x=\dfrac{1}{p}\sum_{i=0}^{n-1}x_i\alpha^i\\$, we need to show $x\notin \mathcal O_K$. Take $j=\min\{i|x_i\neq 0\}$, $N_{K/\Q}(x)=\dfrac{N_{K/\Q}(\alpha^j)}{p^n}N_{K/\Q}(\sum_{i=j}^{n-1} x_i\alpha^{i-j})$

Since $\dfrac{N_{K/\Q}(\alpha^j)}{p^n}=\dfrac{((-1)^na_n)^j}{p^n}$, $p||a_n$, we only need to show $p\not\mid N_{K/\Q}(\sum_{i=j}^{n-1}x_i\alpha^{i-j})$

However $N_{K/\Q}(\sum_{i=j}^{n-1}x_i\alpha^{i-j})=\prod_{k=1}^n (x_j+x_{j-1}\sigma_k(\alpha)^{i-j}\cdots)$, from calculating we get the result, thus $N_{K/\Q}(x)\notin \Z$, hence the result.



E.g. Cyclotomic Extension.

Consider $p^2|Disc(1,\cdots,\zeta_{p^n}^{p^n-p})$, $\Phi_{p^n}(x+1)$ Eisesnstein, thus $\mathcal O_{K[\zeta_{p^n}]}=\Z[\zeta_{p^n}]$



Prop. Assume $K\cap L=\Q$, $d=\gcd (\Delta_K,\Delta_L)$, then $\mathcal{O}_{KL}\subset \dfrac{1}{d}\mathcal O_K\mathcal O_L$

Pf. Take $(\alpha_i),(\beta_i)$ a integral basis of $\mathcal O_K,\mathcal O_L$,  let $x\in \mathcal O_{KL}$, then $x=\sum_{i,j}\dfrac{x_{ij}}{r}\alpha_i\beta_j$

We need to show $r|d$, i.e. $r|\Delta_K$. Consider dual basis and a bunch of computations leads to the result.(Require More Details!)