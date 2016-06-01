---
layout: post
title:  "Mapbox Drive challenges Here and Tomtom in ADAS maps"
date:   2016-06-01 10:00:03
categories: sdc maps mapbox
comments: true
---

![Mapbox Drive]({{site.baseurl}}/images/posts/mapbox.png)

Today, Mapbox introduced [Mapbox Drive][mapbox-drive], a new product designed to be embedded in cars to support lane by lane navigation and autonomous driving.

This is huge news. With this move, Mapbox enters the kingdom of automotive maps, now dominated by TomTom and Here. In the same way that they are now a strong competitor of Google for mobile and web maps, there is a good chance that they can shake the car maps industry as well.

For those who are not familiar with the company, Mapbox makes it easy to integrate, customize and display maps for mobile or web apps. Their maps are tweakable and most of their software is open-source, which makes them a developer's best friend. Whenever there is something that the Google Maps API does not offer, Mapbox lets you do it. Thanks to that approach, they have landed major customers like Pinterest, Foursquare, MileIQ, GitHub, etc. 

But today's announcement changes the image of the company from selling pretty maps to delivering a complete suite of tools for mobility - lane by lane directions, traffic, autonomous guidance, powered by tons of telemetry data. This comes in addition of their current satellite and streets products.

Their successful strategy with web and mobile maps may very well have the same success with car manufacturers and dashboard app developers. Mapbox makes the bet of building their products in the open and designs the easiest SDKs to integrate. This reputation and know-how should give Mapbox Drive an edge over the legacy mapmakers TomTom and Here. Their update cycles are slow, and their skills revolve around map creation, not so much map integration and delivery.

One other crucial difference between the established map companies and Mapbox is their autonomous driving strategy. [Here][here-hd-map] and [TomTom][tomtom-road-dna] are betting on HD maps that contain a 3D view of the world to provide accurate localization and navigation. This is intended for cars with high end hardware, in particular Lidar sensors, and requires powerful onboard computers to process 3D data. Those maps are extremely costly to build, and very heavy (in the order of gigabytes per mile). Mapbox made the choice to deliver centerlane geometries that are lightweight and built from crowdsourced data. Such a map could be delivered quickly and integrated right away with highway lane keeping technologies such as Tesla Autopilot or GM Super Cruise. Cars do not require HD maps to run those products. They are not even equiped with Lidar to consume HD maps anyway.

With this strategy, Mapbox might very well shortcut TomTom and Here to market in the highway autonomy space, especially because I hear that many manufacturers doubt the ability of Here to deliver their HD map anytime soon. Eric Gundersen, Mapbox CEO, disclosed that they already have one OEM which will integrate their Drive product by the end of the year.

A lot of this obviously sounds familiar for me as we are building trajectory maps for ADAS systems as well, here at [ExoNav][exonav] (check our [demo map][exonav-demo] built automatically from telemetry!). Hopefully this announcement will shake the mapping world and make the industry realize that this type of map product makes the most sense to bring automation forward. This way we can bring autonomous technology to market sooner, and finally be able to take naps on the highway.


[mapbox-drive]: https://www.mapbox.com/drive/
[here-hd-map]: https://company.here.com/automotive/intelligent-car/here-hd-live-map/
[tomtom-road-dna]: http://corporate.tomtom.com/releasedetail.cfm?ReleaseID=931327
[exonav]: http://exonav.com
[exonav-demo]: http://exonav.com/map


