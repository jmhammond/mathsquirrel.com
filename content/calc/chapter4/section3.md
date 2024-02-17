---
author: John Hammmond
title: section 4.3
mathjax: true
showbreadcrumbs: true
showTableOfContents: true
tocopen: false
---

Section 4.3 The Fundamental Theorem of Calculus
<!--more-->

The Fundamental Theorem of Calculus is conveyed in two parts. Just like subtraction is the inverse of addition, and division is the inverse of multiplication, the Fundamental Theorem tells use that integration is the inverse of differentiation. 


## Integral as a function

In the previous section, we say the *definite* integral, which evaluates to a number. We can interpret that number as the area under the function between endpoints, for example. 

Consider the following integral with its upper bound replaced *by a variable*:

$$
F(x) = \int_a^x f(t) \\, dt
$$

The value of $F(x)$ will tell you the area under the curve $f(t)$ on the interval $[a, x]$ with $x \ge a$. 


## The Fundamental Theorem of Calculus, part 1
(The core idea: the derivative is the inverse of the integral)

If $f$ is a continuous function on $[a, b]$, then the function $F$ defined by 
$$
F(x) = \int_a^x f(t) \\, dt \hspace{2em} a \le x \le b
$$
is continuous on $[a, b]$, and differentiable on $(a, b)$ and $F'(x) = f(x)$

**Repeating for emphasis**:
$$
\dfrac{d}{dx} \int_a^x f(t) \\, dt = f(x)
$$
The derivative of an integral, with respect to its variable upper limit is the integrand evaluated at the upper limit.

### Example
Find the derivative of the function  $\displaystyle g(x) = \int_a^x \sqrt{1-t^2}\\, dt$

{{<spoiler>}}
$g'(x) = \sqrt{1-x^2}
{{</spoiler>}}

### Example
Find  $\displaystyle \frac{d}{dx} \int_1^{x^4} \sec t\\, dt$
*Hint*: use the chain rule

{{<spoiler>}}
$\begin{align*}  \frac{d}{dx} \int_1^{x^4} \sec t\\, dt &= \sec(x^4) \cdot \dfrac{d}{dx}(x^4) \\ 
&= 4x^3 \sec(x^4) \end{align*}$
{{</spoiler>}}

### Example
Find the derivative of $\displaystyle h(x)  = \int_x^a t \\, dt$
*Hint*: Look at the order of the bounds.

{{<spoiler>}}
The FTC, part 1 requires that the *upper* bound be the variable. Using properties of the integral, we write: 
$\begin{align*} \dfrac{d}{dx} \int_x^a t \\, dt &= \dfrac{d}{dx}\left( - \int_a^x t \\, dt \right) \\ &= - \dfrac{d}{dx} \int_a^x t \\, dt \\  &=  -x \end{align*}$
{{</spoiler>}}

## The Fundamental Theorem of Calculus, part 2
(The core idea: the integral is the inverse of the derivative)

If $f$ is continuous on $[a, b]$, then 
$$
\int_a^b f(x) \\, dx = F(b) - F(a)
$$
where $F$ is any antiderivative of $f$, that is, a function such that $F' = f$


### Example
Evaluate the integral $\displaystyle \int_{-1}^2 x^3\\, dx$

**Solution**
Since $\dfrac{x^4}{4}$ is an antiderivative of $x^3$, we apply the fundamental theorem of calculus to find:
$\begin{align*} \int_{-1}^2 x^3\\, dx &= \left. \dfrac{x^4}{4} \right|_{x=-1}^2 \\ &= \left(\frac{2^4}{4}\right) - \left(\frac{(-1)^4}{4}\right) \\ &= \frac{16}{4} - \frac{1}4 \\ &= \frac{15}{4} \end{align*}$


### Comment on notation

If $F$ is an antiderivative of $f$, then we write:

$$
\int_a^b f(x) \\, dx =  F(x) \Big|_{x = a}^b
$$

where the 

$$
F(x)\Big|_{x = a}^{b} 
$$

means $F(b) - F(a)$.  Plug in upper value, plug in lower value, and subtract them.

Our textbook omits the $x=\dots$ part on the lower bound, but I do it and encourage you as well. Later it will be very beneficial when we're trying to keep track of what the actual variable of integration is.


### Example 
Evaluate the integral $\displaystyle \int_{0}^3 x^3\\, dx$

{{< youtube xv7qTqWfp-0 >}}

### Example 
Find the area under the sine curve between 0 and $\pi$.

{{< youtube BaprYujR0Hs >}}


### Example
What is wrong with this work? 
$$
\int_{-1}^3 \frac{1}{x^2} \\, dx = \left. \dfrac{x^{-1}}{-1} \right|_{x=-1}^3 = -\dfrac13 - 1 = -\dfrac43 
$$

*Hint*: Is the integrand continuous?

{{<spoiler>}}
Because the integrand is positive, the integral should also be positive! Since it's negative, that suggests a problem. 

Notice that at $x=0$, the integrand is discontinuous. The fundamental theorem of calculus only applies to continuous functions, so this work is totally incorrect! [^1] 

[^1]: We'll learn about how to deal with 'improper integrals' in calculus 2.
{{</spoiler>}}
