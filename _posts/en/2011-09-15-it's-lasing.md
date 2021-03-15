---
layout: post
title: It's lasing!
name: its-lasing
comments: true
---

It took me more than a month to fully process my first quantum cascade laser. Do not think that it normally takes so long; I just had to do things slowly to learn them properly, but also I had to wait more than two weeks for one step to be done by someone else. It seems I am a bit too technical with my posts so I will try to reduce the amount of boring, meaningless words from now on.

I am sitting next to my experimental setup where a few minutes ago I **saw** my device lasing for the first time. It is fairly simple: a cryostat (to cool the sample down to 4K),  a thermopile (collects the radiation from the laser and converts it to voltage) and a few standard lab tools: an oscilloscope, a function generator and a lock-in. Oh, and obviously I needed pumps to evacuate the cryostat!

For the first time I saw LabVIEW being useful — I learned to use it at university but I cannot say we invented a wheel at that time and it was just a fun way of programming. Nevertheless, it is a powerful tool that allows me to do other things while it is collecting the data. I will try to make a few cosmetic improvements to the script later.

The final steps of processing are perhaps the most stressful, because you know that any false move can lead to destroying your samples. Wire bonding - connecting the laser with its package with a very thin gold <em>thread</em> - was the last of these. Fortunately, with a little help from Yash, my 250μm wide precious was given 11 beautiful bonds and it showed a few ohms of resistance across itself as a sign of happiness!

Now I need to measure it properly and then understand the figures, which will take me a few days. However, there are more devices to be processed so I won't be bored at all in the nearest future. I present my little friend to you:

{% include _figure.html src='samples/lasernablog.jpg' caption='The tiny dark rectangle with golden stripes is my laser.' %}