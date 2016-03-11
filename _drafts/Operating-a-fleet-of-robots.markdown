---
layout: post
title:  "Operating a Fleet of Robots"
date:   2016-03-14 10:00:03
categories: sdc operations
comments: true
---

![Robot Taxi]({{site.baseurl}}/images/posts/robottaxi.jpg)

Making a car drive itself is basically a solved problem. By that I mean that it is only a matter of time before we are able to make a robot drive in most situations, while being at least an order of magnitude safer than a human. How long it will take is still open for discussion: Elon Musk - optimistically - says we will reach that point [by 2018][musk-2018], Continental says [2025][2025ad] will be the year of automated driving, Google's jobboards suggests that they are bulking up for vehicle design and going out of R&D, and outsiders like [Zoox][zoox] market a 2020 goal. Recent improvements in machine vision performance suggest that there are no more technological barriers to reaching this goal - at least conceptually. What it will take is lots of engineering manhours, testing and [mapping][mapping], but we will get there eventually.

The next step is the exciting part. Now that I have autonomous cars, how should they be operated?

First of all, I strongly believe that self-driving vehicles will be mainly used as a service, not owned. Japan's [RobotTaxi][robottaxi], Uber, Zoox and Google tend to agree with me on this point (or is it the other way around?). So let's assume from here on that we are in control of a few hundred fully autonomous cars in a given city. Suppose you also have a Uber-like app that allows anyone in town to order a self-driving taxi instantly. How do you build the system that coordinates your fleet and dictates where each individual vehicle should go?

Thinking about the complexity of this problem gives me chills.

# How is this different from what Uber already does?

In a way, being in control of all your fleet should be easier than relying on drivers that take their own decisions, right? There is no uncertainty about the number of drivers on the road, whether they will pick up the next rider or take a break, etc. You have full control on each of your vehicles. But there is a good thing about Uber drivers: they can make decisions on their own.

They decide when it is time to fill up the tank, start or stop driving, when to pick up a passenger or not. The more they drive, the better they know how to optimize their revenue by remembering the best time slots and neighborhoods. This may not be optimal from Uber's point of view, but what choice do they have?  What is left to them is only adapting the prices to balance the offer and demand.

I do not want to take away any credit to Uber and Lyft for what they achieved in that field, because this dynamic pricing problem is hard. However, it leaves a good part of the "computation" up to the drivers, since each individual driver makes decisions on their own. When operating a fleet of autonomous taxis, it will be up to the operator to take those decisions, which adds a big computational overhead for the operator.

One solution would be to model the behavior of a single driver, program it into each of the cars, and use the same kind of algorithms as Uber to run a fleet of robot taxis where each vehicle take actions on its own. Easy, but not optimal.

A second solution is to have a central system that controls all vehicle flows.

# One brain to rule them all

This is where you start having chills as well, don't you? It's like having to solve hundreds of [travelling salesmen][tsp] at once with dynamic demand, while handling battery charging (or swapping, more realistically), dispatching your idle vehicles across the city to match demand forecasts, minimizing waiting times, all with uncertainty in the demand and travel times. There is also some tricky [facility location][facility-location] problems coming into play in order to chose where to place the charging stations and parking spots. All of this with demanding performance and reliability constraints  This is a really, really hard optimization problem. As an Operations Research engineer, I am torn between fear and excitement when I think about it.

I think this will be a big challenge to take on when fully autonomous taxis reach the market. Some folks have started working on it, like Improbable with their [SpatialOS][improbable]. Having a central Operating System monitoring an entire city's mobility could be really powerful. It would allow to have faster, balanced flows while reducing infrastructure and using less energy.

However, looking at the bigger picture, there are some tough design decisions to make when designing these algorithms. The fundamental question is: what do I optimize for?

Am I willing to let some customers take a longer ride, for the greater good of the city's flows? Do I sacrifice service level to focus on dense neighborhoods with a higher yield? It is unclear that optimizing for revenue only will push towards the big vision of cheap, on-demand mobility for all. Governemental or local agencies should have their say in managing those flows. Otherwise some areas will be under-served, leaving people behind in this revolution.

# Integrating fleets of robot taxis in the city

Ultimately, on-demand mobility will have to integrate with the existing infrastructure - rail networks for instance - for improved multi-modal transportation and better accessibility. Autonomous driving has the potential to be the cheap last-mile transportation mode that does not exist yet: taxis are expensive, bicycles are not always convenient, and buses are always late on schedule. This integration will need a powerful central engine that can forecast flows and operate these vehicles seamlessly. Built the right way, such central system could save us energy, square footage of parking space, and a *lot* of time. 

Even more interesting will be the mutation of the cities around this mode of transportation once it is established. Most cities today are built to accomodate for cars. What happens when nobody owns a car anymore? More free space, pollution rates go down, people are happy. The design of cities will have to change accordingly, and this is a good thing. The faster we can figure how to deploy and operate large fleets of self-driving cars, the sooner we can start this joyful transition. 


[mapping]: {{site.baseurl}}/There-is-no-middle-ground-for-autonomous-cars/
[musk-2018]: http://www.theverge.com/2016/1/10/10746020/elon-musk-tesla-autonomous-driving-predictions-summon
[2025ad]: https://www.2025ad.com/
[zoox]: http://zoox.com/
[robottaxi]: https://robottaxi.com/en/
[tsp]: https://en.wikipedia.org/wiki/Travelling_salesman_problem
[facility-location]: https://en.wikipedia.org/wiki/Facility_location_problem
[improbable]: http://www.traffictechnologytoday.com/news.php?NewsID=77573
