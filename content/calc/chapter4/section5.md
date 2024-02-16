---
author: John Hammmond
title: section 4.5
mathjax: true
showbreadcrumbs: true
showtoc: true
tocopen: false
---

Section 4.5 Substitution
<!--more-->

By the way, I may call this variously "u-substitution" (which  most people do) or "basic substitution." When I call it basic, I don't mean to be rude, it's just that I'm teaching calc 2 at the same time, and in that class I've been saying "this is a basic calc 1 substitution" a lot.

## Recall: The Chain Rule

Recall: If $h(x) = f(g(x))$, then
$$
h'(x) = f'(g(x)) g'(x)
$$

Since integration is the inverse operation of differentiation, let's integrate both sides with respect to x: 

$\begin{align*} \int h'(x) \\, dx &= \int f'(g(x)) g'(x)\\, dx \\ &= f(g(x)) + C \end{align*}$

Here I'm underlining that part involving the composed inner function to really drive home the observation:

$$
 \int f'(\underline{g(x)}) \underline{g'(x)}\\, dx = f(\underline{g(x)}) + C 
$$

## Integration by the Substitution Rule 

### Example

Evaluate the integral
$$
\int 2x \sqrt{1+x^2} \\, dx
$$

**Solution**
We identify that there is an outer function and an inner function in a composition. We're going to substitute $u = 1+x^2$.  Then, using differentials, we'll write
$$
du = 2x \\, dx
$$

Then our original integral will become:
$\begin{align*}
\int 2x \sqrt{1+x^2} \\, dx &= \int \sqrt{1+x^2}  2x \\, dx \\ &= \int \sqrt{u} \\, du \\ &= \int u^{1/2} \\, du \\ &= \frac{u^{3/2}}{3/2} + C \\
&= \frac{2 u^{3/2}}{3} +C 
\end{align*}$

but our original integral was defined in terms of $x$ not $u$, so we substitute back to find 
$$
\int 2x \sqrt{1+x^2} \\, dx = \frac{2 (1+x^2)^{3/2}}{3} +C
$$

Did we get it right? You can *always* check your answer by differentiating!  [Here I'm asking WolframAlpha to perform the calculation](https://www.wolframalpha.com/input/?i=differentiate+%5Cfrac%7B2+%281%2Bx%5E2%29%5E%7B3%2F2%7D%7D%7B3%7D+%2BC) to check my work.

### Example

Evaluate $\displaystyle \int x \sin (x^2) \\,dx$

{{< youtube 7NRvuFrZcBY >}}

### Example

Evaluate $\displaystyle \int  \sqrt{1 - 2x}  \\,dx$

{{< youtube DzwO0pMCxXY >}}

### Example

Evaluate $\displaystyle \int \frac{x}{\sqrt{x^2 - 1}} \\, dx $ 
{{< youtube ZHpAMS4GnkU >}}



## Definite Integrals and substitution 

If $g'$ is continuous on $[a, b]$ and $f$ is continuous on the range of $g$ and $u=g(x)$, then: 
$$
\int_a^b f(g(x))g'(x)\\, dx = \int_{g(a)}^{g(b)} f(u) \\, du
$$

that is, when we change the variable via a substitution, we also change the bounds. Let's see some examples.

### Example
Evaluate $\displaystyle \int_1^2 \dfrac{dx}{(1-3x)^2}$.

{{< youtube R_qIPhRWoWk >}}

### Example
Evaluate $\displaystyle \int_0^4 x \sqrt{x^2 + 1}\\, dx$.

{{< youtube LWUuCUsmmfY >}}