---
title: 'Notes_Misc_Math'
permalink: /notes/notes_misc_math/
tags:
  - notes
  - math
---

- [1. Pade Approximation](#1-pade-approximation)
- [2. Gamma Function Derivation](#2-gamma-function-derivation)
## 1. Pade Approximation
## 2. Gamma Function Derivation

# Padé Approximation

Constructing $\left[N/M\right]$ Padé approximants for $f\left(x\right)$
$$P_{M}^{N}\left(x\right)=\frac{\stackrel[i=0]{N}{\sum}A_{i}x^{i}}{\stackrel[j=0]{M}{\sum}B_{j}x^{j}}$$

::: algorithm
1.  Find the Taylor series for $f\left(x\right)$ $$\begin{aligned}
    f\left(x\right) & \approx f\left(0\right)+xf'\left(0\right)+\frac{x}{2!}f''\left(0\right)+\cdots+\frac{x^{n}}{n!}f^{\left(n\right)}\left(0\right)\nonumber \\
     & \approx c_{0}+c_{1}x+\cdots c_{N+M}x^{N+M}\label{eq:Talyor}
    \end{aligned}$$

2.  Equate $\left(1\right)$ with
    $$\left(1\right)=\frac{A_{0}+A_{1}x+\cdots+A_{N}x^{N}}{B_{0}+B_{1}x+\cdots+B_{M}x^{M}}$$

3.  Rearrange $\left(1\right),\left(2\right)$ and WLOG, let $B_{0}=1$
    $$A_{0}+A_{1}x+\cdots+A_{N}x^{N}=\left(1+B_{1}x+\cdots+B_{M}x^{M}\right)\left(c_{0}+c_{1}x+\cdots c_{N+M}x^{N+M}\right)$$

4.  Solve the coefficients by (suppose $N<M$) $$N+1\begin{cases}
    A_{0} & =c_{0}\\
    A_{1} & =c_{1}+B_{1}c_{0}\\
    A_{2} & =c_{2}+B_{1}c_{1}+B_{2}c_{0}\\
    \vdots & =\qquad\vdots\\
    A_{N} & =c_{N}+B_{1}c_{N-1}+\cdots+B_{N}c_{0}
    \end{cases}\label{eq:pade1}$$ $$M-1\begin{cases}
    0 & =c_{N+1}+B_{1}c_{N}+\cdots+B_{N}c_{1}\\
    0 & =c_{N+2}+B_{1}c_{N+1}+\cdots+B_{N+1}c_{1}\\
    \vdots & =\qquad\vdots\\
    0 & =c_{N+M}+B_{1}c_{N+M-1}+\cdots+B_{N+M-1}c_{1}
    \end{cases}\label{eq:pade2}$$
:::

-   In $\left(\ref{eq:pade1}\right)$, $\left(\ref{eq:pade2}\right)$ make
    sure the subscripts sum to the same degree

::: rem*
* 1*. Problems with Taylor series
:::

-   Taylor series often cannot extrapolate for very long before rapidly
    diverging, Padé approximation often follows the function more
    closely for longer.

#### ![image](\string"/Users/weichen/Desktop/Screen Shot 2022-02-06 at 8.52.10 PM\string".eps){width="100%"} 

# Lagrange Interpolation

The idea is to create a set of Lagrange basis polynomials
$l_{i}\left(x\right)$ such that each polynomial equals $1$ at node $i$
and $0$ otherwise, then multiply $y_{i}$ and add them together.

![image](Lagrange_polynomial){width="1\\columnwidth"}

::: algorithm
1.  Let $$l_{i}\left(x\right)=\begin{cases}
    1 & x=x_{i}\\
    0 & x=x_{j},j\neq i
    \end{cases}$$

2.  For a set of nodes, $x_{i},i=0,1,2,\cdots,n$, we have $n+1$ Lagrange
    basis polynomials
    $$l_{i}\left(x\right)=\stackrel[j=0,j\neq i]{n}{\prod}\frac{\left(x-x_{j}\right)}{\left(x_{i}-x_{j}\right)}$$

3.  Lagrange polynomials are
    $$L\left(x\right)=\stackrel[i]{n}{\sum}y_{i}l_{i}$$
:::

::: rem*
* 2*. $L\left(x\right)$ is of order $n$ and is the lowest order
polynomials which interpolate nodes $x_{i},i=0,1,2,\cdots,n$.
:::

# Gamma Function Derivation

The Gamma function expands $n!$ from $\mathbb{\mathbb{Z}}^{+}$ to
$\mathbb{R}^{+}$, where $$\begin{aligned}
\Gamma\left(n\right) & =\stackrel[0]{\infty}{\int}x^{n-1}e^{-x}dx\\
 & =\left(n-1\right)!
\end{aligned}$$

::: proof
*Proof.* Gamma Function Derivation

$$e^{at}=\stackrel[0]{\infty}{\sum}\frac{a^{n}t^{n}}{n!}\label{eq:gamma1}$$
and $$\begin{aligned}
\stackrel[0]{\infty}{\int}e^{-st}e^{at}dt & =\stackrel[0]{\infty}{\int}e^{\left(a-s\right)t}dt\nonumber \\
 & =\frac{1}{s-a}\nonumber \\
 & =\frac{1}{s}\cdot\frac{1}{1-\frac{a}{s}}\nonumber \\
 & =\frac{1}{s}\stackrel[0]{\infty}{\sum}\left(\frac{a}{s}\right)^{n}\label{eq:gamma2}
\end{aligned}$$ combining $\left(\ref{eq:gamma1}\right)$ and
$\left(\ref{eq:gamma2}\right)$ $$\begin{aligned}
\stackrel[0]{\infty}{\int}e^{-st}e^{at}dt & =\stackrel[0]{\infty}{\int}e^{-st}\stackrel[0]{\infty}{\sum}\frac{a^{n}t^{n}}{n!}dt\nonumber \\
\Rightarrow\stackrel[0]{\infty}{\sum}\frac{a^{n}}{n!}\stackrel[0]{\infty}{\int}t^{n}e^{-st}dt & =\frac{1}{s}\stackrel[0]{\infty}{\sum}\left(\frac{a}{s}\right)^{n}\nonumber \\
\Rightarrow\frac{a^{n}}{n!}\stackrel[0]{\infty}{\int}t^{n}e^{-st}dt & =\frac{a^{n}}{s^{n+1}}\nonumber \\
\Rightarrow\frac{1}{n!}\stackrel[0]{\infty}{\int}t^{n}e^{-st}dt & =\frac{1}{s^{n+1}}\label{eq:gamma3}
\end{aligned}$$ now let $x=st$ , then $t=\frac{x}{s}$ and
$dt=\frac{1}{s}dx$, so $$\begin{aligned}
\stackrel[0]{\infty}{\int}t^{n}e^{-st}dt & =\stackrel[0]{\infty}{\int}\frac{x^{n}}{s^{n}}e^{-x}\cdot\frac{1}{s}dx\\
 & =\stackrel[0]{\infty}{\int}\frac{x^{n}}{s^{n+1}}e^{-x}dx
\end{aligned}$$ hence $\left(\ref{eq:gamma3}\right)$ is
$$\begin{aligned}
\frac{1}{n!}\stackrel[0]{\infty}{\int}\frac{x^{n}}{s^{n+1}}e^{-x}dx & =\frac{1}{s^{n+1}}\\
\Rightarrow\stackrel[0]{\infty}{\int}x^{n}e^{-x}dx & =n!
\end{aligned}$$ ◻
:::

# Lagrange Theorem (Group Theory)

# Riemann Rearrange Theorem

# Wilson's theorem

For $n\in\mathbb{Z}$ and $n>1$,

$$\left(n-1\right)!\equiv-1\left(mod\:n\right)$$

if and only if $n$ is prime

# misc

## ome equation

$$\frac{\left(n+4\right)!}{n!}+1=a^{2}$$

where $a=n^{2}+3n+1$

## Fermat's little theorem

Theorem
$$a\equiv b\:\left(mod\:p\right)\Rightarrow a^{n}\equiv b^{n}\:\left(mod\:p\right)$$

proof:

Let $a=Cp+b$, then all terms contains $Cp$ is divisible by $p$
$$\begin{aligned}
a^{n}\:\left(mod\:p\right) & \equiv\left(Cp+b\right)^{n}\:\left(mod\:p\right)\\
 & \equiv\stackrel[i=0]{n}{\sum}\begin{pmatrix}n\\
i
\end{pmatrix}\left(Ap\right)^{n-i}b^{i}\:\left(mod\:p\right)\\
 & \equiv b^{n}\:\left(mod\:p\right)
\end{aligned}$$

Note that $b$ is the remainder of $a|p$, thus it also can be written as
$$a^{n}\:\left(mod\:p\right)\equiv\left(a\:\left(mod\:p\right)\right)^{n}\:\left(mod\:p\right)$$

this essentially is saying that for a large number $a$, eg.
$$2222^{5555}\:\left(mod\:7\right)\equiv\left(2222\:\left(mod\:7\right)\right)^{5555}\:\left(mod\:7\right)\equiv3^{5555}\:\left(mod\:7\right)$$

this reduce the magnitude of base $a$ in calculation

Furthermore, using Fermat's little theorem ($p$ is prime here)
$$a^{p-1}\equiv1\:\left(mod\:p\right)$$

combing with the above property, $$\begin{aligned}
a^{C\left(p-1\right)} & \equiv1^{C}\:\left(mod\:p\right)\\
 & \equiv1\:\left(mod\:p\right)
\end{aligned}$$

the magnitude of exponent $n$ can also be reduced.

Suppose $n\equiv m\:\left(mod\:\left(p-1\right)\right)$ or
$n\equiv C\left(p-1\right)+m$, then $$\begin{aligned}
a^{n}\:\left(mod\:p\right) & \equiv a^{m}a^{C\left(p-1\right)}\:\left(mod\:p\right)\\
 & \equiv a^{m}1^{C}\:\left(mod\:p\right)\\
 & \equiv a^{m}\:\left(mod\:p\right)
\end{aligned}$$

thus, the above example can be further calculated as $$\begin{aligned}
3^{5555}\:\left(mod\:7\right) & \equiv3^{5555\:\left(mod\:6\right)}\:\left(mod\:7\right)\\
 & \equiv3^{5}\:\left(mod\:7\right)\\
 & \equiv5\:\left(mod\:7\right)
\end{aligned}$$
