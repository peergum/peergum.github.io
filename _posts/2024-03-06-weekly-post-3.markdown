---
layout: post
title:  "Weekly Post #3"
date:   2024-03-06 12:00:00 -0500
categories:
  - Learning
  - Coding
  - Jobs
  - Taxes
tags: weekly activity coding learning golang java ANTLR4 languages 1BRC
image:
  thumbnail: /assets/images/grammar_parser_AI.jpg
  name: "AI generated grammar parser... go figure!"
images:
  - path: /assets/images/grammar_parser_AI.jpg
    name: "AI generated grammar parser... go figure!"
    caption: "AI generated grammar parser... go figure!"
---
Last week has been more of the same: jobs, taxes, ANTLR v.4, but I also spent time on some interesting programming
challenge, the **one billion row challenge** AKA "1BRC"; I'll get there in a bit.

Most of LinkedIn readings are boring: self-promotion, big companies marketing, people complaining,
people posting useless charts with blinking/moving lines and what not, people posting useless or weird AI
generated stuff, but occasionally, there's an interesting post coming out of the lot, and it's
usually about coding - YAY! - and about how to either do things better (patterns and stuff) or
just some coding challenge. But, since I mentioned AI generated pictures, let me first explain what the featured one in this post
is supposed to mean.

In the past, when I was posting blogs, I used to do a quick Google Image search about the topic I
wanted to blog about, then either capture and slightly modify one interesting picture, or just use
the link to that picture, which often ended in a missing picture after a while... Now, thanks to AI,
I just go to Bing.com. I used to hate Bing, but lately I have to say I've been impressed by their
progress, as long as you don't use their search engine; unfortunately, their self-censoring is giving
either no answer or just dumb ones on many occurrences. But for AI genrated pictures, Bing is THE
site to go. I'm not sure how many AI pictures you can generate for free in a day, but as far as I'm
concerned, I seem to be able to get a few for my occasional posts so that's perfect.

But perfection in the AI world is quite relative. First, unless you ask specifically for certain words,
the generated picture will likely have scrambled <s>eggs</s> words. Also, most things generated are
usually highly disturbing: a combination of impossible, fantastic, ingenious, weird, and frankly crazy.
For instance, today I asked Bing to generate the "picture of a grammar parser". Yes, I know: what 
could a grammar parser even be? Honestly, I don't know, but I was curious to see what AI would think
it is. And to my surprise, Bing generated four pictures of **colored birds standing on books**...

My first reaction was: "is a parser some kind of bird?!?". So I checked Google (yeah, I didn't trust
Bing too much on that one...), and no: no trace of any parser birds. But well, that doesn't matter,
because everyone knows that the picture is just there to call attention (which is why you're reading
this, to my knowledge) and what could be nicer than a colorful bird posing on books? And totally related
to my learning of ANTLR (the books, not the bird...). But let's get back to the coding challenge first.

So, what is the One Billion Rows Challenge, you ask. Well, here's the link: [1brc][1brc]. Yes, that's a
bit technical if you're not into coding. Simply put, the challenge is about reading one billion rows from
a file in the minimal amount of time, each row representing a city and a temperature; while reading the
file, program has to calculate the minimum, maximum, and average temperature per city (cities can appear
several times with different temperatures). It is a very simple problem, but the size of the input
file is what makes things interesting. Oh, and I just realized I didn't read about this challenge in
LinkedIn, but rather in Reddit, in [r/golang][r/golang] subreddit, and it was referring to a [post][BenHoyt] from
Ben Hoyt (a coder, doh!) about how he optimized his code (in Go, rather than the original Java) step-by-step to
to have it eventually run in 4s, rather than the initial 1m45s. Respect! That was actually a very educational
post, and overall it just convinced me that Go is an amazing language (although I knew it already...)

As a side note, one thing I always found complex in Go is the fact it treats strings as an array of
bytes, but in the same time, the base of the language, as far as characters are concerned, is runes,
which are the UTF-8 representation of characters. So any character transformation you do pretty quickly
and easily in any other language, like PHP, Java, Javascript, C/C++, Python, can become some burden in
Go. Go "interfaces" (handled in go like some kind of omnishaped variables), are the other complexity in
the language, IMHO. But these complexities are also what make the language so much more powerful than
any other language I've been learning. Go has a **steep** learning curve. But when you master it - or
at least get an understanding of the way it works - you cannot avoid being amazed. I have the strong
conviction that Go is **the language of the future** and will one day be the replacement for C/C++ and
Java in the back-end. And to be clear, runes and interfaces are only the tip of the iceberg. Once you'll
start working with go routines and channels, you'll wonder why other languages don't have those features.

Anyways, back to my week. After spending some time reading and learning about this challenge, I continued
my self-training in ANTLR v.4. I have to say, ANTLR is amazing too, because it allows to separate the
grammar from the code (if you're lost here, please check my previous weekly post about ANTLR), at least in
v.4 since v.3 didn't have that feature. And using ANTLR is quite simple and straight-forward: I built a
mini-grammar for a pseudo language in a few hours, and it parsed correctly almost from the first attempt;
antlr was pretty clear about where there may be issues, and I could even visualize a tree representation 
of an attempt to parse a test program. So at this point, I feel pretty confident about creating a simple
grammar. I'll likely rework a quick tool I had done in the past, some sort of a calculator that shows
values in all possible formats (including time values), and that was using flex/bison for the grammar part;
I'll probably work on this after I read about the implementation of the code itself, which also doesn't
seem very complicated. Plus side of ANTLR: by default it generates code in Java, but generating code in
Go is as simple. I'll likely do a dedicated post on ANTLR at that point.

Other than that, the rest of my week was pretty boring, with job search and taxes. Did I mention I
hate doing accounting?

Talk to you again next week!


[1brc]: https://github.com/gunnarmorling/1brc
[r/golang]: https://www.reddit.com/r/golang/
[BenHoyt]: https://benhoyt.com/writings/go-1brc/

