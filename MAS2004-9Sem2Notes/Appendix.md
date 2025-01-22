(chap:app)=
# Appendix

Throughout these notes, there have been times where a proof or more technical discussion has been omitted due to time limitations. Some of these proofs are included here, for interest. Note that this chapter is non-examinable, with the exception of the statement of [Theorem A.3](#udiff'), which has already been stated earlier in the notes ({prf:ref}`udiff`).

## A.1 Continuous functions are integrable
````{admonition} Theorem A.1
Let $f:[a,b]\to \mathbb{R}$ be continuous. Then $f$ is Riemann integrable.
````

**Proof.**
Since $f$ is continuous, it is bounded, by {prf:ref}`thm:evt`, and so we may consider its upper and lower integrals.

Let $\varepsilon>0$. We aim to show that $U(f)-L(f)<\varepsilon$. The result will then follow by {prf:ref}`intcond`.

Since $f$ is continuous, for each $x\in[a,b]$ there exists $\delta_x>0$ such that 

$$
|f(x)-f(y)|<\frac{\varepsilon}{b-a} \hspace{2em} \text{ whenever }|x-y|<\delta_x.
$$

Here, we use the subscript $x$ to emphasise that $\delta$ may depend on $x$. 

*Claim.*
$\delta$ can be chosen independently of $x$. 

*Proof of claim.*
If not, then for each $n\in\mathbb{N}$ we can choose $x_n,y_n\in[a,b]$ such that 
```{math}
:label: eq:xn-yn
|x_n-y_n|<\frac{1}{n}
```
and
```{math}
:label: eq:fxn-fyn
|f(x_n)-f(y_n)|\geq\frac{\varepsilon}{b-a}.
```
Now $(x_n)$ is a bounded sequence, and so must have a convergent subsequence. Suppose that $(x_{n_j})$ is a subsequence converging to $l$. Then by equation [](eq:xn-yn), we must also have $y_{n_j}\rightarrow l$. By continuity, $f(x_{n_j})-f(y_{n_j})\rightarrow 0$, which contradicts [](eq:fxn-fyn). 


We have shown that there is a single number $\delta>0$ such that for any $x,y\in[a,b]$,

$$
|f(x)-f(y)|<\frac{\varepsilon}{b-a} \hspace{2em} \text{ whenever }|x-y|<\delta.
$$

Let $a=x_0<x_1<x_2<\ldots<x_n=b$ be chosen so that $x_k-x_{k-1}<\delta$ for $k=1,2,\ldots,n$ (this is always possible if we take $n$ large enough), and let $P=\{x_0,x_1,\ldots,x_n\}$. By continuity, $f$ attains its maximum and minimum on each interval $[x_{k-1},x_k]$. Let $c_k,d_k\in[x_{k-1},x_k]$ such that

$$
f(c_k) = \inf\{f(x):x_{k-1}\leq x\leq x_k\},
$$

and

$$
f(d_k) = \sup\{f(x):x_{k-1}\leq x\leq x_k\}.
$$

Note that $f(c_k)<f(d_k)$, and also, since $0<x_k-x_{k-1}<\delta$, we have $f(c_k)-f(d_k)<\frac{\varepsilon}{b-a}$. The lower and upper sums associated with $P$ are therefore

$$
L(f,P) = \sum_{k=1}^nf(c_k)(x_k-x_{k-1}) \hspace{.5em} \text{ and } \hspace{.5em} U(f,P) =  \sum_{k=1}^nf(d_k)(x_k-x_{k-1}).
$$

Hence

$$
L(f) \geq \sum_{k=1}^nf(c_k)(x_k-x_{k-1})  \hspace{.5em} \text{ and } \hspace{.5em} U(f) \leq  \sum_{k=1}^nf(d_k)(x_k-x_{k-1}).
$$

Also, since $0<x_k-x_{k-1}<\delta$, we have $\ds f(c_k)-f(d_k)<\frac{\varepsilon}{b-a}$. Thus
	\begin{align*}
	U(f) - L(f) &\leq \sum_{k=1}^nf(d_k)(x_k-x_{k-1}) - \sum_{k=1}^nf(c_k)(x_k-x_{k-1})\\
	&= \sum_{k=1}^n(f(c_k)-f(d_k))(x_k-x_{k-1}) \\
	&\leq \sum_{k=1}^n\frac{\varepsilon}{b-a}(x_k-x_{k-1}) = \varepsilon.
	\end{align*}
Since $\varepsilon$ was arbitrary, it follows that $U(f)=L(f)$, and so $f$ is Riemann integrable.

(sec:intdiffunif)=
## A.2 Integration and differentiation under uniform 
In [Chapter 5](#chap:seq&seriesoffns), we saw that continuity is preserved under uniform limits. We also saw that, provided certain conditions are met, differentiability is preserved by uniform limits. In this section, we will prove this result, by first proving a similar result about integration.

The following result is called the {\em uniform limit theorem for integrals}.

````{admonition} Theorem A.2 (Uniform limit theorem for integrals)
:label: uct
Let $f_n :[a,b]\rightarrow \mathbb{R}$ be a cont:inuous function, for $n\in\mathbb{N}$. Suppose the sequence $(f_n)$ converges uniformly to a function $f$. Then

$$
\lim_{n\rightarrow \infty} \int_a^b f_n(x)dx = \int_a^b f(x)dx.
$$

````

**Proof.**
By {prf:ref}`ucont`, the function $f$ is continuous, and therefore integrable. Let $\varepsilon >0$. 
Since $(f_n)$ converges uniformly to $f$,
 we have $N\in \mathbb{N}$ such that

$$
|f_n (x) -f(x)| < \frac{\varepsilon}{2(b-a)}
$$

whenever $n\geq N$, for all $t\in [a,b]$.

Hence by {prf:ref}`propsint` and {prf:ref}`bdint`, for $n\geq N$ we have
\begin{align*}  
\left| \int_a^b f_n (x)dx - \int_a^b f(x)dx \right| 
&=\left|  \int_a^b \big(f_n(x) -f(x)\big)dx \right|\\
&\leq \int_a^b |f_n(x) -f(x)|dx \leq \frac{(b-a)\varepsilon}{2(b-a)} =\frac{\varepsilon}{2} < \varepsilon. \\
\end{align*} 
The result now follows.


Thus we can, \emph{under suitable conditions}, swap limits and integral signs. This is frequently useful. 

The result actually still holds if each $f_n$ is Riemann integrable rather than continuous, but the proof is much more involved, and the above is enough for our purposes.

The following example shows that we do need {\emph{uniform}} convergence to be able to swap limits and
integrals.

````{prf:example}
Let $f_n:[0,1]\to\mathbb{R}$, for $n\in\mathbb{N}$ be defined by

$$
f_n(x)=nx(1-x^2)^n.
$$

(i) Show that $(f_n)$ converges pointwise to the zero function.

(ii) Calculate $\lim_{n\to\infty}\int_0^1 f_n(x)dx.$

(iii) Does $(f_n)$ converge uniformly?
````

**Solution.**
(i) Clearly, if $x=0$ or $x=1$, then $f_n(x)=0$ for all $n$ and so $f_n\rightarrow 0$ pointwise.
So now suppose $x\in (0,1)$. Then $0<1-x^2<1$. So we can find a positive number $h$ such that
$1-x^2=1/(1+h)$. Using the binomial expansion for $(1+h)^n$, we see that $(1+h)^n>\frac{n(n-1)}{2}h^2$, so

$$
0<nx(1-x^2)^n=\frac{nx}{(1+h)^n}<\frac{2nx}{n(n-1)h^2}=\frac{2x}{(n-1)h^2}.
$$

Since $\frac{2x}{(n-1)h^2}\to 0$ as $n\to\infty$, by the sandwich rule, $f_n(x)\to 0$ as $n\to \infty$. Thus $(f_n)$ converges pointwise to the zero function.

(ii) Substitute $u=x^2$, to get
\begin{align*} 
\int_0^1 f_n(x)dx&=\int_0^1 nx(1-x^2)^n\,dx= \int_0^1 nx(1-u)^n \frac{1}{2x}du \\
&=\frac{n}{2}\int_0^1 (1-u)^ndu=\frac{n}{2}\left[-\frac{(1-u)^{n+1}}{n+1}\right]_0^1=\frac{n}{2(n+1)}.
\end{align*} 
So 

$$
\lim_{n\to\infty}\int_0^1 f_n(x)dx=\lim_{n\to\infty}\frac{n}{2(n+1)}=\lim_{n\to\infty}\frac{1}{2+\frac{2}{n}}=\frac{1}{2}.
$$

(iii) From the previous parts we see that 

$$
\lim_{n\to\infty}\int_0^1 f_n(x)dx=\frac{1}{2}\neq 0=\int_0^1 \lim_{n\to\infty} f_n(x)dx.
$$

Thus $(f_n)$ cannot converge uniformly (otherwise this example would contradict the uniform limit theorem).


Our first immediate application is to differentiation. Indeed, it is natural to ask at this point about swapping limits and differentiation.

(udiff')=
````{admonition} Theorem A.3 (Uniform limit theorem for differentiation)
Consider differentiable functions $f_n:[a,b]\rightarrow \mathbb{R}$. Suppose $(f_n)$ converges pointwise to a function $f$, each $f_n'$ is continuous and the sequence of derivatives $(f'_n)$ converges uniformly to a function $g$. Then $f$ is differentiable, and $f'=g$.
````

**Proof.**
By the fundamental theorem of calculus, for each $x\in [a,b]$

$$
f_n (x) = f_n (a) + \int_a^x f'_n (t)\ dt
$$

for each $n\in \mathbb{N}$.
So

$$
\lim_{n\to\infty} f_n (x) = \lim_{n\to\infty} f_n (a) +\lim_{n\to\infty} \int_a^x f'_n (t)\ dt.
$$

Since $(f_n)$ has pointwise limit $f$ on $[a,b]$, and $(f'_n)$ has uniform limit $g$ on $[a,x]$, using the uniform limit theorem for integrals, this gives

$$
f(x) = f(a) + \int_a^x g(t)\ dt
$$

for all $x\in [a,b]$. 
Applying the fundamental theorem of calculus, $f$ is differentiable and

$$
f'(x) =g(x)
$$

for all $x\in [a,b]$, as required.


Thus we can, {\emph{under suitable conditions}}, swap limits and differentiation.

(sec:exp)=
## A.3 $e$ and the exponential function

````{prf:definition} Exponential function
We define the {\em exponential function}, $\exp:\mathbb{R}\to\mathbb{R}$, by

$$
\exp (x) = \sum_{n=0}^\infty \frac{x^n}{n!}.
$$   
````

In {prf:ref}`eg:exp`, we proved that this series converges uniformly on bounded intervals, and that $\exp$ is continuous, infinitely differentiable and satisfies $\exp'(x)=\exp(x)$ for all $x\in\mathbb{R}$.

In MAS107, you saw\footnote{See Example 3.12 in the MAS107 lecture notes.} that the limit 

$$
\lim_{n\rightarrow \infty} \left( 1 + \frac{1}{n} \right)^n
$$

exists and the limit was taken as a definition of the number $e$.

We would like to prove that $\exp(x)=e^x$ for all $x\in\mathbb{R}$. This needs to be done in stages.

````{prf:proposition} 
:label: esum
Let $a,b\in \mathbb{R}$. Then

$$
\exp (a+b) = \exp (a) \exp (b).
$$

````

**Proof.**
Let $c\in \mathbb{R}$. Define $f:\mathbb{R}\to\mathbb{R}$ by

$$
f(x) = \exp (c+x) \exp (-x).
$$

Then by the product rule

$$
f'(x) = - \exp (c+x) \exp (-x) + \exp (c+x) \exp (-x) =0.
$$

So

$$
f(x) = \exp (c+x) \exp (-x) = A,
$$

where $A$ is constant. By the series definition, $\exp (0)=1$, so letting $x=0$, we get $A = \exp (c)$. So

$$
\exp (c+x) \exp (-x) = \exp (c).
$$

Now let $c=a+b$, $x=-b$, giving

$$
\exp (a+b) = \exp (a) \exp (b),
$$

as required.


Now we relate the exponential function to the limit expression for $e$.

````{prf:proposition}
Let $x\in \mathbb{R}$. Then

$$
\lim_{n\rightarrow \infty} \left( 1 + \frac{x}{n} \right)^n = \exp (x).
$$

````

**Proof.**
We will give the proof for $x\geq 0$. The case where $x<0$  can be treated similarly.
We write

$$
t_n(x)= \left( 1 + \frac{x}{n} \right)^n, \qquad s_n(x)=\sum_{k=0}^n \frac{x^k}{k!}.
$$

One can show that for each $x\in\mathbb{R}$, $(t_n(x))$ is a monotonic increasing and bounded sequence, so it is convergent. 

We want to show that $\lim_{n\to\infty} t_n(x)=\lim_{n\to\infty} s_n(x)$.


Using the binomial theorem,
\begin{align*} 
	t_n(x)
	&= \sum_{k=0}^n \left( \frac{n!}{k!(n-k)!} \right) \frac{x^k}{n^k}\\
	&=  \sum_{k=0}^n\frac{n(n-1)(n-2)\cdots (n-(k-1))}{n^k}\frac{x^k}{k!}\\
	&= \sum_{k=0}^n\left( 1- \frac{1}{n} \right) \left( 1- \frac{2}{n} \right) \cdots \left( 1- \frac{k-1}{n} \right)\frac{x^k}{k!}.
\end{align*}
Thus we see that $t_n(x)\leq s_n(x)$ for all $n,x$ and so 

$$
\lim_{n\to\infty} t_n(x)\leq \lim_{n\to\infty} s_n(x).
$$

On the other hand, we also have, for $n\geq m$,

$$
t_n(x)\geq \sum_{k=0}^m \left( \frac{n!}{n^k(n-k)!} \right) \frac{x^k}{k!}.
$$

So, using the algebra of limits,
\begin{align*}
\lim_{n\to\infty} t_n(x)\geq  \lim_{n\to\infty} \sum_{k=0}^m& \left( \frac{n!}{n^k(n-k)!} \right) \frac{x^k}{k!}\\
&= \sum_{k=0}^m\lim_{n\to\infty} \left( \frac{n!}{n^k(n-k)!} \right)  \frac{x^k}{k!}\\
&=\sum_{k=0}^m\lim_{n\to\infty} \left( 1- \frac{1}{n} \right) \left( 1- \frac{2}{n} \right) \cdots \left( 1- 		\frac{k-1}{n} \right)\frac{x^k}{k!}\\
&=\sum_{k=0}^m  \frac{x^k}{k!}=s_m(x).
\end{align*}
Now taking the limit as $m\to\infty$, we have

$$
\lim_{n\to\infty} t_n(x)\geq \lim_{m\to\infty} s_m(x).
$$

Thus $\lim_{n\to\infty} t_n(x)=\lim_{n\to\infty} s_n(x)$, as required.


In particular,

$$
\exp (1) = e = \lim_{n\rightarrow \infty} \left( 1+ \frac{1}{n} \right)^n.
$$


````{prf:proposition}
The number $e$ is irrational and $2< e\leq 3$.
````

**Proof.**
We first show that $2< e\leq 3$. %(This was already seen in semester 1 in Example 2.3.6, but let's check from the series point of view.) 
We have

$$
e = 1+ \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \cdots
$$

Certainly

$$
e> 1 + \frac{1}{1!} =2 .
$$

Now $n! >2^{n-1}$ for $n\geq 3$, so

$$
e=1+ \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \cdots \leq 1+1+ \frac{1}{2} + \frac{1}{4} +  \frac{1}{8} + \cdots =1+2=3 ,
$$

by the formula for the sum of a geometric series. 

Now we prove $e$ is irrational. We work by contradiction, so suppose that $e$ is rational. Since $e$ is positive, we then have $e= \frac{a}{b}$ where $a,b\in \mathbb{N}$.
So $be=a$, and so $b!e \in \mathbb{N}$.

\noindent But

$$
b!e = b!+ \frac{b!}{1!} + \frac{b!}{2!} + \cdots + \frac{b!}{b!} + \frac{b!}{(b+1)!} + \frac{b!}{(b+2)!}+ \cdots
$$

 Notice that the terms up to $b!/b!$ are all integers. Let
\begin{align*} 
R&= \frac{b!}{(b+1)!} + \frac{b!}{(b+2)!} + \cdots  \\
&= \frac{1}{b+1} + \frac{1}{(b+1)(b+2)} + \frac{1}{(b+1)(b+2)(b+3)} + \cdots 
\end{align*}
Notice that

$$
R< \frac{1}{b+1} + \frac{1}{(b+1)^2} + \frac{1}{(b+1)^3} + \cdots
$$

By the formula for the sum of a geometric series,

$$
0< R < \frac{1}{b+1} \times \frac{1}{1-\frac{1}{b+1}} = \frac{1}{b}.
$$

In particular, $R$ is not a natural number. Therefore $b!e$ is not a natural number.
But this is a contradiction. So $e$ is irrational.
