---
layout: post
title:  "Weekly Post #1"
date:   2024-02-20 10:00:00 -0500
categories:
  - Learning
  - Coding
  - Jobs
tags: weekly activity coding learning golang java AWS CloudFormation Lambda
image:
  thumbnail: /assets/images/squirrel.jpg
  name: "learning squirrel"
images:
  - path: /assets/images/squirrel.jpg
    name: "learning squirrel"
---
So, I decided I should just try to post at least once a week. It's good for writing practice, it helps
summarizing the activity from last week, and maybe it will give (someone) a feeling of progress...
This will be my kind of standup meeting (for the week... not going to bore you everyday, LOL)

Last week (actually possibly starting with the week before that), along with continuing applying to several jobs, and receiving several thank you letters,
I decided to make a few changes in my activities. Some internal restructuring if you will. I decided
to refocus my development and learning skills.

Firstly, p-xo is a bit on-hold. I realized that coding it with Laravel + InertiaJS + VueJS might not
be the best strategy. I know it's a MVP, but since I'm the only one working on it, I need to make it
worth my while. Laravel-Inertia-Vue (let's call that "LIV" for now) is great to get something off the ground
quickly, but it also means locking it in to that ecosystem, which leads me to my second point...

I don't want to get stuck in PHP+Laravel. PHP is great and you can build things fast with it. It's a
bit like a web-bash or web-awk if you want. You script it to do whatever you want quickly. The (huge)
downside is, it's looked down by the developer community, because it's not strongly typed. In other
words, it's the new BASIC. I think that opinion tends to be a little bit of an overreaction,
and PHP can be a powerful scripting language with not much to envy to Java, C++ or other OOP languages,
but the market being what it is, it doesn't really matter what I think or like, the main objective
being you need to use what the market uses otherwise you're just a marginal coder that nobody wants
in their team. Another issue with LIV is, Inertia is a BIG bandwidth consumer, not to mention it
even passes the list of APIs you use in any requests. So much for security, IMHO!

So, I eventually opted for another strategy. I initially though, what about using Laravel as a
front-end and refreshing my skills in Java? So I powered up JetBrains IDEA, and started a quick
RESTFUL API development using SpringBoot, which was a great idea, because I realized the concept of
RESTFUL APIs slightly incomplete. SpringBoot's tutorial opened my eyes with their reference to the [Roy Fielding's
"controversy" or argument](https://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven),
in which he argues most people tend to code incomplete RESTFUL APIs. Like most people, I used to
think that as long as I provided all the proper methods (GET, POST, PUT, DELETE,
and optionally HEAD and OPTIONS) to manage a resource and made all of them but POST idempotent, I'd
be building RESTFUL APIs. Fact is, an actual RESTFUL API also needs to be self-descriptive and include
links in its responses. I'd rather avoid a bad or imprecise paraphrasing of Roy Fielding's message, so I
invite you to check the link above, and his following post too, where he slightly clarifies his
message. What I took away from all this is, if you use SpringBoot AND Spring [HATEOAS](https://en.wikipedia.org/wiki/HATEOAS),
you're much closer to a creating proper RESTFUL API. But then another realization hit me.

Java is great. I did code in Java several years ago at Lasso Datasystems (now part of ECI Software Solutions),
when the development team decided to migrate all APIs away from PHP and implement Java APIs instead. Java
is likely one of the most common development environment used today (or its one of its JVM variants, like Kotlin), thanks to its portability and not
having to buy expensive licenses to develop with it. Yet, from a developer's perspective, coding with
Java means being likely part of a pool of 60-80% (pure estimate on my part) of the coder population, only
second to Python, which obviously helps getting a job, but also increases competition for that job. With
this in mind, I eventually opted to focus on another language.

Golang (or more formally, simply "Go") is a programming language that Google started developing around 15 years ago. I
got introduced to the language by my friend and colleague Charles Krempeaux while we were working at Trulioo,
back in 2013, and quickly came to love the efficiency and specificities of the languages. Even though the
language is not yet ranked among the 15 most used languages, many companies are starting to pick it up, for
backend solutions mainly. Go, a compiled language like Java or C/C++, is particularly championing concurrency and
networking, and that's one of the main reason why I decided to focus on improving my skills in Go, adding to
the fact Go developers are not (yet) legion, mostly due to some steep learning curve (itself related to
the language being strongly typed, and character handling far more complex, yet powerful, that most languages).

Another learning area I intend to spend time on is Machine Learning (and indirectly AI, or vice-versa). I will
need to understand ML to develop some recommendations in p-xo, and I believe it's currently also something
useful to present to future employers, all the more with current AI trend; I believe this trend is going to fade
away in the next five years, when everyone realizes that "AI" is just fashion rebranding of the old good "ML"
most people was finding boring because it's clearly coding with statistics and probabilities, and people who
love Maths that much are not so many... (hence data scientists are mostly PhD people...)

Well, I think that completes my summary of the last two weeks. I'll talk to you again next week with
some more (hopefully good) news...
