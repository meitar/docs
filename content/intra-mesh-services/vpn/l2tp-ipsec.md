---
title: L2TP/IPsec VPN
aliases:
    - /networking/vpnl2tpipsec
---

An **L2TP/IPsec VPN** is an "enterprise VPN" setup, so called because it is most often used by corporations to provide remote access to one or more computers that are physically disconnected from the rest of their corporate network. It is based on a combination of the aforementioned L2TP and IPsec protocol standards. The former protocol (L2TP, the [Layer 2 Tunneling Protocol](https://en.wikipedia.org/wiki/Layer_2_Tunneling_Protocol)) carries a "call" over the Internet, while the latter protocol suite ([IPsec](https://en.wikipedia.org/wiki/IPsec), Internet Protocol Security) encrypts the call and authenticates the participants.

L2TP/IPsec is a common general-purpose VPN protocol that work with most platforms. For example, computers running Windows, macOS, iPhones, and Android devices all support this type of VPN out-of-the-box. This type of VPN is a little bit oldschool, in that it is typically found in enterprise corporate environments, which is part of what makes it so ubiquitous.  
For this reason, we have decided to provide and endpoint of this protocol.

Technically speaking, it is a combination of L2TP and IPsec protocol standards. The former protocol (L2TP, the [Layer 2 Tunneling Protocol](https://en.wikipedia.org/wiki/Layer_2_Tunneling_Protocol)) carries a "call" over the Internet, while the latter protocol suite ([IPsec](https://en.wikipedia.org/wiki/IPsec), Internet Protocol Security) encrypts the call and authenticates the participants. Although it's possible to use either protocol without the other, L2TP and IPsec are most often used together. This is because L2TP creates a connection but does not secure the connection, while IPsec protects traffic but does not itself create a network connection to carry traffic.

L2TP/IPsec VPNs are often slower than more modern protocols because the implementation on smaller routers is usually implemented in software which makes heavy use of the router's CPU. On the other hand, more expensive routers often have a custom chip to speed-up IPsec encryption, actually making L2TP/IPsec the fastest choice in certain cases.

The best performance you can reasonably expect from on small routers is around ~100Mbps.

## Device support
The L2TP/IPsec protocol enjoys very wide support across platforms and vendors.

* Mikrotik devices: All ( various speeds ) - No Guide Yet
* Apple devices: iPhones, Mac laptops, natively - [iOS Guide Here]({{< relref "#apple-ios" >}}), [macOS Guide Here]({{< relref "#macos" >}})
* Android devices: Most yes - [Guide Here]({{< relref "#android" >}})
* Ubnt routers: Yes, but slow - No Guide Yet
* OpenWRT: Should work - No Guide Yet
* Windows devices: Should work - [Guide Here]({{< relref "#windows-10" >}})
* Linux: Yes, complicated without GUI, works well with Network Manager - [Guide Here]({{< relref "#gnu-linux-gnome-network-manager" >}})


## Endpoints
This section provides connection information for NYC Mesh VPN endpoints that use L2TP/IPsec.

### Supernode 1
* Server domain name: `l2tpvpn.sn1.mesh.nycmesh.net`
* Supported connection methods:
    * Anonymous:
        * Username: `nycmesh`
        * Password: `nycmeshnet`
    * OSPF Node-Peering (Same, connect as above, use [OSPF]({{< relref "ospf" >}}) afterwards.)

### Supernode 3
* Server domain name: `l2tpvpn.sn3.mesh.nycmesh.net`
* Supported connection methods:
    * Anonymous:
        * Username: `nycmesh`
        * Password: `nycmeshnet`
    * OSPF Node-Peering (Same, connect as above, use [OSPF]({{< relref "ospf" >}}) afterwards.)

## Connection Guides
Please follow the below connection guides for each platform.

### Windows 10
1. Click on Start (Title menu) and type VPN
1. Click on on Change Virtual Private Networks (VPN)
1. Click on the plus button (Add a VPN connection)
1. Choose VPN provider (Microsoft by default)
1. Conenction name (Name it whatever you want)
1. Server name or address `l2tpvpn.sn1.mesh.nycmesh.net` or `l2tpvpn.sn3.mesh.nycmesh.net`
1. VPN Type: L2TP/IPsec with pre-shared key
1. Pre-shared key: `nycmeshnet`
1. Type of sign-in info: User name and password
1. Username: `nycmesh`
1. Password: `nycmeshnet`
1. Check box to remember password so you don't have to type this everytime
1. Click save
1. Click on newly created VPN connection and click connect

### macOS
See [Apple Support: Set up a VPN Connection](https://support.apple.com/guide/mac-help/set-up-a-vpn-connection-on-mac-mchlp2963/10.14/mac/10.14).

Be sure to use the appropriate authentication credentials for your connection. For an anonymous connection:

* Enter `nycmesh` as the "account name" and
* `nycmeshnet` in both the User Authentication's "password" field *and* the Machine Authentication's "Shared Secret" field.

### Apple iOS
These instructions refer to Apple-branded handheld devices such as the iPhone and iPad.

1. Go to Settings
1. Tap on VPN
1. Tap on Add VPN Configuration
1. Tap on Type and choose L2TP
1. Description (Anything you want)
1. Server: `l2tpvpn.sn1.mesh.nycmesh.net` or `l2tpvpn.sn3.mesh.nycmesh.net`
1. Account: `nycmesh`
1. Leave RSA SecurID off
1. Password `nycmeshnet`
1. Secret: `nycmeshnet`

See also [How-To Geek: How to Connect to a VPN From Your iPhone or iPad § Connect to IKEv2, L2TP/IPsec, and Cisco IPsec VPNs in iOS](https://www.howtogeek.com/215730/how-to-connect-to-a-vpn-from-your-iphone-or-ipad/).

### Android
See [How-To Geek: How to Connect to a VPN on Android § Android’s Built-In VPN Support](https://www.howtogeek.com/135036/how-to-connect-to-a-vpn-on-android/).

### GNU/Linux - GNOME/Network Manager
Most GNU/Linux distributions ship with IPsec/L2TP support, but you may need to install additional software packages to use your Desktop Environment's standard networking widgets to control the VPN connection. The following short guide assumes you are using GNOME and Network Manager.

1. Make sure you have the necessary software installed:
    * Commands for Ubuntu 20.04 (LTS):
        ```sh
        # Ensure the Ubuntu "Universe" package repository is enabled.
        sudo add-apt-repository universe

        # Install the userspace L2TP daemon, the Network Manager plugin, and its GNOME graphical integration.
        sudo apt install xl2tpd network-manager-l2tp network-manager-l2tp-gnome
        ```
    * Commands for Fedora Workshop:
        ```sh
        sudo dnf install NetworkManager-l2tp-gnome # This should pick up all required dependencies.
        ```
1. You may need to restart `NetworkManager` at this point:
    ```sh
    sudo service NetworkManager restart
    ```
    Or you can try logging out and back into your Desktop Environment.
1. Open the GNOME Settings app and choose the "*Network*" panel.
1. Add a new VPN connection of type "*Layer 2 Tunneling Protocol (L2TP)*". If this option doesn't appear for you, ensure you have installed the necessary software for your distribution, discussed above.
1. In the "Add VPN" dialogue box, enter the following details:
    * Gateway: `l2tpvpn.sn1.mesh.nycmesh.net` or `l2tpvpn.sn3.mesh.nycmesh.net`
    * User name: `nycmesh`
    * Password: `nycmeshnet`  
        (Note: You may have to click a question mark on the right of the textbox to activate the text field.)
1. Still in the "Add VPN" dialogue box, click the "*IPsec Settings*" button.
1. In the "L2TP IPsec Options" dialogue box, enter the following details:
    * Check "Enable IPsec tunnel to L2TP host"
    * Under the *Machine Authentication* heading, enter the pre-shared key: `nycmeshnet`
1. Save the new VPN configuration by clicking the "Add" button.

The above instructions should have created a new Network Manager-managed connection in `/etc/NetworkManager/system-connections`, or viewable with the Network Manager command line interface tool: `nmcli connection show`.

Connecting to the VPN by clicking any of the connect buttons in your Desktop Environment's GUI should now work. Be sure to test the VPN connection to make sure you're actually sending traffic through VPN, perhaps by using any "what is my IP address" website. If it doesn't work, see the troubleshooting tips below for some additional guidance.

#### Troubleshooting tips
* Look for logs in the systemd journal: `journalctl -u NetworkManager`
* On Ubuntu, you may run into AppArmor errors with a helper program called `charon`. You may want to disable the AppArmor profile for this program for subsequent reboots: `sudo ln -s /etc/apparmor.d/usr.lib.ipsec.charon /etc/apparmor.d/disable/usr.lib.ipsec.charon`
