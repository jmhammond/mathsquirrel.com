---
author: John Hammmond
title: section 6.2
mathjax: true
showbreadcrumbs: true
showtoc: true
tocopen: false
---

Section 6.2 Exponential Functions
<!--more-->

An exponential function is a function in which the variable is in the exponent. $y = a^x$ where $a > 0$. Remember that exponentiation is repeated multiplication. That is,

$a^n = a\cdot a \cdot a \cdot \cdots \cdot a$ where $a$ is multiplied $n$ times. 

## Exploring exponential graphs

[Play around with this Geogebra activity](https://www.geogebra.org/m/YK6pcUsB) - move the sliders on the right (they slide up and down) to change the values of the function and see what changes those make to the graph.

https://www.geogebra.org/m/YK6pcUsB

## Recall: Rules of Exponents
If $a > 0$ and $a \ne 1$:
1.  $a^{x+y} = a^x a^y$
2. $a^{x-y} = \frac{a^x}{a^y}$
3. $(a^x)^y = a^{xy}$
4. $(ab)^x = a^x b^x$

## Calculus facts for exponential functions:
If $a > 0$ and $a \ne 1$
1. If $a >1$, then: 
   a. $f(x) = a^x$ is an increasing function.
   b. $\displaystyle \lim_{x\to -\infty} a^x = 0$
   c. $\displaystyle \lim_{x \to \infty} a^x = \infty$
2. If $0 < a < 1$, then: 
   a. $f(x) = a^{x}$ is a decreasing function. 
   b. $\displaystyle \lim_{x\to -\infty} a^x = \infty$
   c. $\displaystyle \lim_{x \to \infty} a^x = 0$


### Example
Find the limit $\displaystyle \lim_{x\to \infty} 3^{-x} + 1$

Solution:
{{<spoiler>}}
$\begin{align*}
 \lim_{x\to \infty} 3^{-x} + 1 &= \lim_{x\to \infty} \left(\frac13\right)^x + 1 \\ &= 0 + 1 \\ &= 1
\end{align*}$
{{</spoiler>}}


## The Natural Exponential Function

{{< figure src="6.2.exponential.jpeg" alt="">}}
Pictured here in green is $y=2^x$, in blue is $y=3^x$, and sitting between them in red is $y = e^x$. 

Any exponential function $f(x) =a^x$ has the point $f(0) = 1$.  However, it becomes very interesting to consider the particular exponential function that has the property that **the slope at $(0,1)$ is itself 1**. That is, $f'(0) = 1$ as well. We define this function to be **the natural exponential function** and call its base $e$:

Define $e^x$ to be the natural exponential function. It has the following remarkable property:

$$
\dfrac{d}{dx} e^x = e^x
$$

... it is its own derivative.

Pairing with the chain rule:

$$
\frac{d}{dx} e^u = e^u \dfrac{du}{dx}
$$

### Example

Find the derivative of $y = e^{2x} \cos x$

{{< youtube D1Xgx6NNFcs >}}


### Integration of $e^x$

Since $\dfrac{d}{dx} e^x = e^x$, that gives rise to its integral: 
$$
\int e^x \\, dx = e^x + C
$$

### Example
Evaluate $\int x^2 e^{x^3} \\, dx$

{{< youtube o1gzIXCOY8E >}}