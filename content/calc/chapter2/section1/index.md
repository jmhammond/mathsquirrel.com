---
author: John Hammond
title: Section 2.1
mathjax: true
ShowBreadCrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

The Derivative

<!--more-->

# Tangent Lines

## Definition
The tangent line to a curve $y=f(x)$ at the point $P(a, f(a))$ is the line through $P$ with slope
$$
m = \lim_{x \to a} \frac{f(x) - f(a)}{x-a}
$$
if that limit exists. 

Slope is always "rise over run." The $y$-values are the outputs of the function, and in order to find the slope at exactly that point, we let $x$ get as close as possible to $a$ via the limit.

{{< figure src="2.1.derivativepicture.png" alt="">}}


### Example

Find the equation of the tangent line to the parabola $y=x^2$ at the point $P(-1,1)$.

{{< youtube 9AbQlLAU2wk >}}

### Example

Find the equation of the tangent line to the hyperbola $\displaystyle y= \frac{1}{x-2}$ at the point $P(3,1)$.

{{< youtube fhA_SeRnQYk >}}


## Visually revisiting the tangent line question

Have a look at [this Geogebra activity](https://www.geogebra.org/m/a6kynjc6) by WSU's Justin Mears to visually and physically play with finding the tangent lines.

https://www.geogebra.org/m/a6kynjc6


# Velocities

If an object moves in a straight line (say, I through a ball straight up in the air), we can let $y=f(t)$ describe a the object's position in space after time $t$. We call this a position function. 

<!--
If time advances $h$ amount after time $a$, the average velocity of an object will always be given by 
$$
\text{average velocity} = \frac{\text{displacement}}{\text{time}} = \frac{f(a+h) - f(a)}{h}
$$ 
//-->

We can define the *instantaneous velocity* of the object at time $t=a$ by using the formula for average velocity and applying the limit: 

$$
v(a) = \lim_{h\to 0} \frac{f(a+h) - f(a)}{h}
$$
where $h$ is an incredibly small amount of time after $t=a$ (and in the limit, goes to 0). 

### Example

Let's imagine I want to drop this toy red panda off the top of Lindquist Hall. 
{{< figure src="2.1.redpanda.png" alt="">}}

He begins its journey at 84 feet[^1].  The equation for the position (measured in feet) of a dropped object from 84ft is $f(t) = -16t^2 + 84 $ after $a$ seconds.

1. What is his velocity after 1 second? 
    Note: the velocity is *negative* which means it's in a *down* direction!
2. How fast is he traveling when he hits the ground? 

{{< youtube t2B-UHBTWCg >}}


### Red Panda aside

No red pandas (or toys) were harmed in this example. If you want to see an adorable red panda, though, check out Sedgwick County Zoo's own Ravi [^2]: 


{{< figure src="2.1.ravi.jpeg" alt="">}}


# The Derivative

Because the the limit that appears in the instantaneous velocity and tangent line questions shows up so frequently, we give it a name. **The Derivative**

## Definition
The derivative of a function $f$ at a number $a$, denoted by $f'(a)$ is
$$
f'(a) = \lim_{h\to 0} \frac{f(a+h) - f(a)}{h}
$$
provided the limit exists.

We pronounce $f'(a)$ as "f prime of a".

### Alternative definition:
We can also write the limit in the derivative of $f$ at point $a$ as: 
$$
f'(a) = \lim_{x\to a} \frac{f(x) - f(a)}{x-a}
$$


### Example 
Find $f'(a)$ for $f(x) = 2x^3 - x +1$ using the definition of the derivative. 

{{< youtube K4wQZFDPAoE >}}

### Example: 
Find the equation of the tangent line to the curve $f(x) = 2x^3 - x + 1$ at the point $P(1, 2)$

{{< youtube RIOxjsQXWFs >}}

# Rates of Change

Derivatives measure the *slope* or rate of range of a function at a particular point. 

* If the slope is large, the function is changing is fast! 
* If the slope is small, the function is changing slowly
* If the slope is positive, the function is increasing
* If the slope is negative, the function is decreasing


### Example
Let $V(t) = 2t^2 - 16t + 35$ be the amount of water in a tank (in liters) after $t$ minutes. 

1. Is the volume of water increasing or decreasing at $t=1$ minute?
1. Is the volume of water increasing or decreasing at $t=5$ minutes?
1. Is the volume of water in the tank changing faster at $t=1$ or $t=5$?
1. Is the volume of ever not changing? If so, when? 

Please work through this example and check your answer below:
{{<spoiler>}}
First, $V'(t) = 4t - 16$. So:
1. $V'(1) = -12$ which means the volume is decreasing (changing in a negative direction)
1. $V'(5) = 4$ which means the volume is increasing (change is positive)
1. The water level is changing *faster* at 1 second than 5 since 12 liters per second is faster than 4 liters per second. 
1. The volume doesn't change if $V'(t) = 0$; this happens when $t=4$ seconds. 
{{</spoiler>}}

### Example
The graph shows the influence of the temperature $T$ on the maximum sustainable swimming speed $S$ of Coho salmon.

{{< figure src="2.1.salmon.png" alt="">}}

1. What is the meaning of the derivative $S'(T)$
2. What are the units of the derivative?
2. Estimate the values of $S'(10)$ and $S'(25)$

{{< youtube 0-1Rvu8wpvk >}}

### Example
A roast turkey is taken from an oven when its temperature has reached 185°F and is placed on a table in a room where the temperature is 75°F. The graph shows how the temperature of the turkey decreases and eventually approaches room temperature. By measuring the slope of the tangent, estimate the rate of change of the temperature after an hour.

{{< figure src="2.1.turkey.png" alt="">}}

Try this example (estimate some points on the tangent line and estimate the slope) then check the solution below: 
{{<spoiler>}}
It looks like the tangent line passes through (30, 145) and (90, 110). The rate of change will be: 
$$
m = \dfrac{145-110}{30-90} = \dfrac{35}{-60} \approx -.5833^\circ\text{F/minute}
$$
So a little over a half a degree of cooling for each minute out of the oven! 
{{</spoiler>}}

##  Now practice!

Head over to WebAssign and work on section 2.1. If you have questions, post them here, and either I or a fellow student will answer them quickly!



[^1]:Linquist is ~79 feet, I'm dropping him from about arm level
[^2]: From SCZ's Facebook post on December 16, 2020. https://www.facebook.com/SedgwickCountyZoo/photos/pcb.10158795726353058/10158795726228058


---- 

# Approximating derivatives

## Forward / Backward / Central Differences

Imagine that we have three (or more) data points for something occurring over time - say distance traveled over time, or electrical current over time... 

Let $(t_0, f_0)$ be the first data point in the past, $(t_1, f_1)$ be the second data point at the present, and $(t_2, f_2)$ be the third data point in the future. 

We define the **forward difference** to be estimation of the derivative from the present time to the future: 
$$
f'(t_1) = \dfrac{f_2 - f_1}{t_2 - t_1}
$$
You can think of it was
$$
f'(\text{now}) = \dfrac{f(\text{future}) - f(\text{now})}{\text{future} - \text{now}}
$$

We define the **backward difference** to be estimation of the derivative from the past to the present time: 
$$
f'(t_1) = \dfrac{f_1 - f_0}{t_1 - t_0}
$$
You can think of it was
$$
f'(\text{now}) = \dfrac{f(\text{now}) - f(\text{past})}{\text{now} - \text{past}}
$$

and we define the **central difference** to be the estimation of the derivative using the past and the future values:

$$
f'(t_1) = \dfrac{f_2 - f_0}{t_2 - t_0}
$$
You can think of it was
$$
f'(\text{now}) = \dfrac{f(\text{future}) - f(\text{past})}{\text{future} - \text{past}}
$$

## An example

A potato is placed in an oven, and the potato's temperature $F$ (in degrees Fahrenheit) at various times is taken and recorded in the following table. Time is measured in minutes

| $t$    | 0   | 15     | 30  | 45  | 60     |
| :----- | :-- | :----- | :-- | :-- | :----- |
| $F(t)$ | 70  | 180\.5 | 251 | 296 | 324.5 |

1. What are the units of $F'(30)$?
2. Use forward differences to estimate $F'(30)$
2. Use backward differences to estimate $F'(30)$
2. Use central differences to estimate $F'(30)$
5. Explain in everyday, practical terms, what $F'(30)$ tells you about the potato. Be as specific as possible.

## A solution  (with spoiler tags)
Go ahead and think about this and attempt each part before revealing the solution

1. What are the units of $F'(30)$?
{{<spoiler>}} Since $F$ is in degrees Fahrenheit and $t$ is in minutes, the units of $F'$ is measured in Degrees Fahrenheit per minute {{</spoiler>}}
2. Use forward differences to estimate $F'(30)$
{{<spoiler>}}
$\begin{align*} F'(30) &= \dfrac{F(40)-F(30)}{40-30} \\\\
&= \dfrac{296 - 251}{40-30} \\\\
&= \dfrac{45}{10}\\\\
&= 4.5  \end{align*}$
{{</spoiler>}}
2. Use backward differences to estimate $F'(30)$
{{<spoiler>}}
$\begin{align*} F'(30) &= \dfrac{F(30)-F(15)}{30-15} \\\\
&= \dfrac{251 - 180.5}{30-15} \\\\
&= \dfrac{70.5}{15}\\\\
&= 4.7  \end{align*}$
{{</spoiler>}}
2. Use central differences to estimate $F'(30)$
{{<spoiler>}}
$\begin{align*} F'(30) &= \dfrac{F(40)-F(15)}{40-15} \\\\
&= \dfrac{296 - 180.5}{40-15} \\\\
&= \dfrac{115.5}{25}\\\\
&= 4.62  \end{align*}$
{{</spoiler>}}
5. Explain in everyday, practical terms, what $F'(30)$ tells you about the potato. Be as specific as possible.
{{<spoiler>}}
This estimates how fast the potato's temperature is rising (because $F'(30)$ is positive). It is rising about 4.5 to 4.7 degrees per minute. 

If we wanted to estimate it further, maybe we could average the values? What do you think? 
{{</spoiler>}}