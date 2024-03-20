---
title:  "Motorcycle Tracker (2016)"
start:   2016
end:    2017
year:   2016
skills:
  - AWS Lambda
  - AWS API Gateway
  - AWS Dynamo DB
  - AWS EC2
  - php
  - Javascript
  - jQuery
  - HTML/CSS
  - Google Maps APIs
  - Particle Electron
  - C/C++
locations:
  - "Vancouver, BC"
thumbnail:
  picture: /assets/images/tracker.jpg
  name: tracker picture
images:
  - path: /assets/images/tracker.jpg
    name: tracker picture
    caption: picture of my tracker
  - path: /assets/images/tracker-1.png
    name: tracker map with paths
    caption: "Tracker map with path (1)"
  - path: /assets/images/tracker-2.png
    name: tracker map with paths
    caption: "Tracker map with path (2)"
  - path: /assets/images/tracker-3.png
    name: tracker map with paths
    caption: "Tracker map with path (3)"
---
Once I got the Electron I had bought through Particle kickstarter, I put it to good use as a bike tracker.

The hardware part was simple and consisted mostly in assembling the electron and an asset tracking board also bought from
Particle. I also wrote a simple firmware for the microcontroller, that was sending the positions to the cloud.

The software part was non-existent, but it seemed to me it would be relatively easy to set something up with AWS. I
created some AWS Lambda that would parse the data received from Particle's webhook, through AWS API gateway, and store
it into an AWS DynamoDB datastore. Then a simple web app, hosted on a server in EC2, was showing the paths taken by
my motorcycle. The javascript part was making the calls to Google Maps APIs, and representing the various paths in 
different colors.

I posted the project on [Hackster.io](https://www.hackster.io/peergum/car-or-motorbike-tracker-d389bc) with some details
about the implementation, but eventually didn't complete the whole project's documentation. The whole project was fun to
build and develop, but it unfortunately showed its limit on my 'round the USA motorcycle trip the same year, when the
tracker ended draining the bike's battery and got me stopped for 3 hours in the evening, on a parking lot on the side of the highway
not far from New Orleans, having to recharge the battery with a 30m cable connected to an outlet in the visitor center.
Luckily, I had a battery tender and that long cable, and I was not in the middle of nowhere... 
