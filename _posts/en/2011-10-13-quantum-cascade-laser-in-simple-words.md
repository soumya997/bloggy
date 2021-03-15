---
layout: post
title: Quantum Cascade Laser in simple words
name: qcl-simple-words
comments: true
---

I am afraid I haven't explained what a QCL really is. I will try to do so in simple words. Fellow physicists: please don't blame me for simplifications.

One of the most amazing technologies invented in the last few decades is definitely Molecular Beam Epitaxy - a technique that allows us to deposit unbelievably thin layers of elements like gallium, phosphorus or antimony. To create a wafer (a sandwich made of these elements) appropriate for a QCL, we need more precision than in other devices. A typical height of one layer of our sandwiches is of order of a few nanometres, and one sandwich consists of hundreds of layers!

Why couldn't we just use one material and don't worry about thickness? It's here when quantum mechanics needs to be mentioned. In the picture below you can see many rectangular shapes. These are intuitively called wells and barriers. If we consider such a well, we get a surprising result: electrons cannot increase their energy by any portion, but are confined to discrete (not continuous) set of states. We say that their energy is **quantized**. Hence in each well there is a ladder of states and an electron can only be on one of its steps. It's visible when you look at the tails of orange lines - they indicate where each electron level is. I should mention that wells' depth and barriers' height represents energy while the real space is drawn horizontally so when electron travels through the structure, it goes from left to right.  Now, why the diagram is diagonal? Because we apply voltage to our structure and it pushes our carriers - electrons - in the right direction.

{% include _figure.html src='drawings/3qw-qcl.png' caption='The quantum cascade structure' %}

How does an electron go through a barrier? This is the tricky part which I don't feel competent enough to explain here. Going through the barriers is the crucial element of QCL design and researchers around the world are constantly searching for the best solution. You could think that they jump over the barriers, but this is not the case. In quantum mechanics, it's possible that they actually go through or **tunnel**. In the picture you can see wavy shapes - these are **wave functions** of electrons. If there are two "hills" emerging from two different lines in one well, it means that an electron can mysteriously go from one well to another.

A laser emits radiation. In this case, it is radiation of a fairly low energy (200-400 times lower than that of visible light). When is it emitted? As an electron goes from left to right, with each transition they jump down, which means they lose energy. It can be passed to the electron's environment, but sometimes it is emitted as a **photon** (as radiation). The whole designing process is about controlling the widths of wells and barriers. As you can imagine it is a very complex task, because one variable (width) corresponds to many effects (emitted energy, tunnelling mechanism, thermal properties etc.).

I hope it makes sense even if you are not a physicist. Next time I will describe how to make such a structure a working device that you can plug in and turn on, provided you have some spare liquid helium around.
