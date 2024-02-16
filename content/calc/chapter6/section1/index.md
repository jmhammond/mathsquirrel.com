---
author: John Hammmond
title: section 6.1
mathjax: true
showbreadcrumbs: true
showtoc: true
tocopen: false
---

Section 6.1 Inverse Functions
<!--more-->

If you're enrolled in Math/CS 321, see this footnote[^1]


### Recall from algebra/precalc/trig:

- A function $f$ is called **one-to-one** if it never takes the same value twice, that ifs $f(a) \ne f(b)$ if $a \ne b$. 
- **The Horizontal Line Test** A function is one-to-one if and only if no horizontal line intersects a graph more than once. 

## Inverse Functions

Let $f$ be a one-to-one function with domain $A$ and range $B$, then its inverse function, $f^{-1}$ has domain $B$ and range $A$ and is defined by
$$
f^{-1}(y) = x \iff f(x) = y
$$
for any $y$ in $B$.

- the domain of $f$ is the range of $f^{-1}$
- the range of $f$ is the domain of $f^{-1}$

that is, the $x$'s become the $y$'s and vice versa.

##  Finding the inverse of a function: the process:
1. Write $y=f(x)$
2. Switch the roles of $x$ and $y$ (swap the variables)
3. Solve this new equation for the new $y$.
4. Write $f^{-1}$ as this function, $y=f^{-1}(x)$

### Example

Find the inverse of $f(x) = x^3 - 5$, then graph both $f$ and $f^{-1}$ on the same axes.

**Answer**
{{<spoiler>}}
Do some algebra and confirm $f^{-1} = \sqrt[3]{x+5}$
{{< figure src="6.1.inverse1.jpeg" alt="">}}
{{</spoiler>}}

### Example

Find the inverse of $f(x) = \sqrt{x - 1}$, then graph both $f$ and $f^{-1}$ on the same axes.

**Answer**
{{<spoiler>}}
Do some algebra and confirm $f^{-1} = x^2 + 1$. **Note** Because the range of $f$ is $[0, \infty)$, the domain of $f^{-1}$ is only $[0,\infty)$, meaning it's only the right-half of the parabola! (otherwise it's not one-to-one).
{{< figure src="6.1.inverse2.png" alt="">}} 
{{</spoiler>}}

**Takeaway**: Inverse function graphs are symmetric over the line $y=x$. 


## The derivative of inverse functions
If $f$ is a one-to-one function with inverse function $f^{-1}$, and $f'(f^{-1}(a))\ne 0$, then the inverse function is differentiable at $a$ and:
$$
(f^{-1})'(a)=\frac{1}{f'(f^{-1}(a))}
$$

### Example

Consider $f(x) = x^2$ on the restricted domain $[0, \infty)$. 
1. Show that $f$ has an inverse and that domain.
2. Find $(f^{-1})'(1)$ using the above formula.
2. Find $(f^{-1})'(4)$ using the above formula.
3. Find the inverse of $f$ and show that the computed derivatives match what we expect.

{{< youtube mqxwwb3l558 >}}



[^1]: Note that in 321 we define a function by a *domain* and a *codomain*. In that context, $f: A \to B$ is invertible if and only if $f$ is both one-to-one (injective) *and* $f$ is onto (surjective). In calculus we're just considering the case where  $B=f(A)$ and so the functions that we are considering are by their very nature already surjective. That's why we only need to test injectivity.