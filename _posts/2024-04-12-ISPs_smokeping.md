---
title: "Comparing ISPs with Smokeping"
date: 2024-04-11 21:00
categories: [NetEng, Homelab] # always lowercase, comma space seperated
tags: [internet,homelab,monitoring] # always lowercase, comma seperated
---

# Comparing ISPs with Smokeping
After my recent post about changing ISPs, I wanted to share some basic latency statistics between BT and Zen, using Smokeping.

I've got Smokeping setup in my Homelab pinging various endpoints, but having recently switched ISPs, it's interesting to see the difference between the two. All of the endpoints have similar results:

![BT_Zen_1](assets/images/BT_Zen_1.png)

![BT_Zen_2](assets/images/BT_Zen_2.png)

As you can see, BT is solid with almost no variation, whereas Zen does. Noticable side-by-side - more than likely the difference in hardware/ASICs.

This isn't a benchmark between the two. I mean, it's a ping test from a house in Manchester. 

Cool though right?

