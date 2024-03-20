---
title:  "Laravel-GeoDB (2023)"
start:   2023
year:   2023
skills:
  - php
  - Laravel
  - vue.js
  - Inertia.js
  - composer
  - packagist 
locations:
  - "Kitchener, ON"
thumbnail:
  picture: /assets/images/laravel-geodb.png
  name: Laravel GeoDB
---
So, starting working on my ["P-xo"](/projects/2023%20-%20p-xo) project, I realized I needed a way to show locations,
starting with cities, states and countries. After a quick look around, and not wanting to aim directly at Google APIs
at this time, I couldn't find any obvious and decent package for Laravel that would help me offer the proper
address selectors to users and so, I decided to try and build my own package.

I had used the free [GeoNames](http://www.geonames.org) site in the past to retrieve big files with the necessary
information, but I still checked a few other providers to be sure. Most of them were requiring an upfront payment to
use the more complete sources of information, and were also constraining buyers to use their own code to decode the
database files, which wasn't the way I wanted to go, so I stayed with GeoNames and started building my package.

The objectives for the package were as follows:
- to offer Laravel controllers to access the data directly from the Laravel code
- to offer APIs to access the data from any Vue component.
- to allow developers to use the database of their choice, and likely the same one as the rest of their site
- to allow developers to choose which countries to include
- to offer translations of city, state or country names, which was actually available through GeoNames files.

Not one week later, the first version of the package is ready, working, and deployed to
[GitHub](https://github.com/peergum/geodb) and to Composer's
[Packagist](https://packagist.org/packages/peergum/geodb). It's a first version, and most of it works as expected but
it doesn't yet include name translations to desired locales, which will likely require a bit more work to code and
set up. The package works with static Laravel blades or with Vue pages and components (tested with Breeze). There
may still be a few teaks to do to make it fully usable, but overall it's pretty satisfying.

Static demo/status blade:
![Example 1](/assets/images/geodb_example_1.png)

Dynamic demo/vue blade:
![Example 2](/assets/images/geodb_example_2.png)

The only downside is, I realize that I may need more than the data provided by GeoNames (cities, states, locations,
latitude/longitude, population, ...) because I will likely require the names and locations of businesses too for the
"P-xo" project. So, I'll eventually have to use Google APIs anyway... In any case, I'll be looking for feddback on
Laravel GeoDB, and possible issues mentioned by developers.

Enjoy!
