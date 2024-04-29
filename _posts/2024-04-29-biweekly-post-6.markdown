---
layout: post
title:  "Bi-Weekly Post #6 - Back to Go"
date:   2024-04-29 00:00:00 -0500
categories:
  - Open Source
  - Coding
  - Devices
tags: biweekly activity coding go hardware e-ink raspberry-pi
image:
  thumbnail: /assets/images/e-ink-device.png
  name: "AI generated image of an e-ink device"
images:
  - path: /assets/images/e-ink-device.png
    name: "AI generated image of an e-ink device"
    caption: "AI generated image of an e-ink device"
---
The way things are going, I better make these posts bi-weekly. Issue is not so much the lack of
time, but rather the strong involvement I have with the projects I dive in. Lately, I'm back to my
e-ink writing device.

Remember when I started my "N0vel1st" (read "novelist", not "novel 1st") project back in 2022, right
after I bought an (expensive) [FreeWrite Traveler][traveler] (big mistake!) and realized it was absolutely not
the device I was expecting? The Traveler was slow, had a poor UI, and felt like a device that had not been
thought through. My device would be all the Traveler was not: a nice UI, simple but efficient,
useful features, and proper communication with the cloud. Unfortunately, my freelancing activity then took all my time, and the N0vel1st was relegated to the
lowest priority, pretty much the same as writing a novel itself...

Since my freelancing activity decreased, I've spent more time back to learning and practicing my
software development skills, initiating p-xo, a friend meeting site similar to meetup, but with a
better interface. P-xo's development started in PHP, with Vue.JS+Inertia in the front end. But then
I came to the realization that PHP may not be the best choice to continue with. Being a decent
PHP developer is nice, but I believe PHP still is for a niche market, mostly used by small to
medium companies, but with not bright future in sight. I might be wrong, but something tells me the
future of development in not in PHP. P-xo also got paused when I decided to try and focus on ML
([Machine Learning][ML]) because the project would need that at some point, and my knowledge of
that area was minimal.

So, it came to me I had several options in front of me:
- Dig into Python, which is intimately connected with ML. I know some Python, but my experience is
really minimal
- Reinforce my knowledge of Go, which is growing as a powerful and reliable back-end language
- Start learning Rust, whose demand is increasing rapidly

Well, you know what I chose: getting back to Go. For that purpose, I had two options: continue Peer-Z, the project I had started in 2016 (as Peer-X)
and lightly reworked in the past years, or just reboot n0vel1st, but in Go. After seeing that many
people showed some interest in ZeroWriter, a DYI open-source project with the same intent as n0vel1st, I
decided that I would make n0vel1st public and open-source, so people could both enjoy my work and
improve it or build on it.

First step was to port to Go some low level C code for the e-ink drivers: I had never worked with 
CGO in the past (a way to compile and integrate C code in Go), and my initial tests left me rather
unsatisfied. Using "unsafe" code in Go felt sketchy... So, I opted for a full rework of the drivers
in Go. I found a decent [GPIO/SPI driver on Github][go-rpio], and used that as a foundation for the new e-ink
driver. That part went fast, and I could quickly initialize and load some bitmaps on the display.

Second step was to start working on a decent interface, and that included writing nice viewing
features: menus, windows, etc. I quickly built a first windowing system, and then started working
on text, porting the [Adafruit GFX Library][GFX] from C to Go (again, not willing to use CGO).

Eventually, I noticed my handling of buffers was subpar, so I'm currently working on redoing that
part, with a better usage of memory and to improve interactions with the e-ink display: e-ink 
technology is nice, but refreshing a full page (1448x1072 in the case of the 6" display I use) can
take around 1s, sometimes more, so it requires handling particularly well partial refreshes of the
screen, e.g. when typing characters.

Hopefully I'll have this done by the end of this week, with the occasional interruptions caused by
applying to jobs...

Some pictures coming soon, along with new repositories on GitHub.

While I'm working on that, enjoy your week and talk to you soon!

[traveler]: https://astrohaus.com/traveler/
[ML]: https://en.wikipedia.org/wiki/Machine_learning
[GFX]: https://github.com/adafruit/Adafruit-GFX-Library
[go-rpio]: https://github.com/stianeikeland/go-rpio
