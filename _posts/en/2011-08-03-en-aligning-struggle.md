---
layout: post
title: Aligning struggle
name: aligning-struggle
comments: true
---

I have just realised that it has been two weeks since I last wrote... that is because I started my first QCL device processing a couple of days ago and spent most of my days in the cleanroom. Now I have some experience, a few pictures and a lot to write about!

I am becoming more confident with mask aligning and developing now, but there were days when I spent 3 hours trying to move a step forward with no results. Yash leaves me alone now so that I can be independent which is great, but it also allows me to make mistakes that I would not have made if I had asked him. Let me tell you the story of the alignment...

The first one is a piece of cake. It is called an etch bead removal: we leave a big undeveloped square in the centre of our sample, removing the resist on the corners (because it forms beads that may interrupt the next steps). The next one is quite important, because the etched ridge (the core of my device) is defined by it. However, there are still no reference points to align to so it does not have to be ideal. The image below shows an n+ sample after the ridge pattern developing. n+ means that it is only a doped GaAs substrate and there is no QCL wafer structure in it. This sample serves only for tests - I do everything on this one before moving to the others to see if everything works fine.

{% include _figure.html src="samples/n_1st_developing.png" caption="n+ sample after 1st developing" %}

Then comes the etching, of which I have already wrote [a few words]({% post_url 2011-07-19-en-etching %} and I will write more because I know it better now. After etching, I had to align a mask for bottom contacts placed on either side of the ridges. On Friday I spent 3 hours trying - every time I looked at it under the microscope, it was completely misaligned and one of the bottom contacts was closer to the ridge than the other. You can repeat it as many times as you want, but it takes time: cleaning with acetone and [IPA](http://en.wikipedia.org/wiki/Isopropyl_alcohol), spinning, aligning, 5 minutes in chlorobenzene, 2-3 minutes developing, 2-3 minutes cleaning. Altogether one repeat took me almost 1 hour. As I am not allowed to stay after 5:30pm., I went home and continued on Monday morning. Somehow I managed to align the n+, but my real samples only made me feel miserable. When Yash came, we realized that I had been using a wrong size of the pattern: there are 5 or 6, each designed for different width of the ridge. How come I had not noticed it before? I think I just forgot that Yash told me they were different sizes.

Now, when I knew which pattern to use, things began to go smoothly... Or at least a bit faster than before. Developing itself is tricky, because the time needed to fully develop the resist varies from one sample to another. For example, the image below shows an underdeveloped one:

{% include _figure.html src="samples/4or5_2nd-developing_underdeveloped.jpg" caption="Underdeveloped sample." %}

>You can see two other contacts (the top stripe and a part of the bottom one) that are fully developed, therefore it was unexpected to see only one underdeveloped. Fortunately, it only takes 5 more minutes to repeat this step. After that, I evaporated metal (AuGeNi) on my samples, but I will describe it in another post. Once it was evaporated, guess what I could practice... more aligning and developing! This time the former went smoothly - I even used a mask aligner that nobody seems to prefer, although I do not know why. See below what happened next: the stripe on the ridge was perfectly developed but the resist looked really weird. We changed chlorobenzene and developer for fresh ones. The resist was changed earlier that day. We redid the process with the same result.

{% include _figure.html src="samples/nplusweird.jpg" caption="Something happened to the resist." %}

Confused, we tried another resit (1828, the thickest we use) and finally we got what we wanted. although still not understanding why it went wrong. Then I faced yet another strange behaviour: I had to redevelop it for 5 times before the resist completely went off! So it took 8-9 minutes, whereas normally 1-2 is sufficient. Ladies and gentlemen, I proudly present my sample ready for top contact evaporation! If you look close, you can see that there is a bright stripe developed on the ridge (the middle rectangle). On the right side of the ridge, there is a small dot of remaining resist, but it does not matter as it will be cleaved later.

{% include _figure.html src="samples/nr4_topcontacts_developed.jpg" caption="After three days of processing." %}