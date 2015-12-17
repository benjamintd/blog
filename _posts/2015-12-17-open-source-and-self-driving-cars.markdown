---
layout: post
title:  "Open Source, Software and Self Driving Cars"
date:   2015-12-17 10:00:03
categories: sdc open-source
comments: true
---

The automotive industry is entering a weird era. There was a time when engineering and manufacturing a good car was hard, and good practices were still to be established. Those who were the best at it stood out and became the giants that we know: GM, Ford, Toyota, etc. This industry is now mature: cars have not changed so much in the last two decades if you compare to the technology improvements - at least from the user's perspective. Changes to new models are mainly incremental details in the industrial design, or adding new minor options.

On the other hand, the industry is on the verge of a huge disruption, with self-driving cars. The current development of autonomous vehicles shows that software companies are the most likely to win the race to market. Google, Baidu, Tesla, Apple... Engineering a self-driving software has become the hard problem, and those who are the best at it will stand out.

This raises a number of issues, because the software industry is so radically different from the automotive industry. The first main difference is testability. A number of independant organizations are dedicated to testing cars, to assess their resistance to crashes (IIHS) and to give them accreditation for release. Even though audits are frequent in the software world, there is still no external entity dedicated to testing self-driving software. 

Of course, there are tons of tests done in-house, but consuming software relies a lot on trust, for most users. I trust Google that their security engineers protect my data efficiently. I trust Microsoft that my Powerpoint will not crash in the middle of my presentation. The truth is, there has been no third party between Google and me to certify that their software update is safe for me. There is no quality label other than their brand name that can assure that. 

You can imagine how this may become a problem when this software controls a vehicle at 70 mph on the highway. I am not skeptical about Google's ability to release robust software, but simply pointing out that releasing software is nothing like releasing a car.

The other issue is that flaws in software are not as easily detectable as mechanical failures. The reason is that it is possible to break a car apart, and examine the pieces one by one. It is easy to reverse-engineer a car. This is not possible for compiled software (although there are techniques that exist to decompile a program, and thus access parts of the source code, but big companies know how to protect against that).

In order to test the autonomous car, we can feed the program with a variety of inputs and check that the outputs are correct; but in the case of a self-driving car, the number of possible situations makes "unit testing" the program as a whole very tidious.

One possible way to go is to make the code open source. Everyone can look, test, and contribute to the code, making it more reliable and easier for third-parties to audit.

Seeing the trend for Silicon Valley players to open-source their precious algorithms, especially for deep learning and artificial intelligence (TensorFlow with Google, Torch and Big Sur for Facebook), I can imagine this happening for self-driving cars. There already exists an open source Robot Operating System (ROS) on which self-driving algorithms could be built.

Will the big players want to go with the open-source movement? I think so. This is an opportunity to gain trust from governments, the public, and create a community of supporters.

Why would they want to give up such amount of intellectual property developed over years of research? 

I think the answer is: because they have the data. The software does not run by itself. It is supported by huge amounts of data about the environment: the maps that run the car, the training images that the models use to recognize a pedestrian from a tree, or a stroller from a cardboard box, etc. Those who can extract meaningful knowledge from the world and feed it to the self-driving cars will probably be ahead of the competition.


