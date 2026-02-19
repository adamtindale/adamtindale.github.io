---
title: "Would Cisco buy Nutanix? The fallout from Broadcom acquiring VMware"
date: 2026-02-19 08:00
categories: [infrastructure] # always lowercase, comma space seperated
tags: [cisco, nutanix] # always lowercase, comma seperated
---

The Broadcom acquisition of VMware handed every HCI competitor a gift. The question was who was positioned to actually catch it.

The price hike coverage has been thorough — enterprise customers on VMware facing significant licensing uplifts isn't news at this point. What's less discussed is where the displaced workloads actually went, and what that movement might mean for Cisco.

Proxmox absorbed much of the SMB displacement — the shops that just needed a hypervisor and weren't going to pay enterprise rates for anything. Nutanix is the more interesting story, because it's where the enterprise workloads went.

Look at what Cisco has done over the past couple of years and a pattern emerges. May 2024: Nutanix validated on Cisco UCS. May 2025: Nutanix opens to all external storage, with Pure Storage named as a strategic partner, breaking from its traditional hyperconverged-only model. January 2026: Cisco, Pure, and Nutanix jointly announce FlashStack — a validated reference architecture that will feel familiar to anyone who lived through the FlexPod era. Three moves. Each one tightening the same triangle.

Cisco UCS has fallen out of favour — including, by most accounts, within Cisco itself. The Nutanix validation gives UCS a credible new story at exactly the moment it needed one.

On the storage side, the move to support external arrays is significant for enterprises that were blocked from Nutanix by existing storage investments. The Pure partnership is a natural fit. Pure supports Fibre Channel, but the industry direction is clearly toward IP — something Pure has been leaning into heavily, not least through its collaborations with Arista around AI infrastructure. That aligns well with where Nutanix has always stood. For shops running FC fabrics, Nutanix's firm IP-only position remains a real blocker worth factoring into any migration plan.

So, would Cisco buy Nutanix? My instinct is no — not yet, and possibly not at all. The FlashStack announcement gives Cisco most of what it needs from a go-to-market perspective without the acquisition risk. Nutanix's value to Cisco is highest when it remains independent and multi-vendor. The moment Cisco buys it, half the customer base starts wondering if they've just traded one lock-in for another.

That said, the numbers aren't prohibitive. Nutanix's enterprise value sits at around $10-12bn in early 2026. Cisco paid $28bn for Splunk. If the strategic logic shifted — say, if HPE or Dell made a move — Cisco has the balance sheet to respond quickly.

That scenario would not be good news for existing Nutanix customers — the ones who ran the VMware migration and are still living with the fallout. Imagine running it twice.
