---
layout: post
title:  "Weekly Post #5 - The Downsides of Open Source"
date:   2024-04-11 00:00:00 -0500
categories:
  - Open Source
  - Coding
  - Vulnerabilities
tags: weekly activity opensource vulnerabilities coding macos-vue
image:
  thumbnail: /assets/images/backdoor-drawing.png
  name: "AI generated backdoor drawing"
images:
  - path: /assets/images/backdoor-drawing.png
    name: "AI generated backdoor drawing"
    caption: "AI generated backdoor drawing"
---
Two weeks without my regular weekly post! What am I doing?! Well, been busy on the MacOS Vue mini-project
and I didn't see the time fly. That should tell me I should start doing planning for myself...
Anyways, today I'm going to just talk about Open Source and its potential pitfalls.

I've been using open-source code for ages, personally and professionally. I've been contributing to
the community too, in the best of my abilities. And yet, as great and amazing it is, there are
strong pitfalls that most people tend to ignore, including myself. The recent news about the
[xz utils backdoor][xz] have been an eye opener. But let's start from what open-source code is, and
how I and other people use it.

Most obvious case is bundled software. For instance, if you want to set up a web
site or blog for yourself and you're no developer, then the easiest is to go to Wordpress.com (or
any equivalent) and just create your blog. Done. You're in business. And you're indirectly using
open-source software (with possible added proprietary components). Yay! You assume wordpress.com
is a great business, and maybe you even pay them for additional services, because you trust them:
they wrote the code afterall...

If you're a web admin, a simple web developer or web designer, then you might just go to wordpress.org
and grab the whole package, or even more likely, your hosting provider already offers the option to
install it for you. You're now really using explicitly an open-source package. You may tune it the
way you want, adding plugins and themes, and whatever other stuff you can grab and is free, and
make it your new home online. Amazing! By the way, have you ever wonder *who* wrote all these
plugins and stuff?

If you're a developer, and are assigned, or assign yourself, a project, you have usually two
ways to handle it: either you build it from scratch, or you put someone else code together and
add the glue to make it work. The former seems and is the long way home, and most people, myself
included, would take the latter path to happiness (and hopefully pay). So the role of a developer
often becomes one of an architect: find the best materials, and design a house that will use them,
according to the buyer's specification. And then the architect puts their hard hat and goes hands
on... But then, again, are the materials used to the norm? who built them, who tested them, who
approved them in the first place?

In the three cases above, you're in the hand of a great unknown: people. The more people worked on
an open-source project (the "building material"), the more chances it has been tested, inspected,
reviewed, and approved. The smaller the project (like the ones I write on my own) the more you're
in the hand of a small number of developers, and someone just one person. And that's when you're
just in great danger...

At the end of March this year, a German developer, Andres Freund, was wondering why his linux
system was slow when login in, and after some investigations that most people, including developers,
would likely **not** do, he figured that an open-source package he had installed actually had a
backdoor in it. What is a backdoor you ask? Well, just imagine letting the door to your yard open,
while you leave your house triple-locked and with the metallic blinds closed and the alarm system
on, which alarm system may well be just besides the garden door.

So, a widely used package had been corrupt by a developer that pretended patching fix and
adding tests over a two years' period, while he was actually slowly planting and activating a
backdoor in the package. To our luck, the vulnerable versions of the package had not yet been
officially integrated into the linux distributions. We all can breathe again... or can we?

What this shows is, we tend to overtrust the open-source community.

Don't take this the wrong way: I'm a fervent supporter and I believe technology has been progressing
fast thanks to people sharing for the sake of sharing, and using each other's effort to build
things. Actually, open-source code is part of **every single appliance you use today**. That should
tell you the level of reliance we have on the community, community that is actually even supported
by big companies.

Actually, choosing proprietary technology over open-source will not decrease the risk, because
closed-source software 99.9% of the time (yes I drew that from my magic hat, but I just didn't
to say 100%) uses open-source packages. It could actually be **worse**, because the companies you
buy your software or software packages from don't have their code publicly inspected and approved,
so having a group of mis-intentioned developers in a company could lead to an easy hackable product.

And this goes to scary levels too: do you trust your remote-controlled lights, your TV, or even
your car? Well, the bad news is, they use open-source code too, and nobody will guarantee you the
code is 100% clean and safe. You can test 1 million hours or times any appliance, and it will work
fine, but that doesn't mean there's no backdoor in them. And even without thinking backdoor, just
a vulnerability nobody thought of could prevent your favorite device to fail at some point, 
intentionally or not.

But don't panic. If you're an end user, there's pretty much **nothing** you can do about it. If
you're a software developer, there is something you can do, and it's called **due diligence**:
- check **who** wrote the packages you use
- check their **credibility**
  - do they have a name?
  - are they easy to find online or are they "invisible"?
  - how long have they been coding?
  - how many packages did they release?
  - are they working with a group of other **credible** developers (recursive rule)
- check **what** the package is entitled to do/access, and if those are strictly necessary
- compare packages with others offering similar functionalities
- check commits if you can to see code changes
- be doubtful of recent committers, who did **not** commit significant changes/fixes but
slowly acquire a "reputation" as a formal committer (in the xz hack case, the culprit had been
committing a few useless changes over two years)
- if you can write an equivalent in a short time, do it rather than use someone else's work
- remember that the bigger the package and team responsible for it, the easier it can be
infiltrated if the team is lax and let's everyone commit changes without reviewing them thoroughly
first

Now, most of us don't have the time for that due diligence, so... you can now start to panic: the
world is doomed.

Enjoy the rest of the week in the meantime, and remember to put your tin foil hat on to stay safe 🤪

[xz]: https://en.wikipedia.org/wiki/XZ_Utils_backdoor
