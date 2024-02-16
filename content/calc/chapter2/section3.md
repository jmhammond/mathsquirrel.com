---
author: John Hammond
title: Section 2.3
mathjax: true
ShowBreadCrumbs: true
showtoc: true
tocopen: false
---

Section 2.3, Differentiation Formulas
<!--more-->

# Differentiation Formulas

For each of these differentiation formulas, we'll give it using Leibniz notation. We'll often use the Newton/prime notation, and if at any time you have a question, please ask! 

## Formulas

1. Constant function: $\dfrac{d}{dx} (c) = 0$ if $c$ is a constant.
    The slope of the line $y=c$ is 0. 
2. Basic linear function: $\dfrac{d}{dx} (x) = 1$ 
    The slope of the line $y=x$ is 1.
3. The Power Rule $\dfrac{d}{dx} (x^n) = nx^{n-1}$ if $n$ is a non-zero integer. 


### Examples

- Find the derivative of $y = x^3$  
   {{<spoiler>}} $\dfrac{dy}{dx} = 3 x^{2} {{</spoiler>}}
- Find the derivative of $y = x^{1551}$ 
   {{<spoiler>}} $\dfrac{dy}{dx} = 1551 x^{1550}$ {{</spoiler>}}
- Find the derivative of $f(x) = \sqrt{x}$ 
   {{<spoiler>}} $f'(x) = \dfrac{1}{2} x^{-1/2} =  \dfrac{1}{2x^{1/2}} = \dfrac{1}{2\sqrt{x}} $ {{</spoiler>}}   
- Find the derivative of $f(x) = \frac{1}{x^5}  = x^{-5}$ 
   {{<spoiler>}} $f'(x)= -5 x^{-5-1} =  \dfrac{-5}{x^{6}}$ {{</spoiler>}}   

## Formulas, continued

4. Constant multiple rule:   if $c$ is a constant,
$$
\dfrac{d}{dx} (c f(x) ) = c \dfrac{d}{dx} f(x)
$$

5. Sum Rule 
$$
\dfrac{d}{dx} (f(x) + g(x) ) = \dfrac{d}{dx} f(x) + \dfrac{d}{dx} g(x)
$$

6. Difference Rule 
$$
\dfrac{d}{dx} (f(x) - g(x) ) = \dfrac{d}{dx} f(x) - \dfrac{d}{dx} g(x)
$$

### Examples

- Find the derivative of $f(x) = x^3 - x + 1$
     {{<spoiler>}} $f'(x) = 3x^2 - 1 + 0 = 3x^2 - 1$, just like we found in a previous section! {{</spoiler>}}

## Formulas, continued

7. $\dfrac{d}{dx} (\sin x) = \cos x$

8. $\dfrac{d}{dx} (\cos x) = - \sin x$

### Examples: 

- Find the derivative of $g(x) = 2\sin x - 3\cos x$
  {{<spoiler>}} $g'(x) = 2\cos x - 3\cdot (-\sin x) = 2\cos x + 3 \sin x$ {{</spoiler>}}

- If $f(x) = \sin x$, find $f'(x)$, $f''(x)$, $f'''(x)$, and $f^{(4)}(x)$
  {{<spoiler>}} $\begin{align*} f(x) &= \sin x \\ f'(x) &= \cos x \\ f''(x) &= - \sin x \\ f^{(4)}(x) &= -\cos x \\ f^{(5)}(x) &= - (-\sin x) = \sin x & \text{ not that I asked...}\end{align*}$  
What pattern do you notice? What do you think $f^{(6)}(x)$ is? What about $f^{(25)}(x)$? {{</spoiler>}}

## Formulas, continued,
I'm going to switch to Newtonian/prime notation for these because it's much cleaner and clearer to write and read.

9. The Product Rule. 
    $$
    (fg)' = f'g + fg'
    $$
 
    **EXAMPLE**  Find the derivative of $f(x) = x\sin x$

{{< youtube Suk-7lPS54c >}}

10. The Quotient Rule.
    $$
    \left[ \dfrac{f}{g} \right]' = \dfrac{gf' - fg'}{g^2}
    $$
    **EXAMPLE** Find the derivative of $h(x) = \dfrac{x^2}{\cos x}$

{{< youtube HIlcNFa-CrY >}}

### Examples

- Compute the derivative of $f(x) = \tan x$
  
{{< youtube T1ps7aiPi04 >}}

- Compute the derivative of $f(x) = \dfrac{1}{x^5}$ using quotient rule.

{{< youtube mp1kHyvUK84 >}}

- Compute the derivative of $f(x) = \dfrac{1}{x^5}$ using the product rule. 

{{< youtube 0iGXE63aTPg >}}

 ##  Now practice!

Head over to WebAssign and work on section 2.3. If you have questions, let me know!