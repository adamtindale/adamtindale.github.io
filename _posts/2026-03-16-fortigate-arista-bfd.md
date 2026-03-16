---
title: "Default BFD timer mismatch: Arista EOS and FortiGate"
date: 2026-03-16 18:00
categories: [neteng] # always lowercase, comma space seperated
tags: [arista, fortinet, fortigate, eos, fortios] # always lowercase, comma seperated
---

When configuring BFD between platforms, matching timer values matters — mismatched defaults directly affect failure detection time.

| Parameter            | Arista EOS | Fortinet FortiOS |
|----------------------|------------|------------------|
| Min TX               | 300ms      | 250ms            |
| Min RX               | 300ms      | 250ms            |
| Detection Multiplier | 3          | 3                |
| Detection Time       | 900ms      | 750ms            |

BFD negotiates the actual transmit interval to the higher of each side's Min TX and the peer's Min RX. Between EOS and a FortiGate with default settings, both sides converge on 300ms — FortiOS does not achieve the 750ms detection time it would see peering with another FortiGate. Detection time on both sides ends up at 900ms.

## FortiGate

BFD can be enabled globally, but I think a best practice is to enable features like this as needed, so per interface and then per neighbor within a routing protocol. To configure it per-interface:

```console
config system interface
    edit "port1"
        set bfd enable
        set bfd-desired-min-tx 300
        set bfd-required-min-rx 300
        set bfd-detect-mult 3
    next
end
```

Then BFD is enabled on the BGP neighbor:

```console
config router bgp
    config neighbor
        edit "10.10.0.1"
            set bfd enable
        next
    end
end
```

## Arista EOS

BFD timers are configured globally under `router bfd`:

These are the default values:
```console
router bfd
   interval 300 min-rx 300 multiplier 3
```

BFD is then enabled per-neighbor within BGP, or within a peer group.

```console
router bgp <ASN>
   neighbor 10.10.0.2 bfd
   !
   neighbor peer group FORTIGATE
   neighbor peer group FORTIGATE bfd
   neighbor 10.10.2.2 peer group FORTIGATE
```


## Verification

**FortiGate:**

```console
get router info bfd neighbor detail
```

A healthy session shows `state: Up`. Confirm the negotiated interval is 300ms if it has been adjusted as above.

You can get a summary view without `detail`.


**Arista EOS:**

```console
show bfd peers detail
```

A healthy session shows `State: Up`. The `Tx interval` field confirms the negotiated transmit interval; it should read 300ms with the aligned configuration above.
