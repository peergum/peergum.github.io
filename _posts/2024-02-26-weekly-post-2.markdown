---
layout: post
title:  "Weekly Post #2"
date:   2024-02-26 12:00:00 -0500
categories:
  - Learning
  - Coding
  - Jobs
tags: weekly activity coding learning golang java lex/yacc flex/bison ANTLR4 neutro languages
image:
  thumbnail: /assets/images/wordobulator.png
  name: "AI generated wordobulator machine"
images:
  - path: /assets/images/wordobulator.png
    name: "AI generated wordobulator machine"
    caption: "AI generated wordobulator machine"
---
Last week started as a "going to do some Go" week, but quickly, some posts and articles
about recent language issues (in French originally) with gender-neutrality adaptation
(and often consecutive dismissal or refusal) sent me through the rabbit hole of linguistics,
translations and language creation.

And here I was, deciding to start a new project (again!), this time about the creation of a
gender-neutral language called Neutro. I started pondering what the language would like and
quickly built a new page where I'd detail the steps of this creation.

At some point, confronted with grammar and vocabulary choices, I realized it would likely be
convenient to build translators to and from English for Neutro, like some kind of [TDD][TDD]
(Test-Driven Development), and I started digging back into lex/flex-yacc/bison and how to do
that in Go (because, why do that in C if I can practice Go instead...).

If you're not familiar with lexers and parsers, [Lex][lex] and Yacc[yacc] are the ancestors of semantical and
analytical parsing, created far back in the 70s, and later adapted under GNU to [Flex][flex] and [Bison][bison].
Mostly these tools take some parsing rules as input, respectively at character and grammar level, and transform
them into C code. I used them in the past to parse documents (in 1998, specifically, to automatically
create work requests from [SITATEX][SITATEX] messages, while working at [SITA/Equant][SITA]).

After a bit of experimentation, and the realization that these lexers and parsers would largely be
inconvenient to generate Go code, I turned to reddit [r/golang][r-golang], where I eventually discovered
[ANTLR4][ANTLR4].

ANTLR4 is something similar to lex/yacc, and has been developed during the last 25 years, and
can generate code in most popular languages, including Go. Version 4 even offers the strong benefit
of allowing developers to separate the grammar from the code, which lex and yacc didn't allow. So,
I ended buying the Bible of ANTLR, [The Definitive ANTLR 4 Reference][antlr-bible], and started
reading it.

This week will likely be dedicated to experimenting with ANTLR4, continue looking for jobs, and...
taking care of tax chore, AKA "the main downside of being a freelancer".

Talk to you next week, and in the meantime, enjoy your taxes too ;)

[TDD]: https://en.wikipedia.org/wiki/Test-driven_development
[lex]: https://en.wikipedia.org/wiki/Lex_(software)
[yacc]: https://en.wikipedia.org/wiki/Yacc
[flex]: https://en.wikipedia.org/wiki/Flex_(lexical_analyser_generator)
[bison]: https://en.wikipedia.org/wiki/GNU_Bison
[SITATEX]: https://www.sita.aero/solutions/sita-at-airports/sita-communications-and-data-exchange/sitatex-services/
[SITA]: https://en.wikipedia.org/wiki/SITA_(business_services_company)
[r-golang]: https://www.reddit.com/r/golang/
[ANTLR4]: https://www.antlr.org
[antlr-bible]: https://amzn.to/3uXaMQ1