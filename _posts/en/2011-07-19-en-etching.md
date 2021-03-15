---
layout: post
title: Etching
name: etching
comments: true
---

This is the second part of [this story]({% post_url 2011-07-13-en-cleanroom-hemt %}). When the mask and the sample are aligned, the latter has to be exposed to UV light for a few seconds. We use a positive resist, which means that we want exposed parts of the sample to vanish during the next step, namely "developing" (sounds a bit like old-school photography, doesn't it).

All the chemical steps of the process are done on a wet bench, that is a small, partially closed area with conditioning system to remove fumes and toxic gases. The sample is immersed in a developer which dissolves the UV-exposed parts of the resist. Then I can check if everything went well under a microscope. There is an interesting invention involved in this part of processing: a DI weir. It checks the purity of deionized water by measuring its resistivity. Pure DI water should show around 18MΩ·cm, so we put the sample on a tray and insert it into the weir, obviously contaminating the water and increasing its resistivity. We usually wait until it goes back over 10MΩ·cm - then we can assume that the sample is clean.

Another interesting fact about the UV lithography room is that it is yellow. It has filters on all windows (a kind of filtering foil I think) to prevent the high-energy part of the Sun radiation from penetrating our samples. One feels as if in one of van Gogh's paintings. I am sure people sometimes leave the room with their samples in their hands before developing... Fortunately, you only have to clean the resist and spin it again if you do that.

{% include _figure.html src="samples/hemt_after_developing.png" caption="Developed sample with some resist debris." %}

Next comes a step in which timing is essential: etching. Sometimes you have to re-etch a few times before you can proceed, because etching time is not always the same. I haven't figured out yet what exactly can affect the etching rate, but the trivial answers should be: impurities and material properties. Wet etching, as opposed to dry etching, is anisotropic - it means that the walls of my device will be diagonal (see the picture below). To check if our structure was etched properly, we use a clever tool called DEKTAK, a stylus profilometer. I had thought that measuring surface roughness with nanometre resolution was done only with AFM/STM so I was surprised when I saw their ancestor in operation! I wonder what drawbacks it has: does it damage the sample? How is the movement of the stylus detected? I have to find out.

{% include _figure.html src="drawings/etching_wet-chemical_vs_rie_de.png" caption="Notice that the etched walls are sloped." %}