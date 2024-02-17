---
author: John Hammmond
title: section 6.4
mathjax: true
showbreadcrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

Calculus of Logarithms
<!--more-->

## Derivative of the Logarithm

Remember that we said the previous post that $\displaystyle \ln(x) = \int_1^x \frac1t \\, dt$?
Use the Fundamental Theorem of Calculus do see that 
$
\begin{align*}
\dfrac{d}{dx} \ln x &= \dfrac{d}{dx} \int_1^{x} \frac1t \\, dt \\
&= \frac1x
\end{align*} $

Thus, $\dfrac{d}{dx} \ln x = \dfrac1x$ . 

### Example 
Compute the derivative $\dfrac{d}{dx} \ln (\cos x)$.
{{< youtube o_bBd3I7dTM >}}

### Example 
Compute the derivative $\dfrac{d}{dx} \ln (\sqrt x)$.
{{< youtube UosJ0UAuZns >}}


## The Natural logarithm as an indefinite integral

Our previous definition of the natural logarithm was as a definite integral, but we can also evaluate the *indefinite* integral:

$$
\int \frac1x \\, dx = \ln |x| + C  \hspace{1em} \text{for } x\ne 0
$$

Notice the absolute value bars on the logarithm! They are essential since the domain of the logarithm requires a positive number!

### Example

Evaluate the integral $\displaystyle \int \dfrac{x}{x^2 - 1} \\, dx$

{{< youtube DIQ1FXeQxAM >}}

### Example

We can now find the antiderivative of more trig functions! Find the antiderivative of $\tan x$ and $\cot x$

{{< youtube MYIvom66Ksk >}}

Check your work:
{{<spoiler>}}
$\int \tan x \\, dx = \ln | \sec x| +C$ and $\int \cot x \\,dx = \ln | \sin x | + C$
{{</spoiler>}}



## General Logarithmic functions

Recall the change of base formula 
$$
\log_b x = \frac{\ln x}{\ln b}
$$

Differentiating both sides, we arrive at the following derivative formula:

$$
\dfrac{d}{dx} \log_b (x) = \dfrac{d}{dx} \frac{\ln x}{\ln b} = \dfrac{1}{x \ln b}
$$

And equivalently, we have the following formula for the derivatives of general logarithmic functions:

$$
\dfrac{d}{dx} b^x = b^x \ln b
$$

**Note** It's important to note that the derivative of an exponential function always has a factor of the logarithm of the base. That is, the slope of the line tangent to the curve is directly related to the logarithm of the base! [^1]

## Logarithmic Differentiation

Logarithms always take multiplication and turn it to an addition problem. This makes complicated calculations simpler. We can apply this to differentiation as well!

Process:
1. Take natural logarithms of both sides of an equation $y=f(x)$ and use the properties of logarithms to simplify.
2. Differentiate implicitly with respect to $x$.
3. Solve the resulting equation for $y'$.

### Example

Find the derivative of $y = x^x$

**VIDEO HERE**

### Example
Find the derivative of $y= (\sin x)^{\ln x}$

**VIDEO HERE**


### Fact / Example
The natural exponential function is an infinite limit:  
$$
e^x = \displaystyle \lim_{n\to \infty} \left(1 + \dfrac{x}{n}\right)^n
$$

I'll show why here, but you can also just glance over it. Don't worry if you don't follow everything. The result is the important part. 

Below, we put together the limit definition of the derivative along with continuity, properties of the logarithm, and the exponential. It's a simple-looking statement that uses all of the class
{{<spoiler>}}
First, recall the limit definition of the derivative: 
$f'(x) = \lim_{h \to 0} \dfrac{f(x+h) - f(x)}{h}$

Let $f(x) = \ln x$, then $f'(x) = 1/x$, which gives the following:

$\begin{align*}
f'(x) &= \lim_{h \to 0} \dfrac{f(x+h) - f(x)}{h} \\
\frac1x &= \lim_{h \to 0} \dfrac{\ln(x + h) - \ln(x)}{h} \\
&= \lim_{h\to 0} \dfrac{\ln\left(\frac{x+h}{x}\right)}{h} \\
&= \lim_{h \to 0} \frac1h \ln\left(\frac{x+h}{x}\right) \\
&= \lim_{h \to 0} \ln\left(\frac{x+h}{x}\right)^{1/h} \\
\frac1x &= \lim_{h \to 0} \ln\left(1 + \frac{h}{x}\right)^{1/h}
\end{align*}$
Now, letting $t = \frac1x$, we get: 
$$
t = \lim_{h \to 0} \ln\left(1 + ht \right)^{1/h}
$$
and replacing $\frac{1}h = n$, then when $h \to 0$ we have $n \to \infty$, which gives us
$$
t = \lim_{n \to \infty} \ln\left(1 + \frac{t}{n} \right)^{n}
$$

Almost there. Now we write $e^t$ by replacing $t$ with what you see above: 

$\begin{align*}
e^t &= e^{ \lim_{n \to \infty} \ln\left(1 + \frac{t}{n} \right)^{n}} \\ 
&= \lim_{n\to \infty} e^{ \ln\left(1 + \frac{t}{n} \right)^{n}}  \hspace{1em}\text{ since e is continuous} \\
&= \lim_{n\to \infty} \left(1 + \frac{t}{n} \right)^{n} \hspace{1em} \text{ inverse property} \\
\end{align*}$

and so, $e^t =  \lim_{n\to \infty} \left(1 + \frac{t}{n} \right)^{n}$ for all $t$. That's pretty darned amazing. 

... by the way, if that was interesting to you, consider taking a few more math classes :slight_smile: 
{{</spoiler>}}



**VIDEO HERE**



## Go forth and do math!
The example which shows that we can actually think of the natural exponential function as the limit $e^x = \lim_{n\to \infty} (1+x/n)^n$ is a mind-blowing way to end the course material.

🎉 At this point, we have covered every piece of new material in the course :confetti_ball: . Go forth and do homework, ask questions, and such! I'll talk to you in the live class :slight_smile: 





[^1]: and if the base is $e$, the slope of $(0,1)$ is 1, which is *sweet*!