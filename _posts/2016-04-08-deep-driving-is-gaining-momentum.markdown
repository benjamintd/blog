---
layout: post
title:  "Deep Driving is Gaining Momentum"
date:   2016-04-08 10:00:03
categories: sdc deeplearning
comments: true
redirect_from:
    - "/deep-driving-is-getting-momentum/"
    - "/deep-driving-is-getting-momentum"
---

![George Hotz in his test car]({{site.baseurl}}/images/posts/comma.png)

A few news hit the self-driving car world this past week. On Monday, comma.ai secured a $3.1 million investment from a16z.
On Tuesday, Nvidia was holding a GPU conference with a particular focus on self-driving technology, where they announced their DaveNet neural network.

What do those two events have in common and why is this a big paradigm shift in the way we think about self-driving tech?

Both [Nvidia][Nvidia-main] and [comma.ai][comma-main] are experimenting with an end-to-end driverless car system controlled by a single (deep learning) neural network - although I'm unsure about comma, that's what I inferred from CEO George Hotz's interviews so far. These networks are trained to link a sensory input - mostly pixel data from various cameras around the car - to a control output - steering angle, acceleration/deceleration. The only design step needed to engineer such a system is to write the deep learning model, which leads to much smaller amounts of code than traditional approaches.

This is opposed to a roboticist way of tackling the problem, composed of these different steps:

* localize yourself on a map

* model your environment and external agents

* forecast their future behavior

* plan your actions in consequence, with rule-based algorithms

* Act on your plan.

This approach comes from a long legacy of DARPA challenges at a time where Deep Learning was not really a thing (and computers not powerful enough for it anyways).

Now we are dealing with potentially much simpler algorithms. Don't get me wrong, though. Building such a deep network is not an easy task. Driving is way more complicated than other computer vision applications like image classification, because of the time component involved. On top of that, because it is meant to be a safety-critical feature of a car, there are problematic issues of performance. Inference must be done in under 10-15 ms, which is flirting with the limits of current GPUs (especially if your input is a time series of 8 camera feeds). If you want real-time training, this becomes even harder.

But once such an architecture is defined, what remains is training, training, and more training. These videos ([here][comma-video], and [there][Nvidia-video]) show that Nvidia and comma.ai's networks start doing pretty well.

# "I'm coming for you, Tesla, Google."

... says George Hotz. Is the traditional approach to self-driving software becoming irrelevant as "deep driving" improves? I cannot say for sure, but there will be some important barriers to overcome in order to make this work.

The first one I see is testability and reliability. Because we are no longer using rule-based code to determine which actions to take at a particular moment, it becomes difficult to debug a particular misbehavior from the system. We can train a car on instances of this problem until it does not pop up anymore, but there are no strict guarantees that the problem is solved.

On the same note, getting official approval to get these systems on the road may be difficult, if lives are at stake. Given that control systems in airplanes rely on 20 years old research because more recent approaches are too difficult to test, I do not know how well deep networks will be received by safety and regulatory organizations.

Finally, embedding road policies in those systems may be hard; we can never be sure that training examples that respect the law will yield an AI that always respects the law, as it remains a statistical process after all. In a way, this is probably fine because human driving requires to break the rules from time to time.

# Deep building blocks

However, it is not unconceivable to have parallel systems running for autonomous driving, and look for concensus between both - just like in airplanes, where two separate implementations of the same control system are required for redundancy. Deep driving could serve as a backup or confirmation for a traditional system, for instance in poorly mapped areas.

Additionally, the deep learning approach already exists in the driverless tech today. Recognizing cars, traffic signs, pedestrians, etc. is already done with neural nets. Going further, autonomous driving will realistically be a mix of rule-based models with deep learning building blocks: object recognition, pedestrian intent detection, object motion tracking and predicition, or even self-localization could be achieved by deep learning, all of which would serve as input for the model of a rule-based path planning algorithm.

I am curious to know what this approach will give in the future. It is certainly receiving a lot of attention lately, and may one day become the standard for self-driving technology. Several other automakers are making that bet by teaming up with [Berkeley Deep Drive][deep-drive], including Ford, Toyota, Volkswagen.

# Some reading about Deep Learning

I've been trying to learn about deep learning lately. If you are interested in knowing more about the topic, I recommend reading the following material:

* This [Deep Learning book][dlbook] is the best introduction to the neural nets and deep learning I have read so far

* [A tutorial focused on Convolutional Neural Nets][deeplearninglenet], using Theano

* Some more involved [Stanford lecture notes][231n] on the same topic, which points you to other great resources

* [A paper on object detection][objdetect] by the guys who created the Caffe framework

* [A mind-blowing project on Recurrent Neural Networks][rnn]

* On the artistic side, I liked [this video][netvideo] (not technical, but impressive. Check what's after 8:40) and [this paper][neural-style] on pasting an artist's style onto a normal picture - example below.

![Homemade neural style - Can you recognize the artist? :-)]({{site.baseurl}}/images/posts/neural-style.jpg)
*Can you recognize the artist?*

If you want to get cranking on some code, looking at documentations for [Caffe][caffe] or [Lasagne][lasagne] is a good place to start. As a Python guy those are the frameworks that I want to learn.

[Nvidia-main]: http://www.nvidia.com/content/global/global.php
[comma-main]: http://comma.ai/
[comma-video]: https://www.youtube.com/watch?v=YjTnYBaQQpw
[Nvidia-video]: https://youtu.be/KnVVJSIiKpY?t=3751
[deep-drive]: http://www.bloomberg.com/news/articles/2016-03-16/automakers-go-back-to-school-to-learn-to-build-self-driving-cars
[caffe]: http://caffe.berkeleyvision.org/tutorial/
[lasagne]: http://lasagne.readthedocs.org/en/latest/user/tutorial.html
[dlbook]: http://neuralnetworksanddeeplearning.com/index.html
[231n]: http://cs231n.github.io/
[objdetect]: http://www.cv-foundation.org/openaccess/content_cvpr_2014/papers/Girshick_Rich_Feature_Hierarchies_2014_CVPR_paper.pdf
[deeplearninglenet]: http://deeplearning.net/tutorial/lenet.html#lenet
[rnn]: http://karpathy.github.io/2015/05/21/rnn-effectiveness/
[netvideo]: https://www.youtube.com/watch?v=0qVOUD76JOg&list=WL&index=24
[neural-style]: http://arxiv.org/pdf/1508.06576v2.pdf

