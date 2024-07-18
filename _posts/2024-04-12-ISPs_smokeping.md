---
title: "Comparing ISPs with SmokePing"
date: 2024-04-11 21:00
categories: [homelab] # always lowercase, comma space seperated
tags: [neteng,homelab,monitoring,internet] # always lowercase, comma seperated
---

After my recent post about changing ISPs, I wanted to share some basic latency statistics between BT and Zen, using SmokePing.

I've got Smokeping setup in my Homelab pinging various endpoints, but having recently switched ISPs, it's interesting to see the difference between the two. All of my endpoints have similar results. Using Cloudflare and Google as examples here:

&nbsp;
&nbsp;

![BT_Zen_Cloudflare1](assets/images/BT_Zen_Cloudflare1.png)
![BT_Zen_Google1](assets/images/BT_Zen_Google1.png)

&nbsp;
&nbsp;
&nbsp;
&nbsp;


![BT_Zen_Cloudflare2](assets/images/BT_Zen_Cloudflare2.png)
![BT_Zen_Google2](assets/images/BT_Zen_Google2.png)

&nbsp;
&nbsp;

As you can see, BT is solid with almost no variation, whereas Zen does. Noticable side-by-side - more than likely the difference in hardware/ASICs.

This isn't a benchmark between the two. I mean, it's a ping test from a house in Manchester. 

Cool though right?

