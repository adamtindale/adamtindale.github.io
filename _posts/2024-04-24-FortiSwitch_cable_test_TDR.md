---
title: "FortiSwitch Cable Diagnostics (TDR)"
date: 2024-04-24 08:45
categories: [neteng] # always lowercase, comma space seperated
tags: [neteng,homelab,fortiswitch,monitoring] # always lowercase, comma seperated
---

How to run a cable diagnostic test using a FortiSwitch, either managed by a FortiGate or individually:

## Managed FortiSwitch:

```console
exe switch-controller switch-action cable-diag <FortiSwitch SN> <port>
port<#>:  cable (4 pairs, length +/- 10 meters)
        pair A Ok, length 20 meters
        pair B Ok, length 22 meters
        pair C Ok, length 22 meters
        pair D Ok, length 20 meters
```
&nbsp;
&nbsp;

## Individual FortiSwitch:

```console
dia switch physical-ports cable-diag <port>
port<#>:  cable (4 pairs, length +/- 10 meters)
        pair A Ok, length 20 meters
        pair B Ok, length 22 meters
        pair C Ok, length 22 meters
        pair D Ok, length 20 meters
```

&nbsp;
&nbsp;

> The slight difference in length of the pairs you see in my example are due to the twists within the physical cable. All 4 of the pairs are twisted differently/unequal, this helps reduce crosstalk/interference.
{: .prompt-tip } 
