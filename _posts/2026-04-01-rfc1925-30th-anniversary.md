---
title: "RFC 1925 - 30th Anniversary"
date: 2026-04-01 19:00
categories: [neteng]
tags: [neteng]
---

RFC 1925 turns 30 today. Written by Jon Postel and published on April Fool's Day / 1 April 1996. The Twelve Networking Truths were framed as a joke. Thirty years later they read less like jokes and more like wisdom.

1. It Has To Work.

   > Of course it does, more so than ever. Reliability expectations only go in one direction.

2. No matter how hard you push and no matter what the priority, you can't increase the speed of light.

   - (2a) No matter how hard you try, you can't make a baby in much less than 9 months. Trying to speed this up *might* make it slower, but it won't make it happen any quicker.

   > Geographic latency hasn't changed, sure we have much higher bandwidth and newer technologies: interestingly, the first commercial deployment of DWDM was in June 1996, just a couple of months after the release of these rules.

3. With sufficient thrust, pigs fly just fine. However, this is not necessarily a good idea. It is hard to be sure where they are going to land, and it could be dangerous sitting under them as they fly overhead.

   > The everpresent gap between technically possible and operationally sound. There's never enough time to do it correctly, always enough time to do it twice.

4. Some things in life can never be fully appreciated nor understood unless experienced firsthand. Some things in networking can never be fully understood by someone who neither builds commercial networking equipment nor runs an operational network.

   > More relevant since the public cloud era. Experience operating them is genuinely valuable, but it's a different discipline to running physical infrastructure — that gap isn't always visible until it matters.

5. It is always possible to aglutenate multiple separate problems into a single complex interdependent solution. In most cases this is a bad idea.

   > I had to Google "aglutenate", turns out the typo is in the original RFC. The point remains: this is why the problem statement has to be clear before anything else.

6. It is easier to move a problem around (for example, by moving the problem to a different part of the overall network architecture) than it is to solve it.

   - (6a) It is always possible to add another level of indirection.

   > Tech debt before the term existed.

7. It is always something.

   - (7a) Good, Fast, Cheap: Pick any two (you can't have all three).

   > Start-ups land in public cloud on cheap and good, due to the low capital cost compared to standing up in a CoLo. Established enterprises see that success and adopt cloud as fast and good, then discover the bill for the workload volume. Cloud repatriation is evidence of that balance.

8. It is more complicated than you think.

   > Usually an unknown unknown — a bug, a constraint, or something nobody thought to document.

9. For all resources, whatever it is, you need more.

   - (9a) Every networking problem always takes longer to solve than it seems like it should.

   > In 2026 the network is faster and has more capacity than most private cloud workloads can reasonably consume, but "resources" includes time - see 2a. For 9a, this is where hindsight networking lives: the post-mortem where everyone agrees we should have got to the solution sooner.

10. One size never fits all.

    > Good enough is a legitimate destination. Chasing perfect standardisation is usually wasted effort.

11. Every old idea will be proposed again with a different name and a different presentation, regardless of whether it works.

    - (11a) See rule 6a.

    > Chassis switches will be fashionable again. Microservices will drift back toward monoliths. Distributed computing will be reinvented.

12. In protocol design, perfection has been reached not when there is nothing left to add, but when there is nothing left to take away.

   > This makes me laugh as we're still in the 'BGP all the things' era. MP-BGP, EVPN, RPKI — BGP has been accumulating rather than simplifying. BGP has survived this rule by ignoring it.

Reference: [RFC 1925](https://datatracker.ietf.org/doc/rfc1925/)

Thirty years is a long time. The kit from 1996 is either in a skip or a museum. 

The thought of a Nexus 7K coffee table is cool though, like the V12 one from Top Gear.
