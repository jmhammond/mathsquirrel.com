---
title: "Clock for students taking a test"
author: ["John Hammond"]
date: 2024-04-30
thumbnailAlt: "my photo of the blackboard after working out Euler's solution to the Basel Problem"
summary: "Adding a clock to a classroom without one, using a screensaver and single line of code"
---

Jabara Hall has many issues[^1], one which is especially relevant at exam time is the fact that none of the electronic wall clocks in the building work. 

In order that my students have the ability to see the time, I found the Mac screensaver app [Fliqlo screensaver](https://fliqlo.com). But because I want to trigger the screensaver at the start of class, rather than waiting for it to load, I found you[^2] can run the following command in the terminal: 

`open /System/Library/CoreServices/ScreenSaverEngine.app`

or more simply:

`open -a ScreenSaverEngine`
 
It's a very simple solution. 

{{< figure src="./thumb Fliqlo screensaver.jpeg" width="75%" default="true" alt="image of my screensaver running on my laptop and external monitor" caption="Image of the clock running in my office when I was testing it out before the exam.">}}
 

[^1]: Oh my goodness, don't get me started. We could talk for a while about it!
[^2]: Thanks to [this post on stackoverflow.](https://stackoverflow.com/questions/4505198/how-can-i-start-the-screensaver-and-lock-the-screen-from-the-os-x-terminal)
