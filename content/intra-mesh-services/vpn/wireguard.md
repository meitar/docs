---
title: WireGuard VPN
aliases:
    - /networking/vpnwireguard
---

[WireGuard](https://wireguard.com/) is a newer, simpler, and faster [Free Software](https://www.gnu.org/philosophy/free-sw.html) VPN implementation and protocol. For comparison, the older [L2TP/IPsec VPNs]({{< relref "l2tp-ipsec" >}}) will max out at about 100Mbps, but WireGuard VPNs can reach speeds upward of 300-400Mbps on decent hardware and even 1Gbps on a good workstation. Performance is better on computers running a Linux kernel because the WireGuard project was designed to live within the Linux kernel from the start. Userspace ports for macOS, Windows, iOS, Android, and other platforms are now available but are not as performant as the Linux kernelspace implementation.

In addition to its speed, WireGuard has some great features such as [built-in roaming](https://www.wireguard.com/#built-in-roaming) (a single encrypted packet moves the tunnel to your new IP), [cryptokey routing](https://www.wireguard.com/#cryptokey-routing), and formal cryptographic verification.

On the other hand, it also has some challenges, such as pre-key exchange and a lack of automatic address assignment. Both of these problems require manual configuration on both ends of the tunnel. Cryptokey routing also presents its own challenges in some situations (see [§ A Note on Cryptokey Routing]({{< relref "#a-note-on-cryptokey-routing" >}})).

A WireGuard VPN is best suited for connecting single end-user devices such as laptops and phones to the mesh over the internet from a location that has no mesh access.

## Routing over WireGuard
WireGuard, like other VPNs, can be used in conjuction with a routing protocol, such as [OSPF]( relref "ospf.md") which we use in NYC Mesh. However, there are some challenges with WireGuard and routing.

These challenge are highlighted on another page, as it is a longer and more technical discussion.

Please see [VPN - WireGuard + OSPF]({{ relref "vpnwireguardospf.md"}})

## Device support
WireGuard implementations are being developed on a variety of platforms. The following list provides an overview, but see the [WireGuard Installation](https://www.wireguard.com/install/) instructions for further details.

* Linux: Yes!
* Android devices: Yes, some - See WireGuard website
* OpenWRT: Yes, in LEDE on latest versions, in certain builds
* Apple devices: Yes, some - See Wireguard website
* Mikrotik devices: No
* Ubnt routers: No (well, technically yes, but the module has caused lots of problems, so please don't use it yet)
* Windows devices: Yes, some - See WireGuard website

## Endpoints

### Supernode 1:
* IPv4/6: `wgvpn.sn1.mesh.nycmesh.net:51820`
* Supported connect methods:
    * End Device
    * ~~OSPF - _Not Yet_~~
    * ~~BGP Node-Peering - _Now legacy, please do not use_~~

### Supernode 3:
* IPv4/6: `wgvpn.sn3.mesh.nycmesh.net:51820`
* Supported connect methods:
    * End Device
    * OSPF Node-Peering

## How To Connect

### Connecting end-devices
1. Ensure WireGuard will work on your device
1. Generate a public key, and give it to Zach.
1. Zach will give you the server public key and assign you an IP address. _This will change later, but just for now to get the docs out, this is what we currently do._
