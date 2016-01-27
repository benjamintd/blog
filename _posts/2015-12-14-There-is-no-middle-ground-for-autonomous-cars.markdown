---
layout: post
title:  "There is no Middle Ground for Autonomous Cars"
date:   2015-12-10 10:00:03
categories: sdc maps
comments: true
---

On many articles that I read about self-driving cars, there is this timeline that shows the different steps towards a fully autonomous vehicle. It first starts as a highway cruise mode, such as Tesla's Autopilot, then progresses to more and more autonomy, with the user having to intervene every 10 miles, 100 miles, 1000 miles until we reach a Google-like future with no wheel and pedals at all. This timeline always looks progressive. There is now a commonly accepted grade of autonomy, on a scale from 1 to 4. I think the road to self driving cars will not be that smooth and continuous.

I believe the reason is not that the product will not be ready or unsafe, but rather that the customers are not ready (nor safe).

# Trusting technology is easy
Take a look at what is happening right now. Even in a setup where customers are aware that the autopilot is only an assistance system, and are liable for any damage that it might cause, drivers start looking away. We have seen [videos][tesla backseat] of Tesla users leaving the front seat or engage in dangerous behaviors, to the point that the company may release an [upgrade][tesla upgrade] that limits the software's capabilities on certain roads. The lesson here is that trusting technology is incredibly easy once we see it working. The users are not to blame if they toggle the autopilot to focus on something else than boring highway driving. What is the point of having an autopilot if you still have to concentrate on the road as much as if you were driving yourself? The issue is that human drivers will still be required to keep an eye on the road, even though interventions from them will be less and less needed as technology improves. Those behaviors will happen even more when failure rates drop down to one in a thousand miles, leading to easily avoidable accidents.

This problem of losing attention does not occur in a fully autonomous car, where users are not expected to take over the vehicle at any time. Until we build such a car, drivers will need to remain focused on the road and detect system failures, however rare they can be. Therefore, the transition from autopilot as an assistance system to a fully autonomous car cannot be smooth, from the driver's perspective: you either have to remain master of your vehicle at all times, or are allowed to sleep while on the highway.

In my opinion, users should never have to watch for system failures in autonomous mode. There is only one way this can happen: if the system never fails.

# Achieveing reliability with maps
How can we be sure that the system never fails? Until we figure out how cars can handle any situation perfectly, we have to limit their scope.
Take the example of autonomous buses, that start arriving in [Switzerland][swiss buses], France, and the [US][us buses] to name a few. This is a perfect example of a limited scope with control on the environment (think theme park shuttles, airport buses, etc.). The limited area makes it easier for the bus to perfectly know its surroundings, and makes testing and quality assurance easier. In the same fashion, it is possible to operate self-driving taxis for known origins and destinations, as it is planned for [Tokyo Olympic Games][tokyo games] in 2020. In all of these situations, the user is never in control of the vehicle, and failures become virtually impossible due to specific knowledge about the environment. Those vehicles reach full autonomy, but on a limited scope.

I guess the point is that the required reliability for full autonomy will only come with an extended knowledge of the environment. All achievements in difficult settings have been made possible by having highly accurate [prior mapping of the area][mapping]. The usual approach is to have a 3D map of the environment, that enables high-precision localization. These maps are costly to make because every street needs to be surveyed regularly, with expensive equipment (Lidar, especially). This is ok to do for a few bus routes, but regular updates of all the network will be extremely expensive and time-consuming. Hopefully, better and cheaper localization can be achieved in the future when the costs of hardware decrease, which will allow more vehicles to contribute to the effort of 3D-mapping the world.

This map is a static view of the world and is a way of making up for the inherent GPS imprecision and add infrastructure information such as lane markings and obstacles. 

I believe there is a second, underestimated layer of mapping necessary for a self-driving car to navigate this static infrastructure. This is a behavior layer that would describes how objects move in the infrastructure space. Of course, I am biased by the fact that I am building [such a map][vds], but think about it: because of the large taxonomy of intersections, it is unrealistic to try to handle every situation through a single software that remains testable and maintainable (although guys at [NuTonomy][nutonomy] are trying to tackle the complexity issue). However, I think we can know a lot about an intersection before being on the spot and use sets of rules coupled to captor information to know how to behave in that specific context. What are the possible maneuvers? Are the vehicles around me following a known trajectory? Where am I supposed to stop in order to make that left turn? Can I predict the intents of the other drivers?

This information can also be surveyed (as Nokia Here is doing with their [HD map][hd map]), but with some care it can be extracted simply from observing real drivers behave. We can do this from the extraction of GPS traces from those vehicle, and perform some statistical analysis to cluster them into meaningful reference trajectories and maneuvers. This layer can serve as a backup or a template behavior to adapt in specific situations. Furthermore, it is self-validating and scales cheaply. 

This layer has the potential to bring the reliability of self-driving cars to the level where you can finally sleep during your daily commute, by giving context awareness to the vehicle, and help cross the huge gap that I think there is from limited assistance systems to fully autonomous vehicles.

[tesla backseat]: https://youtu.be/-okFVuHlxII?t=50
[tesla upgrade]: http://mashable.com/2015/12/11/tesla-restrict-autopilot-report/
[swiss buses]: http://www.digitaltrends.com/cars/first-autonomous-buses-debut-in-spring-2016/
[us buses]: http://gizmodo.com/the-uss-first-autonomous-buses-will-drive-around-a-cali-1734989938
[tokyo games]: http://www.japantimes.co.jp/news/2015/10/04/business/tech/self-driving-cars-let-tourists-ride-tokyo-2020-abe-says/#.VnSIOnUrI8o
[mapping]: http://www.gizmag.com/self-driving-car-mexico/40013/
[vds]: http://www.vds-corp.com/products/
[nutonomy]: http://nutonomy.com/
[hd map]: http://www.slashgear.com/inside-the-nokia-here-hd-maps-putting-google-on-notice-18325742/


