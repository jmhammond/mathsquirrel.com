---
title: "Solution to: MacOS VoiceOver / reader keeps popping up"
author: ["John Hammond"]
date: 2024-05-29
summary: "Does the MacOS VoiceOver keep showing up when you reboot your Mac? The solution is in a different setting."
---

I was being driven crazy by the fact that every time I restarted my Macbook, the VoiceOver prompt would show up:

{{< figure src="picture1.png" width="100%" default="true" caption="The prompt">}} 

... but I'd disabled VoiceOver. I keep checking this every time:

{{< figure src="picture2.png" width="100%" default="true" caption="VoiceOver settings">}} 

It turns out that this prompt is controlled by *another* accessibility setting called "Spoken Content," even though the prompt itself is under a process called VoiceOver\*:

{{< figure src="picture3.png" width="100%" default="true" caption="Spoken Content Settings">}} 

Be sure to disable all of those, and you're good to go.  I had turned them on a couple years ago when I was checking the reading order for [my online textbook](https://www.wichita.edu/discretebook) and making sure it worked for a screen reader.  And it turns out there's a lot of disconnected toggles along the way!

