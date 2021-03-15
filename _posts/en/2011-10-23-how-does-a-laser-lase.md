---
layout: post
title: How does a laser lase?
name: how-laser-lases
comments: true
---

How do I know that my laser works properly? Obviously, I have to measure it somehow, because a human eye (or rather **any** eye) can't see this radiation. In the group, we conduct a few different experiments on QCLs. The simplest one is an LIV (Light-Current-Voltage) characteristics - resulting data indicates whether the laser emits any radiation and for what current the emission is the strongest.

Firstly, I have to mount a device on a cryostat. The end of the cryostat is called a cold finger. As both names suggest, they are used to cool down whatever we place on them - we do it by filling a cryostat with liquid helium (which has a temperature of around 4.5K or -269C), but it does not fill the chamber where the sample is, because that could spoil our measurement. The cold is transferred to it (just as heat is) by a narrow, metal part, hence the name cold finger. Before I put the cryostat on an optical bench, I have to make sure there are no broken connections by simply measuring the resistance across the device using a multimeter.

{% include _figure.html src='samples/zimnypalec.jpg' caption='Cold finger' %}

The cryostat has four windows through which radiation is coming out. Before an LIV measurement, I remove one window and mount a thermopile in its place. No, I am not talking about <a title="Thermopylae" href="http://en.wikipedia.org/wiki/Battle_of_Thermopylae" target="_blank">Greek history</a> here - a thermopile is in fact a pile of thermocouples, which are a kind of thermometers. When a laser is emitting radiation onto this detector, there is a small (because my lasers' output power is only of the order of milliwatts) change in its temperature, which is then converted to voltage.

What useful information I can get from such measurement? Although I will only know my device's power in some arbitrary units, I can determine the current at which it lases with the maximum power, i.e. when it is properly **aligned** see the picture in the [previous post]({% post_url 2011-10-13-quantum-cascade-laser-in-simple-words%}) - in other words it lases best for a particular slope of the diagram, which is controlled by the current). Also, I repeat the experiment in different temperatures to see when it is too hot for the laser to work. Finally, by looking at the features of the plot, we can learn about general behaviour of the laser: what is the range of currents for which it is working, whether there are any additional wavelengths emitted, what is its resistivity and so on. Below is an LIV plot of my first QCL. It is a two colour design, so you can see a second, much smaller hill on the right - this is where the second colour (frequency) is switched on. The upper lines pertain to current-voltage characteristics.

{% include _figure.html src='drawings/myfirstliv.png' caption='LIV of my laser' %}