---
author: John Hammond
title: Section 3.9
mathjax: true
showbreadcrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

Antiderivatives
<!--more-->

### Definition
A function $F$ is called an antiderivative of a function $f$ on an interval if $F'(x) = f(x)$ for all $x$ on the interval.

### Examples: 
Consider the following three three derivatives: 

$\frac{d}{dx} (x^2 + 2) = 2x$
$\frac{d}{dx} (x^2 - 100) = 2x$
$\frac{d}{dx} (x^2 - 42) = 2x$

Each of the functions $x^2 + 2$, $x^2 - 100$ and $x^2 - 42$ are antiderivatives of  the function $2x$. 

### Example
Let's find an antiderivative of 
$$
f(x) = 5x^4 + 3x^2 + 1
$$

Try it first (reverse power rule) then check your answer:
{{<spoiler>}}
An answer is $F(x) = x^5 + x^3 + x + c$ where $c$ is some constant number.
{{</spoiler>}}

We call the most general antiderivative of $f$ on an interval $F(x) + c$ where $F$ is an antiderivative and $c$ is an arbitrary constant.

### Examples
Find the most general antiderivative of:
1. $g(x) = 2x^3 + 4x$
2. $f(x) = 2 \cos x$
3. $k(x) = \sec x \tan x$ 
3. $w(x) = 3\sqrt{x} - 2 \sqrt[3]{x}$

{{< youtube 2FCC6Ou1W-w >}}


### Particular Antiderivatives:

| Function       | Particular Antiderivative |
|----------------|---------------------------|
| $cf(x)$          | $cF(x)$                     |
| $f(x) + g(x)$    | $F(x) + G(x)   $            |
| $x^n \hspace{1em} (n \ne 1)$ | $\dfrac{x^{n+1}}{n+1}$      |
| $\cos x  $       | $\sin x              $      |
| $\sin x  $       | $-\cos x             $      |
| $\sec^2 x$       | $\tan x              $      |
| $\sec x \tan x$  | $\sec x              $      |


### Example

Find all functions $g$ for which 
$$
g'(x) = 5 \cos x + \dfrac{2x^4 - \sqrt{x}}{x}
$$

{{< youtube 2Soshr2GVWg >}}

## Differential Equations

If we know information about the derivative of a function (for example, we know how data is changing over time), we can find information about the function itself. An equation that involves derivatives of a function is called a **differential equation** and many of you will be taking an entire course on the subject. Here we'll start with some small examples.

### Example
Find $f$ if $f'(x) = x\sqrt{x}$ and $f(1) = 2$

{{< youtube eY_8Mh3L2tc >}}


### Example 
Find $f$ if $f''(x) = 12x^2 + 6x - 4$, $f(0) = 4$ and $f(1) = 1$. 

{{< youtube TYr7qeQpNiA >}}

### Gravity Example
For examples which involve things being dropped or thrown upward, we'll use the gravitational constant $g = 9.8$ m/s $^2$ in metric units or $g = 32$ ft/s $^2$ for imperial measurement. We will conventionally make it negative to denote acceleration *down* to Earth.

Here's an example:

A ball is thrown upward at a speed of 48 ft/s from the edge of a cliff 432 ft above the ground. Find its height above the ground $t$ seconds later. When does it reach its maximum height? When does it hit the ground?

{{< youtube oyWQVfNXANw >}}