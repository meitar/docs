---
title: Public Services
weight: 350
---

In addition to more local, [intra-mesh services]({{< relref "intra-mesh-services" >}}), the NYC Mesh community operates several public services for the benefit of our members and the public at large. These services are all hosted in NYC Mesh's IPv4 network space (called a *NetRange* by many [WHOIS database registries](https://en.wikipedia.org/wiki/WHOIS) or more generally as a *network block*). These services should not be confused with publicly-accessible applications designed by NYC Mesh volunteers to assist in various operations, such as the NYC Mesh LOS Web App; see our [Software Reference]({{< relref "software" >}}) for details on these topics.

NYC Mesh's IP address range is all the IP addresses from `199.167.59.0` through `199.167.59.255`, a range often written as `199.167.59.0/24` in [Classless Inter-Domain Routing (CIDR) notation](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

In this documentation, when we say that these services are available to the public, we mean that anyone connected to the Internet can connect to and use them, regardless of whether they are connected to the NYC Mesh network itself. Usually, this is because these services are run on computers that have public IP addresses (such as the [Internet gateways that connect NYC Mesh to the Internet]({{< relref "overview/internet-connectivity" >}})) as opposed to the internal, [private IP addresses](https://en.wikipedia.org/wiki/IP_address#Private_addresses) used by intra-mesh services, although this is not always the case. In some situations, a service may be publicly accessible even if its hosting computer only has a private IP address, but this requires special arrangements to be made in order for the public Internet traffic to make it all the way through to the private network.

Since public services are, by definition, visible to the public Internet, they often show up in various Internet-wide scans published on sites such as [Censys](https://censys.io/ipv4?q=199.167.59.*) or [Shodan](https://www.shodan.io/search?query=%22199.167.59.*%22). This section documents the public services NYC Mesh operates.

If you host a service that you would like to make available to the larger Internet or even just the local NYCMesh Community, please let us know so we can add it here.

You can also discuss services on [our Slack](https://slack.nycmesh.net/) in the `#mesh-services` channel.
