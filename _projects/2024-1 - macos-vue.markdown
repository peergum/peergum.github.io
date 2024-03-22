---
title:  "MacOS Vue (2024-)"
start:   2024
year:   2024
skills:
  - vue.js
  - vite.js
  - npm.js
locations:
  - "Kitchener, ON"
thumbnail:
  picture: /assets/images/macos-demo.png
  name: Macos Vue Demo

---
While working on a side project for my first novel, I realized it would be nice to have a simulation of
a Mac OS environment, as functional as possible, to present some documents and informations. After looking
around a little bit, all I could find was either a real MacOS remote access, which was far too much for what
I needed, and obviously the corresponding expense. So I decided to build my own emulation, using Vue.js,
as another practice training on Vue.

Building the graphical environment was pretty straightforward: taking a desktop background (Big Sur was a
nice choice) and add a top bar to it. Then grab some docking bar and rework it to look real. Then I started
working on actual menus: original look and feel, and dynamic selection of contents. After that, I captured
some icons for the right side of the menu, and added a nice (functional) clock. That was it for the simplest
part.

Then I started working on windows: one text viewer window, that needed some on the fly transformation of
the \n into <br/>, and eventually I added an ANSI to html converter so it could also show colors easily.
That task done, I focused on adding a picture viewer, which would be convenient. I also worked on the window
management so I could click on the title bar to pop-up a given window. At this point, things were going
pretty great, so I added a browser window, in an IFRAME. Still no obvious issue.

Problems started when I decided to add a feature to move and resize windows. Things were easy at
first, but got more complicated when I needed to resize the windows, because the mouse events were
not always firing in the proper element... Well, event is certainly one of the most complex things
to handle in Javascript and in particular between components in Vue.js. But I figured things out.

I tried for a bit to add an address bar into the browser window, but that complicated things, and
the fact a user could click on links inside the IFRAME to move around was good enough for me. One
serious limitations of IFRAMEs is, you can't really control what's going on in there, for security
reasons. Another one is, the whole simulation is running from one site, and consequently, if you
load another site in an IFRAME, some cross-site restrictions apply. One example is, you can't visit
Google or Apple sites in an IFRAME. But at least you can Wikipedia, which is all I personally needed.

Next step of my development was to integrate a terminal emulation. I looked around for some Vue
components that I could use, but again they were all targeting actual systems, running a remote
shell or allowing websockets connections with a/the host, which I had no interest in. A few ones were
basic simulations, the way I wanted, but I didn't like them so much, so I decided to build my own.

Realizing I had save some state for the terminal, so that it would not restart each time I moved the
window, I created some store that could keep the state of the terminal and typing buffers, and the
current location in the virtual filesystem. That worked pretty well and in no time I had something
functional, and extensible. I built in a help command, and a few useful other ones: "ls", "cd",
"pwd". I'm currently working on "cat", and I may add a few other ones with time, based on my own
requirements or other users'.

Last, but not least, I decided to publish the module on NPM.js and GitHub, so others could make good
use of it, and maybe suggest features, improvements, and/or bugs. I had to learn how to build a NPM
package, and even more specifically a Vue library, and documentation on how to do that for Vue3 was
quite sparse unfortunately, but I got it right, eventually. It took me a few attempts (from v1.0.0
to v1.0.7) to get the image assets loaded fine in an external project, but again, with a bit of
persistence, I ended getting things right.

The result NPM package is available [here][macos-vue-npm], the github repo [here][macos-vue],
and a demo [here][macos-vue-demo]. Feel free to try and contribute!

Here are two demo screenshots:
![Screenshot](/assets/images/macos-demo.png)
![Screenshot](/assets/images/macos-demo-2.png)

[macos-vue-npm]: https://www.npmjs.com/package/@peergum/macos-vue
[macos-vue]: https://github.com/peergum/macos-vue
[macos-vue-demo]: https://macos.peergum.com



