---
title: "SNMP to a managed FortiSwitch"
date: 2024-04-17 17:00
categories: [neteng] # always lowercase, comma space seperated
tags: [neteng,homelab,fortiswitch,snmp,monitoring] # always lowercase, comma seperated
---

Hopefully you found this because you're struggling to SNMP poll a FortiSwitch managed by a FortiGate.

I've found there's a lot of conflicting information, sharing my own experience to help others.

This does work using the default IPv4 link-local/APIPA (169.254/16) despite what you read. The FortiGate and/or Switch are not required to run RFC1918 for this function. 
With that said, if you are using the default, your NMS must be able to reach said 169.254/16 prefix. In a production network, I doubt you'd be using it, but I wanted to clear that bit up.

This example covers SNMP v2c.


Initially, the FortiGate will look something like this:

```console
config system snmp community
    edit 1
        set name "example-community-string"
        config hosts
            edit 1
                set source-ip <source ip>>
                set ip <NMS ip>
            next
        end
        set query-v1-status disable
        set trap-v1-status disable
    next
end
```

as well as the below (be it a VLAN or Loopback etc.) 

```console
config system interface
    edit "example-interface"
        set vdom "example-vdom"
        set ip <ip>
        set allowaccess ping snmp
        set type loopback
        set role lan
        set snmp-index 58
    next
end
```

Next, create a Firewall policy allowing the NMS to the FortiLink - this must be done on the CLI as the GUI will not let you create a firewall policy to/from the FortiLink:

```console
config firewall policy
    edit 0
        set srcintf "NMS_interface"
        set dstintf "FortiLink"
        set action accept
        set srcaddr "NMS_addr"
        set dstaddr "all"
        set schedule "always"
        set service "PING" "SNMP"
    next
end
```

Now we open the allowaccess to the FortiSwitch interface via the FortiLink:

*it is worth noting that the 'mgmt-allowaccess' also available within this configuration, relates to the physical management interface*

```console
config switch-controller security-policy local-access
    edit "default"
        set internal-allowaccess ping snmp
    next
end
```


Enable SNMP sysinfo:

```console
config switch-controller snmp-sysinfo
    set status enable
end
```

Now set the same community and the IP address of the NMS, as with the FortiGate:

```console
config switch-controller snmp-community
    edit 1
        set name "example-community-string"
        config hosts
            edit 1
                set ip <NMS ip>
            next
        end
        set query-v1-status disable
        set trap-v1-status disable
        set events cpu-high mem-low log-full intf-ip ent-conf-change
    next
end
```

Assuming you have reachability, the FortiSwitch should now reply to the SNMP poll or walk. 

Add the FortiSwitch from your NMS, and you're done!



