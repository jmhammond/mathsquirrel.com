---
author: John Hammmond
title: section 5.5
mathjax: true
showbreadcrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

Average Value of a Function
<!--more-->

### Recall Averages

If we want to find the average of a dataset: 
$$
\{ 3, 5, 2, 9, 0,  8, 1 \}
$$
we add together all the elements and divide by the total number of them: 
 $$
\dfrac{3+ 5+ 2+ 9+ 0+  8+ 1}{7} = 4
$$
... turns out our average of my set of made up numbers is 4. Nice. 

## Continuous averages

... what instead of discrete numbers, I have a continuous set of values. We still want to *add together* all the values and *divide by* then size of that set. How can we do this? Integration is repeated addition! Length of the interval is the size of the set! 

### Average Value of a Function
If $f$ is a continuous function on an interval $[a, b]$, we define the average value of $f$ on that interval to be:
$$
f_{\text{ave}} = \dfrac{1}{b-a} \int_a^b f(x)\\, dx
$$

**Notation note** The text uses $f_{\text{ave}}$ but I like to abbreviate average by "avg," so if you see me write $f_{\text{avg}}$, I mean the exact same thing. It's my fave way of writing it. 

### Example

Find the average value of $\cos x$ on the interval $[0, \pi/2]$.

Solution:
{{<spoiler>}}
$\begin{align*}
f_\text{ave} &= \dfrac{1}{b-a} \int_a^b f(x) \, dx \\
&= \dfrac{1}{\frac\pi2 - 0} \int_0^{\pi/2} \cos x\, dx \\
&= \frac2\pi (\sin x) \Big|_{x=0}^{\pi/2} \\
&= \frac2\pi (\sin (\pi/2) - \sin 0) \\
&= \frac2\pi 
\end{align*}$
{{</spoiler>}}



### Example

Find the average value of the function $\sin x$ between $0$ and $\pi$.

Solution:
{{<spoiler>}}
$\begin{align*}
f_\text{ave} &= \dfrac{1}{b-a} \int_a^b f(x) \, dx \\
&= \dfrac{1}{\frac\pi - 0} \int_0^{\pi} \sin x\, dx \\
&= \frac1\pi (-\cos x) \Big|_{x=0}^{\pi} \\
&= \frac1\pi (-\cos (\pi) - -\cos 0) \\
&= \frac1\pi (-(-1) + 1)\\
&= \frac{2}{\pi}
\end{align*}$
{{</spoiler>}} 

### Example
Find the average value of $f(x) = x^2$ between -2 and 2. 

Solution:
{{<spoiler>}}
$\begin{align*}
f_\text{ave} &= \dfrac{1}{b-a} \int_a^b f(x) \\, dx \\
&= \dfrac{1}{2 - (-2)} \int_{-2}^2 x^2 \\, dx \\
&= \dots\\
&= \frac43
\end{align*}$
{{</spoiler>}} 


## Mean Value Theorem for Integrals
We had a Mean Value Theorem for derivatives which told us that *there is a point* where the function attains its mean/average value. Here we get the same for integrals:


If $f$ is continuous on $[a,b]$ then there exists a number $c$ in $[a, b]$ so that
$$
f(c) = \dfrac{1}{b-a} \int_a^b f(x)\\, dx
$$

or equivalently,
$$
\int_a^b f(x) \\, dx = f(c) (b-a)
$$

### Example 
Find the values $c$ which satisfy the mean value theorem of integrals for $f(x) = x^2$ on the interval $[-2, 2]$. 

Solution:
Note: Above we found $f_{\text{ave}} = \frac43$. 
{{<spoiler>}}
$f(c) = f_{\text{ave}} = \frac{4}{3}$
so that $c^2 = \frac43$ or $c= \pm \frac{2\sqrt{3}}{3}$
{{</spoiler>}}

### Example

Find all values $c$ which satisfy the mean value theorem for integrals for the function $f(x) = \sqrt{x}$ on $[0,4]$

{{< youtube 36QDAalj7u8 >}}