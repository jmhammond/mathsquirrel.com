---
author: John Hammmond
title: section 4.4
mathjax: true
showbreadcrumbs: true
showtoc: true
tocopen: false
---

Section 4.4 Indefinite Integrals
<!--more-->

If $f$ is continuous on $[a, b]$ and $F$ is an antiderivative of $f$, 
- the  **definite integral** $\displaystyle \int_a^b f(x) \\, dx = F(b) - F(a)$ 
   is a *number*. We find the *definite* exactly value.
- the **indefinite integral** is a *function* or a family of functions. 
   $$
\int f(x) \\, dx = F(x) + C
   $$
   where $C$ is some constant. 

### Why $+C$ ? 

Consider the following derivatives:
- $\displaystyle \dfrac{d}{dx} \left( \frac{x^3}{3} + 1 \right) = x^2$
- $\displaystyle \dfrac{d}{dx} \left( \frac{x^3}{3} - 7 \right) = x^2$
- $\displaystyle \dfrac{d}{dx} \left( \frac{x^3}{3} + 42 \right) = x^2$
- $\displaystyle \dfrac{d}{dx} \left( \frac{x^3}{3} + C \right) = x^2$ where $C$ is a constant. 

...

since the derivative of that family of functions is always $x^2$, any of them is an antiderivative of $x^2$.  

### Many, many integrals

- $\displaystyle\int cf(x)\\,dx=c \int f(x)\\, dx$                     
- $\displaystyle\int(f(x) + g(x))\\, dx=\int f(x)\\, dx + \int g(x)\\, dx $            
- $\displaystyle\int k \\,dx=kx + C$ 
- $\displaystyle\int x^n \\, dx  =\dfrac{x^{n+1}}{n+1} + C$      if $n \ne -1$  
- $\displaystyle\int \cos x \\, dx  =\sin x     +C         $      
- $\displaystyle\int \sin x  \\,dx =-\cos x      +C       $      
- $\displaystyle\int \sec^2 x \\, dx=\tan x       +C       $      
- $\displaystyle\int \sec x \tan x\\, dx=\sec x     +C         $      

Any time you integrate, you can always check your answer by differentiating! 

### Example

Evaluate the integral
$$
\int 15x^4 - \cos x \\, dx
$$

{{< youtube rsiD9WOTO4A >}}

### Example

Evaluate the integral
$$
\int_0^2 x^3 - 5x  \\, dx
$$

{{< youtube YskwLedoL2k >}}

### Example

Find the area under the $y=\sin x$ between $-\pi/2$ and $\pi/2$

{{< youtube SgnqdvTvCjs >}}

### Example 

Evaluate the integral
$$
\int \sec t (\sec t + \tan t) \\, dt
$$

{{< youtube EjzkOZZXQn0 >}}