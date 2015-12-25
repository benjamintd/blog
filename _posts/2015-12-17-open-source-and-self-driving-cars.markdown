---
layout: post
title:  "Open Source, Software, and Self Driving Cars"
date:   2015-12-17 10:00:03
categories: sdc open-source
comments: true
---

The automotive industry is entering a weird era. There was a time when engineering and manufacturing a good car was hard, and good practices were still to be established. Those who were the best at it stood out and became the giants that we know: GM, Ford, Toyota, etc. This industry is now mature: cars have not changed so much in the last two decades if you compare to the technology improvements - at least from the user's perspective. Changes to new models are mainly incremental details in the industrial design, or adding new minor options.

On the other hand, the industry is on the verge of a huge disruption, with self-driving cars. The current development of autonomous vehicles shows that software companies are the most likely to win the race to market. Google, Baidu, Tesla, Apple... Engineering a self-driving software has become the hard problem, and those who are the best at it will stand out.

This raises a number of issues, because the software industry is so radically different from the automotive industry. The first main difference is testability. A number of independant organizations are dedicated to testing cars, to assess their resistance to crashes (IIHS) and to give them accreditation for release. Even though audits are frequent in the software world, there is still no external entity dedicated to testing self-driving software. 

Of course, there are tons of tests done in-house, but consuming software relies a lot on trust, for most common users. I trust Google that their security engineers protect my data efficiently. I trust Microsoft that my Powerpoint will not crash in the middle of my presentation. The truth is, there has been no third party between Google and me to certify that their software update is safe for me. Even though audits are frequent, and there exists security labels (SOC3), not every release is tested externally, as opposed to car models. There is no quality label other than their brand name that can assure that it works as advertised. Software updates are so frequent that it is impossible to review their reliability one by one, externally. 

You can imagine how this may become a problem when this software controls a vehicle at 70 mph on the highway. I am not skeptical about Google's ability to release robust software, but simply pointing out that releasing software is nothing like releasing a car. It is true that safety critical software is released for airplanes and air traffic control, and they are tested thoroughly. However, there are enormous constraints on these models, for instance on the types of algorithms that are authorized. As a result, the models used for control inside commercial planes are decades old, while state-of-the-art research is way ahead. This is not a bad thing for safety, but I cannot imagine self-driving car software to be bound to the same constraints. I think deep learning and image recognition algorithms that are used in current prototypes are not as easy to approve, since their efficiency depends so much on how they are trained, and there fore are less predictable.

The other issue is that flaws in software are not as easily detectable as mechanical failures. The reason is that it is possible to break a car apart, and examine the pieces one by one: it is easy to reverse-engineer a car. This is not always possible for compiled software. In order to test the autonomous car, we can feed the program with a variety of inputs and check that the outputs are correct; but in the case of a self-driving car, the number of possible situations makes "unit testing" the program as a whole very tidious.

One possible way to go is to make the code open source. Everyone can look, test, and contribute to the code, making it more reliable and easier for third-parties to audit, and for engineers to try to break (breaking things is good, because it shows a fix is needed). Moreover, this may push the industry to adopt a sngle core system instead of each developping its own. This would improve both the time to market and the reliability.

Seeing the trend for Silicon Valley players to open-source their precious algorithms, especially for deep learning and artificial intelligence (TensorFlow with Google, Torch and Big Sur for Facebook...), I can imagine this happening for self-driving cars. There already exists an open source Robot Operating System (ROS) on which self-driving algorithms could run, and the opportunity for an open-sourced robotic environment is big.

Will the big players want to go with the open-source movement? I think so. This is an opportunity to gain trust from governments, the public, and create a community of supporters.

Why would they want to give up such amount of intellectual property developed over years of research? 

I think the answer is: because they have the data.

The software does not run by itself. It is supported by huge amounts of data about the environment: the maps that run the car, the training images that the models use to recognize a pedestrian from a tree, or a stroller from a trash bin... Those who can extract meaningful knowledge from the world and feed it to the self-driving cars will probably be ahead of the competition. And why not give the software for free when the map that the software runs on needs a subscription?

The future might prove me wrong, but as a believer in open source and self-driving cars, I can see the big potential of those two worlds colliding.

